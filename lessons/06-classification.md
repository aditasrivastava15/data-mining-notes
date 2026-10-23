# Classification

Supervised: each training row has a class. Training learns the rule. Testing scores it on rows it did not use. Scoring only on training rows rewards memorizing noise. That is overfitting.

## Decision trees

Each question is a split on one attribute. A leaf says the class. Pick the split that makes the child piles purer.

Gini impurity and entropy both score mix. Both are 0 when a pile is one class, and highest when classes are even. Information gain is the drop in entropy. Trees that grow until every leaf is pure memorize. Pruning cuts branches that do not help on held-out rows. Trees are easy to read. They stumble when the true boundary is a diagonal across many columns, because each question is usually one column.

## Rules

A rule is if this and this, then class. Mutually exclusive means only one rule fires. Exhaustive means every row hits some rule. A tree path is both, until you drop a condition. Then rules can overlap, so you order them and keep a default. Associative classification builds rules from patterns that often appear with a class.

## K-nearest neighbors

Store the training rows. A new row takes the k closest and votes. k = 1 is jumpy. Larger k smooths and can blur a small real group. Scale columns first, or a huge-numbered column owns the distance. Prediction slows as the table grows.

## Naive Bayes

P(class | evidence) is proportional to P(evidence | class) times P(class). The naive step pretends columns are independent once you know the class, so you multiply one-column probabilities. That is often false and still useful, because you only need the winning class. If a value never appeared with a class, the product is 0. Smoothing adds a fake count so nothing is impossible.

## Support vector machines

Among straight cuts that separate two classes, the SVM picks the widest empty margin. Points touching the margin are the support vectors. A kernel maps points into a space where a straight cut exists. A soft margin lets a few points sit on the wrong side so one odd point cannot tilt the fence.

## Neural nets, as far as the lectures go

A neuron multiplies inputs by weights, adds a bias, and squashes the sum. A step is a hard yes or no. Sigmoid and tanh are smooth S-curves, so a small weight change makes a small output change. Softmax turns scores into probabilities that add to 1.

A feed-forward net stacks layers with no loops. Backpropagation shares the output error backward so each weight learns whether turning up would have helped.

A convolutional net slides small filters over an image. Pooling keeps the strongest response in each window, so a small shift still matches.

A recurrent net reads a sequence and keeps a state. The same weights run at every step. A clue in the first word can fail to affect the loss at the last word. That is a vanishing gradient.

An autoencoder squeezes the input through a narrow middle and rebuilds it. The middle is a learned compression.

Word2vec places words so similar contexts land nearby. Vector directions can carry relationships such as king toward queen. It is context statistics, not understanding.
