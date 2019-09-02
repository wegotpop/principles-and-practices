---
layout: page
title: SQL Alchemy Basics
---

POPSSS uses SQLAlchemy ORM for use in code. All the models can be found under popsss.model as well as the DBSession which provides an already initialized session to access the Database called DBSession. If you're not familiar with SQLAlchemy, here are some examples of basic use.

### Create

```
from popsss.model import DBSession, MyModel
obj = MyModel()
obj.attr = value
DBSession.add(obj)
```

### Retrieve

```
from popsss.model import DBSession, MyModel

result = DBSession.query(MyModel).filter(MyModel.attr == value).first()
```

### Update

```
from popsss.model import DBSession, MyModel

result = DBSession.query(MyModel).filter(MyModel.attr == value).first()

result.attr = new_value
```

Optional to apply the change immediately: `DBSession.flush()`

### Delete

```
from popsss.model import DBSession, MyModel

DBSession.query(MyModel).filter(MyModel.attr == value).first().delete()
```

Optional to apply the change immediately: `DBSession.flush()`

