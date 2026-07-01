# Module 4 — Assess: Explain What You Built

## Part 1 — Your Run

**Q1.** Which option did you build (movie reviews or house prices), and what one change did you make, if any?

**A1.** I used Option B. I used K_Fold with 4 folds and then 3 folds

**Q2.** Attach your training curve. Looking at your curve, at which epoch does the validation line stop improving (the turnaround)? How can you tell from the picture?

**A2.** fold 4 stopped going down at about 100 epochs and the 3 fold stoped at around 50 epochs

**Q3.** What is the model actually doing wrong after that turnaround point? What's the name for it, and what's gone wrong?

**A3.** it is overfitting after the turnaround point. the thing going wrong is that it starts trying to over correct the model so much so that it is going wrong.

---

## Part 2 — Working With Your Agent

**Q4.** Describe one moment you corrected or pushed back on your agent. What did it suggest, what did you do instead, and why?

**A4.** i changed the k-fold from 4 to 3 because i wanted to see if i could get to the lowest results faster then the 4-fold

**Q5.** Name one thing your agent did well that saved you time.

**A5.** it made the proccess easier by generating everything faster so i could focus one the models curves itself.

---

## Part 3 — Why Your Settings Are Right (Option B)

**Q6.** Why does the last layer have no activation (a linear output)? Why do you measure MAE instead of accuracy, and why normalize using the training stats only?

**A6.** the last layer has no aactivation because house prices are hard to predict due to the market changing

**Q7.** You'll often hear "more epochs = better." Using your own training curve as evidence, explain why that's not true for your model.

**A7.** this is not true because i noticed that the more epochs the worse it gets because once you hit that bottom line. it only moves up and up the more epochs you have.

---

## Part 4 — Honest Self-Check

**Q8.** How much of what you built do you genuinely understand versus trust your agent on? Name one specific part you'd struggle to rebuild without help.

**A8.**  alot of the code is over my head for some reason. if i had had to build the code by myself i dont know where i would even start

**Q9.** Explain your model to a classmate in three sentences: what it takes in, what it predicts, and how it learns.

**A9.** it takes in 8 numbers about a California neighborhood like income and population. It predicts the median home price for that area. It learns by making price guesses, measuring how far off it was, and adjusting its internal numbers to do better next time.

---

## Training Curves

### K=3 Folds
![3-fold validation MAE](housing_val_mae_3fold.png)
![3-fold truncated](housing_val_mae_truncated_3fold.png)

### K=4 Folds
![4-fold validation MAE](housing_val_mae.png)
![4-fold truncated](housing_val_mae_truncated.png)
