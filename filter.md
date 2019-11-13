напиши функцию filter, которая принимает функцию-предикат и массив.
Возвращает она массив значений, для которых предикат вернет true.

```javascript
var input = [1, 2, 3, 4, 5, 6];
function isEven(x) { return x % 2 == 0; } // проверяет на четность
console.log(filter(input, isEven)); // [2, 4, 6]
```
Функция не должна изменять исходный массив:
```javascript
console.log(input); // [1, 2, 3, 4, 5, 6]
```

# Solution:

```javascript
filter = (arr, fn) => {
	let res = [];

	for (let i = 0; i < arr.length; i++) {
		const current = arr[i];
		if (fn(current)) {
			res.push(current)
		};
	}

	return res;
}
```
