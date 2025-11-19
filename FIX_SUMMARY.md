# Maturity Calculation Consistency Fix

## Problem Description

When setting dimension maturity levels to 3, 3, 3, 4, 5, the system showed inconsistent results across different visualizations:

- **Heatmap**: Correctly showed 3, 3, 3, 4, 5 (100% for levels 1-3, then 0%)
- **Key Insights**: Incorrectly showed weakest dimension at 2.00 instead of 3.00
- **Overall Maturity Gauge**: Showed 2.87 instead of expected 3.60
- **Radar Chart**: Incorrectly showed 2, 2, 2, 3.33, 5
- **Bar Chart**: Incorrectly showed 2, 2, 2, 3.33, 5
- **Scores Table**: Incorrectly showed 2, 2, 2, 3.33, 5

## Root Cause

The `calculateDimensionMaturity()` function used a weighted average algorithm that incorrectly calculated maturity levels:

```javascript
// OLD (INCORRECT) ALGORITHM:
const weightedAvg = weightedSum / totalWeight;
const maturity = (weightedAvg / 100) * 5;
```

This weighted average gave higher weights to higher levels, which sounds reasonable but produced incorrect results. For example, when all of levels 1-3 are complete (100%):
- weightedSum = (100×1) + (100×2) + (100×3) + (0×4) + (0×5) = 600
- totalWeight = 1 + 2 + 3 + 4 + 5 = 15
- weightedAvg = 600/15 = 40
- maturity = (40/100) × 5 = **2.0** ❌ (should be 3.0)

## Solution

Implemented a sequential CMMI-compliant maturity calculation algorithm:

```javascript
// NEW (CORRECT) ALGORITHM:
let maturity = 0;
let foundIncomplete = false;

for (let level = 1; level <= 5; level++) {
  const completion = (full * 1.0 + partial * 0.5) / total;
  
  if (!foundIncomplete) {
    if (completion >= 1.0) {
      maturity = level;  // This level is complete
    } else {
      maturity = (level - 1) + completion;  // Partial completion
      foundIncomplete = true;  // Stop counting higher levels
    }
  }
}
```

### Key Principles:

1. **Sequential Compliance**: CMMI maturity levels must be achieved in order (1→2→3→4→5)
2. **Strict Prerequisites**: Higher level completion is ignored if lower levels are incomplete
3. **Simple Formula**: Maturity = (highest complete level) + (progress on next level)

## Changes Made

### 1. Fixed `calculateDimensionMaturity()` function
- Replaced weighted average with sequential calculation
- Enforces strict CMMI level ordering
- Correctly handles edge cases (partial completion, zero completion, etc.)

### 2. Fixed `createStackedChart()` function
- Removed weighted calculation: `(score * weight) / 15`
- Now directly uses `score` for display
- Consistent with heatmap visualization

### 3. All visualizations now use the same source
- Radar chart: Uses `result.maturity`
- Bar chart: Uses `result.maturity`
- Scores table: Uses `result.maturity`
- Key insights: Uses `result.maturity`
- Gauge chart: Uses `overallMaturity` (average of all `result.maturity`)

## Test Results

### Main Test Case (3, 3, 3, 4, 5)
```
安全管理: 3.00 ✓
安全技术: 3.00 ✓
安全运营: 3.00 ✓
开发安全: 4.00 ✓
数据安全: 5.00 ✓
Overall: 3.60 ✓ (average: (3+3+3+4+5)/5)
```

### Edge Cases
```
Level 1 at 50%: 0.50 ✓
All levels at 0%: 0.00 ✓
Levels 1-2 complete, 3 at 75%: 2.75 ✓
Level 1 complete, 2 with partials (75%): 1.75 ✓
Gap in completion (1 complete, 2 at 50%, 3 complete): 1.50 ✓
  (Level 3 is correctly ignored because level 2 is incomplete)
```

## Impact

✅ **Fixed**: All charts and visualizations now show consistent maturity calculations
✅ **Fixed**: Key insights correctly identify strongest and weakest dimensions
✅ **Fixed**: Overall maturity gauge shows correct average
✅ **Improved**: Algorithm now properly enforces sequential CMMI compliance
✅ **Improved**: Edge cases are handled correctly

## Files Modified

- `/home/engine/project/cmmi.html`
  - `calculateDimensionMaturity()` function (lines 1023-1053)
  - `createStackedChart()` function (lines 1358-1376)
