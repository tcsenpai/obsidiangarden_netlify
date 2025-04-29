---
{"dg-publish":true,"permalink":"/bookmarks/tech/types-vs-interfaces-type-script/","tags":["algorithm","coding","learning","tutorial","work"]}
---


[blog.logrocket.com](https://blog.logrocket.com/types-vs-interfaces-typescript/?ref=dailydev)

# Types vs. interfaces in TypeScript - LogRocket Blog

Yan Sun

17–21 minutes

---

```table-of-contents

```

**Editor’s note:** _This article was last updated on 5 September 2024 by [Vijit Ail](https://blog.logrocket.com/author/vijitail/) to reflect the latest updates on primitive types, union types, and advanced function types in TypeScript_.

![IMG-20241106232537326.png](/img/user/_resources/IMG-20241106232537326.png)

We have two options for defining types in TypeScript: types and interfaces. One of the most frequently asked questions about TypeScript is whether we should use interfaces or types.

The answer to this question, like many programming questions, is that it depends. In some cases, one has a clear advantage over the other, but in many cases, they are interchangeable.

In this article, I will discuss the key differences and similarities between types and interfaces and explore when it is appropriate to use each one.

Let’s start with the basics of types and interfaces.

## Types and type aliases

`type` is a keyword in TypeScript that we can use to define the shape of data. The basic types in TypeScript include:

- String
- Boolean
- Number
- Array
- [Tuple](https://blog.logrocket.com/use-cases-named-tuples-typescript/)
- [Enum](https://blog.logrocket.com/typescript-string-enums-guide/)
- Advanced types

Each has unique features and purposes, allowing developers to choose the appropriate one for their particular use case.

Type aliases in TypeScript mean “a name for any type.” They provide a way of creating new names for existing types. Type aliases don’t define new types; instead, they provide an alternative name for an existing type.  
Type aliases can be created using the `type` keyword, referring to any valid TypeScript type, including primitive types.

type MyNumber = number;
type User = {
id: number;
name: string;
email: string;
}

In the above example, we create two type aliases: `MyNumber` and `User`. We can use `MyNumber` as shorthand for a number type and use `User type aliases` to represent the type definition of a user.

When we say “types versus interfaces,” we refer to “type _aliases_ versus interfaces.” For example, you can create the following aliases:

type ErrorCode = string | number;
type Answer = string | number;

The two type aliases above represent alternative names for the same union type: `string | number`. While the underlying type is the same, the different names express different intents, which makes the code more readable.

## Interfaces in TypeScript

In TypeScript, an interface defines a contract that an object must adhere to. Below is an example:

interface Client {
name: string;
address: string;
}

We can express the same `Client` contract definition using type annotations:

type Client = {
name: string;
address: string;
};

## Differences between types and interfaces

For the above case, we can use either `type` or `interface`. But there are some scenarios in which using `type` instead of `interface` makes a difference.

### Primitive types

Primitive types are inbuilt types in TypeScripts. They include `number`, `string`, `boolean`, `null`, and `undefined` types.  
We can use define a type alias for a primitive type as below:

type Address = string;

We often combine primitive type with union type to define a type alias, to make the code more readable:

type NullOrUndefined = null | undefined;

But, we can’t use an interface to alias a primitive type. The interface can only be used for an object type.  
Therefore, when we need to define a primitive type alias, we use `type`.

### Union types

Union types allow us to describe values that can be one of several types and create unions of various primitive, literal, or complex types:

type Transport = 'Bus' | 'Car' | 'Bike' | 'Walk';

Union type can only be defined using type. There is no equivalent to a union type in an interface. But, it is possible to create a new union type from two interfaces, like so:

interface CarBattery {
power: number;
}
interface Engine {
type: string;
}
type HybridCar = Engine | CarBattery;

### Function types

In TypeScript, a function type represents a function’s type signature. Using the type alias, we need to specify the parameters and the return type to define a function type:

type AddFn = (num1: number, num2:number) => number;

We can also use an interface to represent the function type:

interface IAdd {
(num1: number, num2:number): number;
}

Both type and interface similarly define function types, except for a subtle syntax difference of interface using `:` vs. `=>` when using type. Type is preferred in this case because it’s shorter and thus easier to read.

Another reason to use type for defining a function type is its capabilities that the interface lacks. When the function becomes more complex, we can take advantage of the advanced type features such as conditional types, mapped types, etc. Here’s an example:

type Car = 'ICE' | 'EV';
type ChargeEV = (kws: number)=> void;
type FillPetrol = (type: string, liters: number) => void;
type RefillHandler<A extends Car> = A extends 'ICE' ? FillPetrol : A extends 'EV' ? ChargeEV : never;
const chargeTesla: RefillHandler<'EV'> = (power) => {
// Implementation for charging electric cars (EV)
};
const refillToyota: RefillHandler<'ICE'> = (fuelType, amount) => {
// Implementation for refilling internal combustion engine cars (ICE)
};

Here, we define a type `RefillHander` with conditional type and union type. It provides a unified function signature for `EV` and `ICE` handlers in a type-safe manner. We can’t achieve the same with the interface as it doesn’t have the equivalent of conditional and union types.

### Declaration merging

[Declaration merging](https://www.typescriptlang.org/docs/handbook/declaration-merging.html) is a feature that is exclusive to interfaces. With declaration merging, we can define an interface multiple times, and the TypeScript compiler will automatically merge these definitions into a single interface definition.

In the following example, the two `Client` interface definitions are merged into one by the TypeScript compiler, and we have two properties when using the `Client` interface:

interface Client {
name: string;
}

interface Client {
age: number;
}

const harry: Client = {
name: 'Harry',
age: 41
}

Type aliases can’t be merged in the same way. If you try to define the `Client`type more than once, as in the above example, an error will be thrown:

![IMG-20241106232537355.png](/img/user/_resources/IMG-20241106232537355.png)

When used in the right places, declaration merging can be very useful. One common use case for declaration merging is to extend a third-party library’s type definition to fit the needs of a particular project.

If you need to merge declarations, interfaces are the way to go.

### Extends vs. intersection

An interface can extend one or multiple interfaces. Using the `extends`keyword, a new interface can inherit all the properties and methods of an existing interface while also adding new properties.

For example, we can create a `VIPClient` interface by extending the `Client`interface:

interface VIPClient extends Client {
benefits: string[]
}

To achieve a similar result for types, we need to use an intersection operator:

type VIPClient = Client & {benefits: string[]}; // Client is a type

You can also extend an interface from a type alias with statically known members:

type Client = {
name: string;
};

interface VIPClient extends Client {
benefits: string[]
}

The exception is union types. If you try to extend an interface from a union type, you’ll receive the following error:

type Jobs = 'salary worker' | 'retired';

interface MoreJobs extends Jobs {
description: string;
}

![IMG-20241106232537435.png](/img/user/_resources/IMG-20241106232537435.png)

This error occurs because the union type is not statically known. The interface definition needs to be statically known at compile time.

Type aliases can extend interfaces using the intersection, as below:

interface Client {
name: string;
}
Type VIPClient = Client & { benefits: string[]};

In a nutshell, both interfaces and type aliases can be extended. An interface can extend a statically known type alias, while a type alias can extend an interface using an intersection operator.

### Handling conflicts when extending

Another difference between types and interfaces is how conflicts are handled when you try to extend from one with the same property name.

When extending interfaces, the same property key isn’t allowed, as in the example below:

interface Person {
getPermission: () => string;
}

interface Staff extends Person {
getPermission: () => string[];
}

An error is thrown because a conflict is detected.

![IMG-20241106232537498.png](/img/user/_resources/IMG-20241106232537498.png)

Type aliases handle conflicts differently. In the case of a type alias extending another type with the same property key, it will automatically merge all properties instead of throwing errors.

In the following example, the intersection operator merges the method signature of the two `getPermission` declarations, and a [`typeof` operator](https://blog.logrocket.com/how-to-use-keyof-operator-typescript/) is used to narrow down the union type parameter so that we can get the return value in a type-safe way:

type Person = {
getPermission: (id: string) => string;
};

type Staff = Person & {
getPermission: (id: string[]) => string[];
};

const AdminStaff: Staff = {
getPermission: (id: string | string[]) =>{
return (typeof id === 'string'? 'admin' : ['admin']) as string[] & string;
}
}

It is important to note that the type intersection of two properties may produce unexpected results. In the example below, the `name` property for the extended type `Staff` becomes `never`, since it can’t be both `string` and `number` at the same time:

type Person = {
name: string
};

type Staff = person & {
name: number
};
// error: Type 'string' is not assignable to type 'never'.(2322)
const Harry: Staff = { name: 'Harry' };

In summary, interfaces will detect property or method name conflicts at compile time and generate an error, whereas type intersections will merge the properties or methods without throwing errors. Therefore, if we need to overload functions, type aliases should be used.

### Prefer extends over intersection

Often, when using an interface, Typescript will generally do a better job displaying the shape of the interface in error messages, tooltips and IDEs. It is also much easier to read, no matter how many types you combine or extend.

Compare that to the type alias that uses the intersection of two or more types like `type A = B & C;`, and you then type to use that alias in another intersection like `type X = A & D;`, TypeScript can struggle to display the structure of the combined type, making it harder to understand the shape of the type from the error messages.

Typescript caches the results of the evaluated relationship between interfaces, like whether one interface extends another or if two interfaces are compatible. This approach improves the overall performance when the same relationship is referenced in the future.

In contrast, when working with intersections, TypeScript does not cache these relationships. Every time a type intersection is used, TypeScript has to re-evaluate the entire intersection which can lead to efficiency concerns.

For these reasons, it is advisable to use interface extends instead of relying on type intersections.

### Implementing classes using interfaces or type aliases

In TypeScript, we can implement a class using either an interface or a type alias:

interface Person {
name: string;
greet(): void;
}

class Student implements Person {
name: string;
greet() {
console.log('hello');
}
}

type Pet = {
name: string;
run(): void;
};

class Cat implements Pet {
name: string;
run() {
console.log('run');
}
}

As shown above, both interfaces and type aliases can be used to implement a class similarly; the only difference is that we can’t implement a union type.

type primaryKey = { key: number; } | { key: string; };

// can not implement a union type
class RealKey implements primaryKey {
key = 1
}

![IMG-20241106232537548.png](/img/user/_resources/IMG-20241106232537548.png)

In the above example, the TypeScript compiler throws an error because a class represents a specific data shape, but a union type can be one of several data types.

### Working with tuple types

In TypeScript, the tuple type allows us to express an array with a fixed number of elements, where each element has its data type. It can be useful when you need to work with arrays of data with a fixed structure:

type TeamMember = [name: string, role: string, age: number];

Since tuples have a fixed length and each position has a type assigned to it, TypeScript will raise an error if you try to add, remove, or modify elements in a way that violates this structure.

For example:

const member: TeamMember = ['Alice', ‘Dev’, 28];
member[3]; // Error: Tuple type '[string, string, number]' of length '3' has no element at index '3'.

Interfaces don’t have direct support for tuple types. Although we can create some workarounds like in the example below, it is not as concise or readable as using the tuple type:

interface ITeamMember extends Array<string | number>
{
0: string; 1: string; 2: number
}

const peter: ITeamMember = ['Harry', 'Dev', 24];
const Tom: ITeamMember = ['Tom', 30, 'Manager']; //Error: Type 'number' is not assignable to type 'string'.

Unlike tuples, this interface extends the generic `Array` type, which enables it to have any number of elements beyond the first three. This is because arrays in TypeScript are dynamic, and you can access or assign values to indices beyond the ones explicitly defined in the interface:

const peter: ITeamMember = [’Peter’, 'Dev', 24];
console.log(peter[3]); // No error, even though this element is undefined.

## Advanced type features

TypeScript provides a wide range of advanced type features that can’t be found in interfaces. Some of the unique features in TypeScript include:

- Type inferences: Can infer the type of variables and functions based on their usage. This reduces the amount of code and improves readability
- Conditional types: Allow us to create complex type expressions with conditional behaviors that depend on other types
- [Type guards](https://blog.logrocket.com/how-to-use-type-guards-typescript/): Used to write sophisticated control flow based on the type of a variable
- Mapped types: Transforms an existing object type into a new type
- Utility types: A set of out-of-the-box utilities that help to manipulate types

TypeScript’s typing system constantly evolves with every new release, making it a complex and powerful toolbox. The impressive typing system is one of the main reasons many developers prefer to use TypeScript.

## When to use types vs. interfaces

Type aliases and interfaces are similar but have subtle differences, as shown in the previous section.

While almost all interface features are available in types or have equivalents, one exception is declaration merging. Interfaces should generally be used when declaration merging is necessary, such as extending an existing library or authoring a new one. Additionally, if you prefer the object-oriented inheritance style, using the `extends` keyword with an interface is often more readable than using the intersection with type aliases.

Interfaces with `extends` enables the compiler to be more performant, compared to type aliases with intersections.

However, many of the features in types are difficult or impossible to achieve with interfaces. For example, TypeScript provides rich features like conditional types, generic types, type guards, advanced types, and more. You can use them to build a well-constrained type system to make your app strongly typed. The interface can’t achieve this.

In many cases, they can be used interchangeably depending on personal preference. But, we should use type aliases in the following use cases:

- To create a new name for a primitive type
- To define a union type, tuple type, function type, or another more complex type
- To overload functions
- To use mapped types, conditional types, type guards, or other advanced type features

Compared with interfaces, types are more expressive. Many advanced type features are unavailable in interfaces, and those features continue to grow as TypeScript evolves.  
Below is an example of the advanced type feature that the interface can’t achieve.

type Client = {
name: string;
address: string;
}
type Getters<T> = {
[K in keyof T as `get${Capitalize<string & K>}`]: () => T[K];
};
type clientType = Getters<Client>;
// type clientType = {
// getName: () => string;
// getAddress: () => string;
// }

Using mapped type, template literal types, and `keyof` operator, we created a type that automatically generates getter methods for any object type.

In addition, many developers prefer to use types because they match the functional programming paradigm well. The rich type expression makes it easier to achieve functional composition, immutability, and other functional programming capabilities in a type-safe manner.

## Conclusion

In this article, we discussed type aliases and interfaces and their differences. While there are some scenarios in which one is preferred over the other, in most cases, the choice between them boils down to personal preference.  
I lean towards using types simply because of the amazing type system. What are your preferences? You are welcome to share your opinions in the comments section below.

## [LogRocket](https://lp.logrocket.com/blg/typescript-signup): Full visibility into your web and mobile apps

[![IMG-20241106232537603.png](/img/user/_resources/Bookmarks/Tech/Types%20vs%20Interfaces%20-%20TypeScript/IMG-20241106232537603.png)](https://lp.logrocket.com/blg/typescript-signup)

[LogRocket](https://lp.logrocket.com/blg/typescript-signup) is a frontend application monitoring solution that lets you replay problems as if they happened in your own browser. Instead of guessing why errors happen or asking users for screenshots and log dumps, LogRocket lets you replay the session to quickly understand what went wrong. It works perfectly with any app, regardless of framework, and has plugins to log additional context from Redux, Vuex, and @ngrx/store.

In addition to logging Redux actions and state, LogRocket records console logs, JavaScript errors, stacktraces, network requests/responses with headers + bodies, browser metadata, and custom logs. It also instruments the DOM to record the HTML and CSS on the page, recreating pixel-perfect videos of even the most complex single-page and mobile apps.

[Try it for free](https://lp.logrocket.com/blg/typescript-signup).
