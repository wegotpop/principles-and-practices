---
layout: page
title: Core Technologies
---

We current have experience and expertise in:

* Python
* Javascript
* Typescript
* HTML/CSS
* AWS

## Language specific tools and frameworks

Things marked **Do use** feel free to use where you want.

Things in **Retire** means that we still have code that uses this and it is okay to continue to use it where it is already in use but we should not create any more code using it. We should take the opportunities to remove it from our codebase where they arise.

Things marked as **Don't use** means that we have either retired this successfully or we have tried it and it hasn't worked out and should only be re-trialled if we have had a proper review of what did not work before and why things might now be different.

### Python

#### Do use

* Flask

#### Retire

* Turbogears

### Javascript/Typescript

#### Do use

* Webpack
* React
* CSS Modules

#### Retire

* Redux (use React Hooks instead)
* Flow (use Typescript instead)
* LESS
* jQuery
* React class-based components (use Stateless components instead)
* React Bootstrap

#### Don't use

* Inline styling in React Components