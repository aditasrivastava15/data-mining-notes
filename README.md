# Data mining notes

One course, nine lecture decks. You start with messy facts. You clean them, measure how alike two things are, then either find groups nobody labeled, predict a category, or predict a number.

Every method here is the same habit: pick a simple rule, measure how wrong it is, and keep the rule that is least wrong on examples it did not train on.

## Lessons

1. [Words you need first](lessons/00-background.md)
2. [What kind of fact is this?](lessons/01-data-types.md)
3. [Dirty data, then a smaller cleaner table](lessons/02-preprocessing.md)
4. [Turning writing into numbers](lessons/03-documents.md)
5. [How alike are two things?](lessons/04-similarity.md)
6. [Clustering](lessons/05-clustering.md)
7. [Classification](lessons/06-classification.md)
8. [Did the classifier work?](lessons/07-evaluation.md)
9. [Fewer columns](lessons/08-dimensionality.md)
10. [Regression](lessons/09-regression.md)
11. [Logistic regression](lessons/10-logistic.md)

## The map

| Question | Name | Labels already? |
|---|---|---|
| Which things belong together? | Clustering | No |
| Which category is this? | Classification | Yes, categories |
| What number comes next? | Regression | Yes, a number |
| Can I describe this with fewer columns? | Dimensionality reduction | Optional |

## Before you run anything

1. Name the attribute type before you subtract or average.
2. Say whether the job is a group, a category, or a number.
3. Write the cost the algorithm shrinks.
4. Say what would make it fail.
5. Score it on rows that did not teach it.
