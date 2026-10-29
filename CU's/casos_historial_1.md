# CASO DE USO 1.0
<img width="507" height="557" alt="DIAGRAMA DE CASO DE USO" src="https://github.com/user-attachments/assets/a46c26cc-8df1-46fc-aa72-fae0eea4be99"/><br>
*Original, susceptible a cambios, simple. Lo pensé para usarlo de forma general para establecer casos de uso.*
## CASOS DE USO DEL DIAGRAMA
### CASO DE USO 1: Crear Inventario

| Propiedad | Detalle |
|---|---|
| **ID / Nombre** | `CU-01`: Crear Inventario |
| **Descripción** | Describe paso a paso el proceso del personal encargado de crear un nuevo producto en el inventario. |
| **Actores** | Administrador |
| **Precondición** | Estar autenticado como Administrador y tener listos los datos del producto a añadir. |
| **Postcondición** | El producto se encuentra registrado, así que ya podrá presentar historial de modificaciones: cantidades, fuera de stock, en que 	ventas ha estado envuelto, etc. |

**Secuencia Normal:**

1. El administrador ingresa al sistema para registrar los nuevos productos.
2. El sistema carga el formulario de registro (Nombre, Código, Cantidad, Precio).
3. El administrador completa el formulario y confirma la inserción en el sistema.
4. El sistema almacena los datos, despliega el nuevo producto en pantalla y lo hace visible para los demás usuarios.
5. El sistema genera un registro de historial visible únicamente por administradores.

**Excepciones:**

* **1.a. Código duplicado:** El sistema es *case insensitive*. Los nombres pueden repetirse, pero el código único (generado automáticamente por la base de datos) no. Si existe duplicado, se aborta la inserción.
* **1.b. Cancelación:** Si el administrador cancela el registro, finaliza el caso de uso.

---

### CASO DE USO 2: Eliminar Inventario

| Propiedad | Detalle |
|---|---|
| **ID / Nombre** | `CU-02`: Eliminar Inventario |
| **Descripción** | Describe paso a paso el proceso de eliminación de un producto del inventario. |
| **Actores** | Administrador |
| **Precondición** | Estar autenticado en el sistema como Administrador. |
| **Postcondición** | El producto deja de mostrarse en la interfaz y en la base de datos. Sus registros y acciones previas quedan archivados en un log. |

**Secuencia Normal:**

1. El administrador ingresa a la sección de inventario para eliminar un producto.
2. El sistema carga la lista de productos; el administrador selecciona el botón de acción de eliminación.
3. El sistema muestra un mensaje de advertencia confirmando la acción.
4. El sistema guarda un registro (log) con todo el historial del producto a eliminar.
5. El sistema confirma la eliminación exitosa en pantalla.

**Excepciones:**

* **1.a. Cancelación:** El administrador cancela la alerta de eliminación; finaliza el caso de uso.

---

### CASO DE USO 3: Revisar Inventario

| Propiedad | Detalle |
|---|---|
| **ID / Nombre** | `CU-03`: Revisar Inventario |
| **Descripción** | Describe la consulta general del inventario por parte del personal. |
| **Actores** | Empleado, Administrador |
| **Precondición** | Estar autenticado en el sistema como Empleado o Administrador. |
| **Postcondición** | El usuario obtiene la información detallada del inventario que requería. |

**Secuencia Normal:**

1. El usuario ingresa al sistema.
2. El sistema carga todos los productos registrados.
3. El usuario visualiza los datos detallados: cantidad, fecha de inscripción, ventas/cotizaciones asociadas o estado de stock.
4. El usuario finaliza la consulta o cierra la sesión.

**Excepciones:**

* **1.a. Credenciales erróneas:** Los datos de ingreso son incorrectos; no se carga el inventario.
* **1.b. Sesión finalizada:** La sesión se destruye antes de completar la lectura; finaliza el caso de uso.

---

### CASO DE USO 4: Crear Cotización

| Propiedad | Detalle |
|---|---|
| **ID / Nombre** | `CU-04`: Crear Cotización |
| **Descripción** | Describe paso a paso la generación de cotizaciones en el software. |
| **Actores** | Empleado, Administrador |
| **Precondición** | Estar autenticado como Empleado o Administrador. |
| **Postcondición** | La cotización queda registrada en el sistema y lista para ser revisada/editada antes de su confirmación. |

**Secuencia Normal:**

1. El usuario ingresa al módulo de creación de cotizaciones.
2. El sistema presenta el formulario de entrada: Nombre del Cliente, Producto, Cantidad, Precio, Dirección y Teléfono.
3. El usuario completa el formulario y envía la información.
4. El sistema almacena los datos y carga la nueva cotización en el listado general.
5. El sistema genera el historial de la cotización para rastrear futuras modificaciones.

**Excepciones:**

* **1.a. Código duplicado:** El código de cotización es autogenerado. En caso de colisión de ID, el registro falla.
* **1.b. Cancelación:** El usuario cancela el llenado del formulario; se termina el caso de uso.

---

### CASO DE USO 5: Supervisar Cotizaciones

| Propiedad | Detalle |
|---|---|
| **ID / Nombre** | `CU-05`: Supervisar Cotizaciones |
| **Descripción** | Proceso mediante el cual el personal autorizado audita, edita, confirma o elimina cotizaciones. |
| **Actores** | Empleado, Administrador |
| **Precondición** | Estar autenticado como Empleado o Administrador. |
| **Postcondición** | Se aplican y persisten los cambios sobre las cotizaciones seleccionadas. |

**Secuencia Normal:**

1. El usuario ingresa al módulo de supervisión.
2. El sistema carga las cotizaciones activas pendientes por revisión.
3. El usuario selecciona una acción: editar, confirmar o eliminar una cotización.
4. El sistema despliega un cuadro modal de advertencia para confirmar la acción.
5. El usuario confirma la operación y el sistema muestra un aviso de validación del cambio.

**Excepciones:**

* **1.a. Credenciales erróneas:** Error de autenticación al intentar acceder al módulo.
* **1.b. Cierre de sesión:** El usuario destruye la sesión antes de confirmar la acción; finaliza el caso de uso.
