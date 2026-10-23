# Turning writing into numbers

Models cannot read. They see columns of numbers.

Split text into tokens. Make case agree so "Cat" and "cat" match. Stemming cuts words toward a root so "running" and "runs" can share a column. Stopword removal drops words that appear everywhere: the, a, of. There is no single official stop list. In a legal archive, "court" might be a stopword. In a sports archive it is the point.

Bag of words forgets order. "Dog bites man" and "man bites dog" become the same multiset. That is a real loss, and it is why the method is fast.

Binary weight is 1 if the word appears. Term frequency counts how often. Tf-idf multiplies that count by a rarity bonus. A word in every document gets a small bonus. A word in few documents gets a large one. The result is a document-term matrix: rows are documents, columns are words, cells are weights.
