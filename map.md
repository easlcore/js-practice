Напиши функцию map(fn, array), которая принимает на вход функцию и массив,
и обрабатывает каждый элемент массива этой функцией, возвращая новый массив.

```javascript
function square(x) { return x * x; } // возведение в квадрат
console.log(map(square, [1, 2, 3, 4])); // [1, 4, 9, 16]
console.log(map(square, [])); // []
```

# Solution:

```javascript
const map = (fn, array) => array.map(value => fn(value));
```
