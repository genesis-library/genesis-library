Distributed joins and distributed transactions are hard.
Mongo implements automatic sharding


we’re able to sort the comments we’re interested in, or restrict the number of comments returned from a query using `limit()` and `skip()` operators, whereas in the embedded case, we’re stuck retrieving all the comments in the same order they are stored in the post.


-   The larger a document is, the more RAM it uses.
-   Growing documents must eventually be copied to larger spaces.
-   MongoDB documents have a hard size limit of 16 MB.

Page faults caused by big documents:
MongoDB database caches frequently accessed documents in RAM, and the larger those documents are, the fewer that will fit. The fewer documents in RAM, the more likely the server is to page fault to retrieve documents, and ultimately page faults lead to random disk I/O.

Case: 
In the case of our blogging platform, we may only wish to display the first three comments by default when showing a blog entry. Storing all 500 comments along with the entry, then, is simply wasting that RAM in most cases.