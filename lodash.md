# Lodash most common uses

## Table of Contents - First part
1. map
2. filter
3. reduce
4. find
5. isEqual
6. forEach


## Table of Contents - Second part
1. get
2. set
3. pick
4. omit
5. keys
6. values
7. findKey
8. assign
9. defaults
10. cloneDeep
11. isEmpty
12. has


# First Part

## 1. map
```
let numbers = [1, 2, 3, 4, 5];
let doubledNumbers = _.map(numbers, (x) => x * 2);
console.log(doubledNumbers);  // [2, 4, 6, 8, 10]
```

## 2. filter
```
let numbers = [1, 2, 3, 4, 5];
let evenNumbers = _.filter(numbers, (x) => x % 2 === 0);
console.log(evenNumbers);  // [2, 4]
```

## 3. reduce
```
let numbers = [1, 2, 3, 4, 5];
let sum = _.reduce(numbers, (acc, x) => acc + x, 0);
console.log(sum);  // 15
```

## 4. find
```
let numbers = [1, 2, 3, 4, 5];
let evenNumber = _.find(numbers, (x) => x % 2 === 0);
console.log(evenNumber);  // 2
```

## 5. isEqual
```
let arr1 = [1, 2, 3];
let arr2 = [1, 2, 3];
let arr3 = [1, 2, 4];
console.log(_.isEqual(arr1, arr2)); // true
console.log(_.isEqual(arr1, arr3)); // false
```

## 6. forEach
```
let numbers = [1, 2, 3, 4, 5];
_.forEach(numbers, (x) => console.log(x));
// Output: 1, 2, 3, 4, 5
```

# Second Part

## 1. get
```
let person = {
    name: {
        first: 'John',
        last: 'Doe'
    },
    age: 30
};
let firstName = _.get(person, 'name.first');
console.log(firstName);  // 'John'
```

## 2. set
```
let person = {
    name: {
        first: 'John',
        last: 'Doe'
    },
    age: 30
};
_.set(person, 'name.first', 'Jane');
console.log(person);  // { name: { first: 'Jane', last: 'Doe' }, age: 30 }
```

## 3. pick
```
let person = {
    name: {
        first: 'John',
        last: 'Doe'
    },
    age: 30,
    address: '123 Main St'
};
let nameAge = _.pick(person, ['name', 'age']);
console.log(nameAge);  // { name: { first: 'John', last: 'Doe' }, age: 30 }
```

## 4. omit
```
let person = {
    name: {
        first: 'John',
        last: 'Doe'
    },
    age: 30,
    address: '123 Main St'
};
let noAddress = _.omit(person, ['address']);
console.log(noAddress);  // { name: { first: 'John', last: 'Doe' }, age: 30 }
```

## 5. keys
```
let person = {
    name: {
        first: 'John',
        last: 'Doe'
    },
    age: 30,
    address: '123 Main St'
};
let keys = _.keys(person);
console.log(keys);  // ['name', 'age', 'address']
```

## 6. values
```
let person = {
    name: {
        first: 'John',
        last: 'Doe'
    },
    age: 30,
    address: '123 Main St'
};
let values = _.values(person);
console.log(values);  // [{first: 'John', last: 'Doe'}, 30, '123 Main St']
```

## 7. findKey
```
let person = {
    name: {
        first: 'John',
        last: 'Doe'
    },
    age: 30,
    address: '123 Main St'
};
let key = _.findKey(person, (val) => val > 25);
console.log(key); // "age"
```

## 8. assign
```
let obj1 = {
    a: 1,
    b: 2
};
let obj2 = {
    b: 3,
    c: 4
};
let obj3 = {
    d: 5
};
_.assign(obj1, obj2, obj3);
console.log(obj1); // {a: 1, b: 3, c: 4, d: 5}
```

## 9. defaults
```
let obj = {
    a: 1,
    b: undefined,
    c: 3
};
let defaults = {
    b: 2,
    d: 4
};
_.defaults(obj, defaults);
console.log(obj); // {a: 1, b: 2, c: 3, d: 4}
```

## 10. cloneDeep
```
let original = {
    a: 1,
    b: {
        c: 2
    }
};
let copy = _.cloneDeep(original);
console.log(original === copy); // false
console.log(original.b === copy.b); // false
```

## 11. isEmpty
```
let obj = {};
console.log(_.isEmpty(obj)); // true
```

## 12. has
```
let obj = {
    a: 1,
    b: 2
};
console.log(_.has(obj, 'a')); // true
console.log(_.has(obj, 'c')); // false
```






