cup: a python web framework
=====

# `cup` application

```python
def hello(web):
  return 'Hello, World!'

urls = ('/', hello)

import cup
app = cup.application(urls, locals())
app.run()
```
