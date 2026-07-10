















4. Funcionalidades del Producto modificado por Maximo
El sistema provee las siguientes funcionalidades principales:
• F1 — Solicitud y Gestión de Afiliación Web
• F2 — Gestión de Socios y Núcleo Familiar
• F3 — Registro y Control de Pagos
• F4 — Gestión de Espacios Funerarios
• F5 — Autenticación y Auditoría de Accesos
5. Clases y Características de Usuarios
Perfil de Usuario
Descripción
Nivel de Privilegio
Funcionalidades
Interesado / Postulante
Persona externa que desea afiliarse. Sin cuenta en el sistema.
Sin autenticación
F1 — Alta de Solicitud
Socio Titular
Persona afiliada activa. Accede vía portal con 2FA.
Bajo lectura propia
F2, F3, F4 (consulta)
Empleado
Personal administrativo. Gestiona socios, pagos y espacios.
Medio
F1 (aprobación), F2, F3, F4
Administrador
Empleado con privilegios extendidos. Gestiona empleados y auditoría.
Alto
F1 a F5 completo
6. Entorno Operativo

&#x20;  - Plataforma: Aplicación web (cliente-servidor)

&#x20;  - Backend: Python (Django o Flask). Base de datos relacional (PostgreSQL).

&#x20;  - Frontend: HTML5 / CSS3 / JavaScript. Diseño responsivo para móvil y escritorio.

&#x20;  - Sistema operativo servidor: Linux Ubuntu Server 22.04 LTS.

&#x20;  - Conectividad: Requiere conexión a Internet para acceso externo de socios e interesados.

&#x20;  - Seguridad: HTTPS obligatorio. Autenticación 2FA. Contraseñas almacenadas como hash

7\. Reglas del negocio

RNE01

Toda persona debe tener al menos nombre1 y apell1. Los campos nombre2 y apell2 son opcionales.

RNE02

La CI es el identificador único de cada persona y no puede repetirse.

RNE03

La fec\_nac es obligatoria y se usa para validar mayoría de edad (≥ 18 años).

RNE04

Una persona puede tener múltiples teléfonos de contacto.

RNE05

La dirección se compone de calle, nro y apto; solo calle y nro son obligatorios.

RNE06

Todo socio debe ser una persona registrada en el sistema (referenciada por CI).

RNE07

El alta de un socio debe ser aprobada por un empleado.

RNE08

Un socio puede tener socios adherentes vinculados, indicando el tipo de relación.

RNE09

Un socio adherente no puede ser a su vez titular de otro núcleo familiar.

RNE10

El email del socio debe ser único en el sistema.

RNE11

Todo empleado debe ser una persona registrada en el sistema (referenciada por CI).

RNE12

Cada empleado tiene un cargo asignado y una fecha de ingreso (fec\_ing).

RNE13

El email\_emp del empleado debe ser único en el sistema.

RNE14

El tipo de espacio funerario solo puede ser: Parcela, Panteón o Nicho.

RNE15

Cada espacio funerario tiene una ubicación física única dentro del cementerio.

RNE16

Un espacio funerario puede ser adquirido por uno o más socios.

RNE17

Un socio puede adquirir más de un espacio funerario.

RNE18

Cualquier persona (no necesariamente socia) puede realizar una solicitud de afiliación.

RNE19

El estado de una solicitud solo puede ser: Pendiente, Aprobada o Rechazada.

RNE20

Una solicitud debe ser revisada por al menos un empleado.

RNE21

Se debe registrar la fecha en que el empleado revisó la solicitud (fec\_rev).

RNE22

Una solicitud aprobada deriva en el alta de un nuevo socio.

RNE23

Todo pago debe estar asociado a un socio y registrado por un empleado.

RNE24

El monto de un pago debe ser un valor positivo mayor a cero.

RNE25

Cada pago genera un número de comprobante único.

RNE26

Se debe registrar la fecha de aprobación del pago (fec\_aprob).

RNE27

Todo acceso al sistema queda registrado con fecha y hora de entrada y salida.

RNE28

Cada usuario (id\_user) puede ser empleado o socio, pero no ambos simultáneamente.

RNE29

La contraseña debe almacenarse como hash; nunca en texto plano.

RNE30

El campo 2FA indica si el usuario tiene habilitada la autenticación de dos factores.

