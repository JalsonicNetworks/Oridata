# Oridata Stand for (Object Representation Interface Data)
Oridata is a fixed data that is capable of combining live calculations. It has to allow for embedded code, so that data can make its own calculations, decisions, or even change values when necessary. This will make Oridata the best option for applications that need data to be dynamic, flexible in real-time, and capable of changing on the fly.

### 1. Overview and Purpose

**Start with Purpose:** The data format can be defined as hierarchical, driven by data where Oridata stores more than static data: it supports evaluable code snippets. In this sense, therefore, Oridata is both a data store and a layer of functionality that can execute logic or calculations in place.

**Use Cases:** Explain scenarios where Oridata is beneficial. For example, configurations where computed values or dynamically generated content are needed, or complex data hierarchies that require flexibility.


### Nested Structure

```json
{
  "<object> Root": {
    "<email> UserEmail": "example@domain.com <<< JavaScript Code to update email >>>",
    "<password> UserPassword": "StrongP@ss <<< JavaScript Code to hash password >>>",
    "<Int32> Age": 30 <<< JavaScript Code to calculate age dynamically >>>,
    "<object> Address": {
      "<string> Street": "123 Main St",
      "<string> City": "Sample City <<< JavaScript Code to set city dynamically >>>",
      "<Int32> PostalCode": 12345
    },
    "<array> Tags": [
      "<string> tag1 <<< JavaScript Code here >>>",
      "<string> tag2 <<< JavaScript Code here >>>"
    ]
  }
}
```

JSON in JavaScript:
In JavaScript, JSON is supported natively with two main methods:

Oridata.parse(): Converts a JSON string into a JavaScript object.

javascript Oridata
```javascript
const jsonString = '{"name": "John Doe", "age": 30}';
const obj = Oridata.parse(jsonString);
console.log(obj.name); // Output: John Doe
Oridata.stringify(): Converts a JavaScript object into a JSON string.
```

javascript Oridata
```javascript
const obj = { name: "John Doe", age: 30 };
const jsonString = Oridata.stringify(obj);
console.log(jsonString); // Output: {"name":"John Doe","age":30}
```

### JSON Syntax Rules:
Data is in key/value pairs: Keys must be strings (enclosed in double quotes "), and values can be strings, numbers, objects, arrays, true, false, or null.
Data is separated by commas: Each key/value pair is separated by a comma.
Curly braces {} hold objects: Objects are collections of key/value pairs.
Square brackets [] hold arrays: Arrays are ordered lists of values.

Table summarizing all the data types

| **Data Type** | **Column Name** | **Description**                                                                                     |
|---------------|-----------------|-----------------------------------------------------------------------------------------------------|
| `object`      | `value`         | Represents an object that is not null or an array. It can contain nested objects.                  |
| `array`       | `value`         | Represents an array.                                                                               |
| `string`      | `value`         | Represents a sequence of characters.                                                              |
| `number`      | `value`         | Represents a numerical value, including integers and floating-point numbers.                      |
| `boolean`     | `value`         | Represents a `true` or `false` value.                                                             |
| `datetime`    | `value`         | Represents a date or time. Accepts `Date` objects or valid date strings parseable by JavaScript.  |
| `null`        | `value`         | Represents a null value.                                                                          |
| `email`       | `UserEmail`     | Represents a valid email string, formatted like `example@domain.com`.                             |
| `password`    | `UserPassword`  | Represents a strong password with at least 8 characters, including uppercase, lowercase, numbers, and special characters. |
| `Int32`       | `Age`           | Represents a 32-bit signed integer ranging from -2147483648 to 2147483647.                        |
| `Long`        | `LargeNumber`   | Represents a large integer using JavaScript's `BigInt`.                                           |
| `Double`      | `Price`         | Represents a floating-point number (non-integer).                                                 |
| `Decimal128`  | `Amount`        | Represents a decimal number (no special support for 128-bit precision in JavaScript).             |
| `ObjectId`    | `UserId`        | Represents a MongoDB ObjectId in the format of a 24-character hexadecimal string.                 |


Designed, Built and Maintained by [Imran Malik](https://Imranamanat.com) imran@imranamanat.com and [Jalsonic Secure Team](https://jalsonic.com). A Division of [Jalsonic Networks](https://jalsonic.com).
