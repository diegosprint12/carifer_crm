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
## GESTIÓN DE USUARIOS Y ROLES
### CASO DE USO 1: Registrar Administrador
| Propiedad | Detalle |
|---|---|
| **ID / Nombre** | `CU-01`: Registrar Administrador |
| **Descripción** | Describe paso a paso el proceso del rol de **Superadministrador** para crear usuarios **Administradores** |
| **Actores** | Superadministrador |
| **Precondición** | Estar autenticado como Superadministrador y tener listos los datos del administrador a registrar. |
| **Postcondición** | El administrador podrá utilizar sus credenciales para loguearse |
<img width="600" height="600" alt="CU01" src="https://github.com/user-attachments/assets/931297d5-0578-41a9-9fa1-b2eb9e86c12a" />


**Secuencia Normal:**

1. El Superadministrador ingresa al panel de gestión de usuarios y roles.
2. Selecciona el registro de administrador.
3. El Superadministrador completa el formulario de registro.
4. El sistema almacena los datos, y aparecerá en pantalla el nuevo usuario de administrador.

**Excepciones:**

* **1.a. Nombre duplicado:** Los nombres deben ser diferentes, si está duplicado, el registro fallará.
* **1.b. Cancelación:** Si el superadministrador cancela el registro, finaliza el caso de uso.

---
### CASO DE USO 2: Registrar Empleado
| Propiedad | Detalle |
|---|---|
| **ID / Nombre** | `CU-02`: Registrar Empleado |
| **Descripción** | Describe paso a paso el proceso de creación de usuarios tipo **Empleados** |
| **Actores** | Superadministrador, Administrador |
| **Precondición** | Estar autenticado como Superadministrador/Administrador y tener listos los datos del empleado a registrar. |
| **Postcondición** | El Empleado podrá utilizar sus credenciales para loguearse |
<img width="600" height="600" alt="CU03" src="https://github.com/user-attachments/assets/eac2e514-fe43-4d59-9d68-3203436261cf" />


**Secuencia Normal:**

1. El Superadministrador/Administrador ingresa al panel de gestión de usuarios y roles.
2. Selecciona el registro de Empleado.
3. El Superadministrador/Administrador completa el formulario de registro.
4. El sistema almacena los datos, y aparecerá en pantalla el nuevo usuario tipo Empleado.

**Excepciones:**

* **1.a. Nombre duplicado:** Los nombres deben ser diferentes, si está duplicado, el registro fallará.
* **1.b. Cancelación:** Si el superadministrador cancela el registro, finaliza el caso de uso.
---
### CASO DE USO 3: Modificación de Roles
| Propiedad | Detalle |
|---|---|
| **ID / Nombre** | `CU-03`: Modificación de Roles |
| **Descripción** | Describe paso a paso el proceso de creación de usuarios tipo **Empleados** |
| **Actores** | Superadministrador, Administrador |
| **Precondición** | Estar autenticado como Superadministrador. |
| **Postcondición** | El usuario percibirá un cambio de rol |
<img width="600" height="600" alt="CU03" src="https://github.com/user-attachments/assets/5b2b6190-1c95-4b94-890f-30d19d83b594" />

**Secuencia Normal:**

1. El Superadministrador ingresa al panel de gestión de usuarios y roles.
2. Selecciona un usuario para modificar.
3. El Superadministrador cambia el rol según convenga.
4. El sistema cargará el nuevo rol del usuario.

**Excepciones:**

* **1.a. Cancelación:** Si el superadministrador cancela la modificación, finaliza el caso de uso.
---
## LOGIN Y AUTENTICACIÓN
### CASO DE USO 1: Iniciar Sesión
| Propiedad | Detalle |
|---|---|
| **ID / Nombre** | `CU-01`: Iniciar Sesión |
| **Descripción** | Describe paso a paso el proceso de inicio de sesión de los usuarios |
| **Actores** | Superadministrador, Administrador, Empleado |
| **Precondición** | No haber iniciado sesión y tener credenciales de usuario |
| **Postcondición** | El usuario accederá al software bajo su rol |
<img width="600" height="600" alt="CU04" src="https://github.com/user-attachments/assets/fac54689-4843-4595-84c3-343dd527fa21" />

**Secuencia Normal:**

1. El Usuario ingresa al software, aparecerá el formulario de autenticación.
2. El usuario rellena el formulario.
3. El sistema valida las credenciales y permite el ingreso.
4. El Usuario está dentro del software bajo su rol.

**Excepciones:**

* **1.a Campos vacíos:** Si el usuario no rellena el formulario, no podrá entrar.
---
### CASO DE USO 2: Cerrar Sesión
| Propiedad | Detalle |
|---|---|
| **ID / Nombre** | `CU-02`: Cerrar Sesión |
| **Descripción** | Describe paso a paso el proceso de cierre de sesión de los usuarios |
| **Actores** | Superadministrador, Administrador, Empleado |
| **Precondición** | Haber iniciado sesión como algún tipo de usuario |
| **Postcondición** | El usuario destruirá la sesión de forma segura |
<img width="600" height="600" alt="600" src="https://github.com/user-attachments/assets/2c367e1d-47b1-4f26-be55-72cce585da24" />


**Secuencia Normal:**

1. El Usuario tiene sesión activa y se dirige hacia el panel de perfil.
2. El Usuario selecciona cerrar sesión.
3. El sistema destruye la sesión.
4. El Usuario retorna al formulario de inicio de sesión.

**Excepciones:**

* **1.a Cancelación:** El usuario cancela la acción en el modal de confirmación.
---
## MÓDULO INVENTARIO Y COTIZACIONES
### CASO DE USO 1: Crear Inventario

| Propiedad | Detalle |
|---|---|
| **ID / Nombre** | `CU-01`: Crear Inventario |
| **Descripción** | Describe paso a paso el proceso del personal encargado de crear un nuevo producto en el inventario. |
| **Actores** | Administrador |
| **Precondición** | Estar autenticado como Administrador y tener listos los datos del producto a añadir. |
| **Postcondición** | El producto se encuentra registrado, así que ya podrá presentar historial de modificaciones: cantidades, si está fuera de stock, en qué ventas ha estado envuelto, etc. |
<img width="765" height="611" alt="CU01" src="https://github.com/user-attachments/assets/cb949f0f-e97b-43a4-b872-65797982de93" />




**Secuencia Normal:**

1. El administrador ingresa al sistema para registrar los nuevos productos.
2. El sistema carga el formulario de registro (Nombre, Código, Cantidad, Precio).
3. El administrador completa el formulario y confirma la inserción en el sistema.
4. El sistema almacena los datos, valida el ID, despliega el nuevo producto en pantalla y lo hace visible para los demás usuarios.
5. El sistema genera un registro de las acciones, iniciando siempre por la creación.

**Excepciones:**

* **1.a. Código duplicado:** El sistema es *case insensitive*. Los nombres pueden repetirse, pero el código único (generado automáticamente por la base de datos) no. Si existe duplicado, se aborta la inserción.
* **1.b. Cancelación:** Si el administrador cancela el registro, finaliza el caso de uso.
---

### CASO DE USO 2: Editar Inventario

| Propiedad | Detalle |
|---|---|
| **ID / Nombre** | `CU-02`: Crear Inventario |
| **Descripción** | Describe paso a paso el proceso del personal encargado de editar un producto existente en el inventario. |
| **Actores** | Administrador, Empleado |
| **Precondición** | Estar autenticado como Administrador/Empleado, el producto debe estar registrado/creado. |
| **Postcondición** | El producto se habrá editado y podrá visualizar los cambios en la tarjeta del producto |
<img width="836" height="864" alt="CU02" src="https://github.com/user-attachments/assets/e4a1e4de-a3c3-43e9-aba2-8b25a153fda9" />




**Secuencia Normal:**

1. El administrador/empleado ingresa al sistema para editar el producto.
2. El sistema carga el formulario de registro con algunos campos bloqueados y otros modificables.
3. El administrador cambia campos en el formulario y confirma la edición en el sistema.
4. El sistema almacena los nuevos datos, valida el ID, despliega el producto editado en pantalla y lo hace visible para los demás usuarios.
5. El sistema genera un registro de las acciones, en este caso fue editado.

**Excepciones:**

* **1.a. ID inexistente:** Si se está editando un producto fantasma que no ha sido refrescado. 
* **1.b. Cancelación:** Si el administrador cancela la edición, finaliza el caso de uso.

---

### CASO DE USO 3: Eliminar Inventario

| Propiedad | Detalle |
|---|---|
| **ID / Nombre** | `CU-03`: Eliminar Inventario |
| **Descripción** | Describe paso a paso el proceso de eliminación de un producto del inventario. |
| **Actores** | Administrador |
| **Precondición** | Estar autenticado en el sistema como Administrador. |
| **Postcondición** | El producto deja de mostrarse en la interfaz y en la base de datos. Sus registros y acciones previas quedan archivados en un log. |
<img width="696" height="542" alt="CU02" src="https://github.com/user-attachments/assets/c7e067e1-97d9-4dc6-9fab-9672f25173d0" />



**Secuencia Normal:**

1. El administrador ingresa a la sección de inventario para eliminar un producto.
2. El sistema carga la lista de productos; el administrador selecciona el botón de acción de eliminación.
3. El sistema muestra un mensaje de advertencia confirmando la acción.
4. El sistema guarda un registro (log) con todo el historial del producto a eliminar.
5. El sistema confirma la eliminación exitosa en pantalla.

**Excepciones:**

* **1.a. Cancelación:** El administrador cancela la alerta de eliminación; finaliza el caso de uso.
* **1.b. ID inexistente:** El producto ya ha sido eliminado, pero no se ha refrescado el panel. 

---

### CASO DE USO 4: Revisar Inventario

| Propiedad | Detalle |
|---|---|
| **ID / Nombre** | `CU-04`: Revisar Inventario |
| **Descripción** | Describe la consulta general del inventario por parte del personal. |
| **Actores** | Empleado, Administrador |
| **Precondición** | Estar autenticado en el sistema como Empleado o Administrador. |
| **Postcondición** | El usuario obtiene la información detallada del inventario que requería. |
<img width="844" height="878" alt="CU03" src="https://github.com/user-attachments/assets/3e0ea9d3-81e9-4e5c-a736-b0a381220a39" />


**Secuencia Normal:**

1. El usuario ingresa al sistema.
2. El sistema carga todos los productos registrados.
3. El usuario visualiza los datos detallados: cantidad, fecha de inscripción, ventas/cotizaciones asociadas o estado de stock.
4. El usuario finaliza la consulta o cierra la sesión.

**Excepciones:**

* **1.a. Credenciales erróneas:** Los datos de ingreso son incorrectos; no se carga el inventario.
* **1.b. Sesión finalizada:** La sesión se destruye antes de completar la lectura; finaliza el caso de uso.

---

### CASO DE USO 5: Crear Cotización

| Propiedad | Detalle |
|---|---|
| **ID / Nombre** | `CU-05`: Crear Cotización |
| **Descripción** | Describe paso a paso la generación de cotizaciones en el software. |
| **Actores** | Empleado, Administrador |
| **Precondición** | Estar autenticado como Empleado o Administrador. |
| **Postcondición** | La cotización queda registrada en el sistema con estado inicial **Pendiente**, lista para ser revisada/editada antes de su confirmación. |
<img width="857" height="846" alt="CU04" src="https://github.com/user-attachments/assets/5e440d28-d265-4099-b892-4c728c385221" />


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

### CASO DE USO 6: Supervisar Cotizaciones

| Propiedad | Detalle |
|---|---|
| **ID / Nombre** | `CU-06`: Supervisar Cotizaciones |
| **Descripción** | Proceso mediante el cual el personal autorizado audita y revisa cotizaciones. |
| **Actores** | Empleado, Administrador |
| **Precondición** | Estar autenticado como Empleado o Administrador. |
| **Postcondición** | Se obtuvieron los datos del propósito de revisión |
<img width="831" height="844" alt="CU05" src="https://github.com/user-attachments/assets/94ada771-18e2-4720-b627-a844bded05ed" />

**Secuencia Normal:**

1. El usuario ingresa al módulo de cotizaciones.
2. El sistema carga las cotizaciones que no estén archivadas.
3. El usuario selecciona y expande cualquiera de las cotizaciones con **"Ver más detalles"**.
4. El sistema despliega la cotización completa.
5. El usuario revisa los datos y estado de la cotización.

**Excepciones:**

* **1.a. Credenciales erróneas:** Error de autenticación al intentar acceder al módulo.
* **1.b. Cierre de sesión:** El usuario destruye la sesión antes de confirmar la acción; finaliza el caso de uso.

---

### CASO DE USO 7: Editar Cotizaciones

| Propiedad | Detalle |
|---|---|
| **ID / Nombre** | `CU-07`: Editar Cotizaciones |
| **Descripción** | Proceso mediante el cual el personal autorizado edita cotizaciones. |
| **Actores** | Empleado, Administrador |
| **Precondición** | Estar autenticado como Empleado o Administrador. |
| **Postcondición** | Se aplican y persisten los cambios sobre las cotizaciones seleccionadas. |
<img width="911" height="881" alt="CU07" src="https://github.com/user-attachments/assets/586d6fff-955a-494c-9018-f88dbab8bb99" />

**Secuencia Normal:**

1. El usuario ingresa al módulo de **cotizaciones**.
2. El sistema carga las cotizaciones activas pendientes por revisión.
3. El usuario selecciona la opción de editar.
4. El sistema muestra el formulario con campos bloqueados y otros disponibles para edición.
5. El usuario confirma la operación y el sistema muestra un aviso de validación del cambio.

**Excepciones:**

* **1.a. Credenciales erróneas:** Error de autenticación al intentar acceder al módulo.
* **1.b. Cancelación:** El usuario cancela manualmente la operación.
* **1.c. Cierre de sesión:** El usuario destruye la sesión antes de confirmar la acción; finaliza el caso de uso.

---

### CASO DE USO 8: Confirmar Cotización

| Propiedad | Detalle |
|---|---|
| **ID / Nombre** | `CU-08`: Confirmar Cotizaciones |
| **Descripción** | Proceso mediante el cual el personal autorizado confirma cotizaciones. |
| **Actores** | Empleado, Administrador |
| **Precondición** | Estar autenticado como Empleado o Administrador, expresa autorización y confirmación del cliente |
| **Postcondición** | Se confirma la cotización y entra a categoría de cotizaciones cerradas. |
<img width="872" height="908" alt="CU08" src="https://github.com/user-attachments/assets/9937ddef-bbe6-4cd3-b684-7cabce5530bc" />


**Secuencia Normal:**

1. El usuario ingresa al módulo de **cotizaciones**.
2. El sistema carga las cotizaciones activas pendientes por revisión.
3. El usuario selecciona **"Ver más detalles"**.
4. El sistema despliega la cotización completa.
5. El usuario presiona el botón de confirmación.
6. El sistema despliega un modal de advertencia confirmando la acción.
7. La cotización cambia su estado a Confirmado y entra en la categoría **"Cerradas"**.

**Excepciones:**

* **1.a. Credenciales erróneas:** Error de autenticación al intentar acceder al módulo.
* **1.b. Cancelación:** El usuario cancela manualmente la operación.
---
### CASO DE USO 9: Rechazar Cotización

| Propiedad | Detalle |
|---|---|
| **ID / Nombre** | `CU-09`: Rechazar Cotizaciones |
| **Descripción** | Proceso mediante el cual el personal autorizado rechaza cotizaciones. |
| **Actores** | Empleado, Administrador |
| **Precondición** | Estar autenticado como Empleado o Administrador; cliente no aceptó términos |
| **Postcondición** | Se rechaza la cotización y entra a categoría de cotizaciones cerradas. |
<img width="600" height="600" alt="CU09" src="https://github.com/user-attachments/assets/ef219504-e34d-43f9-9652-a7f33d8c1c72" />



**Secuencia Normal:**

1. El usuario ingresa al módulo de **cotizaciones**.
2. El sistema carga las cotizaciones activas pendientes por revisión.
3. El usuario selecciona **"Ver más detalles"**.
4. El sistema despliega la cotización completa.
5. El usuario presiona el botón de rechazo.
6. El sistema despliega un modal de advertencia confirmando la acción.
7. La cotización cambia su estado a **Rechazado** y entra en la categoría **"Cerradas"**.

**Excepciones:**

* **1.a. Credenciales erróneas:** Error de autenticación al intentar acceder al módulo.
* **1.b. Cancelación:** El usuario cancela manualmente la operación.
---
### CASO DE USO 10: Eliminar Cotización

| Propiedad | Detalle |
|---|---|
| **ID / Nombre** | `CU-10`: Eliminar Cotizaciones |
| **Descripción** | Proceso mediante el cual el personal autorizado elimina cotizaciones. |
| **Actores** | Administrador |
| **Precondición** | Estar autenticado como Administrador, la cotización debe estar en estado **Pendiente** |
| **Postcondición** | Se elimina/cancela la cotización del sistema y DB |
<img width="898" height="879" alt="CU09" src="https://github.com/user-attachments/assets/9df08e41-9eb9-4311-8920-5ff26fd28304" />



**Secuencia Normal:**

1. El usuario ingresa al módulo de **cotizaciones**.
2. El sistema carga las cotizaciones activas pendientes por revisión.
3. El usuario selecciona **"Ver más detalles"**.
4. El sistema despliega la cotización completa.
5. El usuario presiona el botón de eliminación.
6. El sistema despliega un modal de advertencia confirmando la acción.
7. La cotización es borrada del sistema y se actualizará el módulo.

**Excepciones:**

* **1.a. Credenciales erróneas:** Error de autenticación al intentar acceder al módulo.
* **1.b. Cancelación:** El usuario cancela manualmente la operación.
		
### 3.5.8 HISTORIAS DE USUARIO
`HU-01`: TÍTULO: CREACIÓN DE USUARIOS
**Como** superadministrador, 
**Quiero** crear usuarios de tipo admin/empleado en el sistema, 
**Para** delegar control y gestión del software de forma estructurada.
**CRITERIOS DE ACEPTACIÓN**
Criterio 1 (Registro exitoso):
Dado que el admin/empleado se encuentra en el formulario de creación de cotizaciones,
Cuando diligencia los campos obligatorios (cliente, ítems, montos) y hace clic en "Guardar",
Entonces el sistema registra la cotización con estado inicial Pendiente y la muestra en el listado.

Criterio 2 (Restricción de eliminación):

Dado que el usuario intenta eliminar una cotización que ya fue confirmada o rechazada,

Cuando hace clic en el botón de borrar,

Entonces el sistema bloquea la acción y muestra un mensaje indicando que solo se pueden eliminar cotizaciones pendientes o en borrador.

`HU-02`: TÍTULO: ASIGNACIÓN DE ROLES
**Como** superadministrador, 
**Quiero** asignar/cambiar el rol a un usuario del sistema, 
**Para** delegar la gestión operativa del software sin arriesgar a modificarlo o perder el control total.

`HU-03`: TÍTULO: LOGIN
**Como** admin/empleado 
**Quiero** loguearme con las credenciales suministradas/propuestas en el formulario 
**Para** acceder al software.

`HU-04`: TÍTULO: LOGOUT
**Como** admin/empleado 
**Quiero** destruir la sesión de forma sencilla, 
**Para** acabar mis actividades de forma segura.

`HU-05`: TÍTULO: CRUD PRODUCTO
**Como** administrador 
**Quiero** registrar un producto, verlo, actualizarlo y borrarlo 
**Para** gestión de inventario como función del software.

`HU-06`: TÍTULO: CRUD COTIZACIÓN
**Como** administrador/empleado 
**Quiero** registrar una cotización, verla y actualizarla o borrarla si no sirve 
**Para** llevar control y supervisión de esta función del software.

`HU-07`: TÍTULO: CONFIRMACION/RECHAZO
**Como** admin/empleado 
**Quiero** confirmar/rechazar cotizaciones, 
**Para** gestionar y calificar estos documentos según estado.

`HU-08`: TÍTULO: AUDITORÍA DE ACCIONES
**Como** administrador/empleado 
**Quiero** visualizar los registros de acciones llevadas a cabo en una cotización y en un producto 
**Para** auditar los eventos del software.
