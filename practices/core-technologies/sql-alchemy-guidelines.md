---
layout: page

title: SQL Alchemy Guideline

show_toc: true

---

## Query types

Only use `first` or treat the query as an iterable.

Don't use `one` or `all`.

### Rationale

Use of the ResultProxy iterable creates less memory-pressure than `all` and in most cases we don't want or need to do anything with all the results for the query in one go in the application.

`first` is easier to understand for maintainance as it returns `None` if no row is found.

If you use `one` then multiple rows or no rows found are both exceptions and in our code we rarely handle those exceptions explicitly so it is hard to follow what the code should be doing in those cases.

The `fetch` methods may require slightly different management of connections so they should probably never be used in our codebases.

See also the advice in the Essential SQL Alchemy book.

## Clauses

Prefer IN (`in_`) over OR

### Rationale

In the vast majority of cases using the IN clause will be quicker and easier for the query planner to optimise.

The reason has to do with the amount of work the query engine has to do to determine the possible combinations whereas the IN will often define a small subset of the data using indexed values.

See also [Avoiding OR for better query performance](https://www.cybertec-postgresql.com/en/avoid-or-for-better-performance/)
