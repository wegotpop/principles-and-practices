---
layout: page
title: Code review
---

All code should get a review by at least one other developer before being merged.

## Performing a code review

The code review should assume that the code that is being presented for review is correct, has been tested and meets the requirements of the problem.

It is not the reviewer's job to say that the code is: correct, bug-free or appropriate.

The code reviewer is primarily responsible for deciding whether the code makes sense to them and judging whether the code will be easy to maintain in the future. The code reviewer is not responsible for the outcome of the PR being merged, only the submitter.

Examples of reasonable requests during code review:

* Asking for documentation
* Asking for explanation of an approach in the PR
* Asking for a large PR to be broken up into smaller parts
* Asking for clarification on how a change meets the requirements

## Minimum pull request requirements

A PR should have a description that summarises the change, why it is being made and any issues or decisions that came up in the implementation but might not be obvious in the code.

A PR should have a good title that will be easy to find in a search.

If the change is primarily for user interface or styling changes, include a screenshot illustrating what the changes look like. This helps contextualise your changes.

### Tests

A PR should have appropriate unit or functional tests that demonstrate both the happy and unhappy paths of the code.

A PR must pass the full test suite of the code base to be approved and merged.

There may be some exceptions to this rule (for example changing microcopy in the UI) but where this is the case the PR's submitter *must* explain why the tests are not required for the change.

In the case of an emergency deploy, the full test coverage should follow as soon as possible. If not done immediately after the initial release, an Issue should be created in Github and assigned to someone to create the missing test coverage. This should be prioritised over all other non-emergency work.

## Large pull requests

If a change consists of more than 20 file changes then the PR should be considered as unreviewable. Sometimes changes on this scale are inevitable but always try to find ways to create smaller sequences of changes.

## Finding a reviewer

If your PR is urgent ping the #dev channel asking for a review.

If after a day your change has not been reviewed then try:

1. assigning a reviewer to the PR on Github
1. asking for a review on Slack

## Dangerous changes

For big or important changes try to get reviews from multiple reviewers, the more people who see and agree with your change then the easier it will be to support and release it.

## For code reviewers

### Dos

* Be in favour of releasing unless you have major reservations
* Do separate whitespace changes from functional changes
* Be prepared to review code in areas you are unfamiliar with so you can learn about it
* Add a :+1: to the review if you don't feel able to approve, to help indicate that you have read the PR
* Ask for tests or more tests if you feel they will help explain the change and improve the maintainability of the codebase
* Check for common issues

### Don'ts

* Where a stylistic or convention has not been followed you only have to point out one example and not all of them
* Assume you know what the code should be doing, ask if you are not sure
* Don't get into a big comment thread with another reviewer on someone else's pull request, take the conversation onto Slack or the real-world
* Be pedantic

### Use of Github statuses

Request changes when you think the change should **not** be merged into the codebase. You should use it when you have strong concerns that the PR does not address the problem it is meant to solve, when there are problems with the code or logic, the code differs substantially from the conventions of the codebase, there isn't enough tests to support the new code or there is any other fundamental issue that means the change would reduce the overall quality of the product.

Comment when you have questions, when you are unsure about whether a PR should be merged or not or you have an observation about one aspect of a change but no general opionion.

Approve the changes when you think the change addresses the problem and should be merged into the code base

An approval can also be conditional, for example if you think another reviewer has already make the salient points you can approve on the condition that the other reviewer's issues are resolved satisfactorily. You can also approve something conditional on the creation of new Github Issues or JIRA tickets to address particular areas of concern. This can be particularly useful in stopping perfection being the enemy of the good.

## For reviewees

### Dos

* When a reviewer points out a category of problem (for example using `dict` instead of the dictionary literal), check all of your pull request for the problem not just the example given
* Don't try and just address points in the review, where feedback is given consider how you might change your whole approach or change

### Don'ts

* Github will notify reviewers of changes and collapse comments on code that has changed since the comment so you don't need to confirm that each individual change has been made

## Common issues

### Parameter boundaries

Check whether the code deals with the boundaries of the parameters it operates on.

* How does it work if it is passed no arguments or special values such as `None` or `undefined`?
* Does the code cope with empty values such as the empty list or empty string?

#### Upper bounds

Does the code impose any maximum limit on the work it handles. If it was passed a lot of data would it be able to handle it? Would the physical time taken to execute the code exceed any timeouts with the proxy, database or execution environment?

In computer science terms is the code O(1) or O(n) or worse?

In this case it might be reasonable to ask how the reviewee expects the code to behave, will it intentionally crash or timeout? Is there a better solution?

## Further reading

* [How to make your code reviewer fall in love with you](https://mtlynch.io/code-review-love/)