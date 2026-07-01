# Module 4 Reflection — California Housing Regression

## Reflection Questions

### 1. What did you change, and how did the results change?
I changed the K-fold from 4 to 3. The 3-fold run reached its lowest 
validation MAE faster, around epoch 50, compared to the 4-fold run which 
flattened around epoch 100. The 3-fold result sat slightly higher overall 
around 0.30-0.31 versus the 4-fold at 0.28-0.29.

### 2. Where does your model stop improving and how can you tell?
Looking at the truncated curves, the validation MAE stops meaningfully 
dropping around epoch 50 for 3-fold and epoch 100 for 4-fold. After that 
the line just bounces flat — more training is not helping.

### 3. What would you do differently if you ran this again?
I would stop training earlier, somewhere around epoch 50-100 based on where 
the curve flattens, instead of running all 200 epochs. Past that point the 
model is overfitting and extra epochs are not improving results.

---

## Training Curves

### K=3 Folds
![3-fold validation MAE](housing_val_mae_3fold.png)
![3-fold truncated](housing_val_mae_truncated_3fold.png)

### K=4 Folds
![4-fold validation MAE](housing_val_mae.png)
![4-fold truncated](housing_val_mae_truncated.png)
