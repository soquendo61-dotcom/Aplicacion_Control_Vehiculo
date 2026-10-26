# Vehículos Services — Requerimientos no funcionales

## 1. Propósito

Este documento contiene la especificación detallada de los requerimientos no funcionales de Vehículos Services, indicando los módulos, capacidades y etapas a los que aplica cada requerimiento.

Su contenido inicial reúne los requerimientos definidos para la primera etapa del Propietario y las capacidades generales necesarias para su funcionamiento. La incorporación de condiciones específicas de etapas posteriores deberá documentarse expresamente; no se asumirá que todos los criterios actuales cubren automáticamente esas etapas.

Complementa `proyecto.md` y los documentos `requerimientos-funcionales-propietario.md` y `requerimientos-funcionales-prestador.md`. Cada requerimiento no funcional tendrá aquí su única especificación principal; los demás documentos lo referenciarán mediante su identificador.

Las reglas de negocio se desarrollarán en `reglas-negocio.md`. Las decisiones técnicas para cumplir las condiciones de calidad se documentarán en `arquitectura.md`, `modelo-datos.md`, `seguridad.md` y `ux-ui.md`, según corresponda.

Los requerimientos no funcionales aplicables deberán considerarse durante el diseño, implementación y validación de cada entrega. Su documentación independiente no implicará aplazar su cumplimiento hasta finalizar las funcionalidades.

## 2. Identificación y estado

- Los requerimientos no funcionales utilizarán identificadores `RNF-001`, `RNF-002` y sucesivos, conforme a la estructura documental establecida en `proyecto.md`.
- Su numeración será independiente de RF y RN y única en todo el proyecto, sin reiniciarse por módulo, documento o categoría de calidad.
- Cada requerimiento conservará su identificador cuando cambie de ubicación. Los identificadores existentes no se renumerarán ni se reutilizarán para otros requisitos.
- Cada requerimiento indicará su módulo o capacidad, etapa prevista, estado de definición, prioridad, dependencias, referencias y criterios de aceptación verificables.
- Las propuestas y decisiones pendientes no se considerarán aprobadas por su inclusión en este documento ni por su traslado desde el documento anterior.
- Los objetivos, límites y escenarios pendientes necesarios para implementar y comprobar un requisito deberán concretarse y validarse antes de considerarlo listo para desarrollar.
- Las condiciones compartidas tendrán una única definición principal. Las diferencias particulares de un módulo o entrega deberán identificarse expresamente.
- Las referencias a RF conservarán sus identificadores y señalarán el documento funcional correspondiente cuando sea necesario.

## 3. Requerimientos no funcionales

Esta sección especifica las condiciones de calidad que deberá cumplir el módulo del Propietario y las capacidades generales necesarias para su funcionamiento.

Cada requerimiento deberá contar con criterios verificables. Los valores, condiciones o alcances pendientes deberán definirse y validarse antes de considerar el requisito listo para implementar.

Las decisiones técnicas para cumplir estos requerimientos se desarrollarán en los documentos correspondientes de arquitectura, diseño y pruebas.

### RNF-001 — Compatibilidad con Android e iOS

- ID: RNF-001.
- Nombre: Compatibilidad con Android e iOS.
- Tipo: Requerimiento no funcional.
- Módulo o capacidad: Capacidad general compartida — Aplicación móvil.
- Etapa prevista: Primera etapa del Propietario; aplicable posteriormente al módulo del Prestador.
- Estado de la definición: Propuesta; pendiente de definir las versiones, dispositivos y configuraciones soportadas.
- Actor relacionado: Usuario de la aplicación móvil.
- Prioridad: Por definir.
- Referencias relacionadas: Plataformas previstas en `proyecto.md`; compatibilidad contemplada en el punto 28; selección tecnológica pendiente en el punto 32; diseño adaptable previsto para `ux-ui.md`.
- Dependencias: Definición de la matriz de compatibilidad; alcance funcional de la versión que se implemente; decisiones de arquitectura y diseño móvil.

#### Descripción

Vehículos Services deberá disponer de una aplicación para Android y una aplicación para iOS que permitan utilizar las funcionalidades del Propietario incluidas en la versión implementada, dentro de las versiones y configuraciones expresamente soportadas.

La matriz de compatibilidad deberá identificar las versiones de sistema operativo, tipos de dispositivo y configuraciones contempladas. No deberá interpretarse que la aplicación soportará todas las versiones existentes de Android o iOS.

Las reglas de negocio, validaciones, permisos y significado de los resultados deberán conservarse en ambas plataformas. La presentación y las interacciones podrán adaptarse a las características de cada sistema operativo conforme al diseño de UX/UI.

Las funcionalidades que dependan de capacidades o permisos del dispositivo deberán tener un comportamiento definido para cada plataforma. Si una capacidad necesaria no está disponible o su permiso no fue concedido, la aplicación deberá informar la limitación y no presentar la operación como completada.

Una diferencia funcional entre plataformas deberá documentarse y validarse expresamente antes de incluirse en la versión correspondiente.

#### Criterios de aceptación

1. La aplicación podrá instalarse, iniciarse y utilizarse en las configuraciones incluidas en la matriz de compatibilidad aprobada para Android e iOS.
2. Los flujos funcionales incluidos en la versión se verificarán en ambas plataformas conforme a los mismos requisitos y criterios de aceptación.
3. Para los mismos datos, reglas y permisos, ambas plataformas producirán resultados funcionalmente equivalentes.
4. Las diferencias de presentación o interacción respetarán el diseño aprobado y no alterarán las reglas de negocio ni las autorizaciones.
5. Las operaciones que utilicen capacidades del dispositivo tendrán un comportamiento verificable cuando dichas capacidades estén disponibles, no estén disponibles o sus permisos sean rechazados.
6. Una operación que no pueda completarse por una limitación del dispositivo no se mostrará como realizada.
7. Las diferencias funcionales aprobadas entre plataformas estarán identificadas en el alcance de la versión y en sus verificaciones de compatibilidad.

#### Decisiones pendientes

- Definir las versiones mínimas y el rango de versiones soportadas de Android e iOS.
- Definir los tipos de dispositivo incluidos inicialmente, como teléfonos y, si corresponde, tabletas.
- Definir las configuraciones representativas que se utilizarán para verificar la compatibilidad.
- Identificar las capacidades del dispositivo requeridas por las funcionalidades iniciales y su comportamiento ante permisos rechazados o capacidades no disponibles.
- Definir el tratamiento de dispositivos o versiones fuera del alcance soportado.
- Definir cómo se revisará y actualizará la matriz de compatibilidad durante la evolución de la aplicación.

### RNF-002 — Control de acceso a funcionalidades y recursos

- ID: RNF-002.
- Nombre: Control de acceso a funcionalidades y recursos.
- Tipo: Requerimiento no funcional.
- Módulo o capacidad: Capacidad general compartida — Seguridad y autorización.
- Etapa prevista: Primera etapa del Propietario; aplicable posteriormente al módulo del Prestador y a la integración.
- Estado de la definición: Propuesta; pendiente de completar la matriz de permisos y los escenarios de verificación.
- Actor relacionado: Usuario que solicita acceder a una funcionalidad o recurso de la solución.
- Prioridad: Por definir.
- Referencias relacionadas: Control de acceso conforme al punto 25 de `proyecto.md`; seguridad del lado del servidor y autorización por recurso conforme a `67.3` y `67.4`; permisos establecidos en los requerimientos funcionales correspondientes.
- Dependencias: Mecanismos de autenticación; relaciones de propiedad y representación; permisos definidos para cada operación y recurso.

#### Descripción

Vehículos Services deberá comprobar la autenticación y autorización aplicables antes de permitir consultas, modificaciones o acciones sobre recursos protegidos.

El control deberá considerar la operación solicitada, el recurso concreto y las relaciones y permisos vigentes del usuario. La autenticación no deberá otorgar acceso general a todos los vehículos, organizaciones, registros o documentos.

Las comprobaciones deberán realizarse en el servidor. Ocultar una opción en la aplicación móvil no deberá ser el único mecanismo para impedir una acción no autorizada.

El acceso directo mediante una solicitud a los servicios, un identificador de recurso o un enlace no deberá permitir eludir las restricciones aplicadas desde la interfaz.

Los permisos se determinarán conforme a los requisitos funcionales correspondientes, sin redefinirlos en este punto. Si no puede comprobarse una autorización válida, la operación protegida deberá rechazarse.

La autorización deberá respetar el contexto bajo el cual actúa el usuario. Tener funciones de Propietario, representar una persona jurídica o actuar como Prestador no deberá extender automáticamente los permisos entre esos contextos.

#### Criterios de aceptación

1. Las operaciones que requieran autenticación rechazarán solicitudes sin una sesión válida, sin devolver información protegida ni ejecutar cambios.
2. Un usuario autenticado sin permiso para una operación o recurso no podrá acceder a él mediante la interfaz ni mediante solicitudes directas a los servicios.
3. Cambiar el identificador de un vehículo, organización, registro o documento en una solicitud no permitirá acceder a recursos no autorizados.
4. Las operaciones de consulta y modificación comprobarán sus permisos específicos; disponer de uno no habilitará automáticamente el otro.
5. Las solicitudes posteriores a una revocación o finalización de autorización no podrán utilizar los permisos retirados para efectuar nuevas operaciones.
6. Los documentos y archivos mantendrán sus controles de acceso aunque se conozca su identificador o enlace.
7. Una solicitud rechazada por falta de autorización no modificará el recurso protegido.
8. Si no puede determinarse una autorización válida, la plataforma rechazará la operación en lugar de conceder acceso por defecto.
9. Las pruebas verificarán los accesos permitidos y rechazados entre usuarios, vehículos y personas jurídicas diferentes, según las capacidades implementadas.
10. Las respuestas de rechazo no expondrán contenido protegido ni detalles internos innecesarios sobre el recurso solicitado.

#### Decisiones pendientes

- Completar la matriz de operaciones, recursos y permisos a partir de los RF aprobados.
- Definir los escenarios de verificación para propietarios actuales, anteriores y usuarios autorizados de personas jurídicas.
- Precisar el tratamiento de operaciones en curso cuando cambie una autorización.
- Definir cómo se protegerán los accesos directos a archivos y los enlaces que se habiliten.
- Definir el comportamiento ante información de autorización temporalmente no disponible, conservando el rechazo de operaciones cuya autorización no pueda comprobarse.
- Definir las respuestas y evidencias de rechazo necesarias para las pruebas y el seguimiento de seguridad, sin exponer información restringida.

---

### RNF-003 — Protección de información sensible

- ID: RNF-003.
- Nombre: Protección de información sensible.
- Tipo: Requerimiento no funcional.
- Módulo o capacidad: Capacidad general compartida — Protección de datos.
- Etapa prevista: Primera etapa del Propietario; aplicable posteriormente al módulo del Prestador y a la integración.
- Estado de la definición: Propuesta; pendiente de clasificar la información y definir los controles de protección correspondientes.
- Actor relacionado: Usuario cuya información es procesada por la solución.
- Prioridad: Por definir.
- Referencias relacionadas: Protección de datos contemplada en el punto 28 de `proyecto.md`; seguridad definida en los puntos 42 y 67; privacidad y visibilidad establecidas en los RF correspondientes.
- Dependencias: Clasificación de la información; identificación de los lugares donde se transmite o almacena; decisiones de arquitectura y seguridad; controles de acceso conforme a RNF-002.

#### Descripción

Vehículos Services deberá proteger la confidencialidad de la información clasificada como sensible durante su transmisión y almacenamiento.

La clasificación deberá contemplar los datos personales, documentos privados, información de representación y elementos utilizados para autenticar o recuperar el acceso, según su naturaleza y el uso que tenga cada uno.

La transmisión de información sensible entre la aplicación y los servicios deberá utilizar comunicaciones cifradas con validación de la identidad del servicio. No deberá continuarse una transmisión sensible mediante una conexión cuya seguridad no pueda validarse.

La información sensible almacenada deberá contar con controles de protección adecuados a su clasificación. El alcance deberá incluir el dispositivo móvil, los servicios, el almacenamiento de archivos y las copias que se generen, cuando contengan esa información.

Los secretos utilizados para autenticar al usuario o autorizar sesiones no deberán exponerse en pantallas, mensajes de error, registros técnicos o reportes. Cuando Vehículos Services administre contraseñas, estas no deberán conservarse en texto legible ni mediante un mecanismo que permita recuperarlas como texto original.

Las notificaciones, reportes y archivos exportados deberán incluir únicamente la información permitida para su finalidad y destinatario. La protección no deberá limitarse a los datos que permanecen dentro de la aplicación.

Los mecanismos técnicos y su configuración se definirán en arquitectura y seguridad. Este requisito no modificará las reglas de propiedad, privacidad o autorización establecidas en los RF.

#### Criterios de aceptación

1. Existirá una clasificación documentada de la información sensible y de los controles aplicables antes de verificar este requisito.
2. Las comunicaciones que transmitan información sensible utilizarán cifrado y validarán la identidad del servicio conforme a la configuración de seguridad aprobada.
3. Si no puede validarse la seguridad de la conexión, la aplicación no transmitirá información sensible por esa conexión.
4. La revisión de los lugares de almacenamiento identificados comprobará que se aplican los controles definidos para cada categoría de información sensible.
5. Las contraseñas administradas por Vehículos Services no podrán obtenerse como texto original mediante la consulta de los datos almacenados.
6. Los secretos de autenticación y sesión no aparecerán en mensajes, reportes ni registros técnicos.
7. Las notificaciones, reportes y exportaciones respetarán la información permitida para su finalidad y destinatario.
8. Los mensajes de error no expondrán contenido sensible ni secretos utilizados internamente.
9. Las pruebas incluirán la aplicación Android, la aplicación iOS y los servicios y almacenamientos utilizados por la versión implementada.

#### Decisiones pendientes

- Definir la clasificación de datos y los controles exigidos para cada categoría.
- Identificar la información que podrá almacenarse localmente y las condiciones de conservación y retiro.
- Definir los mecanismos de protección de comunicaciones, almacenamiento y secretos en los documentos de arquitectura y seguridad.
- Precisar la protección de copias de respaldo, archivos temporales y otros datos derivados.
- Definir qué información podrá incluirse en notificaciones y exportaciones, conforme a sus requisitos funcionales.
- Definir las verificaciones y evidencias necesarias para demostrar el cumplimiento de los controles.

---

### RNF-004 — Integridad y consistencia de los registros

- ID: RNF-004.
- Nombre: Integridad y consistencia de los registros.
- Tipo: Requerimiento no funcional.
- Módulo o capacidad: Capacidad general compartida — Integridad de la información.
- Etapa prevista: Primera etapa del Propietario; aplicable posteriormente al módulo del Prestador y a la integración.
- Estado de la definición: Propuesta; pendiente de precisar las operaciones que requieren ejecución indivisible y el tratamiento de conflictos.
- Actor relacionado: Usuario que registra o modifica información.
- Prioridad: Por definir.
- Referencias relacionadas: Integridad y continuidad del historial conforme a `63.6` de `proyecto.md`; conservación de registros conforme a `63.6.5`; validaciones y trazabilidad establecidas en los RF correspondientes.
- Dependencias: Reglas de validación; definición de las relaciones entre registros; mecanismos de almacenamiento y procesamiento; controles de autorización conforme a RNF-002.

#### Descripción

Vehículos Services deberá conservar la integridad de los registros y sus relaciones cuando se realicen operaciones de creación, actualización, corrección, incorporación de información o anulación.

Las validaciones necesarias deberán ejecutarse antes de aceptar los cambios. Los errores de procesamiento no deberán dejar registros que incumplan las condiciones obligatorias de la operación.

Cuando una operación requiera que varios cambios se completen conjuntamente, deberá definirse como indivisible: se conservará el conjunto completo de cambios o no se aplicará ninguno. Las operaciones que admitan procesamiento parcial deberán identificar expresamente las partes completadas y pendientes.

Un reintento de la misma solicitud, ocasionado por una interrupción o falta de respuesta, no deberá producir automáticamente un segundo evento. La solución deberá distinguir ese reintento de una solicitud nueva, sin impedir el registro de eventos legítimos con datos similares.

Cuando dos usuarios o procesos intenten modificar información relacionada, la plataforma deberá aplicar una regla definida para resolver el conflicto. No deberá sobrescribir silenciosamente cambios aceptados basándose en una versión desactualizada del registro.

Las actualizaciones de resultados derivados deberán mantener coherencia con los datos que las originaron. Si su procesamiento no es inmediato, deberá poder distinguirse un resultado pendiente de actualización de uno calculado con información vigente.

Las correcciones, incorporaciones y anulaciones conservarán las condiciones de RF-038, RF-039 y RF-040.

#### Criterios de aceptación

1. Una operación que incumpla las validaciones obligatorias no se aceptará como completada ni dejará cambios incompatibles con esas validaciones.
2. Las operaciones definidas como indivisibles no conservarán únicamente una parte de sus cambios ante un fallo de procesamiento.
3. Las operaciones que admitan ejecución parcial permitirán identificar qué partes fueron completadas y cuáles permanecen pendientes o fallaron.
4. Repetir la misma solicitud conforme al mecanismo de reintento definido no creará registros duplicados ni aplicará dos veces el mismo cambio.
5. La existencia de registros con datos similares no impedirá por sí sola incorporar un evento distinto y válido.
6. Una modificación basada en información desactualizada se tratará conforme a la regla de conflicto aprobada, sin sobrescribir silenciosamente cambios aceptados.
7. Los registros conservarán sus relaciones obligatorias con el vehículo y los demás elementos correspondientes después de una operación aceptada.
8. Los resultados derivados afectados por un cambio se actualizarán conforme a sus reglas; mientras estén pendientes, no se presentarán como calculados con la información vigente.
9. Las pruebas verificarán fallos durante el procesamiento, reintentos y modificaciones simultáneas sobre las operaciones incluidas en el alcance.

#### Decisiones pendientes

- Identificar las operaciones indivisibles y las que admitirán ejecución parcial.
- Definir cómo se distinguirá un reintento de una solicitud nueva y durante cuánto tiempo se reconocerá.
- Definir las reglas para resolver modificaciones simultáneas o realizadas sobre versiones desactualizadas.
- Identificar los resultados derivados que requieren actualización y su tratamiento mientras permanezcan pendientes.
- Precisar cómo se recuperarán las operaciones incompletas sin duplicar registros ni perder cambios aceptados.
- Definir los escenarios y evidencias de prueba para comprobar la integridad.

---

### RNF-005 — Auditoría y trazabilidad de acciones

- ID: RNF-005.
- Nombre: Auditoría y trazabilidad de acciones.
- Tipo: Requerimiento no funcional.
- Módulo o capacidad: Capacidad general compartida — Auditoría y trazabilidad.
- Etapa prevista: Primera etapa del Propietario; aplicable posteriormente al módulo del Prestador y a la integración.
- Estado de la definición: Propuesta; pendiente de definir el catálogo de acciones auditables, la conservación de evidencias y los permisos de consulta.
- Actor relacionado: Usuario que realiza una acción auditable; proceso de la plataforma que ejecuta una acción automática; persona autorizada para consultar evidencias de auditoría.
- Prioridad: Por definir.
- Referencias relacionadas: Auditoría y trazabilidad contempladas en el punto 28 de `proyecto.md`; conservación de cambios conforme a `63.6.5`; auditoría y trazabilidad de seguridad conforme a `67.11` y `67.12`.
- Dependencias: Identificación de usuarios y procesos; catálogo de acciones auditables; relaciones con los recursos afectados; protección de información conforme a RNF-002 y RNF-003.

#### Descripción

Vehículos Services deberá conservar evidencias que permitan reconstruir las acciones definidas como auditables y relacionarlas con sus responsables y recursos afectados.

Cada evidencia deberá identificar la acción, su responsable, el momento, el recurso y el resultado. Cuando el usuario actúe en representación de una persona jurídica, deberá conservarse ese contexto. Las acciones automáticas deberán distinguirse de las realizadas directamente por una persona.

La auditoría deberá complementar la procedencia y el historial de los registros, sin reemplazarlos. Las correcciones, incorporaciones y anulaciones conservarán el detalle exigido por sus requisitos funcionales, evitando mantener copias independientes que puedan resultar contradictorias.

La evidencia deberá distinguir el momento del evento vehicular, el momento de la acción en la plataforma y el momento de generación de la evidencia cuando sean diferentes.

Los usuarios que operen sobre un recurso no deberán poder alterar o eliminar sus evidencias de auditoría mediante las funcionalidades ordinarias. Su consulta y administración deberán estar sujetas a permisos específicos.

La auditoría deberá conservar únicamente la información necesaria para su finalidad. No deberá registrar contraseñas, secretos de sesión ni contenidos sensibles que no sean necesarios para documentar la acción.

#### Criterios de aceptación

1. Cada acción incluida en el catálogo aprobado generará una evidencia con los datos obligatorios definidos para ella.
2. La evidencia permitirá identificar la acción, su responsable, el recurso afectado, el momento y el resultado.
3. Las acciones efectuadas en representación de una persona jurídica conservarán la identificación del usuario y de la organización representada.
4. Las acciones automáticas identificarán el proceso responsable y no se atribuirán al usuario como si las hubiera ejecutado directamente.
5. Las evidencias de cambios conservarán o referenciarán el detalle requerido por RF-038, RF-039 y RF-040, según corresponda.
6. La fecha de una intervención registrada posteriormente no se confundirá con la fecha de su incorporación o modificación en la plataforma.
7. Los permisos ordinarios para crear o modificar información no habilitarán la alteración o eliminación de evidencias de auditoría.
8. La consulta de evidencias requerirá autorización específica y respetará las restricciones de información sensible.
9. Las evidencias no incluirán contraseñas ni secretos de autenticación o sesión.
10. Los reintentos se identificarán conforme al mecanismo definido, sin presentar una misma operación aceptada como varias modificaciones independientes.

#### Decisiones pendientes

- Definir el catálogo de acciones auditables, incluyendo los intentos rechazados que deban conservarse por razones de seguridad.
- Definir los datos obligatorios y el detalle necesario para cada tipo de evidencia.
- Definir los permisos para consultar y administrar la auditoría, sin asumir que existirá inicialmente una interfaz para el Propietario.
- Definir los períodos de conservación y las condiciones de archivo o eliminación controlada.
- Precisar el comportamiento cuando no pueda conservarse una evidencia, especialmente para operaciones que requieren trazabilidad obligatoria.
- Definir la referencia temporal utilizada y la forma de ordenar acciones procedentes de distintos componentes.
- Definir las verificaciones para comprobar la generación, integridad y consulta autorizada de las evidencias.

---

### RNF-006 — Rendimiento y tiempos de respuesta

- ID: RNF-006.
- Nombre: Rendimiento y tiempos de respuesta.
- Tipo: Requerimiento no funcional.
- Módulo o capacidad: Capacidad general compartida — Rendimiento.
- Etapa prevista: Primera etapa del Propietario; deberá reevaluarse al incorporar nuevas capacidades y módulos.
- Estado de la definición: Propuesta; pendiente de definir los objetivos medibles y las condiciones de carga.
- Actor relacionado: Usuario que utiliza la aplicación.
- Prioridad: Por definir.
- Referencias relacionadas: Rendimiento y tiempo de respuesta contemplados en el punto 28 de `proyecto.md`.
- Dependencias: Alcance funcional de la versión; volumen de información y concurrencia previstos; configuraciones soportadas conforme a RNF-001; definición de los escenarios de medición.

#### Descripción

Vehículos Services deberá cumplir objetivos de rendimiento definidos para las operaciones incluidas en la versión implementada, bajo condiciones de carga, dispositivo y conectividad expresamente documentadas.

Cada objetivo deberá identificar la operación evaluada, el punto desde el que se mide, la condición de finalización, el tiempo permitido y la proporción de ejecuciones que deberá cumplirlo.

Los tiempos de respuesta percibidos en la aplicación deberán distinguirse de los tiempos de procesamiento de los servicios. La medición deberá indicar si incluye comunicación de red, descarga de información y presentación del resultado.

Las consultas deberán evaluarse con volúmenes representativos de vehículos, eventos y archivos, evitando comprobar el rendimiento únicamente con cuentas o historiales vacíos.

Las operaciones de mayor duración, como cargas de archivos o generación de reportes cuando estén habilitadas, podrán tener objetivos diferentes. La aplicación deberá informar que continúan en procesamiento sin indicar que finalizaron antes de obtener el resultado correspondiente.

Las pruebas deberán registrar tanto los tiempos como los errores y resultados incorrectos. Una respuesta rápida que incumpla las reglas funcionales no deberá considerarse una ejecución satisfactoria.

Este requisito no garantizará los mismos tiempos bajo cualquier condición de red o dispositivo; su cumplimiento se comprobará dentro del escenario aprobado.

#### Criterios de aceptación

1. Antes de verificar el requisito, existirá una tabla de objetivos que identifique las operaciones, tiempos permitidos, proporción de cumplimiento y condiciones de medición.
2. Las operaciones evaluadas cumplirán los objetivos aprobados bajo la carga y los volúmenes definidos.
3. Las mediciones distinguirán el tiempo percibido en la aplicación del tiempo de procesamiento de los servicios.
4. Las pruebas incluirán datos representativos del alcance previsto, además de escenarios con información mínima.
5. Los resultados informarán tiempos, errores y ejecuciones que no produjeron una respuesta funcionalmente válida.
6. Las operaciones de larga duración mostrarán su condición de procesamiento conforme al diseño aprobado, sin presentar una confirmación de éxito anticipada.
7. La carga utilizada en las pruebas no provocará pérdida de integridad ni omisión de controles de acceso para alcanzar los tiempos establecidos.
8. La evidencia permitirá identificar la versión evaluada, los dispositivos o entornos utilizados, la conectividad, el volumen de datos y la concurrencia.

#### Decisiones pendientes

- Identificar las operaciones que tendrán objetivos de rendimiento en la primera etapa.
- Definir los tiempos permitidos y la proporción de ejecuciones que deberá cumplir cada objetivo.
- Definir los puntos de inicio y finalización de cada medición.
- Estimar usuarios concurrentes, frecuencia de operaciones y volúmenes de información.
- Definir las condiciones de dispositivo y conectividad utilizadas para verificar el requisito.
- Precisar los objetivos para archivos, reportes y otros procesos de mayor duración.
- Definir la duración de las pruebas, el tratamiento de errores y los criterios para aceptar sus resultados.

---

### RNF-007 — Disponibilidad del servicio

- ID: RNF-007.
- Nombre: Disponibilidad del servicio.
- Tipo: Requerimiento no funcional.
- Módulo o capacidad: Capacidad general compartida — Disponibilidad.
- Etapa prevista: Primera etapa del Propietario; deberá reevaluarse al incorporar nuevas capacidades y módulos.
- Estado de la definición: Propuesta; pendiente de definir los objetivos de disponibilidad y su método de medición.
- Actor relacionado: Usuario que necesita acceder a las funcionalidades de la solución.
- Prioridad: Por definir.
- Referencias relacionadas: Disponibilidad contemplada en el punto 28 de `proyecto.md`.
- Dependencias: Identificación de funcionalidades esenciales; horario de servicio; infraestructura y servicios externos utilizados; mecanismos de monitoreo.

#### Descripción

Vehículos Services deberá cumplir un objetivo de disponibilidad definido para las funcionalidades esenciales de la versión implementada durante el horario de servicio aprobado.

La disponibilidad deberá comprobarse mediante operaciones representativas que permitan verificar el funcionamiento del servicio. La existencia de un proceso activo o una respuesta técnica no deberá considerarse suficiente si la funcionalidad evaluada no puede utilizarse correctamente.

El método de medición deberá identificar el período evaluado, los intervalos de comprobación y las condiciones para considerar una funcionalidad disponible, degradada o no disponible.

Las interrupciones de servicios externos deberán distinguirse de los fallos propios, sin excluirse automáticamente del cálculo. Su tratamiento dependerá de la regla de medición aprobada.

Cuando falle una capacidad independiente, la solución deberá conservar las funcionalidades que puedan operar correctamente y comunicar la limitación correspondiente, según las dependencias definidas.

Este requisito no implicará funcionamiento sin conexión ni disponibilidad absoluta. El comportamiento de la aplicación ante pérdida de conectividad y la recuperación del servicio se definirán en los requisitos correspondientes.

#### Criterios de aceptación

1. Antes de verificar el requisito, estarán definidos el horario de servicio, el objetivo de disponibilidad, el período de medición y las funcionalidades evaluadas.
2. La disponibilidad medida cumplirá el objetivo aprobado durante el período correspondiente.
3. Las comprobaciones verificarán operaciones representativas y no únicamente que los componentes técnicos respondan.
4. Las interrupciones conservarán información sobre inicio, finalización, funcionalidades afectadas y causa identificada cuando esté disponible.
5. Los mantenimientos programados y fallos de servicios externos se tratarán conforme a las reglas aprobadas, sin exclusiones automáticas.
6. Una interrupción parcial se distinguirá de una indisponibilidad general.
7. Ante un fallo de una capacidad independiente, las funcionalidades que no dependan de ella continuarán disponibles conforme al alcance definido.
8. La aplicación no presentará una operación como completada si el servicio necesario no pudo ejecutarla o confirmar su resultado.

#### Decisiones pendientes

- Definir el horario de servicio y las funcionalidades esenciales.
- Definir el porcentaje objetivo de disponibilidad y el período de medición.
- Establecer la frecuencia y los escenarios de comprobación.
- Definir cuándo una degradación se considerará indisponibilidad.
- Precisar el tratamiento de mantenimientos programados y dependencias externas.
- Definir qué funcionalidades podrán mantenerse disponibles ante fallos parciales.
- Definir cómo se comunicarán las interrupciones y cómo se conservará la evidencia de disponibilidad.

---

### RNF-008 — Recuperación ante fallos

- ID: RNF-008.
- Nombre: Recuperación ante fallos.
- Tipo: Requerimiento no funcional.
- Módulo o capacidad: Capacidad general compartida — Recuperación y continuidad.
- Etapa prevista: Primera etapa del Propietario; deberá reevaluarse al incorporar nuevas capacidades y módulos.
- Estado de la definición: Propuesta; pendiente de definir los escenarios de fallo, tiempos de recuperación y límites de pérdida de información.
- Actor relacionado: Usuario afectado por una interrupción; personal autorizado para recuperar la operación.
- Prioridad: Por definir.
- Referencias relacionadas: Recuperación ante fallos contemplada en el punto 28 de `proyecto.md`; integridad conforme a RNF-004; auditoría conforme a RNF-005; disponibilidad conforme a RNF-007.
- Dependencias: Identificación de componentes y operaciones esenciales; mecanismos de recuperación y respaldo; procedimientos operativos; escenarios de fallo y objetivos aprobados.

#### Descripción

Vehículos Services deberá permitir restablecer las funcionalidades afectadas por los escenarios de fallo definidos, dentro de los objetivos de recuperación aprobados.

Cada escenario deberá identificar las funcionalidades afectadas, el punto desde el que se mide la recuperación, el tiempo máximo permitido y la pérdida máxima de información tolerable, cuando corresponda.

La recuperación deberá comprobar que los datos, archivos y relaciones necesarios para operar permanecen consistentes. Reiniciar un componente no deberá considerarse recuperación completa si las funcionalidades afectadas todavía no pueden utilizarse correctamente.

Las operaciones interrumpidas deberán tratarse conforme a RNF-004. Si no se conoce su resultado, la solución deberá permitir determinar si se completaron antes de repetirlas, evitando duplicar eventos o aplicar nuevamente un cambio aceptado.

Cuando sea necesario restaurar información, deberán verificarse su integridad, el punto temporal recuperado y las diferencias respecto de la información disponible antes del fallo. La restauración no deberá presentarse como recuperación de datos posteriores que no estén incluidos en ella.

El restablecimiento deberá conservar los controles de autenticación, autorización y protección de datos. No deberá habilitarse acceso general como medida para recuperar el servicio.

Este requisito no aprobará por sí solo operaciones sin conexión ni una estrategia técnica específica de recuperación. Esas decisiones se desarrollarán en los documentos correspondientes.

#### Criterios de aceptación

1. Antes de verificar el requisito, existirá una matriz de escenarios de fallo con sus funcionalidades afectadas, objetivos y condiciones de recuperación.
2. Las pruebas de recuperación cumplirán los tiempos y límites de pérdida de información aprobados para cada escenario.
3. La recuperación se confirmará mediante operaciones funcionales representativas y verificaciones de consistencia, no únicamente mediante el reinicio de componentes.
4. Las operaciones interrumpidas se resolverán conforme a sus reglas, sin generar duplicados por reintentos ni ocultar resultados todavía indeterminados.
5. Cuando se restaure información, se identificará el punto temporal recuperado y se verificarán los datos, archivos y relaciones incluidos.
6. Las funcionalidades cuyo estado no pueda comprobarse no se presentarán como recuperadas.
7. Los controles de acceso y protección de información permanecerán activos durante y después de la recuperación.
8. Cada prueba conservará evidencia del fallo simulado, las acciones realizadas, los tiempos, el resultado y las diferencias de información detectadas.
9. Las incidencias que impidan cumplir los objetivos se documentarán y corregirán antes de considerar satisfactorio el escenario evaluado.

#### Decisiones pendientes

- Definir los escenarios de fallo que deberán cubrirse inicialmente.
- Definir los tiempos máximos de recuperación y sus puntos de medición.
- Definir la pérdida máxima de información tolerable para cada escenario y cómo se comprobará.
- Precisar los procedimientos para resolver operaciones cuyo resultado quede indeterminado.
- Definir cuándo se utilizará restauración desde respaldos u otros mecanismos de recuperación.
- Identificar responsables y permisos para ejecutar los procedimientos.
- Definir la frecuencia de las pruebas y las condiciones para declarar restablecida la operación.

---

### RNF-009 — Respaldo y restauración de información

- ID: RNF-009.
- Nombre: Respaldo y restauración de información.
- Tipo: Requerimiento no funcional.
- Módulo o capacidad: Capacidad general compartida — Respaldo de información.
- Etapa prevista: Primera etapa del Propietario; aplicable posteriormente a los componentes incorporados.
- Estado de la definición: Propuesta; pendiente de definir el alcance, frecuencia, conservación y verificaciones de los respaldos.
- Actor relacionado: Personal o proceso autorizado para generar respaldos y restaurar información.
- Prioridad: Por definir.
- Referencias relacionadas: Respaldo contemplado en el punto 28 de `proyecto.md`; protección de datos conforme a RNF-003; integridad conforme a RNF-004; objetivos de recuperación conforme a RNF-008.
- Dependencias: Identificación de información y componentes necesarios para restaurar la solución; almacenamiento de respaldos; procedimientos de generación, protección y restauración.

#### Descripción

Vehículos Services deberá generar y conservar respaldos de la información necesaria para recuperar las funcionalidades incluidas en el alcance aprobado.

El respaldo deberá contemplar los datos, archivos, relaciones y configuraciones necesarios para la restauración, según los componentes implementados. Copiar únicamente los registros de datos no deberá considerarse suficiente cuando su utilización dependa de archivos u otros elementos que no puedan recuperarse.

Los elementos respaldados deberán permitir restaurar un conjunto consistente. Cuando se generen copias desde componentes diferentes, deberá existir un procedimiento para comprobar que corresponden a un punto de recuperación compatible.

La frecuencia y conservación deberán responder a los objetivos de RNF-008. Cada respaldo deberá permitir identificar su alcance, momento, estado de generación y condiciones necesarias para utilizarlo.

Las copias deberán protegerse conforme a su clasificación y quedar accesibles únicamente para personas o procesos autorizados. La estrategia deberá evitar que un fallo o eliminación en el almacenamiento principal afecte automáticamente todas las copias utilizables.

La generación satisfactoria de una copia no deberá considerarse prueba suficiente de su utilidad. Su restauración deberá comprobarse periódicamente en un entorno autorizado, verificando los datos y relaciones recuperados.

#### Criterios de aceptación

1. Existirá un inventario aprobado de la información y los componentes incluidos en el respaldo, con las exclusiones justificadas.
2. Los respaldos se generarán y conservarán conforme a la frecuencia y los períodos definidos.
3. Cada copia permitirá identificar su alcance, momento y resultado de generación.
4. Un respaldo incompleto o fallido no se presentará como una copia válida para restauración.
5. La restauración de una copia válida recuperará un conjunto consistente de datos, archivos y relaciones dentro de su alcance.
6. El acceso, uso y eliminación de respaldos requerirán los permisos definidos y respetarán RNF-003.
7. Los escenarios de fallo del almacenamiento principal previstos en la estrategia no inutilizarán automáticamente todas las copias de recuperación.
8. Las pruebas de restauración conservarán evidencia de la copia utilizada, el punto temporal recuperado, las verificaciones realizadas y su resultado.
9. La frecuencia de respaldo y los resultados de restauración serán compatibles con los objetivos aprobados en RNF-008.
10. La eliminación de copias se realizará conforme a las reglas de conservación, sin retirar respaldos que deban mantenerse vigentes.

#### Decisiones pendientes

- Definir los datos, archivos y configuraciones incluidos, así como las exclusiones y su justificación.
- Definir la frecuencia de generación y los períodos de conservación.
- Definir cómo se obtendrá un punto de recuperación consistente entre componentes.
- Definir la separación y protección de las copias respecto del almacenamiento principal.
- Precisar los permisos y procedimientos de generación, restauración y eliminación.
- Definir la frecuencia, el entorno y el alcance de las pruebas de restauración.
- Definir cómo se detectarán y comunicarán respaldos fallidos o copias que no puedan restaurarse.

---

### RNF-010 — Usabilidad de la aplicación

- ID: RNF-010.
- Nombre: Usabilidad de la aplicación.
- Tipo: Requerimiento no funcional.
- Módulo o capacidad: Capacidad general compartida — Experiencia de usuario.
- Etapa prevista: Primera etapa del Propietario; aplicable posteriormente a las funcionalidades incorporadas.
- Estado de la definición: Propuesta; pendiente de definir los escenarios y objetivos medibles de evaluación.
- Actor relacionado: Usuario de la aplicación móvil.
- Prioridad: Por definir.
- Referencias relacionadas: Usabilidad contemplada en el punto 28 de `proyecto.md`; diseño de experiencia e interfaz previsto en `ux-ui.md`; compatibilidad conforme a RNF-001.
- Dependencias: Requisitos funcionales de la versión; diseño de UX/UI; definición de perfiles de usuario, tareas y condiciones de evaluación.

#### Descripción

Vehículos Services deberá permitir que los usuarios comprendan y completen las tareas incluidas en su alcance mediante una navegación, terminología y presentación coherentes.

La interfaz deberá identificar el vehículo y, cuando corresponda, la persona jurídica o el contexto bajo el cual se realiza una acción. El usuario deberá poder reconocer sobre qué información está operando antes de confirmar un cambio.

Los formularios deberán distinguir campos obligatorios, opcionales y no aplicables. Los mensajes de validación deberán identificar el problema y orientar sobre cómo resolverlo, sin exigir conocimientos de implementación.

La aplicación deberá diferenciar las operaciones en procesamiento, completadas, rechazadas y aquellas cuyo resultado todavía no pueda confirmarse. También deberá distinguir la ausencia de registros, la insuficiencia de información y un error al consultar.

La terminología conservará las diferencias funcionales entre mantenimiento, reparación, revisión, alerta, recomendación y notificación. Su presentación no deberá atribuir a una acción un significado distinto del establecido en sus requisitos.

Los objetivos de usabilidad deberán evaluarse mediante tareas representativas con participantes correspondientes a los perfiles previstos. Se definirán medidas como finalización correcta, tiempo, errores y asistencia requerida, según la tarea.

Este requisito no determinará por sí solo la distribución de pantallas ni un número fijo de pasos. Esas decisiones se desarrollarán y evaluarán en `ux-ui.md`.

#### Criterios de aceptación

1. Antes de verificar el requisito, estarán definidos los perfiles, tareas, condiciones y objetivos de la evaluación.
2. Los participantes completarán las tareas dentro de los objetivos aprobados de finalización, tiempo, errores y asistencia.
3. Las pantallas de consulta y modificación permitirán reconocer el vehículo y el contexto correspondiente cuando sean necesarios para interpretar o realizar la acción.
4. Los formularios identificarán los campos obligatorios y comunicarán los errores de validación junto con una orientación para corregirlos.
5. Los mensajes distinguirán una operación completada de una rechazada, en procesamiento o con resultado todavía indeterminado.
6. La ausencia de registros no se presentará como error de consulta ni como confirmación de que no existe una necesidad de mantenimiento.
7. La terminología utilizada conservará las diferencias establecidas en los requisitos funcionales.
8. Los problemas detectados se documentarán indicando la tarea afectada, su impacto y el resultado de su corrección o tratamiento.
9. La evaluación contemplará Android e iOS dentro de las configuraciones soportadas, considerando las diferencias de interacción previstas para cada plataforma.

#### Decisiones pendientes

- Definir los perfiles de usuario que participarán en la evaluación.
- Seleccionar las tareas representativas de la primera etapa.
- Definir las medidas y los umbrales de aceptación para cada tarea.
- Definir el número de participantes y las condiciones de asistencia durante las pruebas.
- Precisar los mensajes, términos y patrones de interacción en `ux-ui.md`.
- Definir cómo se clasificarán los problemas encontrados y cuáles deberán resolverse antes de liberar la versión.

---

### RNF-011 — Accesibilidad de la aplicación

- ID: RNF-011.
- Nombre: Accesibilidad de la aplicación.
- Tipo: Requerimiento no funcional.
- Módulo o capacidad: Capacidad general compartida — Accesibilidad.
- Etapa prevista: Primera etapa del Propietario; aplicable posteriormente a las funcionalidades incorporadas.
- Estado de la definición: Propuesta; pendiente de definir el alcance de accesibilidad, los criterios técnicos y las condiciones de verificación.
- Actor relacionado: Usuario de la aplicación, incluyendo personas que utilizan funciones de accesibilidad del dispositivo.
- Prioridad: Por definir.
- Referencias relacionadas: Accesibilidad contemplada en el punto 28 de `proyecto.md`; diseño previsto en `ux-ui.md`; compatibilidad conforme a RNF-001; usabilidad conforme a RNF-010.
- Dependencias: Diseño de interfaz; configuraciones soportadas; identificación de tareas esenciales y tecnologías de asistencia incluidas en la evaluación.

#### Descripción

Vehículos Services deberá permitir realizar las tareas esenciales mediante las funciones de accesibilidad incluidas en el alcance aprobado para Android e iOS.

Los controles deberán contar con una identificación comprensible de su propósito y estado. La navegación mediante tecnologías de asistencia deberá seguir un orden coherente y permitir alcanzar las acciones necesarias para completar cada tarea.

La información relevante no deberá comunicarse únicamente mediante color, posición, imágenes o sonido. Los estados de mantenimiento, errores, alertas y resultados deberán contar con una alternativa perceptible dentro de las modalidades soportadas.

La interfaz deberá admitir los ajustes de tamaño de texto definidos para la compatibilidad de la aplicación, sin ocultar información necesaria ni impedir el uso de sus controles. Los textos y elementos visuales deberán cumplir los criterios de contraste y legibilidad que se aprueben.

Los formularios deberán permitir identificar los campos, su obligatoriedad y los errores correspondientes mediante las tecnologías de asistencia soportadas. Los cambios relevantes de estado deberán comunicarse sin depender exclusivamente de una modificación visual.

Cuando una interacción utilice gestos u otras acciones que no puedan realizarse mediante las tecnologías de asistencia contempladas, deberá existir una alternativa accesible para completar la tarea.

Las condiciones técnicas y el diseño detallado se desarrollarán en `ux-ui.md` y en los documentos de implementación y pruebas correspondientes.

#### Criterios de aceptación

1. Antes de verificar el requisito, estarán definidos las tareas esenciales, las tecnologías de asistencia, las configuraciones y los criterios de accesibilidad evaluados.
2. Las tareas seleccionadas podrán completarse mediante las tecnologías de asistencia incluidas en el alcance, sin controles indispensables inaccesibles.
3. Los controles comunicarán su propósito y, cuando corresponda, su estado y valor.
4. El orden de navegación permitirá comprender y completar las tareas sin saltos que impidan acceder a información o acciones necesarias.
5. Los errores, alertas y estados funcionales no dependerán únicamente del color, de una imagen o de un sonido para comunicar su significado.
6. Los ajustes de tamaño de texto contemplados no ocultarán contenido necesario ni impedirán operar los controles.
7. Los elementos evaluados cumplirán los criterios aprobados de contraste, legibilidad y dimensiones de interacción.
8. Los campos obligatorios, errores de validación y cambios relevantes de estado podrán identificarse mediante las tecnologías de asistencia soportadas.
9. Las interacciones indispensables basadas en gestos tendrán una alternativa accesible cuando el gesto no sea utilizable en las condiciones evaluadas.
10. Las pruebas conservarán evidencia de las tareas, configuraciones, resultados y barreras detectadas en Android e iOS.

#### Decisiones pendientes

- Definir los criterios o referencias de accesibilidad que se adoptarán y su alcance de cumplimiento.
- Definir las tecnologías de asistencia y configuraciones incluidas en la primera etapa.
- Seleccionar las tareas esenciales para la evaluación.
- Definir los límites de ajuste de texto y los criterios de contraste, legibilidad y dimensiones de interacción.
- Precisar las alternativas para gestos y contenidos visuales o sonoros que se incorporen.
- Definir las pruebas automáticas y manuales necesarias.
- Definir qué barreras deberán resolverse antes de liberar la versión y cómo se verificará su corrección.

---

### RNF-012 — Comportamiento ante conectividad limitada o interrumpida

- ID: RNF-012.
- Nombre: Comportamiento ante conectividad limitada o interrumpida.
- Tipo: Requerimiento no funcional.
- Módulo o capacidad: Capacidad general compartida — Confiabilidad de la aplicación móvil.
- Etapa prevista: Primera etapa del Propietario; aplicable posteriormente a las funcionalidades incorporadas.
- Estado de la definición: Propuesta; pendiente de definir el comportamiento de cada operación y el alcance del almacenamiento local.
- Actor relacionado: Usuario de la aplicación móvil.
- Prioridad: Por definir.
- Referencias relacionadas: Recuperación ante fallos y usabilidad contempladas en el punto 28 de `proyecto.md`; integridad conforme a RNF-004; recuperación conforme a RNF-008; comunicación de estados conforme a RNF-010.
- Dependencias: Identificación de operaciones que requieren conexión; mecanismos de confirmación y reintento; decisiones sobre información local; protección conforme a RNF-002 y RNF-003.

#### Descripción

Vehículos Services deberá gestionar la pérdida, demora o inestabilidad de conexión sin presentar operaciones no confirmadas como completadas ni comprometer la integridad de la información.

La aplicación deberá comunicar cuándo no puede consultar información o confirmar el resultado de una acción. La imposibilidad de consultar no deberá interpretarse como ausencia de registros.

Si la conexión se interrumpe durante una operación, la plataforma deberá distinguir entre un fallo confirmado y un resultado todavía indeterminado. No recibir una respuesta no deberá considerarse prueba suficiente de que la operación no se ejecutó.

Cuando se restablezca la conexión, la solución deberá comprobar el resultado de las operaciones indeterminadas conforme al mecanismo aprobado antes de repetir cambios que puedan generar duplicados.

La conservación de formularios, borradores o información previamente consultada dependerá del alcance que se defina. Si se habilita información local, deberá identificarse su condición y respetar los controles de acceso y protección aplicables.

Este requisito no aprobará por sí solo la creación o modificación de registros sin conexión ni su sincronización posterior. Si esas capacidades se incorporan, requerirán una definición funcional y reglas de resolución de conflictos.

#### Criterios de aceptación

1. Cuando una consulta no pueda completarse por un problema de conexión, la aplicación indicará esa limitación sin mostrarla como ausencia de información.
2. Una operación sin confirmación no se presentará como completada.
3. La falta de respuesta no provocará automáticamente que una operación se clasifique como no ejecutada.
4. Las operaciones con resultado indeterminado podrán comprobarse conforme al procedimiento definido al recuperar la conectividad.
5. Los reintentos respetarán RNF-004 y no aplicarán dos veces una misma operación.
6. La aplicación mantendrá una navegación utilizable y comunicará la situación conforme al diseño aprobado durante los escenarios de conexión limitada evaluados.
7. Si se habilita la consulta de información local, esta se identificará como información previamente obtenida y no como una consulta actual confirmada.
8. Si se conservan borradores, estos no se presentarán como registros aceptados por la plataforma.
9. La recuperación de la conexión no concederá permisos revocados ni omitirá las validaciones requeridas para ejecutar operaciones pendientes.
10. Las pruebas cubrirán interrupciones antes del envío, durante el procesamiento y antes de recibir la confirmación.

#### Decisiones pendientes

- Identificar las operaciones que requieren conexión y su comportamiento ante interrupciones.
- Definir los tiempos de espera y las condiciones para permitir o ejecutar reintentos.
- Definir cómo se comprobarán los resultados indeterminados.
- Definir si se conservarán formularios o borradores, durante cuánto tiempo y con qué protección.
- Definir si se permitirá consultar información local y cómo se indicarán su antigüedad y alcance.
- Precisar el comportamiento al cerrar la aplicación o la sesión con operaciones pendientes.
- Definir las condiciones de conectividad utilizadas en las pruebas.

---

### RNF-013 — Escalabilidad de la solución

- ID: RNF-013.
- Nombre: Escalabilidad de la solución.
- Tipo: Requerimiento no funcional.
- Módulo o capacidad: Capacidad general compartida — Escalabilidad.
- Etapa prevista: Primera etapa del Propietario; deberá reevaluarse al incorporar nuevas capacidades y módulos.
- Estado de la definición: Propuesta; pendiente de definir los escenarios de crecimiento y los límites de capacidad.
- Actor relacionado: Usuario de la solución; personal responsable de su operación.
- Prioridad: Por definir.
- Referencias relacionadas: Escalabilidad contemplada en los puntos 28 y 50 de `proyecto.md`; rendimiento conforme a RNF-006; disponibilidad conforme a RNF-007.
- Dependencias: Proyección de crecimiento; volúmenes y concurrencia previstos; arquitectura; infraestructura y dependencias externas; objetivos de rendimiento y disponibilidad.

#### Descripción

Vehículos Services deberá permitir aumentar su capacidad para atender el crecimiento aprobado de usuarios, vehículos, registros históricos, documentos y operaciones.

Los escenarios deberán considerar tanto el aumento de solicitudes simultáneas como la acumulación de información a lo largo del tiempo. Una prueba con mayor concurrencia no deberá considerarse suficiente para comprobar el comportamiento frente a historiales o volúmenes de archivos más grandes.

La ampliación de capacidad deberá mantener los objetivos aplicables de rendimiento y disponibilidad, junto con los controles de seguridad e integridad.

La arquitectura deberá identificar las dependencias y límites que puedan restringir el crecimiento. Cuando una ampliación requiera cambios de configuración, recursos o componentes, deberán documentarse las condiciones y el procedimiento correspondiente.

No deberá asumirse que el crecimiento será ilimitado ni que la ampliación se realizará automáticamente. El mecanismo y los límites se definirán en arquitectura y operación.

Este requisito no aprobará capacidades funcionales todavía pendientes ni obligará a implementar anticipadamente el módulo del Prestador.

#### Criterios de aceptación

1. Antes de verificar el requisito, existirán escenarios de crecimiento con volúmenes, concurrencia y objetivos de servicio definidos.
2. La solución atenderá cada escenario aprobado con la capacidad prevista para él, cumpliendo los objetivos correspondientes de RNF-006 y RNF-007.
3. Las pruebas incluirán crecimiento de información acumulada y de solicitudes simultáneas.
4. La ampliación de capacidad no provocará pérdida de registros, duplicación de eventos ni omisión de controles de acceso.
5. Estarán identificados los límites de los componentes y servicios externos que afecten los escenarios evaluados.
6. Los procedimientos de ampliación permitirán comprobar el estado de la solución antes y después del cambio.
7. La evidencia de prueba identificará la configuración utilizada, la carga, los volúmenes y los resultados obtenidos.
8. Los escenarios que excedan la capacidad disponible no se presentarán como soportados sin una ampliación y verificación satisfactorias.

#### Decisiones pendientes

- Estimar el crecimiento inicial de usuarios, vehículos, eventos, archivos y operaciones.
- Definir los escenarios de capacidad y el horizonte temporal de cada uno.
- Definir los objetivos de servicio que deberán mantenerse en cada escenario.
- Identificar límites y restricciones de infraestructura y servicios externos.
- Definir cómo se detectará la necesidad de ampliar capacidad.
- Determinar si la ampliación será manual, automática o mediante una combinación de mecanismos.
- Definir los procedimientos y verificaciones de ampliación en arquitectura y operación.

---

### RNF-014 — Observabilidad y monitoreo de la solución

- ID: RNF-014.
- Nombre: Observabilidad y monitoreo de la solución.
- Tipo: Requerimiento no funcional.
- Módulo o capacidad: Capacidad general compartida — Operación y diagnóstico técnico.
- Etapa prevista: Primera etapa del Propietario; aplicable posteriormente a los componentes incorporados.
- Estado de la definición: Propuesta; pendiente de definir las señales, umbrales, responsables y condiciones de monitoreo.
- Actor relacionado: Personal autorizado responsable de supervisar y atender la operación.
- Prioridad: Por definir.
- Referencias relacionadas: Observabilidad, logging y monitoreo contemplados en el punto 28 de `proyecto.md`; seguridad de logs y auditoría conforme a `67.9`; rendimiento conforme a RNF-006; disponibilidad conforme a RNF-007.
- Dependencias: Inventario de componentes y dependencias; objetivos de servicio; mecanismos de recopilación y consulta de información operativa; protección conforme a RNF-002 y RNF-003.

#### Descripción

Vehículos Services deberá proporcionar información operativa que permita conocer el estado de sus componentes, detectar fallos o degradaciones e investigar su efecto sobre las funcionalidades.

El monitoreo deberá contemplar los componentes y dependencias necesarios para prestar el servicio, así como las operaciones representativas definidas para verificar su disponibilidad.

Las señales podrán incluir tiempos de respuesta, errores, utilización de recursos y estado de procesos, según el alcance aprobado. Cada señal deberá tener un significado, una forma de medición y una condición de evaluación definidos.

Los registros técnicos deberán permitir relacionar las etapas de una operación cuando sea necesario para investigar un incidente. Su contenido deberá limitarse a la información útil para esa finalidad, sin incluir secretos ni datos sensibles innecesarios.

Los registros técnicos y las evidencias de auditoría de RNF-005 conservarán finalidades diferenciadas. El diagnóstico de un error no deberá sustituir la evidencia de una acción que requiera auditoría.

Las condiciones operativas que requieran atención deberán generar avisos al personal responsable conforme a los umbrales y canales aprobados. Estos avisos se distinguirán de las alertas vehiculares y notificaciones al Propietario.

#### Criterios de aceptación

1. Existirá un inventario de componentes, señales y condiciones de monitoreo antes de verificar el requisito.
2. El personal autorizado podrá consultar el estado de los componentes incluidos y la información necesaria para investigar los escenarios definidos.
3. Las mediciones de rendimiento y disponibilidad serán coherentes con RNF-006 y RNF-007.
4. Las pruebas de fallos y degradaciones contempladas producirán las señales y avisos operativos esperados.
5. Cuando el escenario lo requiera, podrá relacionarse una solicitud con sus etapas de procesamiento sin exponer secretos de acceso.
6. Los registros técnicos no incluirán contraseñas, secretos de sesión ni contenido sensible innecesario.
7. La consulta de información operativa y la modificación de su configuración estarán sujetas a permisos.
8. Los avisos operativos identificarán la condición detectada, el componente o funcionalidad afectada y el momento correspondiente.
9. Una interrupción del propio monitoreo se distinguirá de una confirmación de que el servicio funciona correctamente.
10. Los registros técnicos no se utilizarán como sustituto de las evidencias obligatorias de auditoría.

#### Decisiones pendientes

- Definir los componentes, dependencias y operaciones que se supervisarán.
- Definir las señales, intervalos de medición y umbrales de aviso.
- Definir los responsables, canales y tratamiento de avisos repetidos.
- Precisar los datos de correlación necesarios para investigar operaciones e incidentes.
- Definir los permisos y períodos de conservación de la información operativa.
- Definir cómo se detectarán fallos en la recopilación de señales o en el envío de avisos.
- Definir los escenarios de prueba y las evidencias de detección y diagnóstico.

---

### RNF-015 — Mantenibilidad y evolución modular

- ID: RNF-015.
- Nombre: Mantenibilidad y evolución modular.
- Tipo: Requerimiento no funcional.
- Módulo o capacidad: Capacidad general compartida — Mantenibilidad.
- Etapa prevista: Primera etapa del Propietario; aplicable durante la evolución de la solución.
- Estado de la definición: Propuesta; pendiente de definir los criterios de separación, documentación y verificación de cambios.
- Actor relacionado: Equipo responsable del desarrollo y mantenimiento.
- Prioridad: Por definir.
- Referencias relacionadas: Mantenibilidad contemplada en el punto 28 de `proyecto.md`; desarrollo modular y progresivo conforme a `9.1`; documentos complementarios de arquitectura y diseño.
- Dependencias: Definición de componentes y responsabilidades; gestión de versiones; documentación técnica; procedimientos de pruebas y liberación.

#### Descripción

Vehículos Services deberá organizarse en componentes con responsabilidades y dependencias documentadas que permitan identificar, modificar y verificar las partes afectadas por un cambio.

La primera etapa del Propietario deberá poder desarrollarse y operar sin requerir la implementación del módulo del Prestador. Las capacidades generales compartidas deberán contar con una responsabilidad definida para evitar implementaciones independientes y contradictorias.

Los cambios deberán conservar su relación con los requisitos o decisiones que los originan. La documentación necesaria para comprender interfaces, reglas y dependencias deberá actualizarse cuando esos elementos cambien.

Las modificaciones deberán verificarse sobre el comportamiento afectado y sus dependencias. La incorporación de una capacidad nueva no deberá alterar silenciosamente funcionalidades previamente aceptadas.

Cuando un cambio requiera transformar datos existentes, deberán definirse y comprobarse el procedimiento, las validaciones y las medidas de recuperación. La evolución no deberá reiniciar el historial de los vehículos para adaptar la información a una nueva versión.

Este requisito no seleccionará lenguajes, frameworks ni una estructura técnica concreta. Esas decisiones se documentarán en arquitectura y diseño.

#### Criterios de aceptación

1. La documentación identificará los componentes, sus responsabilidades y dependencias correspondientes a la versión implementada.
2. El módulo del Propietario podrá ejecutarse dentro de su alcance aprobado sin depender de componentes exclusivos del Prestador todavía no implementados.
3. Las capacidades generales compartidas tendrán una implementación y responsabilidad identificables, evitando duplicaciones que produzcan comportamientos contradictorios.
4. Cada cambio podrá relacionarse con su requisito, incidencia o decisión de origen.
5. Los cambios en interfaces, reglas o dependencias incluirán la actualización de la documentación afectada.
6. La verificación de una modificación incluirá el comportamiento cambiado y los escenarios existentes que puedan verse afectados.
7. Las transformaciones de datos se probarán con información representativa y conservarán las relaciones y trazabilidad exigidas.
8. Una actualización no reiniciará ni eliminará el historial para resolver incompatibilidades con la nueva versión.
9. Las modificaciones incompatibles se identificarán expresamente y contarán con un procedimiento aprobado de transición.

#### Decisiones pendientes

- Definir los límites, responsabilidades y dependencias de los componentes.
- Definir la documentación técnica mínima y sus responsables.
- Establecer cómo se relacionarán los cambios con requisitos, incidencias y decisiones.
- Definir las verificaciones exigidas según el impacto de cada modificación.
- Definir el tratamiento de cambios incompatibles en interfaces y estructuras de datos.
- Precisar los procedimientos de transformación, liberación y recuperación de versiones.
- Definir las evidencias necesarias para comprobar la separación modular y la conservación del comportamiento aceptado.

---

### RNF-016 — Consistencia y trazabilidad de resultados derivados

- ID: RNF-016.
- Nombre: Consistencia y trazabilidad de resultados derivados.
- Tipo: Requerimiento no funcional.
- Módulo o capacidad: Capacidad general compartida — Calidad de cálculos y recomendaciones.
- Etapa prevista: Primera etapa del Propietario; aplicable posteriormente a las capacidades incorporadas.
- Estado de la definición: Propuesta; pendiente de definir la información de respaldo y los escenarios de verificación de cada resultado.
- Actor relacionado: Usuario que consulta resultados derivados; personal autorizado para verificar su cálculo.
- Prioridad: Por definir.
- Referencias relacionadas: Consistencia y trazabilidad de recomendaciones contempladas en el punto 28 de `proyecto.md`; seguimiento conforme a `63.11`; reglas de negocio y requisitos funcionales de cada resultado.
- Dependencias: Reglas aprobadas; identificación de datos de entrada y referencias temporales; tratamiento de información incompleta; actualización de resultados conforme a RNF-004.

#### Descripción

Vehículos Services deberá producir resultados derivados coherentes con las reglas y la información utilizadas, permitiendo reconstruir su origen dentro del alcance definido.

Este requisito comprenderá los cálculos, estados, alertas y recomendaciones generados por la plataforma. La condición de creación y el significado de cada resultado se conservarán en sus requisitos funcionales correspondientes.

Con los mismos datos de entrada, reglas, unidades y referencias temporales, la plataforma deberá obtener resultados equivalentes conforme a las precisiones y tolerancias aprobadas.

Cada resultado deberá conservar o permitir reconstruir la relación con los registros utilizados, la definición de la regla aplicada y el momento de evaluación cuando influya en el cálculo. No será necesario duplicar todos los datos si existe un mecanismo que preserve esa relación y permita verificarlos.

Los cambios de reglas o datos deberán permitir distinguir una evaluación anterior de una actualizada. La plataforma no deberá atribuir un resultado histórico a una regla o información que no fue utilizada para producirlo.

La falta de información, los resultados parciales y los valores calculados deberán mantenerse diferenciados. Las recomendaciones conservarán su carácter orientativo conforme a sus RF, sin convertirse en diagnósticos por el hecho de contar con trazabilidad.

La información de respaldo que se muestre al usuario respetará sus permisos. La capacidad de verificar internamente un resultado no concederá acceso automático a datos restringidos.

#### Criterios de aceptación

1. Los escenarios de prueba tendrán datos de entrada, reglas y resultados esperados definidos.
2. La repetición de una evaluación con las mismas condiciones producirá resultados equivalentes dentro de las tolerancias aprobadas.
3. Cada resultado permitirá identificar o reconstruir los datos, la regla y la referencia temporal necesarios para verificarlo.
4. Una modificación de datos o reglas no cambiará silenciosamente la procedencia de resultados históricos conservados.
5. La información insuficiente no se sustituirá por valores supuestos para obtener un resultado aparentemente completo.
6. Los resultados parciales indicarán qué condiciones pudieron evaluarse y cuáles quedaron sin determinar.
7. Los cálculos respetarán las unidades, precisiones y reglas de redondeo aprobadas.
8. Las pruebas incluirán valores límite, condiciones combinadas, información incompleta y modificaciones de datos o reglas.
9. La consulta de información de respaldo no expondrá datos para los que el usuario carezca de autorización.

#### Decisiones pendientes

- Definir qué información se conservará para reconstruir cada tipo de resultado y durante cuánto tiempo.
- Definir cómo se identificarán las reglas aplicadas y sus cambios.
- Precisar las referencias temporales, unidades, precisiones y tolerancias de los cálculos.
- Definir cuándo se conservarán evaluaciones anteriores y cómo se distinguirán de las actualizadas.
- Definir qué información de respaldo podrá consultar el usuario y cuál quedará restringida a verificación interna.
- Definir los escenarios y evidencias necesarios para verificar cada capacidad de cálculo o recomendación.

---

### RNF-017 — Configuración y evolución de reglas

- ID: RNF-017.
- Nombre: Configuración y evolución de reglas.
- Tipo: Requerimiento no funcional.
- Módulo o capacidad: Capacidad general compartida — Evolución de reglas de negocio.
- Etapa prevista: Primera etapa del Propietario, según las reglas configurables incluidas en su alcance.
- Estado de la definición: Propuesta; pendiente de definir qué condiciones serán configurables y los límites del mecanismo.
- Actor relacionado: Actor autorizado para establecer o modificar reglas, conforme a los requisitos funcionales correspondientes.
- Prioridad: Por definir.
- Referencias relacionadas: Capacidad de actualizar reglas sin modificar necesariamente el código contemplada en el punto 28 de `proyecto.md`; establecimiento y modificación de reglas conforme a RF-033 y RF-034; trazabilidad de resultados conforme a RNF-016.
- Dependencias: Definición de reglas y parámetros configurables; validaciones y permisos; mecanismos de aplicación, conservación y verificación de cambios.

#### Descripción

Vehículos Services deberá permitir actualizar los parámetros y condiciones expresamente definidos como configurables mediante el mecanismo aprobado, sin requerir cambios de código ni una nueva versión de la aplicación móvil para cada ajuste de esos valores.

El alcance configurable deberá documentarse. No deberá asumirse que cualquier fórmula, comportamiento o condición nueva puede incorporarse mediante configuración.

Antes de aplicar un cambio, la plataforma deberá comprobar que los valores y combinaciones sean válidos dentro del mecanismo soportado. Una configuración inválida no deberá sustituir la definición vigente ni utilizarse para producir resultados.

El establecimiento, modificación y aplicación de reglas se regirán por sus requisitos funcionales. Este punto no concederá permisos adicionales ni determinará por sí solo si un cambio afecta ciclos activos, futuros o históricos.

La evolución deberá conservar la identificación de las definiciones utilizadas y permitir comprobar sus efectos sobre los resultados conforme a RNF-016.

Los cambios que excedan el alcance configurable deberán tratarse mediante el procedimiento de desarrollo y verificación correspondiente, sin presentarse como ajustes ordinarios de parámetros.

#### Criterios de aceptación

1. Existirá un catálogo de parámetros y condiciones configurables, con sus valores admitidos y restricciones.
2. Los cambios incluidos en ese catálogo podrán aplicarse mediante el mecanismo aprobado sin modificar código ni publicar una nueva versión móvil por cada ajuste.
3. Los valores o combinaciones inválidos serán rechazados sin reemplazar la configuración vigente.
4. Solo los actores autorizados podrán establecer o modificar las configuraciones correspondientes.
5. La aplicación de un cambio respetará RF-034 y las reglas funcionales que determinen su alcance.
6. Los resultados producidos permitirán identificar la definición aplicada conforme a RNF-016.
7. Las pruebas comprobarán el comportamiento antes y después de cambios representativos, incluyendo configuraciones inválidas y valores límite.
8. Una condición no soportada por el mecanismo no se aplicará como si fuera una configuración válida.

#### Decisiones pendientes

- Definir las reglas, parámetros y condiciones configurables en la primera etapa.
- Definir sus restricciones y validaciones.
- Determinar el mecanismo de configuración en arquitectura y diseño.
- Precisar cuándo un cambio requerirá desarrollo y una nueva versión.
- Definir cómo se comprobarán y activarán los cambios, conforme a los permisos y procedimientos funcionales.
- Definir el tratamiento de una configuración aplicada que deba retirarse o sustituirse, conservando su trazabilidad.

---

### RNF-018 — Validación y procesamiento seguro de archivos

- ID: RNF-018.
- Nombre: Validación y procesamiento seguro de archivos.
- Tipo: Requerimiento no funcional.
- Módulo o capacidad: Capacidad general compartida — Seguridad de documentos y archivos.
- Etapa prevista: Primera etapa del Propietario; aplicable posteriormente a las capacidades que incorporen archivos.
- Estado de la definición: Propuesta; pendiente de definir los controles de validación y el tratamiento de archivos rechazados o pendientes.
- Actor relacionado: Usuario que incorpora o consulta archivos; proceso autorizado que los valida o procesa.
- Prioridad: Por definir.
- Referencias relacionadas: Seguridad de documentos y archivos conforme a `67.6` de `proyecto.md`; carga de documentos conforme a RF-010; control de acceso conforme a RNF-002; protección de información conforme a RNF-003.
- Dependencias: Formatos y límites aprobados; arquitectura de almacenamiento; mecanismos de validación y procesamiento; reglas de acceso a archivos.

#### Descripción

Vehículos Services deberá validar los archivos recibidos antes de habilitarlos para los usos que requieran esa validación, aplicando controles sobre formato, tamaño, contenido y condiciones de procesamiento conforme al alcance aprobado.

Las comprobaciones deberán realizarse en el servidor. El nombre, la extensión o el tipo declarado por la aplicación no deberán considerarse suficientes por sí solos para aceptar un archivo.

Los archivos pendientes de validación deberán mantenerse diferenciados de los aceptados. No deberán presentarse como disponibles para usos que requieran comprobaciones todavía no completadas.

Los archivos rechazados deberán tratarse mediante un procedimiento definido, evitando su publicación o procesamiento ordinario. Los componentes de análisis autorizados podrán examinarlos bajo las condiciones de seguridad correspondientes.

El procesamiento deberá respetar límites de recursos y duración para evitar que un archivo comprometa el funcionamiento del servicio. Los límites técnicos se definirán en arquitectura y seguridad.

La validación de seguridad no deberá presentarse como comprobación de autenticidad documental, propiedad del vehículo o veracidad del contenido. Esas comprobaciones conservarán sus procedimientos específicos.

#### Criterios de aceptación

1. Las validaciones se aplicarán en el servidor aunque la aplicación haya realizado comprobaciones previas.
2. Cambiar el nombre, la extensión o el tipo declarado de un archivo no permitirá eludir las comprobaciones aprobadas.
3. Los archivos que incumplan los formatos, límites o controles definidos serán rechazados para el uso correspondiente.
4. Los archivos pendientes de validación no se mostrarán como aceptados ni se habilitarán para usos que requieran esa validación.
5. Los archivos rechazados no quedarán disponibles mediante las consultas ordinarias de documentos.
6. Si una comprobación requerida no puede completarse, el archivo no se marcará automáticamente como aprobado.
7. El procesamiento respetará los límites de recursos y duración establecidos y conservará un resultado identificable cuando no pueda completarse.
8. El almacenamiento y la consulta mantendrán los controles de RNF-002 y RNF-003.
9. La aceptación de seguridad no se mostrará como certificación de autenticidad ni validación de propiedad.
10. Las pruebas incluirán archivos permitidos, formatos no admitidos, contenido que no corresponda con el tipo declarado y casos que excedan los límites aprobados.

#### Decisiones pendientes

- Definir los formatos, tamaños y límites de procesamiento, en coherencia con RF-010.
- Definir las comprobaciones de contenido y los mecanismos de análisis en `seguridad.md`.
- Definir los estados de validación y las operaciones permitidas en cada uno.
- Precisar el tratamiento, conservación y eliminación de archivos rechazados o incompletos.
- Definir el comportamiento ante fallos o indisponibilidad de los mecanismos de validación.
- Definir los límites de recursos y duración del procesamiento.
- Definir los escenarios y evidencias de prueba, incluyendo contenido de prueba controlado para verificar los rechazos.

---

### RNF-019 — Protección de secretos y configuración sensible

- ID: RNF-019.
- Nombre: Protección de secretos y configuración sensible.
- Tipo: Requerimiento no funcional.
- Módulo o capacidad: Capacidad general compartida — Seguridad de configuración.
- Etapa prevista: Primera etapa del Propietario; aplicable posteriormente a los componentes incorporados.
- Estado de la definición: Propuesta; pendiente de definir el inventario, los mecanismos de gestión y los procedimientos de sustitución.
- Actor relacionado: Personal o proceso autorizado para utilizar o administrar secretos de la solución.
- Prioridad: Por definir.
- Referencias relacionadas: Secretos, credenciales y configuración sensible conforme a `67.7` de `proyecto.md`; protección de información conforme a RNF-003; auditoría conforme a RNF-005.
- Dependencias: Identificación de ambientes y servicios; inventario de secretos; mecanismos de almacenamiento y acceso; procedimientos operativos de seguridad.

#### Descripción

Vehículos Services deberá gestionar de forma protegida las credenciales de servicios, claves privadas, tokens y demás secretos necesarios para su funcionamiento.

Los secretos no deberán incorporarse directamente al código fuente ni almacenarse en repositorios, documentación, archivos de prueba u otros lugares no autorizados. Tampoco deberán incluirse en la aplicación móvil credenciales que permitan administrar servicios o acceder a recursos reservados al servidor.

Cada secreto deberá tener una finalidad y un responsable identificados. Su utilización se limitará a las personas y procesos que lo necesiten para realizar las operaciones autorizadas.

Los ambientes deberán mantener separados sus secretos conforme a la estrategia aprobada. Las credenciales de producción no deberán utilizarse automáticamente en desarrollo o pruebas.

La solución deberá contar con procedimientos para sustituir o revocar secretos cuando corresponda, incluyendo los casos de exposición o pérdida de control. Los cambios deberán comprobarse para evitar que una credencial retirada continúe habilitando accesos.

Las evidencias de administración deberán identificar la acción realizada sin conservar el valor secreto. Los mecanismos técnicos se definirán en arquitectura y `seguridad.md`.

#### Criterios de aceptación

1. Existirá un inventario de secretos que identifique su finalidad, ambiente, responsable y accesos autorizados, sin exponer sus valores.
2. Las revisiones del código, repositorios, documentación y artefactos de entrega no encontrarán secretos almacenados fuera de los mecanismos aprobados.
3. La aplicación móvil no contendrá credenciales reservadas para administrar servicios o acceder a recursos internos del servidor.
4. Solo las personas y procesos autorizados podrán obtener o utilizar los secretos correspondientes.
5. Los ambientes utilizarán las credenciales asignadas a ellos conforme a la separación aprobada.
6. Los procedimientos de sustitución comprobarán que los servicios autorizados funcionan con el nuevo secreto.
7. La revocación impedirá continuar utilizando el secreto retirado dentro del plazo definido para el procedimiento.
8. Los mensajes, registros técnicos y evidencias de auditoría no expondrán los valores secretos.
9. Las pruebas cubrirán acceso no autorizado, sustitución y revocación sobre los mecanismos incluidos en el alcance.

#### Decisiones pendientes

- Identificar los secretos utilizados por cada componente y ambiente.
- Definir los mecanismos de almacenamiento, entrega y utilización.
- Definir responsables y permisos de administración.
- Establecer las condiciones, frecuencia y plazos de sustitución o revocación.
- Definir el procedimiento ante exposición o pérdida de control de un secreto.
- Precisar el comportamiento cuando un secreto necesario no esté disponible o haya dejado de ser válido.
- Definir las verificaciones y evidencias de gestión segura.

---

### RNF-020 — Validación de entradas y protección contra abuso

- ID: RNF-020.
- Nombre: Validación de entradas y protección contra abuso.
- Tipo: Requerimiento no funcional.
- Módulo o capacidad: Capacidad general compartida — Seguridad de servicios y operaciones.
- Etapa prevista: Primera etapa del Propietario; aplicable posteriormente a los componentes incorporados.
- Estado de la definición: Propuesta; pendiente de definir los límites y controles aplicables a cada operación.
- Actor relacionado: Usuario o proceso que envía información o solicitudes a la solución.
- Prioridad: Por definir.
- Referencias relacionadas: Validación y protección de entradas conforme a `67.5` de `proyecto.md`; seguridad de APIs y servicios conforme a `67.8`; acceso conforme a RNF-002; integridad conforme a RNF-004.
- Dependencias: Reglas funcionales de validación; identificación de operaciones expuestas; volúmenes previstos; controles de seguridad y monitoreo.

#### Descripción

Vehículos Services deberá validar en el servidor la información recibida desde la aplicación móvil, servicios, integraciones y otros canales habilitados antes de utilizarla en una operación.

Las comprobaciones deberán contemplar estructura, tipo, formato, tamaño y consistencia conforme a las reglas aplicables. La validación realizada en la interfaz no deberá considerarse suficiente para proteger los servicios.

Los datos recibidos deberán procesarse como información y no interpretarse como instrucciones capaces de alterar el funcionamiento de los componentes fuera de las operaciones previstas.

Las operaciones expuestas deberán contar con límites y controles de uso adecuados a su finalidad, especialmente cuando puedan utilizarse para intentar accesos repetidos, agotar recursos o generar solicitudes masivas.

Los controles deberán distinguir el uso permitido de las condiciones de abuso definidas. No deberán configurarse sin considerar la concurrencia y frecuencia previstas para usuarios legítimos y procesos autorizados.

El rechazo de una entrada o solicitud no deberá revelar información sensible ni producir cambios incompletos. Los intentos relevantes deberán generar evidencias o señales conforme a RNF-005 y RNF-014.

La validación de archivos conservará sus controles específicos conforme a RNF-018.

#### Criterios de aceptación

1. Las solicitudes que eludan la interfaz estarán sujetas a las mismas validaciones obligatorias del servidor.
2. Las entradas que incumplan la estructura, los tipos, formatos o límites aprobados serán rechazadas antes de ejecutar la operación correspondiente.
3. Los valores recibidos no podrán utilizarse para ejecutar instrucciones ajenas a las operaciones previstas.
4. Una entrada rechazada no generará cambios incompatibles con RNF-004.
5. Las operaciones incluidas en el alcance aplicarán los límites de uso definidos para ellas.
6. Las pruebas comprobarán el comportamiento al alcanzar o superar los límites, así como el uso legítimo dentro de las condiciones previstas.
7. Las respuestas de rechazo no expondrán secretos, contenido restringido ni detalles internos innecesarios.
8. Las condiciones de abuso seleccionadas para monitoreo producirán las señales y evidencias aprobadas.
9. Los procesos autorizados respetarán sus límites específicos y no quedarán exentos de validación por ejecutarse automáticamente.
10. Las pruebas incluirán solicitudes malformadas, entradas fuera de límite y secuencias repetidas sobre operaciones sensibles.

#### Decisiones pendientes

- Definir las validaciones de estructura y tamaño para cada operación, complementando sus reglas funcionales.
- Identificar las operaciones que requieren controles específicos contra abuso.
- Definir los límites, intervalos y criterios de agrupación de solicitudes.
- Precisar el tratamiento de usuarios legítimos y procesos automáticos con frecuencias distintas.
- Definir las respuestas y condiciones para volver a intentar una operación limitada.
- Definir las señales y evidencias que deberán conservarse ante intentos relevantes.
- Definir los escenarios de prueba y los resultados esperados.

---

### RNF-021 — Protección y vigencia de sesiones

- ID: RNF-021.
- Nombre: Protección y vigencia de sesiones.
- Tipo: Requerimiento no funcional.
- Módulo o capacidad: Capacidad general compartida — Seguridad de sesiones.
- Etapa prevista: Primera etapa del Propietario; aplicable posteriormente al módulo del Prestador y a la integración.
- Estado de la definición: Condiciones funcionales de vigencia, renovación e invalidación aprobadas en las reglas relacionadas; mecanismos técnicos de protección y gestión de sesiones pendientes de definición.
- Actor relacionado: Usuario que inicia o mantiene una sesión en la aplicación.
- Prioridad: Por definir.
- Referencias relacionadas: Inicio de sesión conforme a RF-002; recuperación de acceso conforme a RF-048; cierre conforme a RF-049; protección y control de acceso conforme a RNF-002 y RNF-003.
- Reglas de negocio relacionadas: RN-029 — Recuperación de la contraseña propia; RN-031 — Vinculación, incorporación y retiro de métodos de acceso; RN-032 — Registro y autenticación mediante Apple; RN-033 — Cierre de sesión y protección de información local; RN-034 — Vigencia de sesiones y control de intentos de autenticación, definidas en `reglas-negocio.md`.
- Dependencias: Mecanismos de autenticación; gestión de elementos de sesión; almacenamiento seguro en el dispositivo; aplicación de las reglas aprobadas de vigencia, renovación e invalidación.

#### Descripción

Vehículos Services deberá controlar la vigencia de las sesiones y proteger los elementos utilizados para acreditar la autenticación del usuario.

Las condiciones de duración máxima, inactividad, actividad válida y renovación se regirán por RN-034. La aplicación no deberá mantener acceso indefinido por conservar localmente información de una autenticación anterior.

El servidor deberá verificar la validez de los elementos de sesión antes de aceptar operaciones protegidas. La renovación no deberá permitir continuar utilizando una sesión invalidada ni recuperar permisos que hayan sido retirados. Tampoco deberá reiniciar los plazos establecidos en RN-034.

La vigencia de la sesión deberá mantenerse diferenciada de la autorización sobre los recursos. Una sesión válida no deberá conservar automáticamente permisos correspondientes a relaciones que ya no estén vigentes.

Los elementos de sesión almacenados o transmitidos deberán respetar RNF-003. No deberán incorporarse a enlaces públicos, registros técnicos o mensajes que los expongan innecesariamente.

Ante vencimiento o invalidación, la aplicación deberá comunicar la necesidad de autenticación y tratar los cambios sin guardar conforme a las reglas aprobadas. No deberá presentar como aceptadas operaciones que fueron rechazadas por falta de una sesión válida.

El cierre local y la invalidación remota deberán distinguirse conforme a RN-033. Una invalidación pendiente no deberá restaurar el acceso local ni permitir renovar la sesión cerrada.

Los efectos de recuperación de contraseña, gestión de métodos y revocación de autorizaciones de Apple se aplicarán conforme a RN-029, RN-031 y RN-032.

El uso de un proveedor externo de identidad no deberá eliminar el control de las sesiones propias de Vehículos Services.

#### Criterios de aceptación

1. La duración máxima, el vencimiento por inactividad y las condiciones de renovación se aplicarán conforme a RN-034, con controles en el backend que no puedan ampliarse mediante cambios locales en el dispositivo.
2. Los servicios rechazarán operaciones protegidas cuando los elementos de sesión sean inválidos, hayan vencido o hayan sido invalidados. Una vez registrada una invalidación en el backend, se rechazarán las siguientes operaciones y renovaciones de las sesiones afectadas.
3. Una renovación respetará las condiciones aprobadas, no reiniciará los plazos establecidos en RN-034 ni reactivará una sesión invalidada.
4. Una sesión válida no permitirá utilizar permisos retirados, conforme a RNF-002.
5. El cierre de sesión de RF-049 retirará el acceso local e invalidará la sesión conforme a RN-033. Si la invalidación remota permanece pendiente, la aplicación lo informará y no restaurará la sesión anterior.
6. Los efectos de recuperación de contraseña, incorporación o retiro de métodos y revocación de autorizaciones de Apple se aplicarán a las sesiones correspondientes conforme a RN-029, RN-031 y RN-032.
7. Los elementos de sesión se protegerán conforme a RNF-003 y no se expondrán en registros técnicos ni mensajes.
8. El vencimiento o invalidación no eliminará la cuenta ni alterará registros históricos.
9. La aplicación distinguirá una operación rechazada por sesión inválida de una operación completada, y tratará los resultados desconocidos conforme a RN-033 y RN-034.
10. Las pruebas incluirán vencimiento por duración máxima e inactividad, renovación, cierre e invalidación, además de cambios de permisos durante una sesión vigente, sesiones simultáneas y cierre con invalidación remota pendiente.

#### Decisiones pendientes

Las políticas funcionales de sesión ya están definidas en las reglas relacionadas. Permanecen pendientes las siguientes decisiones técnicas:

- Definir los mecanismos de creación, almacenamiento protegido y transmisión de los elementos de sesión.
- Definir los tiempos y mecanismos de renovación de esos elementos, respetando los límites de RN-034.
- Precisar cómo se identificará y controlará cada sesión en los distintos dispositivos.
- Definir cómo se comprobarán y aplicarán las invalidaciones y los permisos vigentes antes de aceptar operaciones protegidas.
- Definir el mecanismo restringido para completar una invalidación remota pendiente conforme a RN-033.
- Precisar la integración técnica con Google y Apple sin sustituir el control de las sesiones propias.
- Definir el tratamiento técnico de datos locales y operaciones pendientes ante vencimiento o invalidación.
- Definir la trazabilidad de creación, renovación, vencimiento e invalidación sin registrar elementos secretos de sesión.



---

### RNF-022 — Verificación de seguridad antes de liberar versiones

- ID: RNF-022.
- Nombre: Verificación de seguridad antes de liberar versiones.
- Tipo: Requerimiento no funcional.
- Módulo o capacidad: Capacidad general compartida — Calidad y seguridad del desarrollo.
- Etapa prevista: Primera etapa del Propietario; aplicable a las versiones posteriores.
- Estado de la definición: Propuesta; pendiente de definir las verificaciones, clasificación de hallazgos y condiciones de liberación.
- Actor relacionado: Equipo responsable del desarrollo, verificación de seguridad y liberación.
- Prioridad: Por definir.
- Referencias relacionadas: Seguridad durante el desarrollo y auditoría de seguridad conforme a `67.10` y `67.11` de `proyecto.md`; controles definidos en los RNF de seguridad; mantenibilidad conforme a RNF-015.
- Dependencias: Alcance de la versión; controles de seguridad aplicables; procedimientos de revisión y pruebas; responsables y criterios de liberación.

#### Descripción

Vehículos Services deberá incorporar verificaciones de seguridad durante el desarrollo y antes de liberar una versión, según los componentes y cambios incluidos.

Las verificaciones deberán relacionarse con los controles definidos en los requisitos. El uso de herramientas automáticas no deberá sustituir las pruebas específicas necesarias para comprobar permisos, reglas de negocio y protección de recursos.

El alcance deberá contemplar, cuando corresponda, la aplicación móvil, los servicios, las dependencias utilizadas y la configuración de despliegue. Los controles aplicables deberán comprobarse sobre la versión candidata a liberación.

Cada hallazgo deberá identificar el comportamiento afectado, su impacto, clasificación y tratamiento. Las condiciones que impidan liberar una versión deberán establecerse expresamente.

Los hallazgos corregidos deberán verificarse nuevamente. Cuando se permita liberar con un hallazgo pendiente, deberá existir una decisión documentada conforme al procedimiento aprobado, con responsable, justificación y condiciones de seguimiento.

La revisión no deberá presentarse como garantía de ausencia absoluta de vulnerabilidades. Su resultado deberá expresar el alcance evaluado, las limitaciones y los hallazgos pendientes.

#### Criterios de aceptación

1. Cada versión candidata contará con un alcance de verificación de seguridad relacionado con sus componentes y cambios.
2. Se ejecutarán las revisiones y pruebas obligatorias definidas para ese alcance.
3. Los controles que requieren comprobación funcional, como la autorización por recurso, se verificarán mediante escenarios específicos y no únicamente mediante análisis automático.
4. Los hallazgos conservarán su clasificación, componente afectado, evidencia y tratamiento.
5. Una corrección no se considerará cerrada sin una verificación satisfactoria del comportamiento afectado.
6. La versión no se liberará si mantiene hallazgos que incumplan las condiciones de liberación aprobadas.
7. Los hallazgos pendientes admitidos para liberación contarán con la decisión y seguimiento exigidos por el procedimiento.
8. Las evidencias identificarán la versión, configuración y alcance realmente evaluados.
9. Los cambios relevantes posteriores a la verificación requerirán revisar nuevamente los controles que puedan verse afectados.
10. El resultado de la revisión indicará sus limitaciones y no afirmará que la solución está libre de toda vulnerabilidad.

#### Decisiones pendientes

- Definir las revisiones y pruebas obligatorias según el tipo e impacto del cambio.
- Definir la clasificación de hallazgos y las condiciones que bloquearán una liberación.
- Definir responsables de revisión, corrección y decisión de liberación.
- Precisar el procedimiento para aceptar y dar seguimiento a hallazgos pendientes.
- Definir la verificación de dependencias y configuraciones utilizadas.
- Definir cuándo se requerirán revisiones manuales o especializadas adicionales.
- Definir las evidencias que se conservarán y sus permisos de consulta.

---


