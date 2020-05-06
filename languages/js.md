# JS

Remove item from array at id

```js
let test = [
 { firstName: 'John', lastName: 'Smith' },
 { firstName: 'Jane', lastName: 'Smith' },
 { firstName: 'Billy', lastName: 'Bob' }
];
test.splice(1, 1);
```

Remove item(s) from array

```js
test.filter((value) => value.lastName !== 'Bob');
```
