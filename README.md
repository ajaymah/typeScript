# TypeScript #

### Type Script Type VS interface ###  
**interface**  
``
interface User {
  name: string;
  age: number;
}
``  
**type**  
``type User = {
  name: string;
  age: number;
};
``
> [!NOTE]
> Note - simple object shapes, both work almost the same.

**Interface can be extended**  
```
interface Person {
  name: string;
}

interface Employee extends Person {
  salary: number;
}
```  
**You can define the same interface multiple times:**  
```
interface User {
  name: string;
}

interface User {
  age: number;
}
//output//
{
  name: string;
  age: number;
}
```
**Type is more powerful (can define more than objects)**  
- **Union types**
```
type Status = "success" | "error" | "loading";
```
- **Primitive types**  
```
type ID = string | number;
```
- **Tuples**
```
type Point = [number, number];
```
- **Function types**  
```
type Add = (a: number, b: number) => number;  
```

### 7 - Why do we use TypeScript? ###  
TypeScript is a superset of JavaScript that adds static typing and other features to help developers write more reliable and maintainable code.  
> JavaScript checks types at runtime, so some errors are only found when the code executes.

### 8 - How does "extends" work in TypeScript and what is the difference between type and interface? ###  
**extends** is used to _inherit properties_ from another interface or class.  
```
interface Person {  
  name: string;  
  age: number;  
}  
interface Employee extends Person {  
  employeeId: number;  
}  
const emp: Employee = {  
  name: "Ajay",  
  age: 25,  
  employeeId: 101  
};  
//Employee inherits all properties from Person.  
```
```
interface Person {  
  name: string;  
}  
interface Contact {  
  email: string;  
}  
interface Employee extends Person, Contact {  
  employeeId: number;  
}  
```
### 9 - TypeScript any vs unknown ###  
**unknown** is safer because you must check the type first.  
```
let a: any = "Hello";
a.toUpperCase(); // Allowed

let b: unknown = "Hello";
// b.toUpperCase(); // Error
```
### 10 - Diffrence between type and interface ###
The main difference between type and interface is that **interfaces support declaration merging** and are commonly used for object-oriented designs  
Types are more flexible because they can represent **unions**, **tuples**, **primitives**, **intersections**,  
**Union Types** -   
let id: string | number;  
**Intersection Types**  
```
type Employee = {  
  name: string;  
};  
type Developer = {  
  skills: string[];  
};  
type FullProfile = Employee & Developer;  
```
**Interface extends**  
```
interface Person {  
  name: string;  
} 
interface Employee extends Person {  
  salary: number;  
}  
```
**Generics**  
```
function getData<T>(value: T): T {  
  return value;  
}  
getData<string>("Hello");  
getData<number>(100);
```
**Generic Interface**  
```
interface ApiResponse<T> {  
  data: T;  
  success: boolean;  
}  
```
Enums  
Utility Types  
- Partial  - All properties become optional.
- Required
- Pick
```
type UserName = Pick<User, "name">;
```
-Omit  
```
type UserWithoutAge = Omit<User, "age">;
```
- **void**
Used when a function does not return a value.
```
function logMessage(message: string): void {  
  console.log(message);  
}  
const handleClick = (): void => {  
  console.log("Button clicked");  
};  
```
- never  
Used when a function can never reach its end
```
function runForever(): never {  
  while (true) {}  
}  
```
void  -> Function finishes without returning a value.  
never -> Function never finishes or never returns. 
   

