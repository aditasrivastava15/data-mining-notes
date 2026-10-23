# Did the classifier work?

Holdout freezes a chunk of labeled rows, trains on the rest, and scores once on the frozen chunk. Cross-validation rotates which chunk is frozen and averages the scores. A learning curve plots score against how many training rows you used. If it is still rising, more data would help. High train score and low test score means overfitting.

Accuracy is correct guesses over all guesses. If 99 of 100 emails are real, "always real" is 99% accurate and useless.

For the spam class:

- True positive: said spam, and it was.
- False positive: said spam, and it was real.
- True negative: said real, and it was.
- False negative: said real, and it was spam.

Precision is true positives over everything you called positive. Recall is true positives over everything that truly was positive. F1 balances the two.

A score plus a threshold makes the class. Lower the threshold and you catch more positives and more false alarms. The ROC curve plots true positive rate against false positive rate as the threshold moves. A useless model is the diagonal. A better model bows toward the top left.

**Check.** A test flags 10 people. 8 are sick. The town has 20 sick people. What are precision and recall for "sick"? Which matters more if missing a sick person is worse than an extra checkup?
