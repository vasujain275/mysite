+++
title = 'How JavaScript Execute Code'
date = 2023-10-17T17:08:40+05:30
draft = false
+++


 **{}** - This is our **Global Execution Context** *(this)*

**Note:** Global Execution Context is different in various environment like Node, Browser, Bun, etc.

It is a window object in browser and a empty object in a runtime like Nodejs.

# Types of Execution Contexts

There are mainly three types of global execution contexts: 
1. Global Execution Context
2. Functional Execution Context
3. Eval Execution Context (Good to Know, mainly used in mongoose) 

# How JS code is Executed?

Let's understand this process with an Example - 

```js
let val1 = 10
let val2 = 5
function addNum(num1, num2){
	let total = num1 + num2
	return total
}

let result1 = addNum(val1,val2)
let result2 = addNum(10,2)
```

## 1. Global Execution / Environment 

#### A global object **{}** - *this* is created.

## 2. Memory Creation Phase 
All variables are created and *undefined* value is assigned to them.

In case of our Example - 

*var1* -> undefined

*var2* -> undefined

*addNum* -> definition of Function i.e. Steps to Execute

*result1* -> undefined

*result2* -> undefined

## 3. Execution Phase
Values are assigned to variables.

*var1* <-- 10

*var2* <-- 5

Now the function creates it own Execution Context first- 

### **addNum** --> *New Variable Environment* + *New Execution Thread* 

**Note:** For each new Function, there will be its own Execution Context where new Memory Creation Phase and Execution Phase will be created.

#### **addNum**'s Memory Phase -

*var1* -> undefined

*var2* -> undefined

*total* -> undefined

#### **addNum**'s Execution Phase -

*num1* -> 10

*num2* -> 5

*total* -> 15
#### The *total* variable with variable is returned to **Global Context**.

#### **Now** the Execution Context of addNum will be **Deleted** and control will reach Global Execution Phase.

*result1* -> 15

*result2* -> 12       // Same logic will be used to get value of result2

#### This was the Basic Overview of How JavaScript Execute Code. 
Concept by - *Hitesh Choudhary (YT)* 

Article by - *Vasu Jain*
