Напиши функцию fmap(a, gen), которая принимает на вход 2 функции, a и gen, где gen — функция-генератор вроде той,
что была в sequence.md. fmap возвращает новую функцию-генератор,
которая при каждом вызове берет следующее значение из gen и пропускает его через функцию a.

```javascript
var gen = sequence(1, 1);
function square(x) { return x * x; }
var squareGen = fmap(square, gen);

console.log(squareGen()); // 1
console.log(squareGen()); // 4
console.log(squareGen()); // 9
console.log(squareGen()); // 16
```

#Solution:

```javascript
const fmap = (fn, gen) => {
	return function() {
		return fn(gen());
	}
}

const fmap = (fn, gen) => () => fn(gen());
```

Сделать так, чтобы в качестве gen можно было указать функцию с аргументами, и при вызове
```javascript
function add(a, b) { 
    return a + b; 
}

// Мы получаем новую функцию, которая вызвает add, и результат пропускает через функцию square
var squareAdd = fmap(square, add);
console.log(squareAdd(2, 3)); // 25 = (2 + 3) ^ 2
console.log(squareAdd(5, 7)); // 144 = (5 + 7) ^ 2
```
Эти аргументы бы передавались функции gen. Аргументов может быть любое количество.

# Solution:

```javascript
const fmap = (fn, gen) => {
	return function() {
		return fn(gen(...arguments))
	}
}
```

