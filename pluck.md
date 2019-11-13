напиши функцию pluck, которая берет массив объектов и возвращает массив значений определенного поля

```javascript
var characters = [
  { 'name': 'barney', 'age': 36 },
  { 'name': 'fred', 'age': 40 }
];

console.log(pluck(characters, 'name')); // ['barney', 'fred']
```

# Solution:

```javascript
const pluck = (arr, prop) => arr.map(val => val[prop]);
```
