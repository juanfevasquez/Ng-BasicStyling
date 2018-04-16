# NgBasicStyling

> This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 1.7.4.

Welcome!  This is a repo derived from another repo called [CSS Architecture Patterns for Ng](https://github.com/juanfevasquez/CssArchitecturePatternsForNg) where I explain the different ways you can use css for an Angular app and how each might affect performance.  It also explains some key concepts of CSS Architecture like specificity, naming conventions, pre-processors, repaints and reflows.  It is quite dense and that's why I decided to created this smaller repo where I only explain the different ways that Angular provides for us to load css styles in our apps.  I hope you enjoy it.

## Install the repo

Just clone the repo and run npm install on your console
```
npm install
```

## How to go through the examples

Each example will live in its own branch.  Master will not hold any example so switch to the respective branch to see the demo.

## The Basics of Css in Angular apps

Angular has provided us with quite a lot of options to work with styles in our apps.  Before this we all were limited to adding our styles globally, meaning we had to use a link or several link tags in our page's head to load all of the different css files.  So for us it would be normal to have a link pointing to a responsive framework like Bootstrap or Foundation, then a link pointing to our own css files.  Also, from time to time we would find some inline styling and also styles added dynamically to our tags through javascript.

Now we are transitioning to a new way of doing things on the web.  This new way is called web components and with this comes new possibilities to work with our styles.

Mind that one of the main philosophies of web components is encapsulation where a custom element has a scoped html, css and javascript.  This "scoped" html and css is what is called Shadow Dom.

> I have another repo where I show a very basic custom element.  [Click here]() if you want to check it out.

Using Shadow DOM, we can scope our styles to our custom elements, avoiding conflict with any global css declaration.  **This is the concept that Angular bases its component css architecture**

But Angular doesn't use Shadow Dom (at least, not by default).  Angular simulates this behavior using something called ViewEncapsulation.  Before learning more about View Encapsulation though, we will learn other ways to work with css in our Angular apps that will result very familiar.

Please, change branch to demo/global-styles-in-angular to start our journey.


