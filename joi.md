# Joi most common use cases

## Table of Contents - First part

1. string
2. email
3. required
4. min
5. max
6. valid
7. regexp
8. number

## Table of Contents - Second part
1. keys
2. pattern
3. nand
4. and
5. xor


# First Part

## 1. string
```
const schema = Joi.object({
    name: Joi.string().required()
});
const { error, value } = schema.validate({ name: "John Doe" });
console.log(value); // { name: "John Doe" }
```

## 2. email
```
const schema = Joi.object({
    email: Joi.string().email().required()
});
const { error, value } = schema.validate({ email: "john.doe@example.com" });
console.log(value); // { email: "john.doe@example.com" }
```

## 3. required
```
const schema = Joi.object({
    age: Joi.number().required()
});
const { error, value } = schema.validate({ age: 25 });
console.log(value); // { age: 25 }
```

## 4. min
```
const schema = Joi.object({
    password: Joi.string().min(8).required()
});
const { error, value } = schema.validate({ password: "password123" });
console.log(value); // { password: "password123" }
```

## 5. max
```
const schema = Joi.object({
    password: Joi.string().min(8).required()
});
const { error, value } = schema.validate({ password: "password123" });
console.log(value); // { password: "password123" }
```

## 6. valid
```
const schema = Joi.object({
    color: Joi.string().valid("red", "green", "blue").required()
});
const { error, value } = schema.validate({ color: "green" });
console.log(value); // { color: "green" }
```

## 7. regexp
```
const schema = Joi.object({
    phoneNumber: Joi.string().regex(/^\d{3}-\d{3}-\d{4}$/).required()
});
const { error, value } = schema.validate({ phoneNumber: "555-555-5555" });
console.log(value); // { phoneNumber: "555-555-5555" }
```

## 8. number
```
const schema = Joi.object({
    age: Joi.number().required()
});
const { error, value } = schema.
validate({ age: 25 });
console.log(value); // { age: 25 }
```

# Second Part

## 1. keys
```
const schema = Joi.object().keys({
    name: Joi.string().required(),
    age: Joi.number().min(18).max(65).required(),
    email: Joi.string().email().required()
});
const { error, value } = schema.validate({ name: "John", age: 25, email: "john.doe@example.com" });
console.log(value); // { name: "John", age: 25, email: "john.doe@example.com" }
```

## 2. pattern
```
const schema = Joi.object().pattern(/^[a-z]+_\d+$/, Joi.string().required());
const { error, value } = schema.validate({ 
    "first_name": "John", 
    "last_name": "Doe", 
    "user_id_1": "abc123", 
    "user_id_2": "def456" 
});
console.log(value); // { "user_id_1": "abc123", "user_id_2": "def456" }
```

## 3. nand
```
const schema = Joi.object({
    username: Joi.string().required(),
    email: Joi.string().email().required(),
    phone: Joi.string().required(),
}).nand('email', 'phone');
const { error, value } = schema.validate({ username: "JohnDoe", email: "john.doe@example.com", phone: "555-555-5555" });
console.log(error); // "\"email\" must not exist simultaneously with [\"phone\"]"
```

## 4. and
```
const schema = Joi.object({
    username: Joi.string().required(),
    email: Joi.string().email().required(),
    phone: Joi.string().required(),
}).and('email', 'phone');
const { error, value } = schema.validate({ username: "JohnDoe", email: "john.doe@example.com" });
console.log(error); // "\"email\" must exist simultaneously with [\"phone\"]"
```

## 5. xor
```
const schema = Joi.object({
    username: Joi.string().required(),
    email: Joi.string().email().required(),
    phone: Joi.string().required(),
}).xor('email', 'phone');
const { error, value } = schema.validate({ username: "JohnDoe", email: "john.doe@example.com", phone: "555-555-5555" });
console.log(error); // "\"email\" must not exist simultaneously with [\"phone\"]"
```


