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
**Primitive types**  
```
type ID = string | number;
```
**Tuples**
```
type Point = [number, number];
```
**Function types**  
```
type Add = (a: number, b: number) => number;  
```
   

