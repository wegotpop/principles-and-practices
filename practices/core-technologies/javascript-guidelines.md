---
layout: page
title: Javascript Guidelines

---

## Prefer null to undefined

If you have a value that represents something that does not exist or which has not been set then prefer the use of `undefined` to `null`.

### Rationale

`undefined` is a constant value that has a specific meaning whereas a `null` is a pointer-type that indicates effectively a non-assignment.

The type of `undefined` is *undefined* whereas the type of `null` is *object*.

This latter assignment makes sense but can be a source of confusion as `null` is a value than can stand in for any object.

