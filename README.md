# tornado_asgi_handler
A request handler runs in tornado to support asgi


# Runs in tornado 

```python
import tornado.ioloop
import tornado.web
import tornado_asgi
import quick_start

application = tornado.web.Application([
    (r".*", tornado_asgi.AsgiHandler, dict(asgi_app=quick_start.app))
])
application.listen(8000)
tornado.ioloop.IOLoop.current().start()

```

# Runs in uvicorn  

```shell
uvicorn quick_start:app
```