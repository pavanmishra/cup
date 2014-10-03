dispel -- it's web.py, stupid, but dispelled
===
## A complete dispel app
```python
import dispel

def hello(web):
  return 'Hello, World!'

urls = ('GET', '/hello', hello)
app = web.application(urls, locals())

if __name__ == '__main__':
  app.run()
```
If python newcomer can get away with __name__ and '__main__', then may be new web programmer can be instructed in 'GET'.

## A sigil and a router for unsuspecting.
```python
import dispel

router = dispel.Router()

def hello(web):
  return 'Hello, World!'

urls = ('GET', '/hello', hello)
app = web.application(urls, locals())

if __name__ == '__main__':
  app.run()
```

## Dispeak

All the wizard speak is quoted as below.

> And muggles quoteth not

## Idiomatic or not, pythonic or not, micro or full stack...

> Gryffindor vs Slytherin  is a passé, lets Ravenclaw vs Hufflepuff

`web.py` is a simple and powerful web framework. It strikes a fine balance between do it all vs micro frameworks. Some parts(request/response handling) of it do feel magical, unpythonic some would say. `dispel` is a tiny layer over request/response handling of `web.py`, in doing so it does not affect the `web.py`'s internals, and makes your code look more pythonic. It also adds some routing alternatives, which look good to some.

## How to dispel?

You can choose to write your web.py application in on of the following ways.

> You have several spells to ward of the charm

###`dispel`, it all started with this.

> stupefy

Possible to define handlers as functions. Ideal and clean, maybe.

```python
def hello(web, name):
  if not name:
    name = 'World'
  return 'Hello, ' + name + '!'

urls = ('GET', '/(.*)', hello)

import dispel # imported here to emphasize simplicity
app = dispel.application(urls, locals())
app.run()

```

###`cup`, pour you some from `flask` or `bottle`

> crucio

`dispel` router allows to keep url patterns close to the handlers. Beautiful, maybe.

```python
import dispel

route = dispel.Route()

@route.GET('/(.*)')
def hello(web, name):
  if not name:
    name = 'World'
  return 'Hello, ' + name + '!'

app = dispel.application(route.urls, locals())
app.run()
```

##`web.py`, dispelled, ofcourse

> expelliarmus

`dispel` lets you write applications as you have been doing all along in web.py. Hysterical, maybe.

```python
import dispel


class Hello:

  def GET(self, name):
    if not name:
      name = 'World'
    return 'Hello, ' + name + '!'


urls = ('/(.*)', Hello)
app = dispel.application(urls, locals())
app.run()
```

##`cork`, you can now `flask` and `bottle` your `web.py`

> reducto

`dispel` router also lets you bring your url patterns close to `web.py` handlers. Paranoid, definitely.

```python
import dispel
route = dispel.Route()


@route('/(.*)')
class Hello:

  def GET(self, name):
    if not name:
      name = 'World'
    return 'Hello, ' + name + '!'


app = dispel.application(route.urls, locals())
app.run()
```

