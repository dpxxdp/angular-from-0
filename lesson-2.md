## Model and View

Angular is a **framework** created by Google to help build complex web applications.  Think of a *framework* as a toolbox that comes with some scaffolding already in place to help you get up and running quickly.

Angular is *not* a language. Typescript is a language. Angular is a framework.

A programmer *builds* within the Angular framework using three languages: Typescript, HTML, and CSS.  These three languages are very different from each other and are used in completely different contexts.  We'll focus on each one seperately throughout these lessons, but here are the high levels for all three:

#### Typescript
Typescript is a strongly-typed programming language, sharing styles with C#, Java, and Javascript. It "compiles" (or, *transpiles*) into Javascript, where it can be run in a browser. It was released recently, in 2012.

It is useful for writing logic that manipulates data and communicates across a network, among other things.

This is the type of language we think of when we think of "programming". The core of programming is manipulating and communicating some data **Model**.

Typescript looks like this:
```typescript
const title: string = "Hello";
if (title == "Hello") {
    console.log("Success!");
}
```

#### HTML
HTML is a "markup language" that is as old as the web itself.  It is used to describe the layout of a webpage.  The browser reads your HTML document and determines exactly where to put everything on your screen.  While you're reading this, hit: CMD+Alt+U. That is the HTML that is rendering the page you're reading.  Do a "Ctrl+F" for "this sentence" and you'll see this sentence!

It is important to seperate in your head two different tasks: structuring some data, and structuring some page.  The page structure is a question of design.  The data structure is a question of good data modeling.  HTML should be responsible *only* for the former.  It doesn't care about structuring data, it just cares about structuring the **View**.

HTML looks like this:
```html
<html>
    <body>
        <h1>Welcome to my webpage</h1>
    </body>
</html>
```

#### CSS
CSS stands for Cascading Style Sheets. CSS is most closely associated with HTML and is responsible for the *style* of the webpage.

Keep in mind this is different from the "structure" of the webpage (which we said was determined by HTML).  The fact that there is a toolbar at the top of this page is dictated by HTML. The fact that it's a nice shade of black is dictated by CSS.

You could *restyle* this entire page without having to worry about the structure of it.  That's the job of CSS.

CSS looks like this:
```css
.large-text {
    font-size: 20px;
    color: darkgrey;
}
```
-------------
Most programmers think about an important split: **View** and **Model**.  The *view* is described by HTML and CSS, and the *model* is described by Typescript.  As we just talked about, you could further break down the view into *structure* (HTML) and *style* (CSS). Often times these two things become very intertwined, so we bundle them together as *view*.

