lets say we have click data of a page for daily, hourly, minutely

Hierarchical allows MongoDB to 

Flat document:
```
{
'daily': 5000,
'hourly': {
	"0": 100,
	"1": 200,
	...
	"23": 200
	},
'minute': {
	'0': 5,
	'1': 5,
	...
	'1439': 5 // 1439 is 23hrs 59mins
	}
}
```

Hierarchical document:
```
{
'daily': 5000,
'hourly': {
	"0": 100,
	"1": 200,
	...
	"23": 200
	},
'minute': {
	'0': {
		'0': 1,
		...
		'59': 1
		},
	...
	'23': {
		'0': 1,
		...
		'59': 1
		}
	
	}
}
```

 