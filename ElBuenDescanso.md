* Bruno Acosta

1\. Introduccion

El documento define la Especificación de Requerimientos de Software (ERS) correspondiente a la versión 1.0 del sistema integral de gestión "El Buen Descanso". Abarca la totalidad del software a construir, incluyendo la administración de personas y socios, la tramitacion de solicitudes de afiliacion, el control de los espacios funerarios, el registro de pagos y el seguimiento de los accesos al sistema.





2\. Alcance del Producto / Software

El sistema “El Buen Descanso” es una aplicación web pensada para digitalizar y agilizar la gestión integral de la empresa funeraria familiar y del cementerio que administra.



unificar en una sola plataforma la administración de socios, las solicitudes de afiliacion, los nucleos familiares, los espacios funerarios, el cobro de cuotas mensuales y la auditoría de accesos, dejando atrás el registro manual y acortando los tiempos operativos.





Beneficios para el negocio:

• Simplificar el tramite de afiliacion, dejando que cualquier persona interesada lo inicie por su cuenta desde la web.

4. Funcionalidades del Producto
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

3\. Funcionalidades del Producto
El sistema provee las siguientes funcionalidades principales:
• F1 — Solicitud y Gestión de Afiliación Web
• F2 — Gestión de Socios y Núcleo Familiar
• F3 — Registro y Control de Pagos
• F4 — Gestión de Espacios Funerarios
• F5 — Autenticación y Auditoría de Accesos



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

