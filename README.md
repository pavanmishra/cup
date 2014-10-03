dispel -- it's web.py, stupid, but dispelled
===

## Dispeak

All the wizard speak is quoted as below.
> And muggles quoteth not

## Idiomatic or not, pythonic or not, micro or full stack...

> Gryffindor vs Slytherin  is a passé, lets Ravenclaw vs Hufflepuff 

`web.py` is a simple and powerful web framework. It strikes a fine balance between do it all vs micro frameworks. Some parts(request/response handling) of it do feel magical, unpythonic some would say. `dispel` is a tiny layer over request/response handling of `web.py`, in doing so it does not affect the `web.py`'s internals, and makes your code look more pythonic. It also adds some of the routing alternatives, which can make it look even better. 

## How to dispel?

You can choose to write your web.py application in on of the following styles.

> You have several spells to ward of the charm

`dispel`, it all started with this.

> stupefy 

```python
def hello(ctx, name):
  if not name:
    name = 'World'
  return 'Hello, ' + name + '!'

urls = ('GET', '/(.*)', hello)

import dispel
app = dispel.application(urls, locals())
app.run()
```

`cup` (`flask`, `bottle`, anyone o_O ).

> crucio

```python
import dispel

route = dispel.Route()

route.GET('/(.*)')
def hello(ctx, name):
  if not name:
    name = 'World'
  return 'Hello, ' + name + '!'

app = dispel.application(*route.urls)
app.run()
```

`web.py`, dispelled, ofcourse

> expelliarmus

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

`cork`, you can now `flask` and `bottle` your `web.py`(dispelled one, ofcourse)

> reducto

```python
import dispel
route = dispel.Route()

route('/(.*)')
class Hello:
  
  def GET(self, name):
    if not name:
      name = 'World'
    return 'Hello, ' + name + '!'

app = dispel.application(*route.urls)
app.run()
```

