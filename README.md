# MongoDB $inc operator error with string value
This repository demonstrates a common error when using the `$inc` operator in MongoDB update operations. The `$inc` operator is used to increment a numeric field by a specified value, but if you provide a string value instead of a number, it will lead to an error.

## Bug
The bug lies in the incorrect usage of the `$inc` operator.  The following code snippet attempts to increment the `counter` field by the string value '1', which is incorrect:
```javascript
db.collection('myCollection').updateOne({fieldName: 'value'}, {$inc: {counter: '1'}});
```

## Solution
To fix this bug, provide a numeric value to the `$inc` operator: 
```javascript
db.collection('myCollection').updateOne({fieldName: 'value'}, {$inc: {counter: 1}});
```