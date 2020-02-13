---
layout: page
title: Learning about the platform
---

The POPSSS platform is a vast and complex application with many moving parts, and lots of people working in the same repository.

It can be quite daunting for someone who is unfamiliar with the code base, so here are a few helpful hints and tips for helping yourself when it comes to learning about the platform.


### Code reviews

Code reviewing is an excellent way to learn your way around the code base.

Features old and new are often documented in pull requests, which include the code changes, and also often the rationale for changes and/or QA steps as a guide for human interaction with that particular part of the platform.

Obviously reviewing current changes is the best way to stay up to date with the latest features.

You should always be nosy and have a look at what is being submitted, even if it's for areas you have not had any exposure to. If you don't know what the code should be doing, ask the pull request submitter.

For more guidance around code reviews please see our [code review page](/principles-and-practices/practices/code-reviews)

Going back to historic pull requests can also help tell the story of how a feature has been developed. You can see how changes and revisions were built up and what design decisions were made. This might be very useful before you add a new feature to an existing part of the system.
### Tests

Reading tests can also be a very helpful first step.

Often they are written with both a positive assumption (i.e. passing valid arguments) and negative assumptions (i.e. passing invalid arguments). From there you can often get a sense of what the code is supposed to do.
