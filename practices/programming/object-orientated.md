---
layout: page
title: Object-orientated programming
---

Advice for working with object-orientated programming languages

## Language-specific advice

### Javascript

In general do not use the object-orientated features of Javascript. If you want to use classes and similar structures we recommend using Typescript instead as this has a richer feature-set and type system than the default Javascript implementation.

### Python

Avoid using multi-class inheritance, this is a comparatively rare feature but it is present in some of our older code.

Where you are using classes prefer `dataclasses`.

## Do

### Do favour composition over inheritance

Avoid using inheritance. If you want to share functionality between classes then create an instance of the shared functionality class on the classes that need it or consider abstracting the shared functionality into a pure function if there is no state involved.

#### Rationale

Wherever we have created anything beyond a singe step of inheritance it has resulted in subtle (and sometimes unsubtle bugs) subsequently. Maintaining an accurate mental mode of multi-level inheritance is difficult particularly in open-class dynamic languages.

#### Exceptions

Common language patterns such as inheriting from Exception in Python.

Common framework inheritance in frameworks such as SQLAlchemy, TurboGears and Unit Test.

Historical one-level inheritance in our own code where we just need to show discipline and awareness in code review not to create deeper hierarchies.

Historical multi-level inheritance in our ORM, again we want to move away from this model in new designs to a more relational model but we won't be altering historical use of the inheritance tree to table mapping.

#### Further reading

* [Inheritance and Composition in Python](https://realpython.com/inheritance-composition-python/)
* The preference for composition is also in the book *Design Patterns*