# Ejercicio 4 - Modelo Entidad-Relación de un Sistema de Gestión de Pedidos

## Descripción

Este ejercicio consiste en diseñar un modelo Entidad-Relación (DER) para un sistema de gestión de pedidos de una tienda. El modelo permite administrar productos, categorías, clientes, direcciones, pedidos, detalles de pedidos y empresas transportistas.

## Entidades y atributos

### 1. Productos

Representa los productos disponibles para la venta.

* `sku`: identificador del producto.
* `id_categoria`: identificador de la categoría.
* `nombre`: nombre del producto.
* `descripcion`: descripción del producto.
* `stock`: cantidad disponible en inventario.

### 2. Categoria

Representa las categorías utilizadas para clasificar los productos.

* `id_categoria`: identificador de la categoría.
* `nombre`: nombre de la categoría.
* `descripcion`: descripción de la categoría.

### 3. Clientes

Representa a los clientes registrados en el sistema.

* `id_cliente`: identificador del cliente.
* `correo`: correo electrónico.
* `contraseña`: contraseña de acceso.
* `nombre`: nombre del cliente.
* `apellido`: apellido del cliente.

### 4. Direccion

Almacena las direcciones asociadas a los clientes.

* `id_direccion`: identificador de la dirección.
* `id_cliente`: identificador del cliente.
* `ciudad`: ciudad de residencia.
* `calle`: calle de la dirección.
* `numero`: número de la dirección.
* `codigo_postal`: código postal.

### 5. Pedidos

Registra las compras realizadas por los clientes.

* `id_pedido`: identificador del pedido.
* `id_clientes`: identificador del cliente.
* `id_direccion`: identificador de la dirección de entrega.
* `fecha`: fecha del pedido.
* `hora`: hora del pedido.
* `estado`: estado actual del pedido.
* `monto_total`: importe total de la compra.
* `numero_guia`: número de seguimiento del envío.

### 6. detalle_pedido

Representa los productos incluidos en cada pedido.

* `nro_pedido`: número del pedido.
* `sku`: identificador del producto.
* `cantidad`: cantidad solicitada.
* `precio_unitario`: precio por unidad del producto.

### 7. Transportista

Representa a las empresas encargadas de realizar las entregas.

* `cuit`: CUIT del transportista.
* `razon_social`: nombre legal de la empresa.
* `telefono`: número de contacto.
* `numero_pedido`: número del pedido asociado.

## Relaciones y cardinalidades

* **Categoria – Productos (Clasifica):** una categoría puede incluir varios productos y cada producto pertenece a una categoría.
* **Productos – detalle_pedido (Incluido):** permite registrar los productos incluidos en los pedidos.
* **Pedidos – detalle_pedido (Contiene):** un pedido puede contener varios detalles de productos.
* **Clientes – Direccion (Registra):** un cliente puede registrar varias direcciones.
* **Direccion – Pedidos (Tiene):** una dirección puede utilizarse en varios pedidos.
* **Clientes – Pedidos:** un cliente puede realizar varios pedidos.
* **Pedidos – Transportista (Despacha):** permite asociar los pedidos con los transportistas encargados de entregarlos.

## Objetivo

Diseñar una base de datos que permita gestionar el proceso de compra y entrega de productos, controlar el inventario, registrar clientes y direcciones, administrar pedidos y sus detalles, y realizar el seguimiento de los envíos.
