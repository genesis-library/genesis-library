- Individual document growing significantly
Forces MongoDB to move the document on disk. 
Allocates as it grows. This padding gives more space than it really needs.

- Collection scans

- Documents with a large number of keys
This is about structure of MongoDB's storing of BSON.