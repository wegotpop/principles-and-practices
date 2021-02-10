---
layout: page
title: Creating a Pull Request
---

If a project contains a pull request (PR) template please read the instructions carefully and follow any additional instructions that might be there.

## Title and description

You should choose a concise title that accurately describes this change. Avoid very generic titles like "Profile changes", "Bug fix". Ideally you want to be able to find your PR by typing in a few keywords to the Github search bar.

In your description of the change you should [link to a Github Issue](https://docs.github.com/en/github/managing-your-work-on-github/linking-a-pull-request-to-an-issue) if this is relevant to the change.

There is no need to use the "magic language" of "Resolves" if you are not using an Issue.

You should link to any requirement information (Trello, Google Docs, etc.) but not reproduce any information from those documents. Again try to avoid generic titles like "Bug Report" and use a specific link text "Slack support request reporting a slow down in export".

## Implementation

This should explain the reasoning behind the way you have chosen to implement the changes required. For most changes there are multiple ways the problem could have been solved so it is important to share your reasoning as to why you have chosen the approach that you have, otherwise your [code reviewers]({{ site.baseurl }}{% link practices/code-reviews.md %}) will need to try and figure out what you were trying to do and whether you have done it successfully.

It is also important to record any conversations that were had during development that change the understanding of the initial requirements. In particular where design changes were agreed then add them here or link to the updated agreed designs.

## Referencing other PRs

If your PR builds on the work done in previous PRs then link to them via their id number using the Github auto-linking.

If in a previous PR you committed to updating the change you will ideally use Github Issues to record the resolution and link the relevant PRs together. If you did not do this for any reason then it will simplify maintenance if you update the older PR to link to the new one that is related.