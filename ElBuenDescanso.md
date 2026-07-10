* Bruno Acosta

1\. Introduccion

El documento define la Especificación de Requerimientos de Software (ERS) correspondiente a la versión 1.0 del sistema integral de gestión "El Buen Descanso". Abarca la totalidad del software a construir, incluyendo la administración de personas y socios, la tramitacion de solicitudes de afiliacion, el control de los espacios funerarios, el registro de pagos y el seguimiento de los accesos al sistema.





2\. Alcance del Producto / Software

El sistema “El Buen Descanso” es una aplicación web pensada para digitalizar y agilizar la gestión integral de la empresa funeraria familiar y del cementerio que administra.



unificar en una sola plataforma la administración de socios, las solicitudes de afiliacion, los nucleos familiares, los espacios funerarios, el cobro de cuotas mensuales y la auditoría de accesos, dejando atrás el registro manual y acortando los tiempos operativos.





Beneficios para el negocio:

<<<<<<< HEAD





4. Funcionalidades del Producto modificado por Maximo
=======
• Simplificar el tramite de afiliacion, dejando que cualquier persona interesada lo inicie por su cuenta desde la web.

4. Funcionalidades del Producto
>>>>>>> 8004de53a1059a0a5b2598138659ef8388082fec
El sistema provee las siguientes funcionalidades principales:
• F1 Solicitud y Gestión de Afiliación Web
• F2  Gestión de Socios y Núcleo Familiar
• F3  Registro y Control de Pagos
• F4  Gestión de Espacios Funerarios
• F5 —Autenticación y Auditoría de Accesos
5. Clases y Características de Usuarios
• Contar con un registro unico y trazable de los socios y sus respectivos nucleos familiares.

• Automatizar el seguimiento de los pagos de cuotas, emitiendo el comprobante correspondiente.

• Asegurar una asignacion ordenada de los espacios funerarios disponibles (Parcela, Panteón, Nicho).

• Reforzar la seguridad incorporando autenticación de dos factores (2FA) y un registro de accesos.



Objetivos y metas:

• Bajar el tiempo que insume procesar una solicitud de afiliacion.

• Ofrecer datos actualizados en tiempo real sobre la disponibilidad de espacios funerarios.

• Generar reportes que sirvan de apoyo a la toma de decisiones directivas.



&#x20;.Mateo Blanco

3\. Funcionalidades del Producto modificado por Mateo
El sistema provee las siguientes funcionalidades principales:
• F1 — Solicitud y Gestión de Afiliación Web
• F2 — Gestión de Socios y Núcleo Familiar
• F3 — Registro y Control de Pagos
• F4 — Gestión de Espacios Funerarios
• F5 — Autenticación y Auditoría de Accesos
5. Clases y Características de Usuarios



4. Clases y Características de Usuarios
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
Empleado con privilegios extendidos. Gestiona empleados y auditoria
Alto
F1 a F5 completo
5. Entorno Operativo

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
F1 a F5 complete



























































































7\. Requerimientos Funcionales

7.1. RF1 Solicitud y Gestión de Afiliación Web

Código

RF1

Descripción

Este sistema permite que cualquier persona pueda completar y enviar una solicitud de afiliacion online. Un empleado la revisa y la puede aprobar o rechazar. La aprobacion genera automaticamente el alta del solicitante como un socio

Prioridad

Alta

Acciones iniciadoras / Estímulos

El interesado accede al formulario público e ingresa sus datos (CI, nombre, email, etc)

Comportamiento esperado del sistema

1\. Valida campos obligatorios,  si hay error, muestra un mensaje.2. Registra la solicitud con estado "Pendiente" .3. El empleado la revisa y registra la fecha de revisión.4. Si aprueba: crea PERSONA y SOCIO, cambia estado a "Aprobada" .5. Si rechaza: estado pasa a "Rechazada". En ambos casos se le notifica al solicitanto





7.2. RF2 Gestión de Socios y Núcleo Familiar

Código

RF2

Descripción

Este sistema le permite al empleado gestionar socios activos y administrar los vinculos a un socio titular, indicando el tipo de relacion

Prioridad

Alta

Acciones iniciadoras / Estímulos

El empleado busca un socio por CI o nombre y selecciona la operación deseada.

Comportamiento esperado del sistema

1\. Muestra datos completos del socio y su núcleo familiar.2. Permite modificar email del socio.3. Permite agregar un miembro: valida que no sea titular de otro núcleo.4. Permite quitar un miembro.5. Guarda cambios y muestra confirmación.





7.3. RF3 Registro y Control de Pagos

Código

RF3

Descripción

Este sistema permite que el empleado pueda registrar el pago de de cuota de un socio, generando un numero de comprobante unico automaticamente

Prioridad

Alta

Acciones iniciadoras / Estímulos

El empleado selecciona un socio, ingresa el monto y confirma el pago.

Comportamiento esperado del sistema

1\. Valida monto mayor a cero; si no, muestra error.2 Genera comprobante único automáticamente. 3 Registra fecha de aprobación . 4 Asocia el pago al socio y al empleado que lo registra.5. El socio consulta su historial desde el portal.





7.4. RF4 Gestión de Espacios Funerarios

Código

RF4

Descripción

Este sistema permite al administrador registrar y consultar los espacios funerarios disponibles(Parcela, Panteon, Nicho) y poder asignarlos a socios

Prioridad

Media

Acciones iniciadoras / Estímulos

El administrador accede al modulo de Espacios y elige agregar o asignar

Comportamiento esperado del sistema

1\. Valida que el tipo sea Parcela, Panteón o Nicho.2. Valida que la ubicación no exista previamente. 3 Permite buscar espacios por tipo.4  Permite asignar un espacio a uno o más socios.5  Muestra listado con estado de asignacion





7.5. RF5 Autenticación y Auditoría de Accesos

Código

RF5

Descripción

Este sistema gestiona el acceso de los empleados y socios mediante usuario/contraseña y pudiendo agregar un 2FA, registrado cada sesion con una fecha y hora, de entrada y de salida.

Prioridad

Alta

Acciones iniciadoras / Estímulos

El usuario ingresa sus credenciales en la pantalla de login.

Comportamiento esperado del sistema

1\. Valida credenciales contra LOG\_SYSTEM (contraseña en hash).2 Si 2FA activo, solicita código de segundo factor.3 Registra entrada con fecha/hora.4. Al cerrar sesión, registra la salida.5 El administrador consulta el log completo. 6 Las contraseñas nunca en texto plano.

