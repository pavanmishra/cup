dispel -- alternate web.py interface
===

## dispeak
All the wizard speak is quoted as below.
> And muggles quoteth not

## How to dispel?

You can choose to write your web.py application to one of the following interfaces

> You have several spells to ward of the charm

`dispel`, original inspiration
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

`cup` (in veins of `flask`, `bottle` and friends):

> reducto

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
`web.py` way, only dispelled(explained below)
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
`cork`, you can now flask and bottle your web.py, or rather dispelled one
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
