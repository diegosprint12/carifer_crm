# ESPECIFICACIÓN DE REQUISITOS DE SOFTWARE
## **Proyecto:** Carifer-CRM
---
### 1. INTRODUCCIÓN
  ### 1.1 PROPÓSITO
  Definir los requisitos para el software de Carifer CRM
  ### 1.2 ALCANCE 
  Abarca el control de inventario, cotizaciones, roles, etc. Mejorando ventas y stock.
  ### 1.3 VISIÓN GENERAL
  * **1.3.1 Perspectiva:** Sistema desktop con DB local.
	* **1.3.2 Usuarios:** jefes, empleados. 
  ### 1.4 PERSONAL INVOLUCRADO

|**Nombre**|Diego Andrés Salazar|
|---|---| 
|**Rol**|Analista y Desarrollador de Software|
|**Categoría**|Profesional	Aprendiz ADSO - SENA|
|**Responsabilidad**|Análisis, Diseño y Desarrollo|

### 2. REFERENCIAS
  * Estándar IEEE29148:2018
  * Casos de Uso (Documento Interno)

### 3. REQUISITOS ESPECÍFICOS
  * 3.1 INTERFACES DE USUARIO
			- Pendiente
	* 3.2 INTERFACES DE HARDWARE
			- Pendiente
	* 3.3 INTERFACES DE SOFTWARE
			- Pendiente

### 3.4 REQUISITOS FUNCIONALES
				
|**Número de requisito**|`RF-01`|
|---|---|
|**Nombre de requisito**|Asignar Roles a Usuarios|
|**Tipo**|🔲Requisito 🔳Restricción|
|**Fuente del requisito**|Supervisión – Caso de Uso|
|**Prioridad del requisito**|🔲Alta/Esencial 🔳Media/Deseado 🔳Baja/Opcional|
|**Descripción**|El sistema deberá permitir al superadministrador asignar o modificar el rol de un usuario registrado para controlar sus permisos de acceso|
		
|**Número de requisito**|`RF-02`|
|---|---|
|**Nombre de requisito**|Login/Registro|
|**Tipo**|🔲Requisito 🔳Restricción|
|**Fuente del requisito**|Creación/Supervisión – Casos de Uso|
|**Prioridad del requisito**|🔲Alta/Esencial 🔳Media/Deseado	🔳Baja/ Opcional|
|**Descripción**|El sistema deberá permitir el logueo/registro de los usuarios con las credenciales suministradas/propuestas para ejercer el rol correspondiente|

|**Número de requisito**|`RF-03`|
|---|---|
|**Nombre de requisito**|CRUD para Producto|
|**Tipo**|🔲Requisito 🔳Restricción|
|**Fuente del requisito**|Creación/Supervisión – Casos de Uso|
|**Prioridad del requisito**|🔲Alta/Esencial	🔳Media/Deseado	 🔲Baja/ Opcional
|**Descripción**|El sistema deberá permitir el CRUD de un producto que hacer parte del inventario|

|**Número de requisito**|`RF-04`|
|---|---|
|**Nombre de requisito**|CRUD para Cotización|
|**Tipo**|🔲Requisito 🔳Restricción|
|**Fuente del requisito**|Creación/Supervisión – Casos de Uso|
|**Prioridad del requisito**|🔲Alta/Esencial 🔳Media/Deseado	 🔳Baja/ Opcional|
|**Descripción**|El sistema deberá permitir el CRUD de una cotización, para su gestión, supervisión y demás|
		
|**Número de requisito**|`RF-05`|
|---|---|
|**Nombre de requisito**|Auditoría|
|**Tipo**|🔲Requisito 🔳Restricción|
|**Fuente del requisito**|Creación/Supervisión – Casos de Uso|
|**Prioridad del requisito**|🔳Alta/Esencial 🔲Media/Deseado	🔳Baja/ Opcional
|**Descripción**|El sistema deberá permitir la visualización de un historial de las acciones llevadas a cabo en cada Producto y Cotización. Si se elimina alguno, se guardarán logs locales|


### 3.5 REQUISITOS NO FUNCIONALES
		
### 3.5.1 RENDIMIENTO Y EFICIENCIA
|**Requisito**|**Descripción**|
|---|---|
|`RNF-01`|El sistema deberá cargar todos los datos de productos y cotizaciones en menos de 1 seg|
		
### 3.5.2 SEGURIDAD Y PRIVACIDAD
|**Requisito**|**Descripción**|
|---|---|
|`RNF-02`|Las contraseñas de los usuarios deben ser almacenadas utilizando algoritmo mínimo Bcrypt, evitar algoritmos desfasados|
|`RNF-03`|El sistema deberá aplicar mínimo el OWASP10|

### 3.5.3 FIABILIDAD Y DISPONIBILIDAD
|**Requisito**|**Descripción**|
|---|---|		
|`RNF-04`|El sistema deberá mantener disponibilidad del 100% desde el minuto 1|
|`RNF-05`|Las actualizaciones nunca deberán afectar la integridad de los datos|
		
### 3.5.4 USABILIDAD
|**Requisito**|**Descripción**|
|---|---|		
|`RNF-06`|Un usuario nuevo deberá ser capaz de registrar productos y crear cotizaciones en 4 minutos sin supervisión|
		
### 3.5.6 MANTENIBILIDAD Y PORTABILIDAD
|**Requisito**|**Descripción**|
|---|---|		
|`RNF-07`|El software deberá ejecutarse correctamente en el equipo desde el primer momento de la instalación, podrá ejecutarse desde USB, será portable| 
		
### 3.5.7 CASOS DE USO
DIAGRAMA DE CASO DE USO
<img width="507" height="557" alt="DIAGRAMA DE CASO DE USO" src="https://github.com/user-attachments/assets/cc3403fa-fcd5-4f0f-9cec-6c743504bb5d" />
  
  * Las flechas unidireccionales indican pertenencia única.
  * Las flechas sin dirección indican pertenencia doble/múltiple.
	
  FUNCIONALIDADES
  * CREAR INVENTARIO
  * ELIMINAR INVENTARIO
  * REVISAR INVENTARIO
  * CREAR COTIZACIÓN
  * SUPERVISAR COTIZACIONES
	
	ACTORES
  * Administrador
  * Empleado
	
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
		
### 3.5.8 HISTORIAS DE USUARIO

`HU-01`: TÍTULO: ASIGNACIÓN DE ROLES
**Como** superadministrador, 
**Quiero** asignar/cambiar el rol a un usuario del sistema, 
**Para** delegar la gestión operativa del software sin arriesgar a modificarlo o perder el control total.

`HU-02`: TÍTULO: LOGIN Y REGISTRO
**Como** empleado/jefe 
**Quiero** registrarme/loguearme con las credenciales suministradas/propuestas en el formulario 
**Para** acceder al software.

`HU-03`: TÍTULO: CRUD PRODUCTO
**Como** administrador 
**Quiero** registrar un producto, verlo, actualizarlo y borrarlo 
**Para** gestión de inventario como función del software.

`HU-04`: TÍTULO: CRUD COTIZACIÓN
**Como** administrador/empleado 
**Quiero** registrar una cotización, verla y actualizarla o borrarla si no sirve 
**Para** llevar control y supervisión de esta función del software.

`HU-05`: TÍTULO: AUDITORÍA DE ACCIONES
**Como** administrador/empleado 
**Quiero** visualizar los registros de acciones llevadas a cabo en una cotización y en un producto 
**Para** auditar los eventos del software.

