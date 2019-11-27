---
layout: page

title: SQL Alchemy Guidelines

show_toc: true

---

## Query types

If you are looking for a single result prefer the use of `first` or `one_or_none`

If you want multiple rows then treat the query object as an iterable.

Don't use `all`.

If you use `one` then handle the cases where zero and more than one row occurs and handle the associated exceptions so that other developers can understand what you expected to happen.

### Rationale

Use of the ResultProxy iterable creates less memory-pressure than `all` and in most cases we don't want or need to do anything with all the results for the query in one go in the application.

`first` is easier to understand for maintenance as it returns `None` if no row is found.


If you use `one` then multiple rows or no rows found are both exceptions and in our code we rarely handle those exceptions explicitly so it is hard to follow what the code should be doing in those cases.

For `one_or_none` then you should do something appropriate with the multiple rows exception.

The `fetch` methods may require slightly different management of connections so they should probably never be used in our codebases.

See also the advice in the Essential SQL Alchemy book.

### Technical detail

`first` uses a `LIMIT` clause to restrict it's return type which is fast but can obscure problems in the underlying database structure. If you use it on anything other than a Primary Key column then if there are multiple rows that satisfy your query then the row returned by `first` will essentially be random and therefore inconsistent behaviour and intermittent bugs can arise.

## Clauses

Prefer IN (`in_`) over OR

### Rationale

In the vast majority of cases using the IN clause will be quicker and easier for the query planner to optimise.

The reason has to do with the amount of work the query engine has to do to determine the possible combinations whereas the IN will often define a small subset of the data using indexed values.

See also [Avoiding OR for better query performance](https://www.cybertec-postgresql.com/en/avoid-or-for-better-performance/)
