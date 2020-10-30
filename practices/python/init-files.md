---
layout: page
title: Using init files effectively
---


Init files should only be used to:

* hide the internal structure of a package
* declare constant values that do not have high computation value

Despite the name pre-emptive or anticipatory initialisation should not be done in init files but instead when the relevant functionality is first used.

This avoids unexpected resource usage when the package is loaded in say a testing context or in other short-lived execution contexts such as Lambda invocations.

It also avoids complexity dependency interactions such as for example initialising the ORM system.

We have also had problems with circular dependencies on initialisation as a result of side-effects in initialisation code.

If you want to try and have a more predictable initialisation point then consider an explicit initialisation function that can be invoked at a specified point in the code (for example, in Turbogear hooks). This will allow you to do intensive or expensive activity before say web requests were being served but without happening as soon as the code is imported.

## Related information

* [Why running code during import is a bad idea](https://utcc.utoronto.ca/~cks/space/blog/python/ImportTimeCodeStall)