
<p align="center">
<img width="300px" src="https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcTCFs4dE1QHHr29MYJ4cij1eqMNZfet-vtrzg&usqp=CAU" alt=""/>
</p>

# Typescript

  Install typescript cli
```
npm install -g typescript
```
Compile Typescript
```
tsc filename.ts
```
 Recompile ts file automatically
 ```
 tsc filename.ts -w
```

## Type in TS

We can define spacific data type in typescript but we cant do same thing in JS
we can declare variable using let , var or const 

```
let age = 30;
let isBlack = true

let age = '30'  // error
let isBlack = 'true'  // error
```
We cant change type in TS. Here we cant change age as a character or we cant change isBlack in any other data type

```
const circ = (diameter) =>{
    return diameter * Math.PI
}
console.log(circ('hello')) // Here we pass any type of data but that dosen't make any sence . we cant calculate diameter of str
----------------------------------
const circ = (diameter:number) =>{
    return diameter * Math.PI
}
console.log(circ(243))  // But here we can pass only numbers
```
## Objects & Array in TS

If you declare a array with same datatype then you cant push another datatype in that array
```
let names = ['samuel' , 'john' ,'sammy' ,'allo'];  //only char
let numbers = [5,6,3,4,62];                           // only num
let mixed = ['samuel' , 3 ,'john',4 ,'lala'];     // mixed

names.push('boy');
mixed.push(3);

 name.push(4); // Error
```
similarly for objects also you cant add other type of dataType
```
let human = {
    name:'sahil',
    age: 21,
    sex:'male'
}

human.age = 20;
human.age = 'sj';
```
## Explicit Type in TS
We know that define dataType is important in typescript . so Explicitly we define Datatype of a variable 

```
let age: number;  // you can't change datatType of age again
let character:string;
let isLogedin: boolean;
let human: string[] = [];  //only string
let mixed: (string!number!biilian)[] = [];  //only string
```
## Dynamic (any) Type in TS

```
let age : any;
age = "sahil";
console.log(age);
```
## Better Workflow
Initialize TS configuration
``` 
tsc --init 
```
- rootDir // input files where TS file pesent
-outDir   // output files 
- "include":["Folder name"]  // add this in end of tsconfic
It means exicute those ts file which is inside Specifiedfolder

## Function

```
let greet:Function;

greet = () =>{
    console.log("hello")
}
greet();
```
Optional parameter
```
const add = (a:number,b:number,c?: number | string) => {
    console.log(a+b);
    console.log(c);
}
add(5,8)
```
### Function Signatures
```
let greet: (a:string,b:string) =>void;
greet = (name : string,greetings:string) =>{
    console.log(`${name} says ${greetings}`)
}
greet("sahil","hello");

let calc: (n1:number, n2:number) =>number; 
calc = (num1:number,num2:number)=>{
    return num1+num2;
}
calc(1,6);
```
## Dom manuepulation and Typecasting
```
const anchor = document.querySelector('a')!;
if(anchor) {
  console.log(anchor.href);
}
console.log(anchor.href);

//const form = document.querySelector('form')!;
const form = document.querySelector('.new-item-form') as HTMLFormElement;
console.log(form.children);

// inputs
const type = document.querySelector('#type') as HTMLInputElement;
const tofrom = document.querySelector('#tofrom') as HTMLInputElement;
const details = document.querySelector('#details') as HTMLInputElement;
const amount = document.querySelector('#amount') as HTMLInputElement;

form.addEventListener('submit', (e: Event) => {
  e.preventDefault();

  console.log(
    type.value, 
    tofrom.value, 
    details.value, 
    amount.valueAsNumber
  );
});
```
