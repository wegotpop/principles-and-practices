---
layout: page
title: React Practices
---

## Hooks

Prefer hooks to class-based components.

Don't use Redux if Hook's State or Context will do what you need. In particular if you just want to record the internal state of a component then Hook's State should be fine.

### Rationale

Hooks are the [preferred future ](https://dev.to/dan_abramov/making-sense-of-react-hooks-2eib) of travel of the React team.

## Hidden components

When a components visibility is conditional then prefer the form:

```
flag && <Component />
```

Over a visibility state flag on the Component:

```
<Component visibleFlag=flag />
```

### Rationale

In the conditional form the Component will not be mounted if the condition is false and therefore you can avoid the cost of the lifecycle methods in the Component.

Where you are using stateless functional components this may not make much of a difference.