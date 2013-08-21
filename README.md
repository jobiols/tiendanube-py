tiendanube-python
=================

TiendaNube API Python Client.

Install
-------

```bash
$ git clone git@github.com:catalanojuan/tiendanube-python.git
$ pip install -r tiendanube-python/requirements.txt
```

Usage
-----

Query list of products:

```python
> api_key = 'API_KEY'
> from tiendanube import NubeClient
> client = NubeClient(api_key)
> store = client.get_store(1)
> [p.name.es for p in store.products.list()]
[u'Mi primer producto',
 u'Probando publicaci\xf3n',
 u'hola',
 u'Producto de Prueba']
```
 
Query one product in particular:

```python
> api_key = 'API_KEY'
> from tiendanube import NubeClient
> client = NubeClient(api_key)
> store = client.get_store(1)
> p = store.products.get(911)
> p.name.es
u'Mi primer producto'
```

Query images for a given product:

```python
> api_key = 'API_KEY'
> from tiendanube import NubeClient
> client = NubeClient(api_key)
> store = client.get_store(1)
> p = store.products.get(911)
> [i.src for i in p.images.list()]
[u'http://example.com/image.jpg']
```
