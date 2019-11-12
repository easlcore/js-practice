Усовершенствовать функцию partial, чтобы зафиксировать можно было любые аргументы,
пропущенные аргументы обозначаются с помощью undefined.

```javascript
function test(a, b, c) { return 'a=' + a + ',b=' + b + ',c=' + c; }
var test1_3 = partialAny(test, 1, undefined, 3);
console.log(test1_3(5)); // a=1,b=5,c=3
```

# Solution: 

```javascript
const partial = (fn, ...args) => {
	return function() {
		let count = 0;
		const params = args.map(val => val === undefined ? arguments[count++] : val);
		return fn(...params);
	}
}
```
