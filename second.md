Напиши функцию take(gen, x) которая вызвает функцию gen заданное число (x) раз и возвращает массив с результатами вызовов

```javascript
var gen2 = sequence(0, 2);
console.log(take(gen2, 5)); // [0, 2, 4, 6, 8 ]
```

# Solution:

```javascript
const take = (fn, x) => {
	let result = [];

	for (let i = 0; i < x; i++) {
		result.push(fn());
	}

	return result;
}
```
