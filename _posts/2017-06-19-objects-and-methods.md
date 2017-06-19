---
layout: post
title: Objects and Methods
---
### Introduction

We've covered types of variables in the Programming Basics post, and we've covered functions in the same post. We're now going to lightly touch on a slightly more advanced topic, which is heavily used in javascript: objects. There will be a lot more on object-oriented programming in future posts, but for now we're going to cover a few basics, as these are unavoidable in JS.

### Why objects matter in Javascript

During the design of JS as a language, the decision was made that everything in the language will be represented in memory as an object. Even a simple boolean value such as `var x = true;` will create a new object in memory. Up until now, this has been an irrelevant implementation detail, but as we start trying to solve a few problems we'll need to understand a bit about what this decision provides us with.

### Objects

At the simplest level, an object is simply an unordered map of arbitrary keys storing arbitrary values. For example

    {% highlight javascript %}
    var myObj = {
        thing: 'This thing',
        wotsit: 'Something else'
    };
    {% endhighlight %}

This object has two _properties_, set using a key and a value. A property key must always be a valid string, but the value can be anything of any type (including other objects). In this object, each value is also a string. Once an object is defined, you can access it's properties using a dot. For example, to access the value of `wotsit` on the above object `myObj` you would use `myObj.wotsit`, which will return you `"something else"`.

You can also add new arbitrary keys to an object. With the above object, we would add a new property like this: `myObj.newKey = 'new value'`. This would result in the previous object now being defined in memory like this:

    {% highlight javascript %}
    {
        thing: 'This thing',
        wotsit: 'Something else',
        newKey: 'new value'
    }
    {% endhighlight %}

"Plain" objects like this example are very useful for storing information. For example, in the real world, you may have a basket full of items, and each item can be stored as an object that looks a bit like this:

    {% highlight javascript %}
    {
        description: "iPhone 7 - Jet Black",
        sku: "i7jb",
        qty: 2,
        cost: 700,
        weight: 250,
        dimensions: {
            width: 7.5,
            height: 15,
            depth: 8
        },
    }
    {% endhighlight %}

### Methods

As well as storing boring old data, object can contain functions. When a function is attached to an object, it is often referred to as a "method" of that object. These methods can do anything you'd like them to, but due to some complexities of the language, defining methods is a topic for another day.

We will be talking about use of existing methods though, and one key area of this is in The DOM. Up til now, we've been using javascript in isolation, but when you start integrating your JS into a webpage, you'll need to do a fair bit of working with the DOM, or Document Object Model. This is the browsers representation of your HTML, and DOM methods are the key to interacting with users.

When you load a webpage, the browser sets up a few `global` objects you can use. A useful one is `document`, which is the browsers entry point into the DOM. You can call `document` methods to fetch elements, read information about the page or setup `listeners` to hook into user events.

It is also worth knowing that the javascript built-in types often have a bunch of pre-defined methods attached, which can make your life very easy. Learning these methods by heart is not something I'd expect you to do, however it is very useful to know roughly what they can do, so that when you need one, you can search for it's exact name and usage.

### Using Methods

Methods are called like any other functions in javascript, you invoke them by passing zero or more parameters in parentheses like this `myObj.someMethod()` or `myObj.otherMethod(param, paramTwo)`. The difference between methods and plain functions is that usually the method operates on the value it is attached to, rather than taking in a parameter to work with.

### Method examples

#### String methods

_.toLowerCase() example_

    {% highlight javascript %}
    var str = "This is MY StrinG.";
    var newStr = str.toLowerCase();
    {% endhighlight %}

_result_

In the above code, the toLowerCase() method makes a _copy_ of the string it is called on, and returns that converted all to lower case characters. So the result of this code is that str still contains `"This is MY StrinG."` and newStr contains `"this is my string."`.

_.slice() example_

    {% highlight javascript %}
    var str = "This is another string.";
    var cutOutBit = str.slice(5, 8);
    {% endhighlight %}

_result_

The slice method takes two parameters, a start index and an end index. It then slices that chunk out of a copy of the string. The result of this will be that `cutOutBit` contains `"is "` but `str` will be unaffected.


#### Methods on The DOM.

_.getElementbyId()_

A very useful method, you can use this to fetch an `element` from a document. Given a DOM fragment that looks like this:

    {% highlight html %}
    <div id="some-thing"><p>I'm a paragraph in a div!</p></div>
    {% endhighlight %}

You can use `document.getElementById('some-thing')` to get a reference to that div. For example:

    {% highlight javascript %}
    var someDiv = document.getElementById('some-thing');
    someDiv.style.color = "red";
    {% endhighlight %}

The above code will set the colour of text inside the div to red.
