# Automatización QA - SauceDemo

Este es un proyecto de práctica para aprender a automatizar pruebas de una página web con Python. Uso [SauceDemo](https://www.saucedemo.com/), una página de ejemplo, para probar el inicio de sesión y revisar algunos elementos de la lista de productos.

Por ahora el proyecto tiene dos pruebas. La idea es seguir agregando casos a medida que aprenda más sobre automatización.

## Herramientas que uso

- Python para escribir las pruebas.
- Selenium para abrir Firefox e interactuar con la página.
- Pytest para ejecutar las pruebas y comprobar los resultados.
- Pytest HTML para generar el reporte.

## Archivos del proyecto

| Archivo o carpeta | Para qué sirve |
| --- | --- |
| `tests/test_login.py` | Prueba el inicio de sesión con datos válidos. |
| `tests/test_inventory.py` | Revisa la página y la lista de productos. |
| `pytest.ini` | Configura cómo se ejecutan las pruebas y dónde se guarda el reporte. |
| `reports/` | Carpeta donde se genera el reporte HTML. |
| `README.md` | Resumen del proyecto. |
| `guia.md` | Pasos para instalar y ejecutar el proyecto. |

Los archivos de prueba también pueden estar en la carpeta principal: Pytest los encuentra por sus nombres `test_*.py`.

## Instalación

Se necesita Python, pytest, Firefox y conexión a internet. Desde una terminal, dentro de la carpeta del proyecto, instalar:

```terminal
pip install python
```

```terminal
pip install selenium
```

```terminal
pip install pytest
```

```terminal
pip install pytest-html
```

## Ejecutar las pruebas

Desde la carpeta donde está `pytest.ini`:

```terminal
pytest
```

Al terminar, abrir `reports/reporte.html` en el navegador para ver los resultados. El archivo se vuelve a generar cada vez que se ejecutan las pruebas.

## Qué comprueban las pruebas

### Inicio de sesión

- Ingresa con el usuario de prueba `standard_user` y la contraseña `secret_sauce`.
- Comprueba que la dirección contiene `/inventory.html`.
- Revisa que aparezcan los textos `Swag Labs` y `Products`.

### Página de productos

- Inicia sesión y comprueba el título `Swag Labs`.
- Verifica que haya productos en la lista.
- Revisa que el primer producto sea `Sauce Labs Backpack` y cueste `$29.99`.
- Comprueba que el botón del menú y el filtro estén visibles.

## Resultado del reporte compartido

El reporte incluido muestra las dos pruebas aprobadas en una ejecución de aproximadamente 18 segundos. Es el resultado de esa ejecución; puede cambiar si cambia la página o el entorno.

## Cosas que quiero mejorar

- Agregar pruebas de usuario o contraseña incorrectos.
- Probar agregar y quitar productos del carrito.
- Usar esperas explícitas para que las pruebas sean menos sensibles al tiempo de carga.
- Evitar repetir el código de inicio de sesión y de apertura del navegador.

El carrito todavía no está probado. El menú y el filtro solo se revisan para comprobar que se ven, sin probar sus acciones.