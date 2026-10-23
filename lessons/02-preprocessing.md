# Dirty data, then a smaller cleaner table

Noise is a true value that was shaken. An outlier does not belong with the crowd; it may be a typo or a real rare case. A missing value is an empty cell. A duplicate is the same object twice after a bad merge.

Aggregation combines rows or columns, such as daily rain into monthly rain. You lose detail and gain a stabler picture.

Sampling keeps a smaller set. Simple random means every row has the same chance. The sample must look like the whole.

For missing values, common choices are drop the row, fill with a typical value, or mark "missing" as its own fact. Filling hides uncertainty. Say which you did.

## The curse of dimensionality

Each new column is a new direction. Points that felt close in a few columns become far apart in all of them. Neighbors stop being special. Methods that rely on "who is nearby" get lost.

## Fewer columns

Feature subset selection keeps some original columns. Feature creation builds a new column, such as area from length times width. Mapping to a new space rewrites the numbers. Two wiggly waves look messy in time and clear as spikes in frequency.

## Bins and scale

Discretization chops a ruler into bins. Equal width makes bins the same size. Equal frequency gives each bin the same count. K-means bins sit where points clump. Supervised cuts look at the class and split where the class changes.

Binarization turns one category into yes/no columns. Color red, blue, green becomes three columns, exactly one of them 1. That stops a model from thinking green is "more than" blue because you numbered them.

Min-max stretches a column into 0 to 1. Z-score subtracts the mean and divides by the standard deviation. Compute those stats on training rows only, then apply the same shift to new rows.
