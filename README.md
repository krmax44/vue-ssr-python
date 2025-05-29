# Vue Server-Side Rendering in Python

Client for [`vue-ssr-service`](https://github.com/krmax44/vue-ssr-service). See its documentation for a [quick start guide](https://github.com/krmax44/vue-ssr-service#getting-started-with-vite).

## Stand-alone

```python
from vue_ssr import ServerRenderer

renderer = ServerRenderer()
renderer.render("myComponent", props={"name": "friend"})
# "<p>Hello, friend!</p>"
```

## With Django

Works well in conjunction with [`django-vite`](https://github.com/MrBin99/django-vite). Add it to your installed apps:

```py
INSTALLED_APPS = [
  "vue_ssr",
  ...
]
```

Then, you can simply use the provided template tag:

```django
{% load vue_ssr %}
<user-greeting>{% render_vue "userGreeting" name=request.user.username %}</user-greeting>
```

Or pass a dict with props:

```django
<my-app>{% render_vue "myApp" props=props %}</my-app>
```
