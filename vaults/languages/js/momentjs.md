We must use new timezone library

```javascript
moment.tz('2018-07-17 19:00:00', 'YYYY-MM-DD HH:mm:ss', 'UTC').format() // "2018-07-17T19:00:00Z"

moment('2018-07-17 19:00:00', 'YYYY-MM-DD HH:mm:ss').tz('UTC').format() // "2018-07-18T00:00:00Z"

moment.utc(sagSwellData.date)
```


The first code takes in the date and assumes the timezone is the one passed in. 

The second one will take date, assume the timezone from the browser and then change the time and timezone according to the timezone passed in.