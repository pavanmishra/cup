dispel -- alternate web.py interface
===



Lets you write web applications as
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
Or as:
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
Even as:
```python
import dispel

class Hello(dispel.ContextResponder):
  
  def GET(self, name):
    if not name:
      name = 'World'
    return 'Hello, ' + name + '!'

urls = ('GET', '/(.*)', Hello)
app = dispel.application(*route.urls)
app.run()
```
And as:
```python

```
