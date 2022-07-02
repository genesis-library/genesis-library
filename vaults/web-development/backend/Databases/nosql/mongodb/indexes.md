indexing slows insertion
accelerates queries.

Indexes stored as B-tree, sorted order.
hint() to show MongoDB preffering of index.

index when total number of distinct paths are small.
HOW INDEXING WORKS? HOW DOES IT REDUCE SCANNED DOCUMENT COUNT? RAM?

USE CASE:
- Product catalog: Product catalog query count is far more than product catalog insert time. Insert time is important.

[[compound-vs-single-index]]
[[index-orders]]
[[index-sortings]]
[[explain()]]
[[index-size]]