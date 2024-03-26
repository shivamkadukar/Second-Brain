- Logical AND operator: && 
- Logical OR operator: || 
- Logical NOT operator: ! 
- The modulus operator: % 
- The equality operator: ==
- The strict equality operator: ===
- The inequality operator: !=
- The strict inequality operator: !==
- The addition assignment operator: += 
- The concatenation assignment operator: +=

__Conditionals__
- If...else if...else
	```javascript
	if (condition) {
	/* code to run if condition is true */
	} else if {
	/* code to run if condition is true */
	} else {
	/* run some other code instead */
	}
	```
- Switch statements
```javascript
switch (expression) {
  case choice1:
    // run this code
    break;

  case choice2:
    // run this code instead
    break;

  // include as many cases as you like

  default:
    // actually, just run this code
    break;
}
```
- Ternary Operator
```javascript
condition ? run this code : run this code instead
```
__Loops__
- For Loop
```javascript
for (initialization; condition; afterthought)
  statement
```
- do...while loop
```javascript
do
  statement
while (condition);
```
- while loop
```javascript
while (condition)
  statement
```
__Try...Catch__
```javascript
try {
  tryStatements
  throw new errortype("error message")
} catch (exceptionVar) {
  catchStatements
} finally {
  finallyStatements
}
```

__Javascript Object Notation__
```javascript
var strObj = '{"greeting": "hello"}'

// Parse string to JSON
var jsonObj = JSON.parse(strObj);

jsonObj.greeting = "hi";

// Convert Json object to string
JSON.stringify(jsonObj);
```
