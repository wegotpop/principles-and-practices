---
layout: page
title: Database indexes
---

## Optimise access to data with indexes

If a database query is slow or getting slower as the number of rows is growing in a table, you can often solve this problem by adding an index to the columns used in the where clause of the query.

If the index is over a single column, use `index=True` as a Column argument in the model and then create the respective migration. Otherwise define the index on **table_args** (see the documentation).

For booleans or any value where a column contains a few values that apply to many rows, it will probably make sense to use a [partial index](https://www.postgresql.org/docs/10/indexes-partial.html) when you care only about one of the values in the query, for example True or False.

This is because in general the query optimizer will perform a full-table scan if it cannot create a sensible sub-division of the query space. As a rule of thumb you want to try and identify 10% or less of a table during a query.

### Note: don't let indexes make things slower

Indexes make writing to the database slower as the entries into the index file need to be written along with the data row changes.

Don't add them unless there is a clear need.

Indexes work best when the data is written once and read frequently.

## Primary Keys

In Postgres [Primary Keys always have an associated index](https://www.postgresql.org/docs/current/sql-createtable.html) and you shouldn't need to specify this.

## Foreign Keys

If you're adding a foreign key, use the SQLAchemy Column keyword argument `index=True` in the migration to ensure lookups are as fast as possible.

Always try to reference an indexed set of columns on the foreign key table.

In Postgres an index is *not* automatically created when a Foreign Key is created because, despite the name, the Foreign Key is primarily a constraint that restricts the values in the child column to those present in the parent.

However Foreign Key columns are often used in joins which then means they need performant lookups to avoid a query slowdown.

## Using indexes on the SQLAlchemy model

You define a column as indexed on the model but this is just advisory. You need to actually create the index on the database by generating a migration.

If you create the index then it will be used even if not defined on the model. However to avoid confusion it makes sense to keep the two aligned.