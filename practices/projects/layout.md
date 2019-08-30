---
layout: page
title: Project Structure
---

It is useful to be able to quickly understand how a project is structured. Therefore we should endeavour to keep our project structures as similar as possible.

## Top-level files

Always include a `README`. The README should be aimed at developers and should focus on how to get the application running locally.

If relevant include a `CONTRIBUTING` file that explains how to structure PRs and changes so they are easy to review.

Project-specific rules should be in the CONTRIBUTING file not generally in the README.

## Directories

* `/docs` for human-written documentation that would be useful if doing a search across the codebase
* `/tf` store Terraform configuration here
* `/cf` store CloudFormation here