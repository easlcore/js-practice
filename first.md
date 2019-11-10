Напиши функцию создания генератора sequence(start, step).
Она при вызове возвращает другую функцию-генератор, которая при каждом вызове дает число на 1 больше, и так до бесконечности.
Начальное число, с которого начинать отсчет, и шаг, задается при создании генератора.
Шаг можно не указывать, тогда он будет равен одному. Начальное значение по умолчанию равно 0.
Генераторов можно создать сколько угодно.

```javascript
var generator = sequence(10, 3);
var generator2 = sequence(7, 1);

console.log(generator()); // 10
console.log(generator()); // 13

console.log(generator2()); // 7

console.log(generator()); // 16

console.log(generator2()); // 8
```

# Solution:

```javascript
const sequence = (start, step = 1) => {
	let current = start;
	let isFirstCall = true;

	return function() {
		if (isFirstCall) {
			isFirstCall = false;
      
			return start;
		}
		current += step;
    
		return current;
	}
}
```
