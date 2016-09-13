# Search and replace in YASnippets

I write a lot of SQLAlchemy ORM models where a table function looks something
like this:

```python
class MyTable(Base):
    __tablename__ = 'my_table'
    id = Column(Integer, Sequence('wids'), primary_key=True)
```

This seemed like a great use for a snippet, and I wanted to also handle
converting the CamelCase class name to a lowercase table name. Here's what I
(finally) came up with. Get a load of those backslashes!

```
# -*- mode: snippet -*-
# name: table
# key: ta
# --
class ${1:}(Base):
    __tablename__ = '${1:$(let* ((case-fold-search nil)) (downcase (replace-regexp-in-string "\\\\(.\\\\)\\\\([A-Z]\\\\)" "\\\\1_\\\\2" yas-text)))}'
    id = Column(Integer, Sequence('wids'), primary_key=True)
    $0
```
