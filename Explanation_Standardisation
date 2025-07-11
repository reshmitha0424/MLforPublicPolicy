## 📊 Linear Modeling with Standardization – Summary

### ✅ Project Flow

1. **Started with raw data**
   - `x_orig` = `year`
   - `y_orig` = `leb_us` (life expectancy at birth)
   - Plotted `x_orig` vs `y_orig` using a scatterplot

2. **Fitted a model on original values**
   - Used `SGDRegressor`
   - Model gave **poor predictions** (`y_pred`)
   - Red line looked incorrect due to large scale difference between `year` and `leb_us`

3. **Standardized both X and Y**
   - Applied:

     ```python
     x_st = (x_orig - x_orig.mean()) / x_orig.std()
     y_st = (y_orig - y_orig.mean()) / y_orig.std()
     ```

   - Now both features had **mean = 0** and **std = 1**

4. **Trained a new model on standardized data**
   - Model was fit on `x_st`, `y_st`
   - Predicted `y_pred_st` (predicted Y values in standardized scale)

5. **Unstandardized the predicted Y values**
   - Converted standardized predictions back to original scale:

     ```python
     y_pred = y_pred_st * y_orig.std() + y_orig.mean()
     ```

   - ✅ **Important Insight**:
     > We unstandardize `y_pred_st` using `y_orig` values because `y_st` was created using `y_orig`.  
     > `y_pred_st` lives in the same space as `y_st`, so we must use the **same** mean and std.

6. **Final Plot**
   - **X-axis**: `x_orig` (years)
   - **Y-axis (blue dots)**: `y_orig` (actual life expectancy)
   - **Y-axis (red line)**: `y_pred` (predicted life expectancy in original scale)

---

### 🎯 Outcome

By standardizing the input and output before training, the model was able to learn the relationship accurately. After unstandardizing the predictions, we achieved a well-fitted linear model in real-world terms — ideal for communicating with policymakers.
