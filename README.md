# Automatización QA - SauceDemo

Este proyecto es una práctica de automatización de pruebas con Python, Selenium y Pytest. Uso la página [SauceDemo](https://www.saucedemo.com/) para practicar el inicio de sesión, la revisión de productos y el uso del carrito.

Por ahora tengo tres pruebas. La idea es seguir mejorando el código y agregar más casos mientras aprendo.

## Herramientas utilizadas

- Python: para escribir el código.
- Selenium: para interactuar con la página desde Firefox.
- Pytest: para ejecutar las pruebas y comprobar los resultados.
- Pytest HTML: para generar un reporte que se puede abrir en el navegador.

## Archivos del proyecto

| Archivo o carpeta | Descripción |
| --- | --- |
| `tests/test_login.py` | Prueba el inicio de sesión con un usuario válido. |
| `tests/test_inventory.py` | Comprueba datos y elementos de la página de productos. |
| `tests/test_cart.py` | Agrega un producto al carrito y verifica que aparezca. |
| `pytest.ini` | Configura la búsqueda de pruebas y la generación del reporte. |
| `reports/reporte.html` | Reporte de la ejecución de las pruebas. |
| `README.md` | Presentación del proyecto. |
| `guia.md` | Instrucciones para preparar y ejecutar el proyecto. |

## Instalación

Primero hay que tener Python y Firefox instalados, además de conexión a internet. Python se instala por separado; no se instala con `pip`.

Desde una terminal dentro de la carpeta del proyecto, instalar las librerías:

```bash
python -m pip install selenium pytest pytest-html
```

## Ejecución

Desde la carpeta donde está `pytest.ini`:

```bash
python -m pytest
```

Al terminar, abrir `reports/reporte.html` en el navegador. El reporte se actualiza con cada ejecución.

## Casos de prueba

### Inicio de sesión

En `test_login.py` se ingresa con el usuario de demostración `standard_user` y la contraseña `secret_sauce`. Después se comprueba que:

- La dirección contiene `/inventory.html`.
- El logotipo muestra `Swag Labs`.
- El título de la sección muestra `Products`.

Esta prueba usa una espera implícita de 10 segundos y esperas explícitas para localizar los campos y esperar que el botón de login se pueda pulsar.

### Página de productos

En `test_inventory.py` se inicia sesión y se verifica que:

- El título del navegador sea `Swag Labs`.
- La lista tenga al menos un producto.
- El primer producto sea `Sauce Labs Backpack` y su precio sea `$29.99`.
- El botón del menú y el filtro estén visibles.

### Carrito

En `test_cart.py` se inicia sesión, se guarda el nombre del primer producto y se agrega al carrito. Después se comprueba que el contador muestre `1` y que el nombre del producto dentro del carrito coincida con el que se agregó.

## Resultado del reporte incluido

El reporte del 7 de octubre de 2026 muestra las tres pruebas aprobadas. Ese resultado corresponde a la ejecución guardada en el archivo y puede cambiar en futuras ejecuciones.

## Mejoras pendientes

- Agregar casos de login con datos incorrectos.
- Probar quitar productos del carrito y completar una compra.
- Probar las acciones del menú y del filtro; por ahora solo verifico que estén visibles.
- Revisar las esperas y aplicarlas donde hagan falta en las otras pruebas.
- Evitar repetir el inicio de sesión y la creación del navegador.
- Cambiar el nombre de la función de la prueba del carrito a uno más claro, como `test_agregar_producto_al_carrito`.
