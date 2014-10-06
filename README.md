cup: a pythonic wrapper around web.py framework
=====

## A complete `cup` application

```python
def hello(web):
  return 'Hello, World!'

urls = ('/', hello)

import cup
app = cup.application(urls)
app.run()
```

## `web.py` like application

```python
class Hello:

  def GET(self, name):
    if not name:
      name = 'World'
    return 'Hello, ' + name + '!'

urls = ('/(.*)', Hello)

import cup
app = cup.application(urls)
app.run()
```

## `bottle` or `flask` like routed application

```python
import cup

route = cup.Route()

@route.GET('/(.*)')
def hello(ctx, name):
  if not name:
    name = 'World'
  return 'Hello, ' + name + '!'

app = cup.application(route.urls)
app.run()
```

## `web.py` with router
```python
import cup

route = cup.Route()

@route('/(.*)')
class Hello:

  def GET(self, name):
    if not name:
      name = 'World'
    return 'Hello, ' + name + '!'

app = cup.application(route.urls)
app.run()
```
