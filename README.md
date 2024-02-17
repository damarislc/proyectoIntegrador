# Proyecto Integrador ecoomerce Backend comision 50035

Author: Damaris Lujan Calvillo

## Rutas

El proyecto cuenta por el momento con 2 API REST, las rutas con las siguientes:

### Products routes:

1.  Obtener todos los productos
    ```bash
    GET http://localhost:8080/api/products/
    ```
2.  Obtener producto por su id
    ```bash
    GET http://localhost:8080/api/products/:pid
    ```
    donde el :pid corresponde al id del producto
3.  Añadir producto

    ```bash
    POST http://localhost:8080/api/products
    ```

    el cual debe contener con un body raw JSON con el producto a añadir, por ejemplo:

    ```bash
    {
     "title": "Pintura Blanca",
     "description": "Pintura blanca 25L",
     "code": "X0A21233",
     "price": 1500,
     "status": true,
     "stock": 5,
     "category": "Pintura"
     "thumbnail": ["/public/images/imagen1.jpg", "/public/images/imagen2.jpg"]
     }
    ```

    Todos los campos son obligatorios excepto "status", que por default es _true_, y "thumbnail".

    El campo "code" debe ser único.

4.  Actualizar producto

    ```bash
    PUT http://localhost:8080/api/products/:pid
    ```

    donde el :pid corresponde al id del producto a actualizar.

    Debe contener con un body raw JSON con los campos del producto a modificar, por ejemplo:

    ```bash
    {
    "title": "Pintura Berel Rojo",
    "description": "Pintura rojo mate, 25L"
    }
    ```

5.  Borrar producto

    ```bash
    DELETE http://localhost:8080/api/products/:pid
    ```

    donde el :pid corresponde al id del producto a borrar.

### Cart routes:

1. Crear carrito
   ```bash
   POST http://localhost:8080/api/carts
   ```
2. Obtener productos del carrito
   ```bash
   GET http://localhost:8080/api/carts/:cid
   ```
   donde el :cid corresponde al id del carrito.
3. Añadir producto al carrito
   ```bash
   POST http://localhost:8080/api/carts/:cid/product/:pid
   ```
   donde el :cid corresponde al id del carrito y :pid al producto a añadir.

### Chat:

El chat se encuentra en la ruta raiz y se puede acceder desde:

```bash
http://localhost:8080/
```

Los mensajes serán almacenados en la base de datos en la colección messages y contendrá un campo user con el email del usuario y el campo message con el mensaje enviado.
