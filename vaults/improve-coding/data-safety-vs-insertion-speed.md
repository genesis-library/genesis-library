Write Concern is a special statement in MongoDB.
Journal Commit too
```
// unsafe writing but fast
db.events.insert(event, w=0, j=False)
```

Bulk insert shortens time when safe writing.