# Array Methods

## 1.map
The map method creates a new array populated with the results of calling a provided function on every element in the calling array.

```ts
const numbers = [1, 2, 3, 4];
const doubled = numbers.map(num => num * 2);
console.log(doubled); // Output: [2, 4, 6, 8]
```

## 2. filter
The filter method creates a new array with all elements that pass the test implemented by the provided function.

```ts
const numbers = [1, 2, 3, 4];
const evenNumbers = numbers.filter(num => num % 2 === 0);
console.log(evenNumbers); // Output: [2, 4]
```

## 3. reduce
The reduce method executes a reducer function (that you provide) on each element of the array, resulting in a single output value.

```ts
const numbers = [1, 2, 3, 4];
const sum = numbers.reduce((accumulator, currentValue) => accumulator + currentValue, 0);
console.log(sum); // Output: 10
```

In the reduce method's callback function, you can make use of all four parameters available:

- **accumulator:** The accumulated value returned by the previous iteration's callback function. It accumulates the callback's return values.

- **currentValue:** The current element being processed in the array.

- **currentIndex (optional):** The index of the current element being processed in the array.

- **array (optional):** The array reduce was called upon.

## 4. find
The find method returns the first element in the array that satisfies the provided testing function. If no values satisfy the testing function, undefined is returned.

```ts
const numbers = [1, 2, 3, 4];
const found = numbers.find(num => num > 2);
console.log(found); // Output: 3
```

## 5. findIndex
The findIndex method returns the index of the first element in the array that satisfies the provided testing function. Otherwise, it `returns -1`.

```ts
const numbers = [1, 2, 3, 4];
const index = numbers.findIndex(num => num > 2);
console.log(index); // Output: 2
```

## 6. indexOf
The indexOf method returns the first index at which a given element can be found in the array, or -1 if it is not present.

```ts
const numbers = [1, 2, 3, 4];
const index = numbers.indexOf(3);
console.log(index); // Output: 2
```

## 7. some
The some method tests whether at least one element in the array passes the test implemented by the provided function. It returns a Boolean value.

```ts
const numbers = [1, 2, 3, 4];
const hasEven = numbers.some(num => num % 2 === 0);
console.log(hasEven); // Output: true
```

## 8. every
The every method tests whether all elements in the array pass the test implemented by the provided function. It returns a Boolean value.

```ts
const numbers = [1, 2, 3, 4];
const allEven = numbers.every(num => num % 2 === 0);
console.log(allEven); // Output: false
```

## 9. forEach
The forEach method executes a provided function once for each array element. It doesn't return anything (i.e., the return value is always undefined).

```ts
const numbers = [1, 2, 3, 4];
numbers.forEach(num => console.log(num * 2)); // Output: 2, 4, 6, 8 (each on a new line)
```

## 10. sort
The sort method sorts the elements of an array in place and returns the array. The default sort order is according to string Unicode code points.

```ts
const numbers = [4, 2, 3, 1];
numbers.sort();
console.log(numbers); // Output: [1, 2, 3, 4]

const words = ['banana', 'apple', 'cherry'];
words.sort();
console.log(words); // Output: ['apple', 'banana', 'cherry']
For numerical sorting, a compare function is needed:

const numbers = [4, 2, 3, 1];
numbers.sort((a, b) => a - b);
console.log(numbers); // Output: [1, 2, 3, 4]
```

## 11. includes
The includes method determines whether an array includes a certain value among its entries, returning true or false.

```ts
const numbers = [1, 2, 3, 4];
const hasTwo = numbers.includes(2);
console.log(hasTwo); // Output: true

const hasFive = numbers.includes(5);
console.log(hasFive); // Output: false
