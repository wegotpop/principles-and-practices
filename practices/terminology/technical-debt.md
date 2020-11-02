---
layout: page
title: Technical Debt
---

We should endeavour to use [Ward Cunningham's original meaning](https://youtu.be/pqeJFYwnkjE) of Technical Debt which can roughly be summarised as the extent to which the system no longer accurately reflects the domain problem it is addressing.

An application can express this problem in two common ways: the domain has changed and the development capability is no longer present to adjust the system or the system has started to reflect non-domain principles such as abstract rules on the way software is created in the group.

Cunningham recommends that new understanding of the domain or the way technology can solve the domain is regularly reincorporated back into the codebase of the system.

## Other meanings

Sometimes technical debt is used to refer to "friction" of developing features in a codebase. It is probably better to think of this problems as "developer ergonomics" or "developer experience". This problem is important but the outcome is to address those experience problems not to make abstract changes to the codebase.

Technical debt can also be used to describe the conscious act of creating "poor" code to achieve a tactical objective in the knowledge that the lack of quality or failure to address broad use cases may create a problem later.

Again in these cases the debt description is not quite correct. If either of these concerns become manifest then they are better addressed by different development strategy. A focus on regression testing in the former and a generalisation of the problem space in the latter.

This case of generalisation might actually be the closest practice to what Cunningham describes in his conception of technical debt. So when we encounter this case we should try to reframe any attempt to solve the problem as a way to reincorporate domain understanding (the range of problems the software may be used to address) rather than create "generic" software.

## Metaphorical concerns

Technical debit is meant to appeal to financial people so it might be an opaque term to people in terms of what it is trying to convey.

To be a valid metaphor the problem described as "technical debt" should exert some regular recurring form of cost that is paid in exchange for the tactical solution.

If a problem in a codebase occurs no particular cost then the debt metaphor is inappropriate.