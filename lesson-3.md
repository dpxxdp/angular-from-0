# The Model
*make sure* `ng serve` *is running and open your app in VS Code*

Open up app.component.html (remember CMD+P then start typing "appts"). Add the following code to the HTML:

```html
<div>
   <button (click)="buttonClicked()">Execute</button>
</div>
<div>
   Result: {{ result }}
</div>
```

It won't look pretty. That's okay, this lesson is not about styling, that comes later.

Now close the HTML file, that's all we'll need for now to start learning about the Model. The button acts as a handy way to "Execute" your code. The Result acts as a handy way to see the result.

### Variables

A variable is a "box" that you can put data in.  It keeps it for you and is handy to reference in other places throughout the app.  You can update that variable once, and everywhere else that refers to it will automatically get the new variable because they're all referring to the same "box of data".

Open up app.component.ts and add this somewhere, (ideally at the bottom, below the `constructor`, but before the last `}`):

```typescript
public result: number;

public buttonClicked() {
    result = 10;
}
```

Run the code by clicking the button in your browser.

We have a variable here called "result". Ignore everything else for now. Just keep in mind that the variable `result` is also in `{{ }}` in the HTML which should display it's current value in the browser.

To assign a value to that variable (ie to put data in the box) we use the **assignment** operator; you'll probably recognize it as the equals sign.

Here we're putting the number 10 in the box, and everyone who refers to `result` can access that data.

You can experiment with this for a while:

```typescript
result = 15;
result = 10 * 5;
result = 8 + 8;
result = 10 - 5;
result = -8;
result = 0.4;
result = 1/5;
```

It becomes obvious pretty quickly that you can do regular math with these numbers and save the result to a variable.

Now try something even more interesting:
```typescript
public result: number = 1;

public buttonClicked() {
    result = result + 1;
}
```

You're accessing the result and assigning it at the same time. You're saying "take whatever is already in the box, add 1, and reassign it to the box."  Now each time you press the button, we increment the number.

We can see the power of exponential growth this way too, after not a whole lot of clicks you end up with massive numbers:

```typescript
public result: number = 1;

public buttonClicked() {
    result = result * 2;
}
```

Let's do one last thing:

```typescript
public result: number = 1;

public buttonClicked() {
    var multiplier: number = 2;
    result = result * multiplier;
}
```

Here we are creating another variable called `multiplier`. As we adjust this variable, we can see that it causes result to grow quickly or slowly.

You can create variables two ways: declaring them "public" and putting them directly inside the AppComponent{ ... } or by declaring them using the keyword "var" inside of some other block of code.

Real quick: open up the HTML file again and try to add `{{ multiplier }}` to the HTML code.  You should see it fail. This is because `multiplier` only exists as a variable inside the block that you put it in, it doesn't exist as a "public" variable in the AppComponent { } block.

(Note: each time I talk about a "block" of code, I'm referring to something in between `{` and `}`. These are the natural boundaries for all coding in Typescript.)

### Typing

Okay, now what happens when you do:

```typescript
public result: number;

public buttonClicked() {
    result = 'Hello world!'
}
```

Here you are witnessing the power of **Strong Typing**.  VS Code is probably yelling at you right now.  There's likely some signal that what you did is *not* allowed.

This is because you are trying to assign a `string` to a variable that has been declared as a `number`.

In a weakly typed language, you may not have noticed your error until the program was running and people were using it.  By then it's just a bug and your users are like WTF dude! I can't overemphasize the importance of this!

In Typescript we declare Types using the `:` operator.

Every declaration goes like this: `[some-declaration] : [some-type]` . Think of an imaginary set of parenthesis around the variable name and the the type.  

Imagine: `public (result : number) = 2`

The fact that you're assigning it here and declaring it public are irrelevent to this conversation, we're interested in the variable name and the type.

You have several basic types to choose from in Typescript:
* number
* string
* boolean
* array
* tuple
* enum
* null
* undefined
* any

See all here: [https://www.typescriptlang.org/docs/handbook/basic-types.html](https://www.typescriptlang.org/docs/handbook/basic-types.html)

And you have many more advanced types to work with: [https://www.typescriptlang.org/docs/handbook/advanced-types.html](https://www.typescriptlang.org/docs/handbook/advanced-types.html)

Let's start with string.  To get your code working again, you probably know the obvious step. Change the **type** of our `result` variable:

```typescript
public result: string;

public buttonClicked() {
    result = 'Hello world!'
}
```

This should start working again without a problem.

Now play around with the other types until you're comfortable with:

string, number, boolean

#### Boolean

Here are some great ones to play around with using booleans.  This is pure logic.  Do each one slowly and try to understand what is happening.

What do you think `!` means in plain English?  What do you think `&&` means in plain English?  What about `||`?

```typescript
result = true;
result = false;
result = !true;
result = !false;
result = true && true;
result = true && false;
result = false && false;
result = true || true;
result = true || false;
result = false || false;
```

Here's another great one to play with for boolean. Can you see what's happening here?:

```typescript
public result: boolean = false;

public buttonClicked() {
    result = !result;
}
```

#### String

Strings are used very frequently and are quite straightforward. Here are some strings to play around with (second one shouldn't work):
```typescript
result = 'Hello' + ' World' + '!';
result = Hello World;
result = 'Hello + World';
result = "Hello World";
```

We'll get to arrays, enums, and tuples later.
Left to the reader: what does the `any` type do?  Why might this be useful?  Why might this be dangerous?
