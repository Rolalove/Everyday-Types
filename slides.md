---
# You can also start simply with 'default'
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: Everyday Types
info: |
  ## Everyday Types
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# https://sli.dev/guide/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/guide/syntax#mdc-syntax
mdc: true
---

# Everyday Types
<div></div>
Let's deconstruct the Everyday type's molecular makeup.

<a target="blank" href="https://github.com/Rolalove/Everyday-Types">Link to Repository</a>
 

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space to learn more about types <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<style>
h1 {
  background-color: #40E0D0; 
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
a{
  color: white;
}

</style>


---
layout: two-cols
layoutClass: gap-16
transition: slide-up
class: grid place-content-center
hideInToc: true
---

# Table of content

What are the thing we will be covering?

::right::
<Toc v-click minDepth="1" maxDepth="2"></Toc>

<style scoped>
h1 {
  color: #40E0D0; 
  
}

</style>


---
transition: slide-up
level: 2
---

# The primitives: string, number, and boolean
<div></div>
There are three main primitives in JavaScript and TypeScript.

- boolean - true or false values
- number - whole numbers and floating point values
- string - text values like "sulphur"

A primitive in Js (Primitive value, primitive datatype) is a data that is not an object and has no method or properties. We have 7 primitive types: string, number, bigint, boolean, symbol, null.

NOTE: Always use <span v-mark.underline.red>string</span>, <span v-mark.underline.yellow> number</span>, or <span v-mark.underline.green> boolean</span>, for types.

```js {monaco-run}
let name = "Rola"
name = -5
console.log(name)
```

```ts {monaco-run}
let name1: string ="Rola"
name1 = 2;
console.log(name1)
```

<style scoped>
h1 {
  color: #40E0D0; 
  
  
}
  .slidev-monaco-container {
  @apply overflow-scroll max-h-screen-sm ;
  max-height: 300px;
  }
</style>
---

# Arrays []
<div></div>
For an array <br>
1. string[] <br>  
2. number[] <br>
3. booloean[] <br>
4. object [] 
<br>
<br>

## Any
<div></div>
<span color="red">any</span> is a type that disables type checking and effectively allows all types to be used.
The any type is useful when you don’t want to write out a long type just to convince TypeScript that a particular line of code is okay.

```ts{monaco-run}
let con:any = "word";
con = 300.7; 
console.log(Math.round(con)); 
```

<style scoped>
h1,h2 {
  color: #40E0D0; 
}
  
</style>

---

# noImplicitAny
<div></div>
When you don’t specify a type, and TypeScript can’t infer it from context, the compiler will typically default to any.

You usually want to avoid this, though, because any isn’t type-checked. Use the compiler flag noImplicitAny to flag any implicit any as an error.


### Type Annotations on Variables
<div></div>
When you declare a variable using const, var, or let, you can optionally add a type annotation to explicitly specify the type of the variable:
```ts
let userName: string ="divine";
let accountNumber: number =12345678
```

<style scoped>
h1,h3 {
  color: #40E0D0; 
  
  
}
  
</style>
---
level: 2
---

# Function
<div></div>
TypeScript allows you to specify the types of both the input and output values of functions.
<br>
<br>

### Parameter Type Annotations
When you declare a function, you can add type annotations after each parameter to declare what types of parameters the function accepts. Parameter type annotations go after the parameter name:
Note: When a parameter has a type annotation, arguments to that function will be checked:

```ts{monaco-run}
function greet(name: string) {
  return("Hello, " + name.toUpperCase() + "!!");
 
}
greet()
 console.log(greet('umar'))
  console.log(greet('10'))
```

<style scoped>
h1,h3 {
  color: #40E0D0; 
}
  
</style>
---

# Object Types
<div></div>
To define an object type, we simply list its properties and their types.
```ts
const car: { type: string, model: string, year: number } = {
  type: "Toyota",
  model: "Corolla",
  year: 2009
};
```

### Optional Properties
Object types can also specify that some or all of their properties are optional. To do this, add a ? after the property name:

```ts{monaco-run}
const car: { type: string, mileage: number } = { 
  type: "Toyota"
};
console.log(car)
```
<style scoped>
h1,h3 {
  color: #40E0D0; 
}
</style>
---

# Union Types  | (OR)
<div></div>
A union type is a type formed from two or more other types, representing values that may be any one of those types. We refer to each of these types as the union’s members.

```ts{monaco-run}
function printAge(age: string | number) {
  console.log(`My name is mimi and i'm  ${age}.`)
}

printAge(20);
```
<style scoped>
h1,h3 {
  color: #40E0D0; 
}
</style>


---

# Type Aliases
<div></div>
it’s common to want to use the same type more than once and refer to it by a single name.
A type alias is exactly that - a name for any type.
You can actually use a type alias to give a name to any type at all, not just an object type.

```ts{monaco-run}
type CarYear = number
type CarType = string
type CarModel = string
type Car = {
  year: CarYear,
  type: CarType,
  model: CarModel
}

const carYear: CarYear = 2001
const carType: CarType = "Toyota"
const carModel: CarModel = "Corolla"
const car: Car = {
  year: carYear,
  type: carType,
  model: carModel
};
console.log(car)
```
<style>
h1{
  color: #40E0D0; 
}

  .slidev-monaco-container {
  @apply overflow-scroll max-h-screen-sm ;
  max-height: 450px;

}
</style>


---

# Interfaces
<div></div>
An interface declaration is another way to name an object type:
interfaces are similar to type aliases, except they only apply to object type

```ts
interface Rectangle {
  height: number,
  width: number
}

const rectangle: Rectangle = {
  height: 20,
  width: 10
}
```

<style>
h1{
  color: #40E0D0; 
}

</style>

---

# Differences Between Type Aliases and Interfaces





