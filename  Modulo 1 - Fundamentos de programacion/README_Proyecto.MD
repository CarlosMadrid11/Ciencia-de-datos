# 📚 Sistema de Gestión para Biblioteca Escolar

Prototipo desarrollado en Python que funciona completamente en consola. Permite registrar libros, gestionar usuarios y controlar préstamos y devoluciones sin necesidad de bases de datos ni instalaciones extra.

---

## 🗂 Contenido del notebook

El archivo `SistemaParaBiblioteca_Final.ipynb` está organizado en **5 secciones** que deben ejecutarse en orden:

| # | Sección | ¿Qué contiene? |
|---|---------|----------------|
| 1 | Importaciones | Carga la librería `date` para registrar fechas automáticamente |
| 2 | Clases (POO) | Define `Libro`, `Usuario` y `Biblioteca` con toda la lógica del sistema |
| 3 | Funciones utilitarias | Funciones de apoyo para la consola: menú, validaciones, mensajes |
| 4 | Función `main()` | El punto de entrada que inicia la interfaz interactiva |
| 5 | Pruebas automáticas | Demuestra todas las funcionalidades sin necesidad de escribir nada |

---

## ▶️ Cómo ejecutar el proyecto

> **Importante:** las celdas deben ejecutarse **en orden de arriba hacia abajo**. Si se salta alguna o se ejecuta en desorden, el programa marcará error porque las clases y funciones aún no estarán cargadas en memoria.

### Paso 1 — Abrir el archivo
Abre `SistemaParaBiblioteca_Final.ipynb` en **Jupyter Notebook** o **VS Code** con la extensión de Jupyter instalada.

### Paso 2 — Ejecutar todas las celdas
Ve al menú superior y selecciona:

```
Kernel → Restart & Run All
```

Esto reinicia el entorno y ejecuta todas las celdas desde cero, garantizando que todo funcione correctamente.

### Paso 3 — Ver los resultados
Al ejecutar, verás automáticamente la **demostración completa** del sistema con datos de prueba. Cubre todos los escenarios: libros, usuarios, préstamos, devoluciones, errores y reportes.

<!-- 💡 Aquí puedes insertar una captura de pantalla de la salida de las pruebas -->
<!-- ![Demostración del sistema](imagenes/demo_pruebas.png) -->

---

## 🖥️ Activar la interfaz interactiva

La **última celda** del notebook contiene esta línea comentada:

```python
# main()
```

Para activar el menú interactivo en consola, simplemente **quita el `#`** para que quede así:

```python
main()
```

Luego ejecuta esa celda. Aparecerá el menú principal y podrás navegar con el teclado escribiendo el número de la opción deseada.

> **Nota:** El menú interactivo funciona mejor desde una **terminal** (ejecutando el archivo como `.py`), ya que Jupyter a veces presenta limitaciones con la función `input()`. Las pruebas automáticas de la celda anterior son la forma recomendada de demostrar el sistema dentro del notebook.

<!-- 💡 Aquí puedes insertar una captura del menú en consola -->
<!-- ![Menú principal](imagenes/menu_principal.png) -->

---

## ⚙️ Funcionalidades disponibles

### 📖 Gestión de libros
- Agregar libros al catálogo con ISBN, título, autor y número de ejemplares.
- Consultar cuántos ejemplares están disponibles en este momento.
- Buscar libros por título o autor (la búsqueda no distingue mayúsculas).
- Ver todos los libros de un autor específico.

### 👤 Gestión de usuarios
- Registrar usuarios con un ID único y su nombre.
- Ver el listado completo de usuarios y cuántos préstamos activos tiene cada uno.

### 🔄 Préstamos y devoluciones
- Prestar un libro a un usuario registrando la fecha automáticamente.
- Devolver un libro y liberar el ejemplar para otros usuarios.
- Ver todos los préstamos que están activos en este momento.

<!-- 💡 Aquí puedes insertar una captura del flujo de préstamo -->
<!-- ![Flujo de préstamo](imagenes/prestamo.png) -->

### 📊 Reportes
- **Top 3 libros más prestados:** muestra los libros más solicitados en la historia del sistema.

---

## 🛡️ Reglas del sistema

El sistema aplica automáticamente las siguientes restricciones:

- No se puede prestar un libro si no hay ejemplares disponibles.
- Un usuario no puede tener el mismo libro prestado dos veces al mismo tiempo.
- Cada usuario tiene un **límite máximo de 3 préstamos activos** simultáneos.
- No se pueden registrar dos libros con el mismo ISBN ni dos usuarios con el mismo ID.

Si alguna de estas reglas se incumple, el sistema muestra un mensaje de advertencia claro y **no interrumpe el programa**.

---

## 🧰 Requisitos técnicos

- Python **3.10 o superior** (para compatibilidad completa)
- Jupyter Notebook o VS Code con extensión Jupyter
- No requiere instalar librerías externas

---

## 👥 Equipo de desarrollo

 ## Alumnos: 
 ## GUTIERREZ CHAVEZ DENZEL ARTURO
 ## QUIÑONEZ MADRID JUAN CARLOS
