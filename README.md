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

## Component scoped styles

In this branch we have our card component with its own css file.

PICTURE HERE

The styleUrls property of the @Component decorator lets Angular know that the card component will use its own style, or styles files.

Here we have the css of our app on 2 different files.  One if for the global styles, the style.css file, and the other stylesheet is inside our card folder in card.component.css.  This last file holds the styles only for the card component.

If you run the app or run the build you'll see that 2 ```<style>``` tags are added in our head.  The first style holds the global css from style.css and the second one holds the card component's styles.

PICTURE HERE

But there's something weird with our selectors in our second style tag.  You read .card[_ngcontent-c0] and all the other selectors have this weird atribute as well.

### View Encapsulation

What you're seeing is the way Angular mimics Shadow DOM to encapsulate the card css.  By default, every component that has its own css file will use the Emulated View Encapsulation.  Let's turn this default functionality off to see what happens.

PICTURE HERE

As you can see, we've added a property inside our card @Component decorator called encapsulation with a value of ViewEncapsulation.None.  To make this option work, you need to import the ViewEncapsulation module into your component.

If you run ng serve or ng build again, you will notice the weird attribute selectors now disappear.

PICTURE HERE

View Encapsulation has 3 modes:
* None: When you set View Encapsulation to None, your card styles are global, meaning they apply to the whole project.
* Emulated: This mode tries to emulate Shadow DOM, using attribute selectors to scope our styles.  Remember, this is the default option AND this is not real Shadow DOM, just a browser friendly way to scope our styles.
* Native: This is the real deal, when using Native we are enabling Shadow DOM.  The downside of this is browsers that don't support Shadow DOM go kaput.
