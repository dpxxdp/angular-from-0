# Lesson 1

## Typescript

Typescript is a language created by Microsoft.  It has two features that you should know about and understand now:
(1) it is strongly typed
(2) it "compiles" to Javascript

### Strong typing 101
Strong typing is the act of specifically defining the *type* of data that you will be dealing with everywhere you go. It is a way for the language to do a nice "double check" that nobody is using your code incorrectly anywhere before you actually run your program.

Take this invented example:

When I write code that stores and manipulates your data, there are a couple ways I could ask you for that data. 

First, I could say: "give me your name and your age". We'd like to think that a smart user knows what to do here, but we can't always assume that our users are smart. In fact, typically we assume just the opposite.  What if your program was to calculate the year they were born?  It would probably do something like:

```bash
2017 - <their age> = <their birth year>
```

So what happens when the user passes in `"twenty"`?  Your code blows up! It doesn't know how to subtract the word "twenty" from the number 2017!

So a better way of asking for the data is by saying, "give me your name (only alphabetic characters and spaces allowed) and give me your age (only integers allowed)". This precludes the user from passing in *anything* other than an integer for an age. The code will not even accept anything else, so you don't have to worry about handling all the cases where the user passes in something you weren't expecting!

This is strong typing in a nutshell: it is important to be *strongly specific* about the *type* of data you are using in any given place.

Now the "user" in our story is typically just another coder, writing code that interacts with your code. It may even be *you*, days or months after you wrote the first bit of code. Strong typing helps us communicate what our code does without having to say a word.

Not all languages are strongly typed.  There are some advantages to forgoing any type system at all... but I've found that clean, maintainable code is nearly always characterized by a strong type system. Typescript (given its name?) was designed from the bottom up as a "Typed" language.


### Typescript compiles to Javascript
Javascript was a language invented in the 1990s for writing code that can be run *inside* of a browser. To this day it remains nearly the universal favorite for writing code that is interpreted by your browser. So any website that does anything remotely dynamic is typically doing it using Javascript. There are now other uses for Javascript- a lot of people use Javascript outside of the browser as well, running it on a platform called [node.js](https://nodejs.org/en/).

But if you want to do web development, you need to use Javascript. Chrome/Firefox/IE/Opera/Brave won't understand anything else.

Javascript is immensely popular, especially with younger programmers. But in my opinion, it has one massive shortcoming: it's type system is *weak*. With Javascript, you don't declare types before they're used, so nobody every knows what the code does unless there is handwritten documentation that goes along with it.

It becomes clear, then, why Microsoft invented Typescript: (1) it's strongly typed, so we can write decent clean code with it, (2) it compiles into javascript, so we can run it in our browsers (so we can use it to build web apps)


## Git
*This assumes you've set up Angular and have `ng serve` running and have opened the code in VS Code*

Before doing anything else, `cd` into the directory where your app is and run:

```bash
git init
git add -A
git commit -m "initial commit"
```

Make a github account.

In Github, do New -> New repository -> Give it the same name you gave your app -> Keep it public -> Don't need to add README or license or .gitignore

Follow the commands for adding your repository to Github, they'll look something like this: (remember to run them from inside your app directory)

```bash
git remote add origin https://github.com/mattbarrett/honeybadger.git
git push -u origin master
```

This will save a snapshot of your code in a "git repository". This will let you revert to this state whenever you want, so that if you screw something up you know you can always safely return here.

Any time you feel that you're in a good place and want to take another snapshot, do:

```
git add -A
git commit -m "describe your changes here"
git push
```
Remember, these can never hurt.  You can always go back to an earlier snapshot. Git is incredible.
