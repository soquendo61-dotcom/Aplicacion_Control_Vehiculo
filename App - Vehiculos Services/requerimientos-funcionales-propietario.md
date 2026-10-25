# Vehículos Services — Requerimientos funcionales del Propietario

## 1. Propósito

Este documento contiene la especificación detallada de los requerimientos funcionales del módulo del Propietario de Vehículos Services, así como de las capacidades generales necesarias para su funcionamiento.

Complementa `proyecto.md`, que conserva la visión, el alcance, las definiciones generales y las decisiones comunes de la solución.

Los requerimientos funcionales propios del Prestador de Servicios Vehiculares se documentarán en `requerimientos-funcionales-prestador.md`. Cuando ambos módulos utilicen una capacidad general, su definición se mantendrá en un único documento y el otro la referenciará mediante su identificador, evitando duplicar su especificación.

Los requerimientos no funcionales se documentarán en `requerimientos-no-funcionales.md`. Sus condiciones aplicables deberán considerarse junto con los requerimientos funcionales de cada entrega.

Los requerimientos se desarrollarán progresivamente. La primera etapa deberá permitir que el Propietario gestione sus vehículos y la información asociada sin depender de la implementación del módulo del Prestador.

Este documento también podrá incluir acciones del Propietario que requieran una integración posterior con el Prestador. Cada requerimiento indicará su etapa prevista y sus dependencias; su inclusión no implicará que forme parte de la primera implementación.

El alcance funcional de las entregas del Propietario se establecerá en este documento, distinguiendo los requerimientos incluidos inicialmente y los previstos para entregas posteriores.

Los identificadores de los requerimientos funcionales serán únicos en el proyecto y se conservarán cuando un requerimiento cambie de documento.

Una propuesta o decisión pendiente no deberá interpretarse como aprobada para implementación. Los flujos detallados se desarrollarán en `casos-uso.md`; las condiciones y cálculos específicos, en `reglas-negocio.md`.

---

## 2. Identificación y estado

- Los requerimientos funcionales utilizarán identificadores `RF-001`, `RF-002` y sucesivos, de acuerdo con el punto 27 de `proyecto.md`.
- Los identificadores serán únicos en todo el proyecto, incluidos `requerimientos-funcionales-propietario.md` y `requerimientos-funcionales-prestador.md`. Cada nuevo requisito utilizará un identificador que no haya sido asignado previamente.
- Un requisito conservará su identificador cuando se traslade de un documento a otro. Los saltos de numeración resultantes no deberán corregirse mediante la renumeración de los requisitos existentes.
- Cada requisito tendrá una única especificación principal. Cuando otro documento necesite referenciarlo, indicará su identificador y el documento donde está definido, sin duplicar su contenido.
- Las capacidades generales compartidas que se documenten aquí se identificarán como tales en el campo «Módulo o capacidad». Su utilización por el Prestador no requerirá una segunda especificación del mismo requisito.
- Los requerimientos no funcionales tendrán su definición principal en `requerimientos-no-funcionales.md`. Los requisitos funcionales podrán referenciarlos mediante sus identificadores `RNF`, sin reproducir su especificación.
- Cada requerimiento indicará su etapa prevista, estado de definición, prioridad, dependencias, relaciones y criterios de aceptación verificables.
- La ubicación de un requisito en este documento no implicará que forme parte de la primera implementación. Las acciones del Propietario que dependan de la integración con el Prestador conservarán la etapa y las dependencias correspondientes.
- La prioridad y los mecanismos aún no aprobados se señalarán expresamente como pendientes. Los requisitos con decisiones pendientes necesarias para su implementación deberán completarse y validarse antes de considerarse listos para desarrollar.

## 3. Requerimientos funcionales

### RF-001 — Crear cuenta de usuario

- ID: RF-001.
- Nombre: Crear cuenta de usuario.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Capacidad general compartida — Gestión de cuenta.
- Etapa prevista: Primera etapa del Propietario en Android e iOS; reutilizable posteriormente por el módulo del Prestador.
- Estado de la definición: Aprobado en su alcance funcional para la primera entrega del Propietario. Las verificaciones específicas de corrección mediante soporte se detallarán conforme a RN-037. Los mecanismos técnicos y los casos de uso deberán detallarse en los documentos correspondientes.
- Actor relacionado: Persona que desea registrarse en Vehículos Services.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: RN-025 — Cuenta de usuario e identidad del propietario, considerando su estado de definición; RN-026 — Mecanismos de registro y autenticación; RN-027 — Verificación del correo en el registro propio; RN-028 — Datos, contraseña y coincidencias del registro propio; RN-030 — Registro y autenticación mediante Google; RN-031 — Vinculación, incorporación y retiro de métodos de acceso; RN-032 — Registro y autenticación mediante Apple; RN-037 — Actualización de datos personales y correcciones mediante soporte, definidas en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: CU-001 Crear cuenta.
- Dependencias: Condiciones de registro y habilitación correspondientes a los mecanismos seleccionados; datos, contraseña y coincidencias del registro propio conforme a RN-028; verificación del correo conforme a RN-027; registro externo conforme a RN-030 y RN-032; vinculación de métodos conforme a RN-031; corrección del correo mediante soporte conforme a RN-037.

#### Descripción

Vehículos Services deberá permitir que una persona cree una cuenta mediante registro propio con correo electrónico y contraseña, Google o Apple en Android e iOS, conforme a los mecanismos seleccionados para la primera entrega en RN-026 y en `63.2.3` de `proyecto.md`.

Un propietario únicamente podrá tener una cuenta conforme a RN-025. Durante el registro se comprobará la coincidencia del correo con cuentas existentes. La comprobación del tipo y número de documento se realizará posteriormente, cuando el usuario solicite completar su identificación como propietario y asociar su primer vehículo, conforme a RN-025 y RF-003.

El registro propio solicitará correo electrónico, contraseña y confirmación de contraseña, aplicando las validaciones establecidas en RN-028. La confirmación se utilizará para comprobar la coincidencia y no se conservará como un dato adicional de la cuenta.

La creación de la cuenta no deberá exigir que registre un vehículo ni que suministre desde ese momento todos los datos requeridos para establecer posteriormente una relación de propiedad. Los datos iniciales exigibles y su separación respecto de la identificación del propietario se regirán por RN-028 y RN-025.

Antes de confirmar el envío del formulario de registro propio, el usuario podrá corregir el correo digitado. Una vez creado el registro de la cuenta, incluso si permanece pendiente de verificación, no podrá editar ni eliminar directamente ese correo. Las solicitudes de corrección se tramitarán mediante soporte conforme a RN-037.

En el registro propio, la cuenta permanecerá pendiente de verificación hasta comprobar que el usuario controla el correo indicado. La plataforma generará y enviará un código numérico conforme a RN-027.

Mientras la verificación esté pendiente, el usuario únicamente podrá realizar las acciones permitidas por RN-027 para completar el registro, introducir el código, solicitar uno nuevo o consultar las indicaciones para contactar a soporte. No podrá gestionar vehículos ni acceder a sus registros.

Si un error en el correo impide verificar la cuenta o retomar el registro, el usuario podrá solicitar ayuda mediante el canal definido en RN-037 sin iniciar sesión. El contacto con soporte no autorizará automáticamente una corrección ni habilitará la cuenta.

La corrección autorizada del correo durante el registro propio pendiente conservará la misma cuenta y aplicará las condiciones de RN-027 y RN-037. La continuidad del registro, los controles del código, el tratamiento de errores y solicitudes repetidas, y la conservación y eliminación del registro provisional deberán cumplir RN-027.

Completar satisfactoriamente la verificación permitirá habilitar el uso de la cuenta, sin perjuicio de otras restricciones aplicables. Verificar el correo no acreditará por sí solo la identidad personal ni la propiedad de un vehículo.

El registro mediante Google o Apple utilizará la autenticación del proveedor y la información que este permita compartir con autorización del usuario. Vehículos Services no solicitará ni gestionará las contraseñas de esos proveedores.

Las condiciones de registro y habilitación mediante Google se regirán por RN-030 y las correspondientes a Apple por RN-032. La comprobación adicional del correo se realizará cuando corresponda conforme a esas reglas, sin asumir que todo registro externo cumple automáticamente las condiciones de habilitación.

Si una solicitud de registro propio utiliza un correo asociado a una cuenta existente, se aplicará RN-028. La solicitud no deberá crear una cuenta duplicada, sobrescribir credenciales ni vincular automáticamente métodos de acceso. Retomar un registro pendiente requerirá autenticarse con las credenciales correspondientes.

Las coincidencias durante el registro mediante Google o Apple se resolverán conforme a RN-030 y RN-032, respectivamente.

La incorporación de otro método de acceso a una cuenta existente se realizará conforme a RN-031. La coincidencia del correo no autorizará por sí sola esa incorporación.

Los demás proveedores de identidad se contemplarán para entregas posteriores y no se presentarán como disponibles mientras no estén habilitados.

Este requisito tendrá una única definición en `requerimientos-funcionales-propietario.md` y podrá referenciarse desde `requerimientos-funcionales-prestador.md` cuando se incorpore dicho módulo.

#### Criterios de aceptación

1. Una persona podrá crear una cuenta mediante correo electrónico y contraseña, Google o Apple en Android e iOS, cumpliendo las condiciones aprobadas para el mecanismo elegido.
2. En el registro propio, la cuenta permanecerá pendiente de verificación hasta completar satisfactoriamente la comprobación del correo.
3. La plataforma generará y enviará el código de verificación al correo indicado conforme a RN-027, aplicando sus condiciones de vigencia, uso único, generación y comprobación.
4. Generar o enviar un código, o solicitar uno nuevo, no habilitará por sí sola la cuenta.
5. Mientras la verificación esté pendiente, el acceso se limitará a las acciones permitidas por RN-027 y, cuando se trate de un registro externo, por RN-030 o RN-032, sin permitir gestionar vehículos ni consultar sus registros.
6. Una comprobación fallida o incompleta no habilitará la cuenta. Si la comprobación se completó, pero la aplicación no recibió la respuesta, se recuperará el resultado conforme a las reglas aplicables.
7. Una cuenta habilitada conforme al procedimiento correspondiente permitirá utilizar las capacidades disponibles sin exigir vehículos asociados.
8. La creación de la cuenta y la verificación del correo no crearán automáticamente vehículos ni relaciones de propiedad.
9. Verificar el correo o autenticarse mediante Google o Apple no se considerará prueba de propiedad de un vehículo.
10. El registro mediante Google o Apple no solicitará ni almacenará la contraseña que el usuario utiliza con ese proveedor.
11. La coincidencia de un correo con una cuenta existente no provocará por sí sola la vinculación de un método de acceso; se aplicarán RN-028, RN-030, RN-031 y RN-032 según corresponda.
12. Los proveedores previstos para entregas posteriores no se mostrarán como mecanismos disponibles en la primera entrega.
13. La corrección del correo durante el registro propio pendiente requerirá autorización y ejecución mediante soporte conforme a RN-037, conservará la misma cuenta y aplicará las condiciones y controles establecidos en RN-027. El usuario no podrá realizar directamente ese cambio.
14. El usuario podrá retomar un registro pendiente que todavía se conserve, conforme a las reglas del mecanismo correspondiente, sin reiniciar sus tiempos ni contadores.
15. La aplicación informará el plazo de conservación del registro provisional y aplicará su eliminación al vencimiento conforme a RN-027 y su aplicación expresa en RN-030 o RN-032. Un registro cuyo plazo haya vencido no podrá completar la verificación y requerirá iniciar un nuevo registro.
16. El registro propio solicitará los datos iniciales definidos en RN-028, sin exigir documento de identidad, teléfono, dirección ni datos vehiculares para crear la cuenta.
17. El correo y la contraseña del registro propio deberán cumplir las validaciones de RN-028. La contraseña y su confirmación deberán coincidir, y la confirmación no se conservará como un dato adicional.
18. Una solicitud de registro propio con un correo asociado a una cuenta existente no creará otra cuenta ni modificará sus credenciales. Se aplicará el tratamiento correspondiente de RN-028.
19. Repetir una solicitud de registro con el correo de una cuenta pendiente no sobrescribirá su contraseña ni generará automáticamente otro código.
20. Ante una coincidencia que impida completar el registro, se mostrará el mensaje aprobado en RN-025 y RN-028, conforme a las reglas del mecanismo correspondiente. No se mostrarán datos personales, vehículos, el estado de la cuenta existente ni sus métodos de acceso.
21. Los registros mediante Google o Apple se asociarán a la identidad estable validada del proveedor y aplicarán sus condiciones de comprobación del correo antes de habilitar la cuenta.
22. El registro mediante Apple aceptará la dirección privada autorizada por el proveedor, sin exigir revelar el correo personal, conforme a RN-032.
23. La creación de una cuenta con un correo diferente no eximirá de la comprobación posterior de unicidad del tipo y número de documento establecida en RN-025. Esa comprobación no se adelantará al registro inicial ni permitirá fusionar cuentas automáticamente.
24. Antes de confirmar el envío del formulario de registro propio, el usuario podrá corregir el correo digitado. Después de crear la cuenta, no podrá editarlo ni eliminarlo directamente, incluso mientras permanezca pendiente de verificación.
25. Las indicaciones para contactar a soporte por un correo incorrecto estarán disponibles sin exigir inicio de sesión ni verificación de ese correo, conforme a RN-037. Enviar una solicitud no modificará automáticamente la cuenta, verificará el correo ni concederá acceso.

#### Definiciones posteriores relacionadas

- Documentar CU-001 Crear cuenta en `casos-uso.md`.
- Detallar los mecanismos técnicos de registro, autenticación externa, comprobación del correo y tratamiento de coincidencias.
- Detallar la presentación del canal de soporte durante el registro y la continuidad del proceso después de una corrección autorizada, conforme a RN-027 y RN-037.
- Aplicar las condiciones aprobadas en las reglas relacionadas, sin duplicar su definición en este requisito.




---

### RF-002 — Iniciar sesión

- ID: RF-002.
- Nombre: Iniciar sesión.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Capacidad general compartida — Gestión de cuenta y acceso.
- Etapa prevista: Primera etapa del Propietario en Android e iOS; reutilizable posteriormente por el módulo del Prestador.
- Estado de la definición: Aprobado en su alcance funcional para la primera entrega del Propietario. Los mecanismos técnicos de autenticación y gestión de sesiones deberán detallarse en los documentos correspondientes.
- Actor relacionado: Usuario con una cuenta registrada en Vehículos Services.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: RN-025 — Cuenta de usuario e identidad del propietario, considerando su estado de definición; RN-026 — Mecanismos de registro y autenticación; RN-027 — Verificación del correo en el registro propio; RN-030 — Registro y autenticación mediante Google; RN-031 — Vinculación, incorporación y retiro de métodos de acceso; RN-032 — Registro y autenticación mediante Apple; RN-034 — Vigencia de sesiones y control de intentos de autenticación, definidas en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: CU-002 Iniciar sesión.
- Dependencias: Cuenta registrada conforme a RF-001; mecanismo de acceso habilitado y asociado a esa cuenta; condiciones de habilitación y gestión de sesiones correspondientes. Aplicarán los controles de RNF-021, definido en `requerimientos-no-funcionales.md`, y la política de RN-034.

#### Descripción

Vehículos Services deberá permitir que un usuario registrado inicie sesión mediante correo electrónico y contraseña, Google o Apple en Android e iOS, según los mecanismos habilitados y asociados a su cuenta conforme a RN-026.

En una cuenta creada mediante registro propio, presentar credenciales correctas no será suficiente para habilitar el acceso ordinario mientras el correo permanezca pendiente de verificación. Durante ese estado, el acceso se limitará a las acciones permitidas por RN-027 para completar o corregir el registro, introducir el código y solicitar uno nuevo.

El usuario podrá retomar un registro propio pendiente que todavía se conserve al autenticarse con las credenciales de esa cuenta. La plataforma deberá consultar su estado actual y mantener los tiempos, contadores y restricciones establecidos en RN-027.

Cuando un registro mediante Google o Apple requiera una comprobación adicional del correo, su continuidad y acceso limitado se regirán por RN-030 o RN-032, respectivamente. No se exigirá una contraseña propia que no haya sido incorporada.

Si el plazo de conservación del registro provisional ya venció, no se permitirá retomar ni verificar ese registro. El usuario deberá iniciar un nuevo registro conforme a RF-001 y las reglas aplicables.

Si la verificación ya se completó, pero la aplicación no recibió la confirmación, se recuperará el estado registrado conforme a las reglas aplicables, sin exigir una segunda verificación.

Después de completar las comprobaciones correspondientes, el acceso continuará sujeto a las restricciones vigentes y permisos de la cuenta.

La disponibilidad de los tres mecanismos en la plataforma no implicará que cualquier cuenta pueda utilizarlos indistintamente. Incorporar o retirar un método de acceso requerirá el procedimiento definido en RN-031.

Cuando se utilice Google o Apple, la plataforma comprobará la autenticación y su correspondencia con la identidad externa vinculada a la cuenta de Vehículos Services, conforme a RN-030 o RN-032. No solicitará ni gestionará la contraseña del proveedor. La coincidencia del correo no será suficiente para conceder acceso a una cuenta no vinculada.

La sesión podrá conservarse entre usos de la aplicación mientras siga vigente. Su duración, inactividad, renovación y uso en distintos dispositivos se regirán por RN-034 y los controles de RNF-021. Una sesión cerrada, vencida o invalidada no deberá recuperarse mediante renovación.

Los intentos fallidos de autenticación con contraseña, las restricciones temporales y los mensajes se tratarán conforme a RN-034. Estos controles serán independientes de los límites de comprobación de códigos.

La autenticación deberá identificar al usuario, pero no deberá otorgar por sí sola propiedad sobre un vehículo ni permisos para actuar en nombre de un Prestador de Servicios Vehiculares.

Una persona que posteriormente tenga funciones de Propietario y de Prestador podrá conservar una sola cuenta. Las funciones y permisos disponibles en cada contexto deberán regirse por las relaciones y autorizaciones correspondientes, sin requerir cuentas personales duplicadas.

Este requisito tendrá una única definición en `requerimientos-funcionales-propietario.md` y podrá referenciarse desde `requerimientos-funcionales-prestador.md` cuando se incorpore dicho módulo.

#### Criterios de aceptación

1. Un usuario con una cuenta habilitada podrá iniciar sesión mediante correo electrónico y contraseña, Google o Apple en Android e iOS, siempre que el mecanismo utilizado esté habilitado y asociado a su cuenta.
2. En el registro propio, las credenciales correctas no permitirán el acceso ordinario mientras el correo permanezca pendiente de verificación.
3. Durante una comprobación pendiente del registro, cualquier acceso permitido se limitará a las acciones definidas en RN-027, RN-030 o RN-032, según corresponda, sin habilitar la gestión de vehículos ni la consulta de sus registros.
4. Completar la comprobación del correo no eliminará otras restricciones vigentes ni concederá permisos adicionales.
5. Si la autenticación no puede completarse, la plataforma no deberá conceder acceso a las funcionalidades que requieran una sesión autenticada.
6. La autenticación mediante Google o Apple deberá corresponder a la identidad externa vinculada a la cuenta a la que se concede acceso. La coincidencia de un correo no autorizará por sí sola el acceso ni la vinculación.
7. El inicio de sesión no deberá crear automáticamente vehículos, relaciones de propiedad ni autorizaciones de Prestador.
8. Una vez autenticado y con la cuenta habilitada, el usuario solo podrá acceder a las funcionalidades y recursos que sus relaciones y permisos le permitan.
9. La disponibilidad de un mecanismo adicional no lo habilitará automáticamente para una cuenta existente.
10. Las restricciones vigentes de la cuenta y las condiciones de acceso se aplicarán independientemente del mecanismo utilizado.
11. La plataforma no solicitará ni gestionará las contraseñas de Google o Apple para iniciar sesión.
12. El usuario podrá retomar un registro pendiente que todavía se conserve, autenticándose mediante el mecanismo correspondiente, sin reiniciar los tiempos ni contadores establecidos en las reglas aplicables.
13. Un registro provisional cuyo plazo de conservación haya vencido no permitirá retomar el proceso ni completar la verificación; se deberá iniciar un nuevo registro.
14. Si el correo ya fue comprobado conforme al procedimiento correspondiente, la plataforma recuperará ese estado sin exigir repetir la comprobación, manteniendo las demás condiciones de acceso aplicables.
15. La indisponibilidad de un proveedor permitirá utilizar otro método únicamente si ya está habilitado y vinculado a la cuenta.
16. Un método retirado conforme a RN-031 no permitirá iniciar sesión en esa cuenta. Las autorizaciones revocadas por Apple se tratarán conforme a RN-032.
17. La permanencia, duración máxima, inactividad, renovación y sesiones simultáneas cumplirán RN-034 y RNF-021, sin reactivar sesiones invalidadas ni conservar permisos retirados.
18. Los intentos fallidos con contraseña, las restricciones temporales y los mensajes cumplirán RN-034, sin confundirlos con fallos de conexión, errores de proveedores externos o intentos de comprobación de códigos.

#### Definiciones posteriores relacionadas

- Documentar CU-002 Iniciar sesión en `casos-uso.md`.
- Detallar los mecanismos técnicos de autenticación con contraseña, Google y Apple.
- Implementar los controles de vigencia, renovación, invalidación y protección de sesiones conforme a RN-034 y RNF-021.
- Detallar los mecanismos técnicos de control de intentos fallidos y mensajes de autenticación conforme a RN-034.
- Mantener coherencia con la recuperación de acceso de RF-048 y el cierre de sesión de RF-049.


---

### RF-003 — Agregar vehículo como propietario

- ID: RF-003.
- Nombre: Agregar vehículo como propietario.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Gestión de vehículos y relación Propietario ↔ Vehículo.
- Etapa prevista: Primera entrega del Propietario para personas naturales; representación de propietarios persona jurídica prevista para entregas posteriores.
- Estado de la definición: Propuesta; las condiciones iniciales de identificación y comparación están desarrolladas en RN-025 y RN-036. La validación básica de captura, los mensajes, las condiciones de corrección y repetición de comprobaciones y el tratamiento inicial de inconsistencias están aprobados en RN-036. El bloqueo de los datos confirmados y su corrección mediante soporte se desarrollan en RN-037, con sus verificaciones específicas pendientes. La revisión especial de conflictos vehiculares corresponderá a una entrega posterior. Permanecen pendientes las precisiones y procedimientos señalados en esas reglas y en este requerimiento.
- Actor relacionado: Usuario registrado que solicita asociar un vehículo de su propiedad; en entregas posteriores, usuario que actúa en representación de una persona jurídica propietaria, con la autorización correspondiente.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: RN-025 — Cuenta de usuario e identidad del propietario; RN-035 — Revisión manual de conflictos de identificación del propietario; RN-036 — Identificación, coincidencias y comparación documental del vehículo; RN-037 — Actualización de datos personales y correcciones mediante soporte, considerando sus estados de definición. Aplican las definiciones generales de los puntos 63.1.5, 63.1.6 y 63.4 de `proyecto.md`.
- Caso de uso preliminar relacionado: CU-003 Registrar vehículo.
- Dependencias: Cuenta de usuario registrada; datos personales conforme a RN-025; identificación y comparación del vehículo conforme a RN-036; revisión manual conforme a RN-035 y RF-051 cuando exista un conflicto de identificación del propietario; correcciones mediante soporte conforme a RN-037; autorización de representación cuando corresponda en entregas posteriores.

#### Descripción

Vehículos Services deberá permitir que un usuario solicite agregar un vehículo del cual sea propietario o que pertenezca a una persona jurídica en cuya representación esté autorizado para actuar. La relación de propiedad deberá establecerse con el propietario validado, sin convertir al usuario representante en propietario del vehículo.

Para la primera entrega, esta capacidad comprenderá únicamente propietarios persona natural y vehículos y documentos de Colombia. La representación de personas jurídicas se contempla para entregas posteriores y no formará parte de la primera entrega.

Cuando el usuario vaya a asociar su primer vehículo, la plataforma deberá solicitar sus nombres, apellidos, tipo y número de documento conforme a RN-025. Estos datos no serán obligatorios para crear la cuenta. En asociaciones posteriores se utilizará la información disponible, sujeta a las condiciones de actualización y revisión correspondientes.

Los datos de identidad podrán corregirse mientras se diligencian, antes de confirmar su envío. Una vez confirmados, aceptados y guardados, no podrán editarse ni eliminarse directamente por el usuario, aunque la asociación del vehículo todavía no se haya completado. Las correcciones posteriores requerirán soporte conforme a RN-037.

Antes de completar la identificación como propietario y la primera asociación, se comprobará si el mismo tipo y número de documento ya están asociados a otra cuenta. Si existe esa coincidencia, no se completará la identificación ni la asociación solicitada desde la nueva cuenta. Se mostrará el mensaje establecido en RN-025, sin fusionar cuentas, trasladar vehículos ni modificar permisos automáticamente. Mientras la coincidencia permanezca sin resolver, la solicitud no podrá completarse.

El usuario autenticado podrá solicitar una revisión manual del conflicto conforme a RN-035 y RF-051. Presentar la solicitud o recibir una aprobación de soporte no asociará automáticamente el vehículo. Cuando se autorice y ejecute una corrección dentro de los límites de RN-035, el usuario deberá completar nuevamente las comprobaciones normales de identificación y asociación.

Durante el proceso, la plataforma deberá obtener la información obligatoria que corresponda al tipo de vehículo, incluida su placa y su lectura actual de uso. También deberá obtener la información necesaria de la tarjeta de propiedad para comprobar que el documento corresponde al vehículo solicitado y que el propietario indicado en él corresponde con el propietario registrado en Vehículos Services.

En la primera entrega, la información del propietario registrado corresponderá a los datos declarados por el usuario. Su comparación con la tarjeta de propiedad deberá respetar las condiciones y limitaciones de RN-025 y de los puntos 63.4.3, 63.4.4 y 63.4.7 de `proyecto.md`. No constituirá una comprobación independiente de la identidad real de quien utiliza la cuenta ni acreditará por sí sola la autenticidad o vigencia de la tarjeta de propiedad.

La plataforma deberá comprobar si el vehículo ya existe antes de crear un nuevo registro vehicular. Si ya existe, conservará su identidad y su historial, y evaluará si corresponde establecer la relación solicitada. Si existe una relación vigente con otro propietario, la solicitud permanecerá sin completar conforme a RN-036. La primera entrega no permitirá sustituir esa relación ni realizar una transferencia mediante el registro.

La detección de coincidencias por placa y VIN, la normalización de identificadores y la comparación con la tarjeta de propiedad se realizarán conforme a RN-036. Una coincidencia impedirá crear automáticamente otro vehículo hasta comprobar la correspondencia. Si los identificadores obligatorios apuntan a vehículos diferentes o contradicen un registro existente, no se fusionarán registros ni se sobrescribirán identificadores, y la asociación permanecerá sin completar.

El propietario deberá ingresar el VIN y la plataforma comprobará su correspondencia con el VIN informado en la tarjeta de propiedad. El número de chasis y el número de motor serán información complementaria opcional. Su ausencia, falta de ingreso o imposibilidad de lectura no impedirán por sí solas completar el registro o la asociación, ni sustituirán el VIN obligatorio.

La plataforma aplicará las validaciones básicas de captura y los mensajes establecidos en RN-036. Antes de confirmar el envío de los datos vehiculares, el usuario podrá corregir lo digitado o presentar una nueva captura. Si las comprobaciones rechazan datos que todavía no hayan sido aceptados y guardados como información definitiva del vehículo, podrá corregirlos y repetir el proceso.

Después de cada corrección o sustitución del documento deberán repetirse las comprobaciones documentales y la búsqueda de coincidencias con la información actualizada, sin generar vehículos, historiales o relaciones duplicados. Estas acciones no permitirán editar datos de identidad personal ni datos vehiculares que ya estén confirmados y guardados conforme a RN-025, RN-036 y RN-037.

Si la inconsistencia con un registro existente persiste, se mostrará el mensaje establecido en RN-036 y no podrá completarse la asociación mediante las opciones de la primera entrega. El procedimiento especial de revisión de conflictos vehiculares se desarrollará posteriormente. RN-035 y RF-051 no permitirán resolver estos conflictos ni autorizar cambios de placa, VIN o propiedad.

Si el vehículo no existe, podrá registrarse como un vehículo nuevo dentro de la plataforma cuando se cumplan las validaciones requeridas.

El vehículo solo deberá quedar asociado como propiedad actual cuando se haya validado la correspondencia entre el propietario, el vehículo y la tarjeta de propiedad. Conocer la placa u otros datos del vehículo no deberá ser suficiente para establecer esa relación.

Después de confirmar, aceptar y guardar el registro definitivo, los datos obligatorios aplicables del vehículo no podrán editarse ni eliminarse directamente por el propietario. Los errores de captura se tramitarán mediante soporte conforme a RN-037 y los límites de RN-036. Esta vía no permitirá resolver conflictos entre vehículos existentes, sustituir su identidad ni transferir su propiedad.

#### Criterios de aceptación

1. La plataforma solicitará la información obligatoria común y la información adicional obligatoria aplicable al tipo de vehículo seleccionado, conforme al punto 63.1.5 de `proyecto.md`.
2. La plataforma no completará la incorporación del vehículo si falta información obligatoria aplicable, incluida la placa, o si no se puede validar la propiedad conforme a las reglas definidas.
3. La plataforma no exigirá datos que no apliquen al vehículo y distinguirá esa situación de un dato aplicable que no fue suministrado.
4. La plataforma comprobará que la tarjeta de propiedad presentada corresponde tanto al propietario registrado como al vehículo que se solicita agregar.
5. Si la correspondencia del propietario o del vehículo no se valida, la plataforma no establecerá automáticamente la relación de propiedad.
6. Antes de crear un vehículo, la plataforma comprobará si ya existe. Si existe, no creará otra identidad vehicular ni otro historial para él.
7. Cuando el vehículo ya exista, la plataforma conservará su historial y validará la asociación solicitada sin reemplazar automáticamente una relación vigente con otro propietario. Si existe esa relación con otro propietario, la asociación no se completará en la primera entrega, conforme a RN-036.
8. Cuando el vehículo no exista y se cumplan las validaciones requeridas, la plataforma creará su identidad vehicular y lo asociará al propietario validado.
9. La lectura actual de uso ingresada durante el proceso se conservará como el primer kilometraje conocido por Vehículos Services cuando el vehículo se registre por primera vez. No se interpretará como el comienzo de su vida útil real.
10. Cuando el propietario sea una persona jurídica, la autorización del usuario para actuar en su representación no establecerá una relación de propiedad personal entre ese usuario y el vehículo. Este criterio corresponderá a la entrega posterior que habilite dicha capacidad.
11. La primera entrega permitirá esta asociación únicamente para propietarios persona natural y vehículos y documentos de Colombia.
12. Antes de completar la primera asociación, deberán estar disponibles los nombres, apellidos, tipo y número de documento declarados por el usuario, conforme a RN-025. Su ausencia no impedirá crear una cuenta conforme a RF-001.
13. Una coincidencia documental no se presentará como una comprobación independiente de la identidad real del usuario ni de la autenticidad o vigencia de la tarjeta de propiedad.
14. La comparación y las validaciones aplicables se realizarán individualmente para cada vehículo; asociar uno no validará automáticamente la propiedad de otros.
15. Si el tipo y número de documento ya están asociados a otra cuenta, no se completará la identificación como propietario ni la asociación desde la nueva cuenta. Se mostrará el mensaje aprobado en RN-025 y no se fusionarán cuentas, trasladarán vehículos ni modificarán permisos automáticamente.
16. Ante ese conflicto de identificación, el usuario autenticado podrá solicitar revisión conforme a RF-051. La asociación permanecerá sin completar mientras el conflicto no se resuelva. Una corrección ejecutada conforme a RN-035 permitirá retomar las comprobaciones normales, sin asociar automáticamente el vehículo.
17. La detección de coincidencias y la comparación de identificadores aplicarán RN-036. Las coincidencias contradictorias impedirán completar la asociación, sin crear un duplicado, fusionar registros ni sobrescribir los identificadores existentes.
18. Si el vehículo ya está asociado al solicitante, se informará que está registrado y se permitirá consultarlo conforme a RF-004, sin crear otro vehículo, historial ni relación de propiedad.
19. El propietario deberá ingresar el VIN. No se completará el registro definitivo ni la asociación si falta ese dato, resulta ilegible en la tarjeta de propiedad o no puede comprobarse su correspondencia con el documento.
20. El número de chasis y el número de motor serán opcionales. Su ausencia, falta de ingreso o imposibilidad de lectura no bloquearán por sí solas el registro o la asociación. Se conservarán en campos separados del VIN, sin copiar automáticamente valores entre ellos ni utilizarlos para sustituirlo.
21. La placa y el VIN deberán superar la validación básica de captura establecida en RN-036: datos obligatorios con letras o números, sin espacios internos ni signos, aplicando la normalización aprobada. No se impondrá un patrón único de placa para todas las categorías ni se rechazará un VIN únicamente por tener una longitud distinta de 17 caracteres cuando corresponda con el campo VIN de la tarjeta de propiedad y cumpla las demás comprobaciones aplicables.
22. Cuando falten la placa o el VIN, existan caracteres no admitidos, se detecte una diferencia con la tarjeta de propiedad o no pueda leerse la información obligatoria, se mostrarán los mensajes establecidos en RN-036. Cuando pueda determinarse el campo afectado, se identificará para facilitar su corrección.
23. El usuario podrá corregir los datos vehiculares de la solicitud que todavía no hayan sido aceptados y guardados como información definitiva, o presentar una nueva captura, conforme a RN-036. La plataforma repetirá las comprobaciones documentales y la búsqueda de coincidencias con los datos actualizados. No creará definitivamente el vehículo ni establecerá la relación de propiedad hasta superar las comprobaciones obligatorias, y los reintentos no generarán vehículos, historiales o relaciones duplicados.
24. Si persiste un conflicto entre vehículos existentes o con una relación vigente de otro propietario, se mostrará el mensaje correspondiente de RN-036 y la asociación permanecerá sin completar, sin revelar información privada de terceros. La primera entrega no ofrecerá la revisión especial de esos conflictos ni utilizará RN-035, RF-051 o las correcciones de RN-037 para eludir esa limitación.
25. Una vez confirmados, aceptados y guardados, los nombres, apellidos, tipo y número de documento no podrán editarse ni eliminarse directamente por el usuario, aunque la asociación del vehículo todavía no se haya completado. Las solicitudes de corrección se tramitarán mediante soporte conforme a RN-037, respetando la unicidad de RN-025.
26. Después de confirmar, aceptar y guardar el registro definitivo del vehículo, el propietario no podrá editar ni eliminar directamente sus datos obligatorios aplicables. Sus solicitudes de corrección de errores de captura se tramitarán mediante soporte conforme a RN-037 y los límites de RN-036, sin modificar automáticamente los datos por presentar la solicitud.
27. La actualización posterior del kilometraje se realizará mediante nuevos registros conforme a RF-005. La edición de la información general no permitirá sobrescribir la lectura inicial ni las anteriores.

#### Decisiones pendientes

- Detallar los mecanismos técnicos de búsqueda de coincidencias por placa y VIN, respetando las condiciones aprobadas en RN-036.
- Detallar la implementación técnica de la validación básica de placa y VIN aprobada en RN-036 y las validaciones pendientes de los demás datos obligatorios según el tipo de vehículo. La validación avanzada de patrones por categoría se desarrollará posteriormente.
- Definir el mecanismo técnico para capturar y procesar la tarjeta de propiedad, aplicando los campos y criterios de comparación aprobados en RN-025 y RN-036.
- Desarrollar en los casos de uso y en el diseño de interacción los recorridos de ingreso, confirmación, corrección de datos todavía no guardados como definitivos, nueva captura y repetición de comprobaciones, respetando RN-025, RN-036 y RN-037.
- Detallar los recorridos de solicitudes que no puedan completarse por información obligatoria insuficiente, coincidencias contradictorias, diferencias con la placa o el VIN existentes o una relación de propiedad vigente con otro propietario, aplicando el tratamiento aprobado en RN-036. La revisión especial de conflictos vehiculares y la transferencia de propiedad se desarrollarán posteriormente y no condicionarán la primera entrega.
- Completar los casos de uso y mecanismos técnicos de revisión manual del propietario conforme a RN-035 y RF-051, manteniendo identificados los procedimientos especiales todavía pendientes y el tratamiento posterior de cuentas adicionales.
- Detallar las verificaciones y el procedimiento de corrección de errores de captura mediante soporte de RN-037, diferenciándolo de los conflictos sujetos a RN-035 y de la revisión especial vehicular aplazada.
- Definir cómo se acreditará la autorización para actuar en representación de una persona jurídica cuando se aborde la entrega posterior correspondiente.

---

### RF-004 — Consultar vehículos propios

- ID: RF-004.
- Nombre: Consultar vehículos propios.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Gestión de vehículos.
- Etapa prevista: Primera etapa del Propietario; el alcance de la representación de personas jurídicas está pendiente de precisar.
- Estado de la definición: Propuesta.
- Actor relacionado: Propietario autenticado o usuario autorizado para consultar vehículos de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Por documentar en `reglas-negocio.md`; aplican las definiciones generales de los puntos 63.1 y 63.4 de `proyecto.md`.
- Caso de uso preliminar relacionado: CU-004 Consultar vehículo.
- Dependencias: Autenticación del usuario; relación de propiedad actual válida y autorización de consulta en representación de una persona jurídica cuando corresponda.

#### Descripción

Vehículos Services deberá permitir que el Propietario consulte los vehículos asociados a él como propiedad actual y acceda a la ficha de información de cada uno de ellos.

Cuando el propietario sea una persona jurídica, un usuario autorizado podrá consultar los vehículos que tenga asignados conforme a sus permisos, sin que estos se presenten como de su propiedad personal.

Cada vehículo deberá presentarse como una unidad independiente, con su propia identidad, información general y lectura actual de uso disponible. La consulta deberá respetar las relaciones de propiedad y los permisos aplicables, sin mezclar la información de vehículos diferentes.

La consulta de información histórica, mantenimientos, repuestos, documentos, alertas y demás componentes relacionados se especificará en sus requerimientos correspondientes. La existencia de esos componentes no deberá asumirse como condición para consultar la ficha general del vehículo.

#### Criterios de aceptación

1. El Propietario autenticado podrá consultar los vehículos que tengan una relación de propiedad actual validada con él.
2. Si el Propietario tiene varios vehículos, podrá distinguir cada uno y abrir su ficha individual sin mezclar sus datos con los de otros vehículos.
3. La ficha mostrará la información general registrada para el vehículo y la lectura actual de uso disponible, diferenciando los datos no suministrados de los que no aplican cuando corresponda.
4. Si el Propietario no tiene vehículos asociados como propiedad actual, la plataforma mostrará esa situación sin presentar vehículos de otras personas.
5. La autenticación del usuario no será suficiente por sí sola para consultar un vehículo; deberá existir la relación de propiedad o la autorización de representación correspondiente.
6. Un cambio de propietario no deberá convertir automáticamente al propietario anterior en propietario actual dentro de esta consulta.
7. Un usuario autorizado de una persona jurídica podrá consultar únicamente los vehículos asignados para los que tenga permiso vigente, sin atribuirse su propiedad personal.

#### Decisión pendiente

Precisar el alcance de la consulta para usuarios autorizados de personas jurídicas en la primera etapa, conforme a los permisos y mecanismos de representación que se definan.

---

### RF-005 — Actualizar kilometraje del vehículo

- ID: RF-005.
- Nombre: Actualizar kilometraje del vehículo.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Gestión del kilometraje.
- Etapa prevista: Primera etapa del Propietario; el alcance de la representación de personas jurídicas está pendiente de precisar.
- Estado de la definición: Propuesta.
- Actor relacionado: Propietario autenticado del vehículo o usuario autorizado para actualizar el kilometraje en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: RN-001, RN-002 y RN-003; aplican las definiciones funcionales del punto 63.9 de `proyecto.md`.
- Caso de uso preliminar relacionado: CU-005 Actualizar kilometraje.
- Dependencias: Relación de propiedad actual válida; autorización de representación cuando corresponda; reglas de validación y consistencia de lecturas.

#### Descripción

Vehículos Services deberá permitir que el Propietario registre una nueva lectura del kilometraje de su vehículo sin depender de un Prestador de Servicios Vehiculares.

Cuando el propietario sea una persona jurídica, esta acción podrá realizarla un usuario autorizado para el vehículo y la funcionalidad correspondiente, según el alcance que se habilite.

La plataforma deberá identificar el vehículo, el valor de la lectura, su fecha y su procedencia, y evaluar la consistencia de la información antes de utilizarla para modificar el kilometraje actual. El registro de una lectura no deberá equivaler automáticamente a la actualización del kilometraje vigente.

Cuando la lectura corresponda a un momento anterior, deberá poder conservarse en el contexto histórico que le corresponda sin sustituir automáticamente el kilometraje actual. Las lecturas aceptadas y las correcciones realizadas deberán mantener trazabilidad conforme a las reglas del Historial Vehicular.

Las correcciones de lecturas registradas incorrectamente se regirán por `RF-038`, definido en `requerimientos-funcionales-propietario.md`, y por las validaciones específicas del kilometraje.

#### Criterios de aceptación

1. El Propietario autenticado podrá aportar una lectura de kilometraje para un vehículo con el que tenga una relación de propiedad actual válida. Cuando el propietario sea una persona jurídica, un usuario podrá hacerlo únicamente si cuenta con autorización vigente para ese vehículo y esa acción.
2. La plataforma deberá identificar la lectura, el vehículo al que corresponde y su procedencia antes de evaluarla.
3. Una lectura nueva solo actualizará el kilometraje actual cuando supere las validaciones de consistencia aplicables a su fecha y contexto.
4. Una lectura inferior al kilometraje actual no deberá disminuirlo automáticamente. La plataforma deberá diferenciar si se presenta como nueva lectura actual o si corresponde a un evento histórico.
5. Una lectura superior al kilometraje actual no deberá aceptarse como correcta únicamente por ser mayor; deberá evaluarse conforme a las reglas de consistencia aplicables.
6. Si la lectura no puede validarse para actualizar el kilometraje actual, la plataforma no deberá sustituir la referencia vigente por ese valor.
7. Una actualización aceptada deberá conservarse sin eliminar las lecturas anteriores del historial del vehículo.
8. El registro o la corrección de una lectura no deberá perder la trazabilidad de su valor, fecha, procedencia y cambios, según la información disponible y las reglas aplicables.

#### Decisiones pendientes

- Definir las validaciones concretas para lecturas inferiores, potencialmente atípicas o contradictorias con la secuencia temporal.
- Definir el tratamiento funcional de una lectura cuya consistencia no pueda determinarse con la información disponible.
- Precisar las validaciones y la reevaluación del kilometraje actual cuando se corrija una lectura mediante `RF-038`.
- Definir el permiso de actualización de kilometraje para usuarios autorizados de personas jurídicas y su disponibilidad en la primera etapa.


---


### RF-006 — Registrar mantenimiento realizado

- ID: RF-006.
- Nombre: Registrar mantenimiento realizado.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Gestión de mantenimientos.
- Etapa prevista: Primera etapa del Propietario; el alcance de la representación de personas jurídicas está pendiente de precisar.
- Estado de la definición: Propuesta.
- Actor relacionado: Propietario autenticado del vehículo o usuario autorizado para registrar mantenimientos en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: RN-011 y RN-014; aplican las definiciones funcionales de los puntos 63.6 y 63.7 de `proyecto.md`.
- Caso de uso preliminar relacionado: CU-006 Registrar mantenimiento.
- Dependencias: Relación de propiedad actual válida; autorización de representación cuando corresponda; definición de la información mínima para registrar una intervención y sus actividades.

#### Descripción

Vehículos Services deberá permitir que el Propietario registre un mantenimiento efectivamente realizado sobre su vehículo, compuesto por una o varias actividades. El registro deberá conservar la información necesaria para identificar la intervención, las acciones realizadas, el momento al que corresponde y quién realizó el trabajo cuando esa información esté disponible.

Cuando el propietario sea una persona jurídica, esta acción podrá realizarla un usuario autorizado para el vehículo y la funcionalidad correspondiente, según el alcance que se habilite.

El Propietario podrá registrar una intervención realizada por él mismo o por un taller, técnico u otro tercero, aunque ese actor no tenga una cuenta de Prestador de Servicios Vehiculares en la plataforma. La identificación de quien realizó el trabajo deberá mantenerse separada de la identificación del usuario que incorpora el registro.

Las actividades recomendadas, pendientes, cotizadas o programadas no deberán presentarse como actividades realizadas. Cada actividad efectivamente ejecutada podrá tener su propio seguimiento posterior cuando las reglas aplicables lo requieran; otras podrán permanecer únicamente como parte del historial.

Las reparaciones se documentarán mediante `RF-008`. Si una misma visita incluye mantenimiento y reparación, ambos registros podrán relacionarse sin duplicar las actividades realizadas.

El establecimiento de reglas y la renovación del seguimiento se regirán por `RF-033` y `RF-035`. Las correcciones del mantenimiento se regirán por `RF-038`, con las validaciones específicas de este tipo de registro.

#### Criterios de aceptación

1. El Propietario autenticado podrá registrar un mantenimiento realizado sobre un vehículo con el que tenga una relación de propiedad actual válida, sin depender de que exista un Prestador de Servicios Vehiculares registrado o autorizado. Cuando el propietario sea una persona jurídica, el usuario deberá contar con autorización vigente para ese vehículo y esa acción.
2. El registro permitirá identificar el mantenimiento como una intervención y asociarle una o varias actividades efectivamente realizadas.
3. El registro conservará la fecha a la que corresponde la intervención y la diferenciará de la fecha en que la información fue incorporada a Vehículos Services cuando sean diferentes.
4. Cuando se registre una lectura de kilometraje correspondiente a la intervención, su tratamiento respetará las validaciones aplicables antes de utilizarla para actualizar el kilometraje actual.
5. El Propietario podrá indicar, cuando corresponda, si realizó la intervención personalmente o proporcionar información sobre el taller, técnico o tercero que la realizó. Mencionar a un tercero no creará automáticamente una cuenta de Prestador ni una relación formal Prestador ↔ Vehículo.
6. La plataforma distinguirá las actividades realizadas de las recomendaciones, actividades pendientes o trabajos previstos que se registren en relación con la intervención.
7. Una actividad que requiera seguimiento podrá relacionarse con su propia regla sin imponer ese seguimiento ni los mismos objetivos a las demás actividades del mantenimiento.
8. El mantenimiento y sus actividades realizadas quedarán asociados al historial del vehículo. Una intervención posterior no reemplazará ni eliminará automáticamente las intervenciones anteriores.
9. El registro podrá relacionarse, cuando corresponda, con costos, repuestos, insumos, observaciones o documentos; su ausencia no impedirá por sí sola registrar un mantenimiento, salvo que una regla específica posteriormente aprobada exija alguno de esos elementos.

#### Decisiones pendientes

- Definir la información mínima obligatoria para registrar el mantenimiento y cada actividad realizada.
- Definir los catálogos de actividades y el tratamiento de actividades que el Propietario no encuentre en ellos.
- Precisar cómo se representarán los trabajos realizados y las recomendaciones o actividades pendientes originadas durante una misma intervención.
- Precisar los campos corregibles y las validaciones aplicables al mantenimiento conforme a `RF-038`.
- Definir el permiso de registro de mantenimientos para usuarios autorizados de personas jurídicas y su disponibilidad en la primera etapa.

---
### RF-007 — Consultar historial vehicular

- ID: RF-007.
- Nombre: Consultar historial vehicular.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Historial vehicular.
- Etapa prevista: Primera etapa del Propietario; el acceso de propietarios anteriores dependerá de la habilitación del cambio de propietario. El alcance de la representación de personas jurídicas está pendiente de precisar.
- Estado de la definición: Propuesta.
- Actores relacionados: Propietario actual; propietario anterior respecto de su período de propiedad; usuario autorizado para consultar en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: RN-011 y RN-014; aplican las definiciones funcionales de los puntos 63.6, 63.4.15, 63.4.16 y 63.4.17 de `proyecto.md`.
- Caso de uso preliminar relacionado: CU-007 Consultar historial.
- Dependencias: Autenticación; relación de propiedad actual o histórica y permisos de consulta aplicables; autorización de representación cuando corresponda.

#### Descripción

Vehículos Services deberá permitir que el Propietario actual consulte la información histórica disponible y autorizada de cada uno de sus vehículos.

El historial deberá mantenerse asociado a la identidad del vehículo y conservar su continuidad cuando se incorporen nuevos registros o cambie el propietario. La consulta podrá reunir información procedente de diferentes componentes, como kilometraje, mantenimientos, reparaciones, repuestos, abastecimientos y documentos, según las funcionalidades implementadas y las reglas de acceso correspondientes.

La existencia de un registro dentro del historial no deberá significar que todos sus datos o documentos adjuntos sean visibles para el Propietario actual. En particular, la continuidad del historial no deberá exponer automáticamente información personal o privada de propietarios anteriores.

Cuando finalice una relación de propiedad, el propietario anterior podrá conservar acceso de solo consulta a la información correspondiente a su período, conforme a las reglas de visibilidad aplicables. Este acceso no le permitirá modificar los registros ni consultar automáticamente los eventos de períodos posteriores.

Cuando el propietario sea una persona jurídica, un usuario autorizado podrá consultar el historial de los vehículos asignados dentro del alcance de sus permisos.

#### Criterios de aceptación

1. El Propietario autenticado podrá consultar el historial disponible de un vehículo con el que tenga una relación de propiedad actual válida.
2. Los registros consultados permanecerán asociados a la identidad del vehículo, sin crear historiales independientes por cambio de propietario, prestador o incorporación de información nueva.
3. La incorporación de un registro posterior no deberá eliminar ni sustituir automáticamente los registros anteriores.
4. La consulta permitirá distinguir el momento al que corresponde un evento de la fecha en que fue incorporado a la plataforma cuando ambos datos estén disponibles.
5. Un evento registrado como realizado deberá mantenerse diferenciado de una recomendación, actividad pendiente o intervención prevista.
6. Cuando el historial incluya eventos correspondientes a períodos de propiedad anteriores, la plataforma mostrará únicamente la información histórica cuya consulta esté permitida por las reglas de visibilidad y privacidad aplicables.
7. La plataforma no mostrará automáticamente documentos privados ni información personal de propietarios anteriores por el solo hecho de que formen parte del historial conservado.
8. El propietario anterior podrá consultar únicamente la información permitida de su período de propiedad, sin obtener acceso automático a eventos posteriores ni facultades para modificar registros.
9. Un usuario autorizado de una persona jurídica podrá consultar únicamente el historial de los vehículos y los datos para los que tenga permiso vigente.
10. La autenticación por sí sola no permitirá consultar el historial sin una relación de propiedad o autorización que habilite ese acceso.

#### Decisiones pendientes

- Precisar qué información de períodos de propiedad anteriores será visible, restringida o anonimizada para el Propietario actual.
- Precisar los datos y documentos que conservará visibles el propietario anterior dentro de su período, respetando el carácter de solo consulta.
- Determinar las opciones de búsqueda, filtros, ordenamiento y presentación del historial durante el diseño funcional y de UX/UI.
- Definir los permisos de consulta del historial para usuarios autorizados de personas jurídicas y su disponibilidad en la primera etapa.

---
### RF-008 — Registrar reparación realizada

- ID: RF-008.
- Nombre: Registrar reparación realizada.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Gestión de reparaciones e historial vehicular.
- Etapa prevista: Primera etapa del Propietario; el alcance de la representación de personas jurídicas está pendiente de precisar.
- Estado de la definición: Propuesta; pendiente de precisar la información específica de una reparación.
- Actor relacionado: Propietario autenticado del vehículo o usuario autorizado para registrar reparaciones en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Principios de continuidad, procedencia y visibilidad del historial vehicular definidos en `proyecto.md`; autorización de representación conforme a 63.4.17 y tratamiento del kilometraje conforme a 63.9; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: CU-008 Registrar reparación.
- Dependencias: Relación de propiedad actual válida; autorización de representación cuando corresponda; definición de los datos necesarios para registrar una reparación.

#### Descripción

Vehículos Services deberá permitir que el propietario registre una reparación realizada sobre uno de sus vehículos, aunque quien haya ejecutado el trabajo no utilice la plataforma.

Cuando el propietario sea una persona jurídica, esta acción podrá realizarla un usuario autorizado para el vehículo y la funcionalidad correspondiente, según el alcance que se habilite.

La reparación deberá documentarse como un evento propio del historial vehicular, diferenciado de los registros de mantenimiento. El registro deberá permitir describir la falla o condición atendida y el trabajo realizado, de acuerdo con los datos que se definan para esta funcionalidad.

Si una reparación y un mantenimiento se realizan en una misma visita o intervención, ambos podrán registrarse y relacionarse cuando corresponda, sin duplicar la misma actividad como si hubiera ocurrido dos veces. El hecho de que el propietario cree el registro no deberá indicar que realizó personalmente la reparación ni que el prestador mencionado la confirmó en la plataforma.

Las correcciones de la información registrada se regirán por `RF-038`, con las validaciones específicas de este tipo de evento.

#### Criterios de aceptación

1. El propietario autenticado podrá registrar una reparación realizada sobre un vehículo con el que tenga una relación de propiedad actual válida. Cuando el propietario sea una persona jurídica, el usuario deberá contar con autorización vigente para ese vehículo y esa acción.
2. La reparación quedará incorporada al historial del vehículo como un registro identificable y diferenciado de un mantenimiento.
3. El propietario podrá registrar una reparación efectuada por un tercero aunque ese tercero no tenga una cuenta ni una relación activa con el vehículo en Vehículos Services.
4. El registro conservará la fecha de realización de la reparación, diferenciándola de la fecha de incorporación a la plataforma cuando sean distintas, e identificará quién creó el registro y quién efectuó el trabajo cuando esta última información se conozca.
5. Registrar una reparación no creará automáticamente un registro de mantenimiento, ni registrar un mantenimiento creará automáticamente una reparación.
6. Si se relacionan registros de reparación y mantenimiento correspondientes a una misma intervención, cada registro conservará la descripción de lo que efectivamente se realizó en él.
7. La reparación permanecerá asociada al historial del vehículo conforme a las reglas generales de conservación y visibilidad.
8. Cuando se registre una lectura de kilometraje correspondiente a la reparación, su tratamiento respetará las validaciones aplicables antes de utilizarla para actualizar el kilometraje actual.

#### Decisiones pendientes

- Definir los datos obligatorios y opcionales de una reparación y sus validaciones.
- Precisar la forma de relacionar la reparación con mantenimientos, repuestos, costos, kilometraje y documentos cuando corresponda.
- Definir el permiso de registro de reparaciones para usuarios autorizados de personas jurídicas y su disponibilidad en la primera etapa.

---
### RF-009 — Registrar repuesto

- ID: RF-009.
- Nombre: Registrar repuesto.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Gestión de repuestos e historial vehicular.
- Etapa prevista: Primera etapa del Propietario; el alcance de la representación de personas jurídicas está pendiente de precisar.
- Estado de la definición: Propuesta; pendiente de definir los datos obligatorios y el seguimiento aplicable según el tipo de repuesto.
- Actor relacionado: Propietario autenticado del vehículo o usuario autorizado para registrar repuestos en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Principios de continuidad y trazabilidad del historial vehicular y definiciones de repuestos establecidas en `proyecto.md`; autorización de representación conforme a 63.4.17; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: CU-009 Registrar repuesto.
- Dependencias: Relación de propiedad actual válida; autorización de representación cuando corresponda; RF-006 Registrar mantenimiento realizado o RF-008 Registrar reparación realizada cuando el repuesto esté asociado a alguno de esos registros.

#### Descripción

Vehículos Services deberá permitir que el propietario registre los repuestos instalados, reemplazados o retirados de uno de sus vehículos, de acuerdo con la información que conozca sobre cada elemento.

Cuando el propietario sea una persona jurídica, esta acción podrá realizarla un usuario autorizado para el vehículo y la funcionalidad correspondiente, según el alcance que se habilite.

El registro del repuesto deberá distinguir el elemento involucrado de la actividad realizada sobre el vehículo. Cuando corresponda, deberá poder relacionarse con el mantenimiento, la reparación u otra intervención durante la cual se instaló, reemplazó o retiró, sin duplicar el registro de dicha intervención.

El propietario podrá incorporar esta información aunque el trabajo haya sido realizado por un tercero que no utilice Vehículos Services. La ausencia de datos como marca, referencia, serial o garantía no deberá obligarlo a inventarlos.

Cuando se registre el reemplazo de un repuesto, la información del elemento anterior deberá conservarse en el historial del vehículo; el nuevo repuesto deberá identificarse como un elemento diferente.

#### Criterios de aceptación

1. El propietario autenticado podrá registrar un repuesto relacionado con un vehículo con el que tenga una relación de propiedad actual válida. Cuando el propietario sea una persona jurídica, el usuario deberá contar con autorización vigente para ese vehículo y esa acción.
2. El registro permitirá identificar el repuesto con la información disponible y distinguirlo de la actividad en la que fue utilizado.
3. Cuando se conozca la intervención relacionada, el repuesto podrá asociarse a ella sin crear automáticamente un segundo registro de mantenimiento o reparación.
4. El propietario podrá indicar, cuando corresponda y se conozca, si el repuesto fue instalado, reemplazado o retirado.
5. La plataforma permitirá conservar los datos conocidos del repuesto sin exigir que el propietario proporcione información que desconoce, salvo los datos mínimos que se definan para identificar el registro.
6. Al registrar un reemplazo, la información histórica del repuesto anterior no será sobrescrita por la del nuevo.
7. Registrar un repuesto no implicará que el propietario realizó personalmente la intervención ni que un tercero mencionado confirmó el registro dentro de la plataforma.

#### Decisiones pendientes

- Definir los datos mínimos para registrar e identificar un repuesto y los datos adicionales aplicables según su tipo.
- Definir cuándo corresponde hacer seguimiento a su instalación, permanencia, reemplazo o retiro, y cómo registrar estos eventos cuando no exista previamente un mantenimiento o una reparación en la plataforma.
- Definir el permiso de registro de repuestos para usuarios autorizados de personas jurídicas y su disponibilidad en la primera etapa.

---

### RF-010 — Adjuntar documento o evidencia

- ID: RF-010.
- Nombre: Adjuntar documento o evidencia.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Gestión documental e historial vehicular.
- Etapa prevista: Primera etapa del Propietario; el alcance de la representación de personas jurídicas está pendiente de precisar.
- Estado de la definición: Propuesta; pendiente de definir formatos, límites y validaciones de los archivos.
- Actor relacionado: Propietario autenticado del vehículo o usuario autorizado para adjuntar archivos en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Reglas de privacidad, visibilidad y procedencia del historial vehicular definidas en `proyecto.md`; autorización de representación conforme a 63.4.17; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: CU-010 Adjuntar documento.
- Dependencias: Relación de propiedad actual válida; autorización de representación cuando corresponda; existencia del registro relacionado cuando el archivo se adjunte a uno.

#### Descripción

Vehículos Services deberá permitir que el propietario adjunte documentos o evidencias relacionados con uno de sus vehículos o con un registro de su historial, cuando corresponda. Estos archivos podrán incluir, entre otros, facturas, órdenes de servicio, fotografías y documentos del vehículo.

Cuando el propietario sea una persona jurídica, esta acción podrá realizarla un usuario autorizado para el vehículo y la funcionalidad correspondiente, según el alcance que se habilite. La consulta de los archivos por otros usuarios de la organización dependerá de los permisos que se definan.

El archivo adjunto deberá conservar su relación con el vehículo y, cuando aplique, con el registro al que sirve de soporte. Adjuntar un archivo no deberá reemplazar los datos estructurados necesarios para registrar un mantenimiento, una reparación u otro evento.

Los documentos y evidencias incorporados desde el frente del Propietario deberán tratarse como información privada del propietario correspondiente. La existencia de una relación activa entre el vehículo y un Prestador de Servicios Vehiculares no deberá otorgar automáticamente a ese prestador acceso a dichos archivos.

#### Criterios de aceptación

1. El propietario autenticado podrá adjuntar un archivo a un vehículo con el que tenga una relación de propiedad actual válida o a un registro de ese vehículo cuando la funcionalidad correspondiente lo permita. Cuando el propietario sea una persona jurídica, el usuario deberá contar con autorización vigente para ese vehículo y esa acción.
2. La plataforma conservará la asociación del archivo con el vehículo y, cuando corresponda, con el registro al que fue adjuntado.
3. El propietario podrá consultar sus archivos conforme a las reglas de acceso aplicables. Los usuarios de una persona jurídica podrán consultarlos únicamente cuando sus permisos lo habiliten.
4. Un Prestador de Servicios Vehiculares no podrá consultar automáticamente los archivos incorporados desde el frente del Propietario por el solo hecho de tener una relación activa con el vehículo.
5. El permiso para consultar los datos estructurados de un registro no concederá por sí mismo permiso para consultar sus archivos adjuntos.
6. Un mantenimiento, una reparación u otro evento podrá registrarse sin archivo adjunto cuando se hayan proporcionado sus datos requeridos, salvo que una regla específica establezca expresamente lo contrario.
7. Adjuntar un archivo no creará automáticamente un registro de mantenimiento, reparación u otro evento, ni completará por sí solo los datos requeridos para ese registro.

#### Decisiones pendientes

- Definir los formatos admitidos, el tamaño y la cantidad de archivos permitidos, así como las validaciones necesarias durante la carga.
- Definir los datos que acompañarán a cada archivo y las operaciones disponibles para consultarlo, reemplazarlo o retirarlo, respetando la trazabilidad del historial.
- Definir los permisos para adjuntar y consultar archivos en representación de personas jurídicas y su disponibilidad en la primera etapa.

---

### RF-011 — Consultar próximos mantenimientos

- ID: RF-011.
- Nombre: Consultar próximos mantenimientos.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Seguimiento de mantenimientos.
- Etapa prevista: Primera etapa del Propietario; el alcance de la representación de personas jurídicas está pendiente de precisar.
- Estado de la definición: Propuesta; pendiente de definir la presentación y los criterios de consulta.
- Actor relacionado: Propietario autenticado del vehículo o usuario autorizado para consultar el seguimiento en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Reglas de mantenimiento por kilometraje y tiempo y determinación del próximo objetivo definidas en 63.11 de `proyecto.md`; autorización de representación conforme a 63.4.17; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: CU-011 Consultar próximos mantenimientos.
- Dependencias: Relación de propiedad actual válida; autorización de representación cuando corresponda; regla aplicable conforme a RF-033 y referencias válidas para determinar los objetivos. La renovación de ciclos se regirá por RF-035.

#### Descripción

Vehículos Services deberá permitir que el propietario consulte las actividades de mantenimiento de su vehículo que tengan seguimiento definido y conozca sus próximos objetivos cuando exista información suficiente para determinarlos.

Cuando el propietario sea una persona jurídica, esta consulta podrá realizarla un usuario autorizado para el vehículo y la funcionalidad correspondiente, según el alcance que se habilite.

Según la regla aplicable, el próximo objetivo podrá expresarse en kilometraje, fecha o ambos. Cada actividad deberá conservar su propio seguimiento, incluso si fue registrada junto con otras actividades en un mismo mantenimiento.

La consulta deberá diferenciar una actividad sin seguimiento de una actividad que requiere seguimiento, pero cuyo próximo objetivo aún no puede calcularse por falta de información. La plataforma no deberá inventar fechas, kilometrajes ni intervalos para completar los datos faltantes.

La actualización del kilometraje actual o el transcurso del tiempo podrán modificar la evaluación del avance hacia un objetivo, pero no deberán desplazar por sí solos dicho objetivo.

#### Criterios de aceptación

1. El propietario autenticado podrá consultar el seguimiento de un vehículo con el que tenga una relación de propiedad actual válida. Cuando el propietario sea una persona jurídica, el usuario deberá contar con autorización vigente para ese vehículo y esa consulta.
2. Para cada actividad con una regla aplicable e información suficiente, la plataforma mostrará el próximo objetivo calculado en kilometraje, fecha o ambos, según corresponda.
3. Si una actividad requiere seguimiento, pero falta información para calcular un objetivo, la consulta reflejará esa situación sin presentar un objetivo inventado.
4. La consulta distinguirá las actividades que no tienen seguimiento definido de aquellas cuyo seguimiento no puede calcularse todavía.
5. Cuando varias actividades de un mismo mantenimiento tengan reglas diferentes, sus próximos objetivos se mostrarán de forma diferenciada.
6. Un cambio en el kilometraje actual o el avance de la fecha actual no modificará por sí solo el objetivo previamente determinado.
7. En una regla combinada, si solo puede determinarse uno de los objetivos, la consulta mostrará el objetivo calculable e identificará la información insuficiente para el otro.
8. La consulta utilizará la información y las reglas correspondientes al vehículo seleccionado, sin incluir datos de vehículos a los que el usuario no tenga acceso.

#### Decisiones pendientes

- Definir los datos y estados que se mostrarán en la consulta, así como sus criterios de ordenamiento y presentación.
- Precisar en `reglas-negocio.md` los cálculos y el tratamiento de información incompleta, manteniendo coherencia con RF-033, RF-034 y RF-035.
- Definir los permisos de consulta del seguimiento para usuarios autorizados de personas jurídicas y su disponibilidad en la primera etapa.

---

### RF-012 — Consultar alertas

- ID: RF-012.
- Nombre: Consultar alertas.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Alertas del vehículo.
- Etapa prevista: Primera etapa del Propietario; el alcance de la representación de personas jurídicas está pendiente de precisar.
- Estado de la definición: Propuesta; pendiente de definir las condiciones específicas que originan cada alerta y su presentación.
- Actor relacionado: Propietario autenticado del vehículo o usuario autorizado para consultar alertas en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Definiciones de alertas, su vigencia y las condiciones que pueden originarlas establecidas en 63.12 de `proyecto.md`; autorización de representación conforme a 63.4.17; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: CU-012 Consultar alertas.
- Dependencias: Relación de propiedad actual válida; autorización de representación cuando corresponda; información del vehículo y reglas aplicables para identificar condiciones relevantes.

#### Descripción

Vehículos Services deberá permitir que el propietario consulte las alertas relacionadas con sus vehículos. Cada alerta deberá comunicar una condición relevante identificada a partir de la información disponible y de las reglas funcionales aplicables.

Cuando el propietario sea una persona jurídica, esta consulta podrá realizarla un usuario autorizado para el vehículo y la funcionalidad correspondiente, según el alcance que se habilite.

La consulta deberá permitir identificar a qué vehículo y situación corresponde cada alerta, así como su condición vigente cuando esta haya evolucionado. Por ejemplo, una actividad de mantenimiento próxima a su objetivo podrá pasar a una condición de objetivo alcanzado o superado según la información disponible y las reglas aplicables.

Una alerta deberá mantenerse diferenciada del próximo objetivo de mantenimiento, de una recomendación, de una notificación y del registro de una intervención efectivamente realizada. Consultar una alerta no deberá interpretarse como haber atendido la condición que la originó.

#### Criterios de aceptación

1. El propietario autenticado podrá consultar las alertas de los vehículos con los que tenga una relación de propiedad actual válida. Cuando el propietario sea una persona jurídica, el usuario deberá contar con autorización vigente para el vehículo y esa consulta.
2. Cada alerta consultada permitirá identificar el vehículo y la condición relevante que comunica.
3. La plataforma no presentará una alerta basada en fechas, kilometrajes u otros datos inventados cuando falte información necesaria para sustentarla.
4. Cuando cambie la información que sustenta una alerta, la condición presentada deberá corresponder a la evaluación vigente según las reglas aplicables.
5. La evolución de una misma condición se tratará conforme a una regla definida de actualización o sustitución de la alerta, sin mostrar como alertas vigentes independientes duplicados que representen la misma condición.
6. Consultar una alerta no registrará automáticamente un mantenimiento, una reparación ni otra intervención sobre el vehículo.
7. El envío de notificaciones relacionadas con una alerta se regirá por RF-036; la existencia de la alerta no exigirá por sí sola una comunicación externa.
8. Un usuario no podrá consultar alertas de vehículos o información para los que no tenga permiso de acceso.

#### Decisiones pendientes

- Definir las condiciones específicas que originarán alertas durante la primera etapa.
- Definir qué información mostrará cada alerta y cómo se presentarán las alertas vigentes e históricas.
- Precisar las reglas para actualizar, sustituir, resolver o cerrar una alerta cuando cambie la condición que la originó.
- Definir los permisos de consulta de alertas para usuarios autorizados de personas jurídicas y su disponibilidad en la primera etapa.
---

### RF-013 — Autorizar Prestador de Servicios Vehiculares para un vehículo

- ID: RF-013.
- Nombre: Autorizar Prestador de Servicios Vehiculares para un vehículo.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Relación y autorización entre Prestador de Servicios Vehiculares y vehículo.
- Etapa prevista: Tercera etapa de integración entre Propietario y Prestador de Servicios Vehiculares.
- Estado de la definición: Conceptual; pendiente de definir los mecanismos de autorización y el alcance detallado de los permisos.
- Actor relacionado: Propietario autenticado del vehículo o usuario expresamente autorizado para gestionar estas relaciones en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Relación, autorización y alcance definidos en 63.5.2 de `proyecto.md`; representación de personas jurídicas conforme a 63.4.17; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: CU-013 Autorizar Prestador de Servicios Vehiculares.
- Dependencias: Relación de propiedad actual válida; disponibilidad del Prestador en la plataforma; permisos aplicables. Cuando la autorización responda a una solicitud del Prestador, se relacionará con RF-015, cuya definición corresponderá a `requerimientos-funcionales-prestador.md`.

#### Descripción

Vehículos Services deberá permitir que el propietario autorice a un Prestador de Servicios Vehiculares para relacionarse con uno de sus vehículos. La autorización podrá iniciarse directamente por el propietario o concederse al aceptar una solicitud presentada por el prestador, según los mecanismos que se habiliten en la etapa de integración.

Cuando exista una solicitud, el propietario deberá poder revisarla y aceptarla o rechazarla. Una solicitud pendiente o rechazada no deberá establecer una relación activa ni conceder los accesos que dependan de ella.

Cuando el propietario sea una persona jurídica, la gestión de estas autorizaciones podrá realizarla un usuario con permiso expreso para esa acción. Tener asignado un vehículo no deberá otorgarle automáticamente permiso para autorizar prestadores.

La relación autorizada deberá establecerse para un vehículo específico. Autorizar a un prestador para un vehículo no deberá extender la autorización a otros vehículos del mismo propietario.

Una relación activa permitirá al prestador interactuar con el vehículo únicamente dentro del alcance de las funcionalidades, permisos y reglas de visibilidad que le correspondan. La autorización no deberá otorgarle propiedad sobre el vehículo ni acceso irrestricto a su historial o a los documentos privados del propietario.

#### Criterios de aceptación

1. El propietario autenticado podrá autorizar a un Prestador para un vehículo con el que tenga una relación de propiedad actual válida mediante un mecanismo habilitado.
2. Cuando el propietario sea una persona jurídica, el usuario deberá contar con permiso vigente para gestionar la autorización sobre ese vehículo.
3. El actor autorizado podrá revisar una solicitud correspondiente al vehículo y aceptarla o rechazarla.
4. La relación entre el prestador y el vehículo solo quedará activa después de una autorización válida.
5. Una solicitud pendiente o rechazada no establecerá la relación ni otorgará al prestador los accesos que dependan de ella.
6. La autorización quedará asociada únicamente al vehículo seleccionado y no se extenderá automáticamente a otros vehículos del propietario.
7. El propietario podrá mantener relaciones independientes entre un mismo vehículo y distintos prestadores cuando corresponda.
8. La existencia de una relación activa no otorgará por sí sola acceso a todos los registros del historial ni a los documentos privados incorporados desde el frente del Propietario.
9. La plataforma conservará la identificación del vehículo, del prestador y de la autorización o decisión sobre la solicitud, junto con el actor responsable y el momento en que se realizó.

#### Decisiones pendientes

- Definir los mecanismos de autorización directa y de revisión, aceptación o rechazo de solicitudes.
- Precisar los permisos y la información visible para el prestador cuando la relación esté activa, manteniendo coherencia con `requerimientos-funcionales-prestador.md`.
- Definir quién podrá gestionar estas autorizaciones en representación de una persona jurídica.
- Precisar las condiciones de vigencia y reactivación de la relación. La revocación por el Propietario se regirá por RF-014.

---

### RF-014 — Revocar acceso de un Prestador de Servicios Vehiculares

- ID: RF-014.
- Nombre: Revocar acceso de un Prestador de Servicios Vehiculares.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Relación y autorización entre Prestador de Servicios Vehiculares y vehículo.
- Etapa prevista: Tercera etapa de integración entre Propietario y Prestador de Servicios Vehiculares.
- Estado de la definición: Conceptual; pendiente de definir el procedimiento de finalización y los permisos que dependen de la relación.
- Actor relacionado: Propietario autenticado del vehículo o usuario expresamente autorizado para gestionar estas relaciones en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Vigencia, finalización y trazabilidad de la relación definidas en 63.5.3 de `proyecto.md`; representación de personas jurídicas conforme a 63.4.17; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: CU-014 Revocar acceso de Prestador de Servicios Vehiculares.
- Dependencias: Relación de propiedad actual válida; existencia de una relación activa con el prestador; permiso de revocación cuando se actúe en representación de una persona jurídica.

#### Descripción

Vehículos Services deberá permitir que el propietario finalice la relación activa entre uno de sus vehículos y un Prestador de Servicios Vehiculares. Al finalizarla, el prestador dejará de estar autorizado para utilizar las funcionalidades y consultar la información del vehículo cuyo acceso dependa de esa relación.

Cuando el propietario sea una persona jurídica, esta acción podrá realizarla un usuario con permiso expreso para gestionar la relación. Tener asignado un vehículo no deberá otorgarle automáticamente permiso para revocar autorizaciones de prestadores.

La finalización deberá aplicarse únicamente a la relación seleccionada. No deberá afectar automáticamente las relaciones del mismo prestador con otros vehículos ni las relaciones del vehículo con otros prestadores.

Los servicios, intervenciones y demás registros incorporados legítimamente al historial durante la relación deberán conservarse con su procedencia. La finalización tampoco deberá cancelar por sí sola obligaciones comerciales, contractuales o garantías externas a Vehículos Services.

Si posteriormente se desea establecer nuevamente la relación, deberá existir una nueva autorización válida conforme a RF-013, conservando la trazabilidad de los períodos anteriores.

#### Criterios de aceptación

1. El propietario autenticado podrá seleccionar una relación activa entre uno de sus vehículos y un prestador y finalizarla.
2. Cuando el propietario sea una persona jurídica, el usuario deberá contar con permiso vigente para revocar la relación correspondiente.
3. Después de la finalización, la relación quedará inactiva y dejará de habilitar los accesos y acciones del prestador que dependían de ella.
4. La finalización de una relación no modificará automáticamente las relaciones del prestador con otros vehículos ni las del vehículo con otros prestadores.
5. Los registros históricos creados durante el período activo permanecerán asociados al vehículo y conservarán la identificación de su procedencia cuando corresponda.
6. La plataforma conservará la trazabilidad del período activo, del actor que realizó la revocación y del momento en que se finalizó la relación.
7. Una relación finalizada no volverá a estar activa automáticamente por haber existido anteriormente; se requerirá una nueva autorización válida.
8. La conservación de registros históricos no otorgará al prestador acceso permanente al vehículo después de finalizar la relación.

#### Decisiones pendientes

- Definir el procedimiento de revocación y si será necesario indicar un motivo o confirmar la acción.
- Precisar qué accesos concretos perderá el prestador, según las reglas de permisos y visibilidad y en coherencia con `requerimientos-funcionales-prestador.md`.
- Definir quién podrá revocar estas relaciones en representación de una persona jurídica.


---

### RF-018 — Consultar recomendaciones

- ID: RF-018.
- Nombre: Consultar recomendaciones.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Recomendaciones para el Propietario.
- Etapa prevista: Primera etapa del Propietario, según las capacidades de recomendación que se incluyan en ella; el alcance de la representación de personas jurídicas está pendiente de precisar.
- Estado de la definición: Propuesta; pendiente de definir las recomendaciones disponibles inicialmente y sus condiciones de generación.
- Actor relacionado: Propietario autenticado del vehículo o usuario autorizado para consultar recomendaciones en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: RN-009 Recomendación automática; principios de diferenciación entre recomendación y diagnóstico definidos en `proyecto.md`; autorización de representación conforme a 63.4.17; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: CU-018 Consultar recomendaciones.
- Dependencias: Relación de propiedad actual válida; autorización de representación cuando corresponda; información del vehículo y reglas aplicables a cada tipo de recomendación.

#### Descripción

Vehículos Services deberá permitir que el propietario consulte las recomendaciones generadas para sus vehículos a partir de la información disponible y de las reglas aplicables.

Cuando el propietario sea una persona jurídica, esta consulta podrá realizarla un usuario autorizado para el vehículo y la funcionalidad correspondiente, según el alcance que se habilite.

Una recomendación automática deberá orientar al propietario sobre una revisión o acción que podría considerar. Deberá identificarse como resultado generado por la plataforma y mantenerse diferenciada de una alerta, un diagnóstico profesional y el registro de un servicio efectivamente realizado.

La plataforma no deberá afirmar que un componente se encuentra en buen estado ni recomendar una intervención específica basándose en información insuficiente. Esto no impedirá sugerir una revisión para obtener información cuando las reglas aplicables así lo determinen.

Las recomendaciones específicas de preparación para viajes se regirán por RF-026, conservando las condiciones generales de este requisito.

#### Criterios de aceptación

1. El propietario autenticado podrá consultar las recomendaciones de los vehículos con los que tenga una relación de propiedad actual válida. Cuando el propietario sea una persona jurídica, el usuario deberá contar con autorización vigente para el vehículo y esa consulta.
2. Cada recomendación permitirá identificar el vehículo al que corresponde y la revisión o acción que propone considerar.
3. Una recomendación generada por la plataforma se presentará como automática, sin atribuirla a un Prestador de Servicios Vehiculares o profesional.
4. La consulta distinguirá una recomendación de una alerta, un diagnóstico profesional y un servicio realizado.
5. La existencia de una recomendación no registrará automáticamente una intervención realizada sobre el vehículo.
6. Una recomendación no afirmará que un componente se encuentra en buen estado o averiado cuando la información disponible no permita sustentar esa conclusión.
7. Una recomendación podrá existir sin estar asociada a una alerta, de acuerdo con las reglas aplicables.
8. Un usuario no podrá consultar recomendaciones de vehículos o información para los que no tenga permiso de acceso.

#### Decisiones pendientes

- Definir qué tipos de recomendaciones estarán disponibles en la primera etapa.
- Definir las condiciones de generación, actualización y vigencia de cada tipo de recomendación.
- Definir qué información de respaldo se mostrará al propietario para que comprenda el origen de una recomendación.
- Definir los permisos de consulta de recomendaciones para usuarios autorizados de personas jurídicas y su disponibilidad en la primera etapa.

---
### RF-019 — Generar reporte vehicular

- ID: RF-019.
- Nombre: Generar reporte vehicular.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Reportes del historial vehicular.
- Etapa prevista: Primera etapa del Propietario, con contenido ajustado a la información y funcionalidades disponibles; el alcance de la representación de personas jurídicas está pendiente de precisar.
- Estado de la definición: Propuesta; pendiente de definir el contenido inicial, el formato y las opciones de generación.
- Actor relacionado: Propietario autenticado del vehículo o usuario autorizado para generar reportes en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Continuidad, procedencia y visibilidad del historial vehicular definidas en `proyecto.md`; autorización de representación conforme a 63.4.17; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: CU-019 Generar reporte vehicular.
- Dependencias: Relación de propiedad actual válida; autorización para generar reportes cuando se actúe en representación de una persona jurídica; información consultable conforme a RF-007.

#### Descripción

Vehículos Services deberá permitir que el propietario genere un reporte con información consolidada del historial de uno de sus vehículos.

Cuando el propietario sea una persona jurídica, esta acción podrá realizarla un usuario autorizado para el vehículo y la generación de reportes. Tener permiso de consulta no deberá conceder automáticamente permiso para generar, descargar o compartir un reporte.

El reporte deberá construirse a partir de los registros disponibles y accesibles para quien lo genera. Según las funcionalidades implementadas y la información existente, podrá incluir datos generales del vehículo, kilometraje, mantenimientos, reparaciones, repuestos y otros eventos de su ciclo de vida.

La generación del reporte no deberá crear eventos históricos nuevos ni completar información faltante con datos supuestos. La inclusión de documentos adjuntos, información privada de propietarios anteriores o datos restringidos de otros actores deberá respetar las reglas de privacidad y visibilidad aplicables.

El reporte podrá servir como apoyo para consultar la evolución del vehículo o para un eventual proceso de venta, sin que su generación transfiera la propiedad ni conceda acceso al vehículo a otra persona.

#### Criterios de aceptación

1. El propietario autenticado podrá solicitar un reporte de un vehículo con el que tenga una relación de propiedad actual válida. Cuando el propietario sea una persona jurídica, el usuario deberá contar con autorización vigente para ese vehículo y la generación del reporte.
2. El reporte identificará el vehículo y presentará de forma consolidada la información histórica incluida en él.
3. El contenido corresponderá a registros existentes y a datos que el usuario tenga permiso de consultar al momento de generar el reporte.
4. Cuando no exista información de una categoría, el reporte no presentará como realizados eventos que no estén registrados.
5. La generación del reporte no modificará los registros del historial ni la relación de propiedad del vehículo.
6. La inclusión de un dato estructurado en el reporte no implicará automáticamente la inclusión de un documento privado adjunto a ese dato.
7. El reporte no expondrá información personal, privada o restringida de otros actores por el solo hecho de estar asociada al historial del vehículo.

#### Decisiones pendientes

- Definir el contenido mínimo del reporte inicial y cómo evolucionará al incorporarse nuevas funcionalidades.
- Definir el formato del reporte y las opciones disponibles para consultarlo, descargarlo o compartirlo.
- Precisar el tratamiento de documentos adjuntos y de información correspondiente a períodos de propiedad anteriores.
- Definir los permisos de generación, descarga y uso compartido de reportes para usuarios autorizados de personas jurídicas y su disponibilidad en la primera etapa.
- Definir si el propietario anterior podrá generar reportes limitados a la información consultable de su período. Su acceso de solo consulta no aprobará por sí mismo esa capacidad.

---

### RF-020 — Transferir vehículo a un nuevo propietario

- ID: RF-020.
- Nombre: Transferir vehículo a un nuevo propietario.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Gestión de propiedad del vehículo.
- Etapa prevista: Etapa posterior por definir; su inclusión en el MVP está pendiente de evaluación.
- Estado de la definición: Conceptual; pendiente de definir el procedimiento y las validaciones de la transferencia.
- Actores relacionados: Propietario actual y nuevo propietario; usuarios con autorización para representar a una persona jurídica en la transferencia cuando corresponda.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Cambio de propietario, períodos de propiedad, validación mediante tarjeta de propiedad y visibilidad del historial definidos en 63.4 de `proyecto.md`; finalización de relaciones con prestadores conforme a 63.5.4; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: CU-020 Transferir vehículo.
- Dependencias: Existencia del vehículo y de su relación de propiedad actual; mecanismos de autorización, aceptación y validación del nuevo propietario; permisos de representación cuando corresponda.

#### Descripción

Vehículos Services deberá contemplar la transferencia de un vehículo de su propietario actual a un nuevo propietario, mediante un proceso que incluya la autorización del propietario actual, la aceptación del nuevo propietario y la validación de la propiedad mediante la tarjeta de propiedad correspondiente.

Cuando alguna de las partes sea una persona jurídica, las acciones deberán realizarse mediante usuarios autorizados para representarla en este proceso. Tener permiso para consultar o gestionar información de un vehículo no deberá conceder automáticamente permiso para transferirlo o aceptar su transferencia.

Una transferencia válida deberá finalizar el período de propiedad anterior e iniciar uno nuevo para el mismo vehículo. La identidad, el kilometraje y el historial vehicular deberán conservar su continuidad, sin crear un vehículo duplicado ni atribuir al nuevo propietario los registros creados anteriormente.

Después de la transferencia, el acceso de cada propietario deberá ajustarse a su relación con el vehículo y a las reglas de privacidad y visibilidad. El propietario anterior podrá conservar acceso de solo consulta a la información correspondiente a su período, sin administrar el vehículo ni acceder automáticamente a los eventos posteriores, conforme a RF-007.

Cuando existan relaciones activas con Prestadores de Servicios Vehiculares, estas deberán finalizar al completarse el cambio de propietario. Las autorizaciones anteriores no se transferirán al nuevo propietario, quien podrá establecer nuevas relaciones conforme a RF-013 cuando la integración esté disponible.

#### Criterios de aceptación

1. La plataforma no establecerá una nueva relación de propiedad únicamente por una solicitud unilateral que no haya completado las autorizaciones y validaciones definidas para la transferencia.
2. Antes de establecer la nueva relación, se validará la propiedad del nuevo propietario mediante la tarjeta de propiedad conforme a las reglas aplicables.
3. Cuando alguna parte sea una persona jurídica, el usuario que actúe en su representación deberá tener autorización vigente para la acción correspondiente.
4. Al completarse una transferencia válida, finalizará el período del propietario anterior y comenzará el período del nuevo propietario sobre el mismo vehículo.
5. La transferencia no creará un vehículo duplicado ni reiniciará su kilometraje o historial.
6. Los registros históricos anteriores conservarán su procedencia y no serán atribuidos al nuevo propietario como si él los hubiera creado.
7. El propietario anterior dejará de tener facultades de administración sobre el vehículo y solo podrá consultar la información de su período que las reglas de acceso le permitan.
8. El nuevo propietario no recibirá automáticamente acceso a información personal o documentos privados del propietario anterior.
9. Todas las relaciones activas con prestadores finalizarán al completarse el cambio de propietario, sin eliminar los registros históricos generados durante esas relaciones.
10. Un prestador previamente relacionado no obtendrá acceso bajo el nuevo propietario sin una nueva autorización válida.
11. La plataforma conservará la trazabilidad del cambio y de los períodos de propiedad resultantes.

#### Decisiones pendientes

- Definir el flujo de autorización, aceptación y validación de la transferencia, incluidos los casos en que alguna parte no pueda participar.
- Definir la fecha efectiva de finalización del período anterior y de inicio del nuevo período.
- Precisar los permisos para realizar o aceptar transferencias en representación de personas jurídicas y el tratamiento de sus autorizaciones de usuarios ante el cambio de propietario.
- Precisar la visibilidad de cada tipo de información después de la transferencia, manteniendo coherencia con RF-007 y las reglas de privacidad del proyecto.

---
### RF-021 — Registrar viaje para su preparación

- ID: RF-021.
- Nombre: Registrar viaje para su preparación.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Preparación para viajes.
- Etapa prevista: Primera etapa del Propietario, sujeta a la definición del MVP; el alcance de la representación de personas jurídicas está pendiente de precisar.
- Estado de la definición: Propuesta; pendiente de definir los datos y el ciclo de vida del viaje registrado.
- Actor relacionado: Propietario autenticado del vehículo o usuario autorizado para registrar viajes en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: RN-016 Preparación para viaje y RN-017 Información del viaje; autorización de representación conforme a 63.4.17 de `proyecto.md`; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: CU-021 Registrar viaje.
- Dependencias: Relación de propiedad actual válida; autorización de representación cuando corresponda; registro de destino conforme a RF-022 o de distancia estimada conforme a RF-023.

#### Descripción

Vehículos Services deberá permitir que el propietario registre un viaje que desea preparar para uno de sus vehículos. Este registro servirá como contexto para consultar posteriormente la preparación, la lista de verificación y las recomendaciones previas al viaje.

Cuando el propietario sea una persona jurídica, esta acción podrá realizarla un usuario autorizado para el vehículo y la funcionalidad correspondiente, según el alcance que se habilite.

Inicialmente, el propietario podrá proporcionar un destino o una distancia estimada, según la información de la que disponga. Los requisitos RF-022 y RF-023 especifican esas formas de aportar información; no implican que ambos datos sean obligatorios ni que deban registrarse en pasos o pantallas independientes.

Registrar el viaje con fines de preparación no deberá significar que el desplazamiento ya se realizó, que el vehículo recorrió esa distancia o que su kilometraje actual debe actualizarse automáticamente.

La funcionalidad deberá poder utilizarse desde el módulo del Propietario sin requerir la participación de un Prestador de Servicios Vehiculares.

#### Criterios de aceptación

1. El propietario autenticado podrá registrar un viaje para un vehículo con el que tenga una relación de propiedad actual válida. Cuando el propietario sea una persona jurídica, el usuario deberá contar con autorización vigente para ese vehículo y esa acción.
2. El registro quedará relacionado con el vehículo seleccionado y permitirá identificar la información del viaje que haya proporcionado el usuario.
3. El propietario podrá iniciar la preparación indicando un destino o una distancia estimada, sin exigir necesariamente ambos datos.
4. El registro del viaje no se presentará como constancia de que el desplazamiento fue realizado.
5. Registrar una distancia estimada no modificará automáticamente el kilometraje actual del vehículo ni creará una lectura de kilometraje recorrido.
6. Registrar el viaje no generará por sí solo un diagnóstico profesional ni una certificación de que el vehículo está en condiciones seguras para viajar.
7. La preparación del viaje no dependerá de que exista un Prestador de Servicios Vehiculares registrado o relacionado con el vehículo.

#### Decisiones pendientes

- Definir los datos mínimos del viaje y las condiciones para registrar, actualizar o cancelar su preparación.
- Definir si los viajes preparados permanecerán en el historial vehicular y cómo se distinguirán de los viajes efectivamente realizados.
- Precisar qué resultados de preparación estarán disponibles en la primera etapa y cuáles se incorporarán posteriormente.
- Definir el permiso de registro de viajes para usuarios autorizados de personas jurídicas y su disponibilidad en la primera etapa.


---

### RF-022 — Registrar destino de viaje

- ID: RF-022.
- Nombre: Registrar destino de viaje.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Preparación para viajes.
- Etapa prevista: Primera etapa del Propietario, sujeta a la definición del MVP; la representación de personas jurídicas se regirá por el alcance definido para RF-021.
- Estado de la definición: Propuesta; pendiente de definir la forma de ingresar e identificar el destino.
- Actor relacionado: Propietario autenticado o usuario autorizado en representación de una persona jurídica, conforme a RF-021.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: RN-017 Información del viaje y RN-024 Información incompleta; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: CU-022 Registrar destino de viaje.
- Dependencias: Contexto del viaje y autorización conforme a RF-021. El destino podrá incorporarse durante el registro inicial del viaje o posteriormente, según las condiciones que se definan.

#### Descripción

Vehículos Services deberá permitir que el propietario indique una ciudad o destino para un viaje que desea preparar con uno de sus vehículos.

El destino deberá quedar asociado al viaje correspondiente y podrá utilizarse como contexto para las funcionalidades de preparación que cuenten con reglas aplicables. Indicar un destino no deberá exigir que el propietario conozca o registre también la distancia estimada.

La plataforma no deberá asumir una distancia recorrida ni calcular automáticamente una ruta a partir del destino mientras no se haya definido e implementado una funcionalidad específica para ello.

Los permisos para registrar el destino se regirán por la autorización aplicable al vehículo y al viaje, sin considerar suficiente el acceso de solo consulta.

#### Criterios de aceptación

1. El actor autorizado conforme a RF-021 podrá indicar un destino durante el registro del viaje o incorporarlo posteriormente cuando las reglas lo permitan.
2. El destino registrado quedará relacionado con ese viaje y podrá consultarse como parte de su información.
3. El propietario podrá proporcionar un destino sin registrar obligatoriamente una distancia estimada.
4. Si únicamente se conoce el destino, la plataforma no asignará una distancia estimada sin información o una funcionalidad que permita determinarla.
5. Registrar o actualizar el destino no modificará el kilometraje actual del vehículo.
6. El destino no se interpretará como prueba de que el viaje se realizó.

#### Decisiones pendientes

- Definir cómo se ingresará el destino y qué nivel de detalle se requerirá, por ejemplo, ciudad o lugar específico.
- Definir si se permitirá registrar más de un destino en un mismo viaje.
- Precisar qué recomendaciones de preparación podrán utilizar el destino cuando no se conozca la distancia estimada.
- Definir las condiciones para actualizar el destino y su efecto sobre los resultados de preparación ya generados.



---

### RF-023 — Registrar distancia estimada del viaje

- ID: RF-023.
- Nombre: Registrar distancia estimada del viaje.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Preparación para viajes.
- Etapa prevista: Primera etapa del Propietario, sujeta a la definición del MVP; la representación de personas jurídicas se regirá por el alcance definido para RF-021.
- Estado de la definición: Propuesta; pendiente de definir el alcance y las validaciones de la distancia estimada.
- Actor relacionado: Propietario autenticado o usuario autorizado en representación de una persona jurídica, conforme a RF-021.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: RN-017 Información del viaje, RN-023 Distancia del viaje y RN-024 Información incompleta; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: CU-023 Registrar distancia estimada.
- Dependencias: Contexto del viaje y autorización conforme a RF-021. La distancia podrá incorporarse durante el registro inicial del viaje o posteriormente, según las condiciones que se definan.

#### Descripción

Vehículos Services deberá permitir que el propietario indique la distancia estimada de un viaje que desea preparar con uno de sus vehículos, aunque no haya registrado un destino.

Cuando existan las reglas y los datos necesarios, la plataforma podrá utilizar esa estimación para evaluar si el próximo objetivo de algún mantenimiento podría alcanzarse durante el recorrido previsto. Esta evaluación se especifica en RF-027.

La distancia estimada deberá mantenerse diferenciada del kilometraje actual del vehículo y de la distancia efectivamente recorrida. Su registro no deberá actualizar automáticamente el kilometraje ni confirmar que el viaje se realizó.

Los permisos para registrar la distancia se regirán por la autorización aplicable al vehículo y al viaje, sin considerar suficiente el acceso de solo consulta.

#### Criterios de aceptación

1. El actor autorizado conforme a RF-021 podrá indicar una distancia estimada durante el registro del viaje o incorporarla posteriormente cuando las reglas lo permitan.
2. La distancia estimada quedará asociada al viaje correspondiente y podrá consultarse como parte de su información.
3. El propietario podrá registrar una distancia estimada sin indicar obligatoriamente un destino.
4. La plataforma no tratará la distancia estimada como una lectura del odómetro ni actualizará con ella el kilometraje actual del vehículo.
5. El valor registrado conservará su unidad de medida y cumplirá las validaciones definidas para una distancia estimada.
6. El uso de la distancia para evaluar próximos mantenimientos se regirá por RF-027, sin producir resultados basados en información insuficiente.

#### Decisiones pendientes

- Definir si la distancia estimada representará solo el trayecto de ida o la totalidad del viaje y cómo se indicará esa elección.
- Definir la unidad de medida, las validaciones del valor ingresado y las condiciones para actualizarlo.
- Precisar cómo se actualizarán los resultados de preparación cuando el propietario cambie la distancia estimada.

---

### RF-024 — Consultar preparación para viaje

- ID: RF-024.
- Nombre: Consultar preparación para viaje.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Preparación para viajes.
- Etapa prevista: Primera etapa del Propietario, sujeta a la definición del MVP; el alcance de la representación de personas jurídicas está pendiente de precisar.
- Estado de la definición: Propuesta; pendiente de definir los resultados incluidos y su presentación.
- Actor relacionado: Propietario autenticado del vehículo o usuario autorizado para consultar la preparación en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: RN-016 Preparación para viaje, RN-018 Análisis previo al viaje, RN-021 Recomendación de inspección, RN-022 No diagnóstico y RN-024 Información incompleta; autorización de representación conforme a 63.4.17 de `proyecto.md`; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: CU-024 Consultar preparación para viaje.
- Dependencias: Viaje registrado conforme a RF-021; autorización de consulta; información disponible del vehículo y reglas aplicables. Los resultados se regirán por RF-025, RF-026 y RF-027 según las capacidades habilitadas.

#### Descripción

Vehículos Services deberá permitir que el propietario consulte la preparación de un viaje registrado para uno de sus vehículos. Esta consulta deberá presentar los resultados que la plataforma pueda obtener al analizar la información disponible del vehículo y del viaje conforme a las reglas aplicables.

Cuando el propietario sea una persona jurídica, esta consulta podrá realizarla un usuario autorizado para el vehículo y la funcionalidad correspondiente. El permiso de consulta no deberá otorgar automáticamente permiso para modificar los datos del viaje o registrar resultados de revisión.

Según las capacidades implementadas, la consulta podrá reunir el checklist definido en RF-025, las recomendaciones de RF-026 y los mantenimientos identificados conforme a RF-027. Cada resultado conservará su significado y sus condiciones de generación; su inclusión no exigirá que el usuario ejecute esas funcionalidades en pantallas o pasos independientes.

Cuando falte información necesaria para evaluar un aspecto, la consulta deberá indicarlo sin asumir que el componente o el vehículo se encuentran en buen o mal estado. La preparación no deberá presentarse como una inspección física, un diagnóstico profesional ni una certificación de seguridad para viajar.

#### Criterios de aceptación

1. El propietario autenticado podrá consultar la preparación de un viaje asociado a un vehículo con el que tenga una relación de propiedad actual válida. Cuando el propietario sea una persona jurídica, el usuario deberá contar con autorización vigente para el vehículo y esa consulta.
2. La consulta identificará el vehículo y la información del viaje utilizada para la preparación.
3. Los resultados mostrados corresponderán a la información disponible y a las reglas aplicables; no incluirán conclusiones basadas en datos inventados.
4. Cuando no exista información suficiente para evaluar un aspecto, la consulta diferenciará esa falta de información de una evaluación que sí produjo un resultado.
5. La consulta mantendrá diferenciados el checklist, las recomendaciones automáticas y los mantenimientos identificados mediante sus requisitos correspondientes.
6. El resultado no afirmará que el vehículo es seguro para realizar el viaje ni reemplazará una inspección o un diagnóstico profesional.
7. Consultar la preparación no registrará automáticamente que el viaje se realizó ni que se ejecutó alguna revisión o intervención.
8. La autorización de consulta no permitirá por sí sola modificar el viaje ni registrar resultados de revisión.

#### Decisiones pendientes

- Definir qué resultados formarán parte de la consulta inicial y cómo se presentarán los elementos todavía no disponibles.
- Definir cuándo se actualizará la preparación si cambian los datos del viaje, el kilometraje o el historial del vehículo, y cómo se distinguirán resultados anteriores de los actualizados.
- Definir los permisos de consulta de la preparación para usuarios autorizados de personas jurídicas y su disponibilidad en la primera etapa.

---

### RF-025 — Generar checklist previo al viaje

- ID: RF-025.
- Nombre: Generar checklist previo al viaje.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Preparación para viajes.
- Etapa prevista: Primera etapa del Propietario, sujeta a la definición del MVP; el alcance de la representación de personas jurídicas está pendiente de precisar.
- Estado de la definición: Propuesta; pendiente de definir los elementos y las reglas de generación del checklist.
- Actor relacionado: Propietario autenticado del vehículo o usuario autorizado para generar el checklist en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: RN-018 Análisis previo al viaje, RN-019 Checklist de viaje, RN-021 Recomendación de inspección y RN-024 Información incompleta; autorización de representación conforme a 63.4.17 de `proyecto.md`; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: CU-025 Generar checklist previo al viaje.
- Dependencias: Viaje registrado conforme a RF-021; autorización correspondiente; información disponible del vehículo y reglas aplicables. Su consulta podrá integrarse en RF-024, sin exigir una consulta previa para generarlo.

#### Descripción

Vehículos Services deberá poder generar una lista de aspectos que el propietario podría verificar antes de realizar un viaje, de acuerdo con la información disponible del vehículo, los datos del viaje y las reglas aplicables.

Cuando el propietario sea una persona jurídica, la generación podrá solicitarla un usuario autorizado para el vehículo y la funcionalidad correspondiente, según el alcance que se habilite.

El checklist podrá incluir, cuando corresponda, aspectos relacionados con fluidos, frenos, neumáticos, luces, batería, elementos de seguridad y mantenimientos pendientes. Su contenido deberá adaptarse a la información disponible y a las características aplicables al vehículo; los ejemplos del proyecto no deberán asumirse como una lista obligatoria para todos los vehículos.

La inclusión de un aspecto en el checklist no deberá indicar que fue revisado, que se encuentra en buen estado o que requiere necesariamente una reparación. Cuando un aspecto necesite inspección física o evaluación profesional, la plataforma deberá diferenciarlo de una verificación que el propietario pueda realizar por su cuenta.

El registro de resultados sobre los aspectos revisados se regirá por RF-028 y no deberá producirse automáticamente al generar el checklist.

#### Criterios de aceptación

1. El propietario autenticado podrá obtener un checklist para un viaje asociado a un vehículo con el que tenga una relación de propiedad actual válida, cuando existan las reglas necesarias para generarlo. Cuando el propietario sea una persona jurídica, el usuario deberá contar con autorización vigente para el vehículo y esa acción.
2. El checklist generado quedará relacionado con el vehículo y el viaje correspondientes.
3. Los aspectos incluidos corresponderán a las reglas aplicables, a las características del vehículo y a la información disponible.
4. La generación del checklist no marcará automáticamente sus elementos como revisados o completados.
5. Un elemento incluido no se presentará como diagnóstico de una falla ni como confirmación de que el componente está en buen estado.
6. Cuando una condición requiera inspección física o profesional según las reglas aplicables, el checklist permitirá distinguir esa necesidad de una revisión general recomendada.
7. La ausencia de datos sobre un componente no se interpretará como evidencia de que se encuentra en buenas condiciones.
8. Generar el checklist no modificará el kilometraje, el historial de mantenimientos ni el estado de una intervención registrada.

#### Decisiones pendientes

- Definir los elementos iniciales del checklist y las reglas para incluirlos según el tipo de vehículo y la información disponible.
- Definir cómo se diferenciarán los aspectos informativos, las revisiones sugeridas y los que requieren evaluación profesional.
- Definir si el checklist generado se conservará como parte de la preparación del viaje y cómo se actualizará cuando cambie la información utilizada, manteniendo la relación con los resultados registrados mediante RF-028.
- Definir los permisos de generación del checklist para usuarios autorizados de personas jurídicas y su disponibilidad en la primera etapa.

---

### RF-026 — Consultar recomendaciones previas al viaje

- ID: RF-026.
- Nombre: Consultar recomendaciones previas al viaje.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Preparación para viajes y recomendaciones.
- Etapa prevista: Primera etapa del Propietario, sujeta a la definición del MVP; el alcance de la representación de personas jurídicas está pendiente de precisar.
- Estado de la definición: Propuesta; pendiente de definir las reglas específicas de recomendación para viajes.
- Actor relacionado: Propietario autenticado del vehículo o usuario autorizado para consultar las recomendaciones en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: RN-016 Preparación para viaje, RN-018 Análisis previo al viaje, RN-021 Recomendación de inspección, RN-022 No diagnóstico y RN-024 Información incompleta; autorización de representación conforme a 63.4.17 de `proyecto.md`; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: CU-026 Consultar recomendaciones previas al viaje.
- Dependencias: Viaje registrado conforme a RF-021; autorización de consulta; información disponible del vehículo y reglas aplicables. Las recomendaciones conservarán las condiciones generales de RF-018 y su consulta podrá integrarse en RF-024, sin exigir una consulta previa de la preparación del viaje.

#### Descripción

Vehículos Services deberá permitir que el propietario consulte las recomendaciones generadas para la preparación de un viaje específico. Estas recomendaciones deberán considerar, según las reglas aplicables, la información disponible del vehículo, sus mantenimientos y los datos registrados para ese viaje.

Cuando el propietario sea una persona jurídica, la consulta podrá realizarla un usuario autorizado para el vehículo y la funcionalidad correspondiente. La autorización de consulta no implicará permiso para modificar los datos del viaje ni registrar resultados de revisión.

Una recomendación previa al viaje podrá orientar sobre aspectos que convendría revisar y, cuando corresponda, sugerir una inspección física por un profesional competente. Deberá conservar las condiciones generales de `RF-018` y mantenerse diferenciada de un diagnóstico, de una certificación de seguridad y de una revisión efectivamente realizada.

Cuando no exista información suficiente para sustentar una conclusión sobre un componente o un mantenimiento, la plataforma deberá indicar esa limitación en lugar de asumir su estado.

#### Criterios de aceptación

1. El propietario autenticado podrá consultar las recomendaciones correspondientes a un viaje asociado a un vehículo con el que tenga una relación de propiedad actual válida. Cuando el propietario sea una persona jurídica, el usuario deberá contar con autorización vigente para el vehículo y esa consulta.
2. Cada recomendación consultada quedará vinculada al viaje y al vehículo utilizados para generarla.
3. Las recomendaciones se basarán en la información disponible y en las reglas aplicables; no utilizarán datos supuestos para afirmar el estado de un componente.
4. Cuando corresponda una inspección física o profesional, la recomendación la presentará como una revisión por realizar, sin atribuir a la plataforma un diagnóstico.
5. Las recomendaciones no afirmarán que el vehículo está en condiciones seguras para viajar.
6. Consultar una recomendación no marcará como completado un elemento del checklist ni registrará una intervención sobre el vehículo.
7. Si falta información necesaria para evaluar un aspecto, el resultado indicará la limitación correspondiente en vez de presentarlo como verificado.
8. La autorización para consultar recomendaciones no habilitará por sí sola la modificación del viaje ni el registro de resultados de revisión.

#### Decisiones pendientes

- Definir las situaciones que generarán recomendaciones específicas para la preparación de un viaje.
- Definir cómo se utilizarán el destino y la distancia estimada cuando uno de esos datos no esté disponible, respetando que RF-021 permite registrar el viaje con al menos uno de ellos.
- Definir cuándo se actualizarán las recomendaciones si cambian los datos del viaje o la información del vehículo, en coherencia con el tratamiento de actualización previsto para RF-024.
- Definir los permisos de consulta de recomendaciones para usuarios autorizados de personas jurídicas y su disponibilidad en la primera etapa.

---

### RF-027 — Identificar mantenimientos pendientes antes del viaje

- ID: RF-027.
- Nombre: Identificar mantenimientos pendientes antes del viaje.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Preparación para viajes y seguimiento de mantenimientos.
- Etapa prevista: Primera etapa del Propietario, sujeta a la definición del MVP; el alcance de la representación de personas jurídicas está pendiente de precisar.
- Estado de la definición: Propuesta; pendiente de definir las condiciones de evaluación y presentación de los resultados.
- Actor relacionado: Propietario autenticado del vehículo o usuario autorizado para consultar la evaluación en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: RN-020 Mantenimientos antes del viaje, RN-023 Distancia del viaje y RN-024 Información incompleta; autorización de representación conforme a 63.4.17 de `proyecto.md`; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: CU-027 Identificar mantenimientos pendientes antes del viaje.
- Dependencias: Viaje registrado conforme a RF-021; autorización de consulta; objetivos y condiciones de seguimiento conforme a RF-011; distancia estimada conforme a RF-023 cuando se evalúe el recorrido previsto. No se requerirá una consulta previa de RF-011 para realizar esta evaluación.

#### Descripción

Vehículos Services deberá evaluar los mantenimientos o actividades con seguimiento aplicable para identificar aquellos que podrían requerir atención antes de un viaje registrado por el propietario.

Cuando el propietario sea una persona jurídica, los resultados podrán ser consultados por un usuario autorizado para el vehículo y la funcionalidad correspondiente.

La evaluación deberá distinguir los objetivos ya alcanzados o superados, los próximos a alcanzarse según las reglas definidas y, cuando exista una distancia estimada y datos suficientes, los objetivos por kilometraje que podrían alcanzarse durante el recorrido previsto.

Para evaluar el recorrido previsto, la plataforma deberá comparar el próximo objetivo por kilometraje con la suma del kilometraje actual válido y la distancia estimada del viaje, utilizando unidades compatibles. Esta proyección no deberá modificar el kilometraje registrado del vehículo.

La identificación de un mantenimiento pendiente deberá basarse en las reglas aplicables y en la información disponible del vehículo. Si faltan datos necesarios para una evaluación, la plataforma deberá indicar que no puede determinar ese resultado, sin interpretar la ausencia de datos como ausencia de necesidades de mantenimiento. La evaluación de las condiciones por kilometraje y por tiempo conservará el tratamiento definido en RF-011, incluyendo los casos en que solo una de ellas pueda determinarse.

Este resultado deberá formar parte de la preparación del viaje sin registrar automáticamente que el mantenimiento fue realizado.

#### Criterios de aceptación

1. Para un viaje asociado a un vehículo con el que el propietario autenticado tenga una relación de propiedad actual válida, la plataforma evaluará las actividades de mantenimiento con seguimiento e información suficiente según las reglas aplicables. Cuando el propietario sea una persona jurídica, el usuario que consulte los resultados deberá contar con autorización vigente para el vehículo y esa consulta.
2. La consulta distinguirá, cuando corresponda, los objetivos ya alcanzados o superados de aquellos próximos a alcanzarse.
3. Si se dispone de una distancia estimada, un kilometraje actual válido y un próximo objetivo por kilometraje determinable, la plataforma identificará si ese objetivo podría alcanzarse o superarse durante el recorrido previsto. La comparación incluirá el caso en que la suma del kilometraje actual y la distancia estimada sea igual al objetivo.
4. Si no se dispone de distancia estimada, la plataforma no afirmará que un objetivo se alcanzará durante el viaje basándose únicamente en el destino registrado.
5. Cuando falten datos necesarios para evaluar una condición, el resultado indicará esa limitación y no la presentará como vigente ni como vencida sin sustento. Las condiciones que sí puedan determinarse se evaluarán conforme a RF-011.
6. La identificación de un mantenimiento pendiente no modificará su objetivo, no cerrará alertas y no registrará una intervención realizada.
7. Los resultados se limitarán al vehículo y al viaje que el usuario está consultando.
8. El kilometraje proyectado para el recorrido no se registrará como kilometraje actual ni como evidencia de que el viaje se realizó.

#### Decisiones pendientes

- Definir las condiciones exactas para considerar un mantenimiento próximo a su objetivo en el contexto de un viaje.
- Resolver en RF-023 si la distancia estimada utilizada incluirá solo la ida o el recorrido total; este requisito utilizará esa misma definición.
- Definir cómo se mostrarán los mantenimientos que no pueden evaluarse o que solo pueden evaluarse parcialmente por falta de información.
- Definir los permisos de consulta de esta evaluación para usuarios autorizados de personas jurídicas y su disponibilidad en la primera etapa.

---

### RF-028 — Registrar resultado de revisión previa al viaje

- ID: RF-028.
- Nombre: Registrar resultado de revisión previa al viaje.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Preparación para viajes.
- Etapa prevista: Primera etapa del Propietario, sujeta a la definición del MVP; el alcance de la representación de personas jurídicas está pendiente de precisar.
- Estado de la definición: Propuesta; pendiente de definir los resultados que podrá registrar el propietario y sus validaciones.
- Actor relacionado: Propietario autenticado del vehículo o usuario autorizado para registrar resultados de revisión en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: RN-019 Checklist de viaje, RN-021 Recomendación de inspección, RN-022 No diagnóstico y RN-024 Información incompleta; principios de procedencia y trazabilidad del historial vehicular; autorización de representación conforme a 63.4.17 de `proyecto.md`; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: CU-028 Registrar resultado de revisión previa al viaje.
- Dependencias: Viaje registrado conforme a RF-021; autorización para registrar resultados; checklist generado conforme a RF-025 cuando el resultado corresponda a un elemento de esa lista.

#### Descripción

Vehículos Services deberá permitir que el propietario registre manualmente el resultado de una revisión previa al viaje, dentro del alcance de las verificaciones que se definan para esta funcionalidad.

Cuando el propietario sea una persona jurídica, el registro podrá realizarlo un usuario autorizado para el vehículo y esa acción. El permiso para consultar la preparación del viaje o el checklist no deberá habilitar por sí solo el registro de resultados.

El resultado deberá quedar relacionado con el vehículo, el viaje y el aspecto revisado. Cuando corresponda a un elemento del checklist, deberá poder identificarse dicha relación. La plataforma deberá conservar la identidad del usuario que registró el resultado y, cuando actúe en representación de una persona jurídica, la relación de representación correspondiente.

La procedencia del resultado deberá permitir distinguir lo declarado por el propietario o su usuario autorizado de una evaluación emitida por un profesional. El hecho de que una misma persona tenga también un rol de Prestador de Servicios Vehiculares no convertirá automáticamente lo registrado mediante esta funcionalidad en una evaluación profesional.

Registrar que un aspecto fue revisado no deberá significar automáticamente que se encuentra en buenas condiciones. De igual manera, la ausencia de un resultado no deberá interpretarse como una revisión satisfactoria.

Los resultados registrados mediante esta funcionalidad no deberán presentarse como diagnósticos profesionales ni como certificación de que el vehículo está en condiciones seguras para viajar. Si durante la revisión se realiza un mantenimiento o una reparación, esa intervención deberá documentarse mediante RF-006 o RF-008, según corresponda.

#### Criterios de aceptación

1. El propietario autenticado podrá registrar un resultado sobre un aspecto revisado para un viaje asociado a un vehículo con el que tenga una relación de propiedad actual válida. Cuando el propietario sea una persona jurídica, el usuario deberá contar con autorización vigente para el vehículo y esa acción.
2. El resultado permitirá identificar el vehículo, el viaje y el aspecto al que corresponde.
3. Cuando el aspecto provenga de un checklist, el resultado conservará su relación con el elemento correspondiente.
4. La plataforma conservará la identidad del usuario que registró el resultado y la trazabilidad del registro. Cuando actúe en representación de una persona jurídica, también identificará esa representación.
5. Un aspecto sin resultado no se mostrará como revisado satisfactoriamente.
6. Registrar una revisión no confirmará automáticamente que el componente está en buen estado ni que el vehículo es seguro para viajar.
7. El resultado declarado mediante esta funcionalidad no se presentará como diagnóstico o evaluación profesional, aunque quien lo registre tenga también un rol de Prestador de Servicios Vehiculares.
8. Registrar el resultado no creará automáticamente un mantenimiento, una reparación ni una actualización de kilometraje.
9. La autorización para consultar la preparación del viaje o el checklist no permitirá registrar resultados si el usuario no cuenta con el permiso correspondiente.

#### Decisiones pendientes

- Definir qué verificaciones podrá registrar el propietario y cuáles requerirán una evaluación profesional.
- Definir los resultados disponibles, los datos obligatorios y la posibilidad de incluir observaciones o evidencias.
- Definir cómo se conservarán y corregirán los resultados y si podrán actualizar la preparación del viaje conforme a reglas específicas.
- Definir los permisos de registro de resultados para usuarios autorizados de personas jurídicas y su disponibilidad en la primera etapa.

---

### RF-029 — Registrar abastecimiento o recarga del vehículo

- ID: RF-029.
- Nombre: Registrar abastecimiento o recarga del vehículo.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Gestión de abastecimiento y consumo.
- Etapa prevista: Primera etapa del Propietario; el alcance de la representación de personas jurídicas está pendiente de precisar.
- Estado de la definición: Propuesta; pendiente de definir los datos mínimos y las validaciones según el tipo de abastecimiento.
- Actor relacionado: Propietario autenticado del vehículo o usuario autorizado para registrar abastecimientos o recargas en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Registro de abastecimientos y recargas definido en `63.10.2` de `proyecto.md`; reglas de kilometraje, información incompleta y trazabilidad del historial; autorización de representación conforme a `63.4.17` de `proyecto.md`; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: Pendiente de incorporar a `casos-uso.md`; esta capacidad no aparece en la lista preliminar del punto 29 de `proyecto.md`.
- Dependencias: Vehículo registrado con una relación de propiedad actual válida; autorización para registrar abastecimientos o recargas; información del combustible o fuente de energía del vehículo; reglas de validación de kilometraje cuando se registre una lectura.

#### Descripción

Vehículos Services deberá permitir que el propietario registre los abastecimientos de combustible o las recargas de energía realizados a uno de sus vehículos.

Cuando el propietario sea una persona jurídica, el registro podrá realizarlo un usuario autorizado para el vehículo y esa acción. La autorización para consultar el vehículo no deberá habilitar por sí sola el registro de abastecimientos o recargas.

El registro deberá adaptarse al combustible o fuente de energía definido para el vehículo. Podrá conservar, según corresponda y se encuentre disponible, la fecha del evento, el kilometraje observado, la cantidad abastecida, su unidad de medida, el valor pagado, la condición de abastecimiento completo o parcial, el lugar, las observaciones y los soportes.

La fecha del abastecimiento o recarga deberá distinguirse de la fecha en que se registra en la plataforma. Registrar posteriormente un evento no deberá cambiar su fecha de ocurrencia ni hacerlo pasar por un abastecimiento realizado en ese momento.

Cada abastecimiento o recarga deberá conservarse como un evento independiente, sin reemplazar los anteriores. La plataforma deberá permitir registrar información incompleta conforme a los datos mínimos que se definan, sin obligar al usuario a inventar cantidades, precios u otros datos desconocidos.

El kilometraje indicado deberá tratarse como una lectura asociada al evento. Su posible utilización para actualizar el kilometraje actual deberá respetar las reglas de validación y consistencia correspondientes.

El registro deberá funcionar sin depender de que el establecimiento donde se realizó el abastecimiento esté registrado como Prestador de Servicios Vehiculares.

#### Criterios de aceptación

1. El propietario autenticado podrá registrar un abastecimiento o una recarga para un vehículo con el que tenga una relación de propiedad actual válida. Cuando el propietario sea una persona jurídica, el usuario deberá contar con autorización vigente para el vehículo y esa acción.
2. Los datos y unidades disponibles para el registro corresponderán al combustible o fuente de energía aplicable al vehículo.
3. La plataforma no exigirá redefinir las características energéticas del vehículo en cada abastecimiento.
4. Cada nuevo registro conservará su individualidad y no sobrescribirá los abastecimientos anteriores.
5. El usuario podrá conservar los datos conocidos aunque falte información adicional, siempre que cumpla los datos mínimos definidos para el registro.
6. Un dato desconocido no se almacenará automáticamente como cero ni se completará con un valor supuesto.
7. Cuando se registre una lectura de kilometraje, su tratamiento respetará las reglas de kilometraje antes de modificar el valor actual del vehículo.
8. La ausencia de registros entre dos abastecimientos no generará automáticamente eventos faltantes.
9. Registrar el abastecimiento no requerirá una cuenta ni una relación activa con el establecimiento que lo suministró.
10. La plataforma distinguirá la fecha del abastecimiento o recarga de la fecha de creación del registro y conservará la identidad del usuario que lo registró.
11. La autorización para consultar el vehículo no permitirá registrar abastecimientos o recargas si el usuario no cuenta con el permiso correspondiente.

#### Decisiones pendientes

- Definir los datos mínimos, las unidades admitidas y las validaciones según el tipo de abastecimiento o recarga.
- Definir cómo se seleccionará la fuente abastecida cuando el vehículo utilice más de una fuente de energía.
- Precisar cuándo corresponde registrar un abastecimiento como completo o parcial y cómo se utilizará esa condición en los cálculos posteriores.
- Definir los permisos de registro de abastecimientos o recargas para usuarios autorizados de personas jurídicas y su disponibilidad en la primera etapa.

---

### RF-030 — Consultar consumo y rendimiento del vehículo

- ID: RF-030.
- Nombre: Consultar consumo y rendimiento del vehículo.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Gestión de abastecimiento y consumo.
- Etapa prevista: Primera etapa del Propietario; el alcance de la representación de personas jurídicas está pendiente de precisar.
- Estado de la definición: Propuesta; pendiente de definir los indicadores iniciales y las condiciones de suficiencia de datos para cada cálculo.
- Actor relacionado: Propietario autenticado del vehículo o usuario autorizado para consultar consumo y rendimiento en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Control de consumo y rendimiento definido en `63.10.3` de `proyecto.md`; reglas de kilometraje e información incompleta; autorización de representación conforme a `63.4.17` de `proyecto.md`; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: Pendiente de incorporar a `casos-uso.md`; esta capacidad no aparece en la lista preliminar del punto 29 de `proyecto.md`.
- Dependencias: Registros de abastecimiento o recarga conforme a RF-029; autorización de consulta; lecturas de kilometraje válidas y reglas de cálculo aplicables a la fuente de energía.

#### Descripción

Vehículos Services deberá permitir que el propietario consulte información sobre el recorrido, consumo y rendimiento de su vehículo utilizando los abastecimientos, recargas y lecturas de kilometraje disponibles.

Cuando el propietario sea una persona jurídica, la consulta podrá realizarla un usuario autorizado para el vehículo y la funcionalidad correspondiente.

La plataforma deberá determinar por separado qué resultados pueden calcularse. Una distancia entre lecturas válidas podrá obtenerse aunque no exista información suficiente para determinar el consumo o el rendimiento correspondiente.

La cantidad abastecida no deberá interpretarse automáticamente como la cantidad consumida desde el registro anterior. Los cálculos deberán considerar las condiciones de abastecimiento, la continuidad de los registros y la información necesaria según la fuente de energía.

Cuando el vehículo utilice más de una fuente de energía, los registros y resultados deberán distinguir la fuente a la que corresponden. No se combinarán cantidades de fuentes o unidades diferentes sin una regla de cálculo expresamente definida.

Los resultados calculados deberán mantenerse diferenciados de los datos registrados y no deberán reemplazarlos. Una variación del rendimiento tampoco deberá presentarse automáticamente como diagnóstico de una falla.

#### Criterios de aceptación

1. El propietario autenticado podrá consultar los resultados de consumo y rendimiento de un vehículo con el que tenga una relación de propiedad actual válida cuando existan datos suficientes para calcularlos. Cuando el propietario sea una persona jurídica, el usuario deberá contar con autorización vigente para el vehículo y esa consulta.
2. La plataforma distinguirá la distancia recorrida entre lecturas, la cantidad consumida determinable y el rendimiento obtenido.
3. Cuando existan dos lecturas válidas y comparables, la distancia entre ellas se calculará como el kilometraje posterior menos el anterior.
4. La existencia de una distancia calculable no producirá automáticamente un indicador de consumo o rendimiento si faltan los datos necesarios.
5. La plataforma no asumirá que dos abastecimientos consecutivos registrados representan necesariamente todos los abastecimientos realizados entre ellos.
6. Los abastecimientos parciales se considerarán cuando sean necesarios para el cálculo conforme a la regla aplicable.
7. Si una métrica no puede calcularse, se indicará la insuficiencia de información sin mostrar un resultado inventado ni sustituirlo por cero.
8. Cada resultado mostrará la unidad de medida correspondiente y permitirá identificar la fuente de energía y el recorrido o conjunto de registros evaluado.
9. Los cálculos no modificarán los datos originales ni impedirán registrar nuevos abastecimientos cuando falte información para una métrica.
10. Los resultados de distintas fuentes de energía se mantendrán diferenciados y no se combinarán sin una regla de cálculo definida.
11. Una variación del consumo o del rendimiento no se presentará por sí sola como diagnóstico de una falla.

#### Decisiones pendientes

- Definir los indicadores y unidades disponibles inicialmente para cada fuente de energía.
- Precisar las fórmulas y las condiciones de suficiencia, continuidad y comparabilidad de los datos.
- Definir cómo se identificarán los registros utilizados en cada resultado y cómo se presentarán las limitaciones del cálculo.
- Definir los permisos de consulta de consumo y rendimiento para usuarios autorizados de personas jurídicas y su disponibilidad en la primera etapa.

---

### RF-031 — Consultar gastos de abastecimiento y recarga

- ID: RF-031.
- Nombre: Consultar gastos de abastecimiento y recarga.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Gestión de abastecimiento y consumo.
- Etapa prevista: Primera etapa del Propietario; el alcance de la representación de personas jurídicas está pendiente de precisar.
- Estado de la definición: Propuesta; pendiente de definir los indicadores económicos iniciales y sus validaciones.
- Actor relacionado: Propietario autenticado del vehículo o usuario autorizado para consultar gastos de abastecimiento y recarga en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Control de costos y gastos de abastecimiento definido en `63.10.4` de `proyecto.md`; autorización de representación conforme a `63.4.17` de `proyecto.md`; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: Pendiente de incorporar a `casos-uso.md`; esta capacidad no aparece en la lista preliminar del punto 29 de `proyecto.md`.
- Dependencias: Registros de abastecimiento o recarga conforme a RF-029; autorización de consulta; información económica registrada y reglas aplicables a cada indicador.

#### Descripción

Vehículos Services deberá permitir que el propietario consulte los valores pagados registrados en abastecimientos o recargas de uno de sus vehículos, así como su acumulación dentro del conjunto de registros consultado.

Cuando el propietario sea una persona jurídica, la consulta podrá realizarla un usuario autorizado para el vehículo y la funcionalidad correspondiente.

Cada valor deberá conservar su relación con el abastecimiento o recarga que lo originó. La suma deberá presentarse como gasto registrado, sin asumir que representa la totalidad del gasto real cuando puedan existir eventos o valores no registrados.

Los valores deberán identificar su moneda. Los importes en monedas diferentes se mantendrán separados, salvo que exista una regla de conversión expresamente definida para la consulta.

Cuando existan datos suficientes, la plataforma podrá proporcionar indicadores adicionales, como precio unitario o costo por kilómetro. Cada indicador deberá calcularse únicamente cuando pueda establecerse una relación válida entre los datos utilizados, sin modificar los valores originales.

#### Criterios de aceptación

1. El propietario autenticado podrá consultar los valores económicos registrados en abastecimientos o recargas de un vehículo con el que tenga una relación de propiedad actual válida. Cuando el propietario sea una persona jurídica, el usuario deberá contar con autorización vigente para el vehículo y esa consulta.
2. Cada valor consultado permanecerá relacionado con el evento que lo originó.
3. El gasto acumulado corresponderá a la suma de los valores disponibles y monetariamente comparables dentro del conjunto consultado y se identificará como gasto registrado.
4. La ausencia de valores registrados no se presentará como evidencia de que el gasto real fue cero.
5. Si existen abastecimientos sin valor pagado, esos datos faltantes no se sustituirán automáticamente por cero y la consulta indicará esa limitación.
6. Los gastos de vehículos distintos se mantendrán diferenciados, salvo que se habilite expresamente una consulta consolidada.
7. El precio unitario podrá calcularse cuando exista un valor pagado y una cantidad válida mayor que cero para efectuar la división. El resultado identificará la moneda y la unidad correspondientes.
8. El costo por kilómetro solo se calculará cuando el gasto pueda relacionarse válidamente con el recorrido correspondiente y la distancia utilizada sea mayor que cero.
9. Los indicadores calculados no reemplazarán ni modificarán los valores registrados.
10. Los importes en monedas diferentes no se sumarán directamente. Si se habilita una conversión, su aplicación deberá respetar la regla definida y permitir distinguir los valores originales del resultado convertido.

#### Decisiones pendientes

- Definir los indicadores económicos disponibles inicialmente y sus condiciones de cálculo.
- Definir las monedas admitidas y el tratamiento de registros con monedas diferentes antes de acumular o comparar valores.
- Precisar las reglas de consistencia cuando el precio unitario registrado difiera del calculado a partir del valor pagado y la cantidad abastecida.
- Definir los permisos de consulta de gastos de abastecimiento y recarga para usuarios autorizados de personas jurídicas y su disponibilidad en la primera etapa.

---

### RF-032 — Consultar métricas de abastecimiento por períodos

- ID: RF-032.
- Nombre: Consultar métricas de abastecimiento por períodos.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Gestión de abastecimiento y consumo.
- Etapa prevista: Primera etapa del Propietario; el alcance de la representación de personas jurídicas está pendiente de precisar.
- Estado de la definición: Propuesta; pendiente de definir los períodos y las opciones de comparación disponibles inicialmente.
- Actor relacionado: Propietario autenticado del vehículo o usuario autorizado para consultar métricas de abastecimiento por períodos en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Métricas y análisis por períodos definidos en `63.10.5` de `proyecto.md`; autorización de representación conforme a `63.4.17` de `proyecto.md`; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: Pendiente de incorporar a `casos-uso.md`; esta capacidad no aparece en la lista preliminar del punto 29 de `proyecto.md`.
- Dependencias: Registros de abastecimiento o recarga conforme a RF-029; autorización de consulta; reglas de cálculo de consumo, rendimiento y gastos definidas en RF-030 y RF-031. No se requerirá consultar previamente esos requisitos para obtener las métricas por períodos.

#### Descripción

Vehículos Services deberá permitir que el propietario consulte la información de abastecimientos y recargas de un vehículo agrupada por períodos y compare los resultados que puedan relacionarse válidamente.

Cuando el propietario sea una persona jurídica, la consulta podrá realizarla un usuario autorizado para el vehículo y la funcionalidad correspondiente.

Las agrupaciones podrán incluir meses, años u otros períodos que se definan. Las métricas de consumo, rendimiento y gastos deberán conservar las reglas establecidas en RF-030 y RF-031, sin introducir fórmulas diferentes por el hecho de agruparlas temporalmente.

La consulta deberá distinguir datos registrados, resultados calculados y métricas no disponibles. Una diferencia entre valores registrados de dos períodos no deberá presentarse automáticamente como una variación equivalente del consumo o gasto real.

La incorporación posterior de un abastecimiento histórico deberá actualizar las métricas del período al que corresponde el evento, sin modificar los registros originales.

#### Criterios de aceptación

1. El propietario autenticado podrá consultar métricas de un vehículo con el que tenga una relación de propiedad actual válida mediante las agrupaciones temporales habilitadas. Cuando el propietario sea una persona jurídica, el usuario deberá contar con autorización vigente para el vehículo y esa consulta.
2. Cada resultado permitirá identificar el vehículo y el período analizado.
3. Los abastecimientos y recargas se asignarán al período correspondiente a la fecha del evento, diferenciándola de la fecha en que fueron registrados en la plataforma.
4. Cada período mostrará únicamente las métricas que puedan obtenerse con información suficiente conforme a las reglas aplicables.
5. La ausencia de información se distinguirá de un resultado calculado igual a cero.
6. Las comparaciones utilizarán métricas compatibles y permitirán identificar los períodos comparados. El tratamiento de fuentes de energía, unidades y monedas conservará las condiciones de RF-030 y RF-031.
7. Una diferencia entre gastos registrados no se presentará por sí sola como una reducción o aumento del gasto real total.
8. Al incorporarse información histórica que afecte un período, sus métricas se actualizarán conforme a las reglas de cálculo.
9. Las agrupaciones y comparaciones no modificarán los registros originales ni mezclarán automáticamente información de vehículos diferentes.

#### Decisiones pendientes

- Definir los períodos, filtros y comparaciones disponibles en la primera etapa.
- Precisar las condiciones de comparabilidad y el tratamiento de recorridos o ciclos de consumo que abarquen más de un período.
- Definir cómo se presentarán la disponibilidad de datos y las limitaciones de cada métrica.
- Definir los permisos de consulta de métricas por períodos para usuarios autorizados de personas jurídicas y su disponibilidad en la primera etapa.

---

### RF-033 — Establecer una regla de seguimiento para una actividad de mantenimiento

- ID: RF-033.
- Nombre: Establecer una regla de seguimiento para una actividad de mantenimiento.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Capacidad general compartida — Reglas de mantenimiento.
- Etapa prevista: Primera etapa del Propietario, mediante un mecanismo que permita su funcionamiento sin depender de la implementación del módulo del Prestador de Servicios Vehiculares.
- Estado de la definición: Propuesta; pendiente de definir el origen de las reglas y quién podrá establecerlas.
- Actor relacionado: Actor autorizado para establecer la regla, por definir; Propietario como usuario del seguimiento resultante.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Definición y aplicabilidad de una regla de mantenimiento establecidas en `63.11.1` de `proyecto.md`; intervalos por kilometraje, tiempo y combinación de ambos; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: Pendiente de incorporar a `casos-uso.md`; esta capacidad no aparece en la lista preliminar del punto 29 de `proyecto.md`.
- Dependencias: Identificación del vehículo y de la actividad que requiere seguimiento; definición del mecanismo y los permisos para establecer reglas.

#### Descripción

Vehículos Services deberá permitir establecer la regla aplicable al seguimiento de una actividad de mantenimiento de un vehículo mediante el mecanismo y los permisos que se definan.

Esta capacidad se especifica en este documento porque es necesaria para el seguimiento del módulo del Propietario. Su inclusión no concede por sí sola al propietario ni a sus usuarios autorizados el permiso para establecer reglas. Si posteriormente se habilita su utilización desde el módulo del Prestador de Servicios Vehiculares, ese documento deberá referenciar este requisito y definir los permisos correspondientes, sin duplicar su especificación general.

La regla deberá identificar el criterio de seguimiento y sus condiciones concretas, como un intervalo de kilometraje, un intervalo de tiempo o una combinación de ambos. Cada actividad deberá conservar su regla aplicable sin asumir que todas las actividades de un mismo mantenimiento comparten los mismos intervalos.

Los valores deberán responder a la definición aprobada para el vehículo y la actividad. La plataforma no deberá utilizar los intervalos ilustrativos del proyecto como reglas universales.

La existencia de una regla permitirá realizar el seguimiento cuando existan referencias válidas y datos suficientes. Establecerla no deberá registrar una intervención realizada ni garantizar que ya pueda calcularse un próximo objetivo.

#### Criterios de aceptación

1. La regla quedará asociada al vehículo y a la actividad sobre la que se realizará el seguimiento.
2. La regla permitirá identificar su criterio y las condiciones concretas que deberán evaluarse.
3. Actividades diferentes de un mismo mantenimiento podrán tener reglas distintas o permanecer sin seguimiento, según corresponda.
4. Una misma actividad podrá tener condiciones de seguimiento diferentes para vehículos distintos.
5. La plataforma no establecerá automáticamente un intervalo universal a partir del nombre de la actividad ni de los ejemplos del proyecto.
6. Si faltan referencias necesarias para calcular un próximo objetivo, la regla podrá conservarse sin producir un objetivo inventado.
7. Establecer la regla no creará un mantenimiento realizado ni modificará el kilometraje actual del vehículo.
8. La plataforma conservará la procedencia de la regla conforme al mecanismo mediante el cual se estableció.
9. Cuando el mecanismo permita que un usuario establezca reglas, la plataforma verificará el permiso correspondiente. La propiedad del vehículo o la autorización para consultarlo no otorgarán por sí solas ese permiso.
10. El mecanismo habilitado para la primera etapa permitirá establecer las reglas necesarias sin requerir la implementación del módulo del Prestador de Servicios Vehiculares.

#### Decisiones pendientes

- Definir el origen de las reglas y el mecanismo disponible en la primera etapa: establecimiento por el propietario, selección desde un catálogo u otro mecanismo aprobado.
- Definir quién podrá establecerlas y los permisos correspondientes, incluyendo el alcance de los usuarios autorizados de personas jurídicas si se habilita esa acción.
- Definir los datos obligatorios, unidades y validaciones de los intervalos y condiciones.
- Definir cómo se seleccionará la regla aplicable cuando existan varias propuestas para la misma actividad y vehículo.
- Definir en `requerimientos-funcionales-prestador.md`, para una etapa posterior, si el prestador autorizado podrá establecer o proponer reglas, referenciando este requisito.

---

### RF-034 — Modificar una regla de seguimiento

- ID: RF-034.
- Nombre: Modificar una regla de seguimiento.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Capacidad general compartida — Reglas de mantenimiento.
- Etapa prevista: Primera etapa del Propietario, mediante un mecanismo que permita su funcionamiento sin depender de la implementación del módulo del Prestador de Servicios Vehiculares.
- Estado de la definición: Propuesta; pendiente de definir los responsables autorizados y la aplicación de los cambios.
- Actor relacionado: Actor autorizado para modificar la regla, por definir.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Modificación y evolución de las reglas establecidas en `63.11.8` de `proyecto.md`; principios de integridad y trazabilidad; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: Pendiente de incorporar a `casos-uso.md`; esta capacidad no aparece en la lista preliminar del punto 29 de `proyecto.md`.
- Dependencias: Regla existente conforme a RF-033; definición del mecanismo y de los permisos para modificarla; reglas de aplicación del cambio al seguimiento.

#### Descripción

Vehículos Services deberá permitir modificar válidamente las condiciones de una regla de seguimiento mediante el mecanismo y los permisos que se definan.

Los permisos para esta acción deberán definirse expresamente. Ser propietario del vehículo, tener autorización para consultarlo o poder establecer una regla no implicará automáticamente tener permiso para modificarla.

La modificación deberá conservar la trazabilidad de las condiciones anteriores y permitir distinguir la regla utilizada históricamente de la que resulte aplicable después del cambio.

Cuando exista un ciclo activo, la plataforma deberá aplicar una condición expresamente definida para determinar si el cambio afecta ese ciclo, los ciclos futuros o ambos. No deberá recalcular todo el seguimiento ni alterar los objetivos históricos únicamente porque se haya modificado la regla.

Una modificación de las condiciones de seguimiento deberá distinguirse de la corrección de un dato que fue registrado erróneamente.

La definición general de esta capacidad se conservará en este documento. Si posteriormente se habilita su utilización desde el módulo del Prestador de Servicios Vehiculares, sus requisitos deberán referenciar RF-034 y definir los permisos correspondientes, sin duplicar esta especificación.

#### Criterios de aceptación

1. Solo un actor con los permisos definidos podrá modificar las condiciones de una regla. El permiso para establecerla no habilitará por sí solo su modificación.
2. La modificación conservará la relación de la regla con el vehículo y la actividad correspondiente.
3. La plataforma conservará las condiciones anteriores y la trazabilidad del cambio, permitiendo identificar quién lo realizó y cuándo.
4. Los ciclos históricos mantendrán el contexto de la regla con la que fueron evaluados, sin sobrescribirse automáticamente con la nueva definición.
5. La aplicación del cambio a un ciclo activo dependerá de una condición funcional definida, sin asumir que todos los cambios deben afectarlo.
6. Si el cambio aplica únicamente a ciclos futuros, el ciclo activo conservará las condiciones que le correspondían.
7. Si el cambio aplica al ciclo activo, sus objetivos y resultados derivados se reevaluarán conforme a las reglas aprobadas y conservarán la trazabilidad correspondiente.
8. La modificación de una regla no registrará una intervención realizada ni modificará las lecturas de kilometraje del vehículo.
9. La plataforma distinguirá un cambio de condiciones de una corrección de información registrada erróneamente.
10. El mecanismo habilitado para modificar reglas en la primera etapa no requerirá la implementación del módulo del Prestador de Servicios Vehiculares.

#### Decisiones pendientes

- Definir quién podrá modificar una regla y qué condiciones requerirán autorización adicional, incluyendo el alcance de los usuarios autorizados de personas jurídicas si se habilita esa acción.
- Definir cómo se determinará la aplicación del cambio al ciclo activo o a los ciclos futuros.
- Precisar el tratamiento de las correcciones y su efecto sobre objetivos, estados, alertas y recomendaciones previamente calculados.
- Definir en `requerimientos-funcionales-prestador.md`, para una etapa posterior, si el prestador autorizado podrá modificar o proponer cambios de reglas, referenciando este requisito.

---

### RF-035 — Renovar el ciclo de seguimiento de una actividad

- ID: RF-035.
- Nombre: Renovar el ciclo de seguimiento de una actividad.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Capacidad general compartida — Seguimiento y reglas de mantenimiento.
- Etapa prevista: Primera etapa del Propietario, sin depender de la implementación del módulo del Prestador de Servicios Vehiculares.
- Estado de la definición: Propuesta; pendiente de precisar las condiciones para identificar una intervención válida y establecer la nueva referencia.
- Actor relacionado: Propietario autenticado o usuario autorizado que registra la intervención en representación de una persona jurídica propietaria; plataforma como responsable de evaluar la renovación.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Cumplimiento y renovación del ciclo de seguimiento definidos en `63.11.6` de `proyecto.md`; autorización para registrar intervenciones conforme al requisito correspondiente; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: Pendiente de incorporar a `casos-uso.md`; esta capacidad no aparece en la lista preliminar del punto 29 de `proyecto.md`.
- Dependencias: Registro de una intervención correspondiente a la actividad bajo seguimiento mediante la funcionalidad aplicable; regla establecida conforme a RF-033, con las modificaciones aplicables de RF-034; referencias válidas para el nuevo ciclo.

#### Descripción

Vehículos Services deberá evaluar la renovación del ciclo de seguimiento de una actividad cuando se registre una nueva intervención válida que corresponda a ella y permita establecer una nueva referencia conforme a la regla aplicable.

La evaluación será responsabilidad de la plataforma a partir del registro de la intervención. Este requisito no concederá permisos adicionales para registrar intervenciones ni para establecer o modificar reglas; esas autorizaciones se regirán por los requisitos correspondientes.

El nuevo objetivo deberá utilizar la fecha o el kilometraje real de la intervención, según corresponda, sin tomar automáticamente el objetivo anterior como referencia. Este comportamiento deberá aplicarse tanto si la intervención ocurrió antes del objetivo previsto como si ocurrió después.

Alcanzar o superar un objetivo no deberá interpretarse como realización de la intervención ni renovar automáticamente el ciclo. Mientras no exista una condición válida para renovarlo, el seguimiento conservará la referencia y el objetivo correspondientes.

La renovación deberá conservar la trazabilidad del ciclo anterior y limitarse a las actividades efectivamente atendidas.

Esta especificación general podrá ser referenciada desde el módulo del Prestador de Servicios Vehiculares cuando se habilite el registro de intervenciones desde ese módulo, sin duplicar las reglas de renovación.

#### Criterios de aceptación

1. La plataforma evaluará la renovación únicamente cuando exista una intervención registrada que corresponda a la actividad bajo seguimiento.
2. Alcanzar o superar el kilometraje o la fecha objetivo no registrará una intervención ni iniciará por sí solo un nuevo ciclo.
3. Cuando exista una nueva referencia válida, el nuevo objetivo se determinará utilizando esa referencia y la regla aplicable.
4. El objetivo anterior no se utilizará automáticamente como referencia de la nueva intervención.
5. Una intervención válida realizada antes o después del objetivo previsto podrá renovar el ciclo desde su fecha o kilometraje real, según corresponda. La fecha de creación del registro no sustituirá automáticamente la fecha en que se realizó la intervención.
6. Si un mantenimiento contiene varias actividades, la renovación afectará únicamente a aquellas para las que exista una intervención válida y una referencia suficiente.
7. El nuevo ciclo conservará su relación con la intervención que lo originó y la trazabilidad del ciclo anterior.
8. Si faltan datos necesarios para establecer una referencia o un objetivo, la plataforma no inventará valores ni presentará un nuevo ciclo como completamente calculado.
9. La renovación no modificará por sí sola los intervalos ni las condiciones de la regla aplicable.

#### Decisiones pendientes

- Definir cómo se identificará que una intervención corresponde a la actividad bajo seguimiento.
- Precisar el tratamiento de intervenciones registradas posteriormente y de referencias incompletas en reglas combinadas.
- Definir cómo se reevaluarán los ciclos si se corrige o anula la intervención que originó una renovación.

---

### RF-036 — Recibir notificaciones

- ID: RF-036.
- Nombre: Recibir notificaciones.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Capacidad general compartida — Notificaciones, con alcance inicial al Propietario.
- Etapa prevista: Primera etapa del Propietario; las comunicaciones propias del Prestador de Servicios Vehiculares se definirán para una etapa posterior.
- Estado de la definición: Propuesta; pendiente de definir los tipos de comunicación, canales y condiciones de envío iniciales.
- Actor relacionado: Propietario como destinatario autorizado o usuario autorizado designado como destinatario en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Condiciones de generación, destinatarios, canales y frecuencia de notificaciones definidos en `63.13` de `proyecto.md`; autorización de representación conforme a `63.4.17` de `proyecto.md`; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: Pendiente de incorporar a `casos-uso.md`; esta capacidad no aparece en la lista preliminar del punto 29 de `proyecto.md`.
- Dependencias: Identificación y autorización del destinatario; información o evento que origina la comunicación; disponibilidad del canal y reglas de envío aplicables; preferencias configurables conforme a RF-037, cuando correspondan.

#### Descripción

Vehículos Services deberá comunicar al propietario información relevante mediante notificaciones cuando exista una condición o evento que deba comunicarse conforme a las reglas aplicables.

Cuando el propietario sea una persona jurídica, la plataforma deberá determinar qué usuarios autorizados recibirán cada tipo de comunicación. La asociación de un usuario con la persona jurídica o con el vehículo no deberá convertirlo automáticamente en destinatario de todas las notificaciones.

Una notificación podrá referirse a una alerta, una recomendación, una solicitud de actualización de kilometraje u otra situación funcional habilitada. La existencia de estos elementos no deberá provocar automáticamente su comunicación por todos los canales. Tampoco será necesario que exista una alerta para comunicar otro evento que tenga una regla de notificación definida.

Antes de comunicar la información, la plataforma deberá determinar el destinatario autorizado y aplicar las condiciones de envío, las preferencias permitidas conforme a RF-037 y la disponibilidad del canal correspondiente.

Enviar o consultar una notificación no deberá resolver por sí solo la condición comunicada ni registrar que el destinatario realizó la acción sugerida.

Las comunicaciones propias del módulo del Prestador de Servicios Vehiculares deberán definirse en `requerimientos-funcionales-prestador.md`, referenciando esta capacidad general sin duplicar su especificación.

#### Criterios de aceptación

1. La plataforma generará una notificación cuando se cumplan las condiciones de comunicación definidas para su tipo.
2. La notificación permitirá identificar la información o situación que comunica y el vehículo cuando corresponda.
3. La información se comunicará únicamente a destinatarios autorizados conforme a su relación y permisos vigentes al momento del envío.
4. La existencia de una alerta o recomendación no exigirá automáticamente una notificación ni el uso de todos los canales disponibles.
5. El envío respetará las condiciones de frecuencia y las preferencias configurables que se definan para ese tipo de comunicación.
6. La notificación no expondrá información restringida a un destinatario por el solo hecho de estar relacionado con el vehículo o con la persona jurídica propietaria.
7. Enviar o consultar la notificación no registrará automáticamente una intervención, actualizará el kilometraje ni resolverá la condición que la originó.
8. La plataforma conservará la relación entre la notificación y su origen conforme a las reglas de trazabilidad.
9. Una situación funcional podrá generar una notificación sin una alerta previa cuando exista una regla de comunicación que lo permita.
10. Cuando el propietario sea una persona jurídica, el envío se limitará a los usuarios definidos como destinatarios autorizados para ese tipo de comunicación y su alcance.

#### Decisiones pendientes

- Definir los tipos de notificación y los canales disponibles en la primera etapa.
- Definir las frecuencias, condiciones de repetición y controles para evitar comunicaciones duplicadas.
- Precisar el tratamiento de canales no disponibles, envíos fallidos y comunicaciones que pierdan vigencia antes de enviarse.
- Definir cómo se designarán los destinatarios de personas jurídicas, qué comunicaciones podrá recibir cada uno y su disponibilidad en la primera etapa.

---

### RF-037 — Configurar preferencias de notificación

- ID: RF-037.
- Nombre: Configurar preferencias de notificación.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Capacidad general compartida — Preferencias de notificación, con alcance inicial al Propietario.
- Etapa prevista: Primera etapa del Propietario; el alcance de la configuración para personas jurídicas está pendiente de precisar.
- Estado de la definición: Propuesta; pendiente de definir las opciones configurables y sus límites.
- Actor relacionado: Propietario autenticado o usuario autorizado para configurar las preferencias correspondientes en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Preferencias y control de notificaciones definidos en `63.13.8` de `proyecto.md`; autorización de representación conforme a `63.4.17` de `proyecto.md`; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: Pendiente de incorporar a `casos-uso.md`; esta capacidad no aparece en la lista preliminar del punto 29 de `proyecto.md`.
- Dependencias: Capacidad de notificación definida en RF-036; autorización para configurar preferencias; definición de los tipos de comunicación, canales y opciones configurables. No se requerirá haber recibido una notificación para configurar las preferencias.

#### Descripción

Vehículos Services deberá permitir que el propietario consulte y configure las preferencias de notificación que se habiliten para su cuenta o sus vehículos, según el alcance que se defina.

Cuando el propietario sea una persona jurídica, la configuración podrá realizarla un usuario con autorización expresa para el alcance correspondiente. Ser destinatario de una notificación o tener acceso al vehículo no deberá conceder por sí solo permiso para modificar esas preferencias.

Las preferencias podrán actuar sobre canales, categorías, frecuencia o recordatorios cuando las reglas de cada comunicación permitan configurarlos. No deberá asumirse que todas las notificaciones pueden desactivarse ni que todas son obligatorias.

Modificar una preferencia deberá afectar únicamente el comportamiento de comunicación permitido. La información, alerta, recomendación o solicitud que origine una notificación conservará su existencia y evolución conforme a sus propias reglas.

La selección de un canal preferido no deberá garantizar su utilización cuando no esté disponible o no cumpla las condiciones necesarias para comunicar la información.

Si posteriormente se habilita esta capacidad para el Prestador de Servicios Vehiculares, su documento de requisitos deberá referenciar esta especificación general y definir el alcance correspondiente.

#### Criterios de aceptación

1. El propietario autenticado podrá consultar las preferencias vigentes y modificar las opciones habilitadas para él. Cuando actúe un usuario en representación de una persona jurídica, deberá contar con autorización vigente para esa acción y su alcance.
2. La plataforma limitará la configuración a las opciones y valores permitidos para cada tipo de comunicación.
3. Las preferencias guardadas se aplicarán a las notificaciones correspondientes conforme a su alcance y a las reglas de envío.
4. Desactivar una comunicación configurable no eliminará ni resolverá la alerta, recomendación o situación que la origina.
5. Modificar preferencias no registrará una intervención, actualizará el kilometraje ni cambiará una regla de mantenimiento.
6. La preferencia de canal se aplicará junto con las condiciones de disponibilidad y uso del canal, sin sustituirlas.
7. Las preferencias personales de un usuario no modificarán automáticamente las de otros usuarios. Si se habilita una configuración compartida para una persona jurídica, sus efectos deberán limitarse al alcance expresamente definido y autorizado.
8. Ser destinatario de notificaciones no habilitará por sí solo la modificación de preferencias compartidas.
9. Configurar una preferencia no concederá acceso a información ni convertirá a un usuario en destinatario autorizado.

#### Decisiones pendientes

- Definir qué comunicaciones y opciones serán configurables en la primera etapa.
- Definir si las preferencias se aplicarán por cuenta, por vehículo, por categoría o mediante una combinación de esos niveles.
- Establecer los valores iniciales, los límites de frecuencia y el tratamiento de notificaciones pendientes cuando cambie una preferencia.
- Definir, para personas jurídicas, qué preferencias serán personales o compartidas, quién podrá modificarlas y su disponibilidad en la primera etapa.

---

### RF-038 — Corregir un registro histórico

- ID: RF-038.
- Nombre: Corregir un registro histórico.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Gestión e integridad del historial vehicular.
- Etapa prevista: Primera etapa del Propietario; el alcance de la representación de personas jurídicas está pendiente de precisar. Las capacidades de corrección del Prestador se definirán para una etapa posterior.
- Estado de la definición: Propuesta; pendiente de definir los campos corregibles y los permisos según el tipo y origen del registro.
- Actor relacionado: Propietario autenticado con autorización para corregir el registro o usuario autorizado para esa acción en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Modificación, corrección y conservación de registros históricos definidas en `63.6.5` de `proyecto.md`; acceso de propietarios anteriores conforme a `63.4.15`; autorización de representación conforme a `63.4.17`; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: Pendiente de incorporar a `casos-uso.md`; esta capacidad no aparece en la lista preliminar del punto 29 de `proyecto.md`.
- Dependencias: Existencia del registro; definición de los datos corregibles, validaciones y permisos aplicables.

#### Descripción

Vehículos Services deberá permitir que el propietario rectifique información registrada incorrectamente cuando el tipo de registro, su origen y los permisos aplicables autoricen la corrección.

Cuando el propietario sea una persona jurídica, la corrección podrá realizarla un usuario autorizado para el vehículo, el registro y esa acción. La autorización para consultar el historial o crear registros no deberá habilitar por sí sola la corrección de información existente.

El valor corregido podrá utilizarse como información vigente, mientras la plataforma conserva internamente el valor anterior, el nuevo valor, quién realizó la corrección y cuándo ocurrió. La corrección no deberá reemplazar la identificación del creador original del registro.

Tener acceso de consulta al historial o ser el propietario actual no deberá otorgar automáticamente permiso para corregir cualquier registro, especialmente los correspondientes a otros actores o a períodos anteriores de propiedad.

El acceso que conserve un propietario anterior a la información de su período de propiedad será de consulta y no le permitirá corregir los registros mediante esta funcionalidad.

Esta funcionalidad deberá distinguirse de completar datos faltantes, conforme a RF-039, y de anular un registro completo, conforme a RF-040.

#### Criterios de aceptación

1. El propietario autenticado podrá corregir únicamente los datos y registros para los que tenga autorización. Cuando el propietario sea una persona jurídica, el usuario deberá contar con autorización vigente para el vehículo, el registro y esa acción.
2. La corrección deberá cumplir las validaciones correspondientes al dato y al tipo de registro.
3. La información rectificada se presentará como valor vigente conforme a las reglas de consulta.
4. La plataforma conservará internamente el valor anterior, el nuevo valor, el actor responsable y la fecha y hora de la corrección.
5. La corrección mantendrá la identificación del creador original y la relación del registro con el vehículo.
6. El acceso de consulta o el permiso para crear registros no habilitarán por sí solos la corrección de información existente.
7. Un cambio de propietario no concederá automáticamente permiso para rectificar registros de períodos anteriores.
8. La conservación de la trazabilidad no hará visibles automáticamente sus detalles a todos los usuarios.
9. El acceso de consulta conservado por un propietario anterior no permitirá corregir registros de su período de propiedad.

#### Decisiones pendientes

- Definir los campos corregibles y los permisos para cada tipo y origen de registro.
- Definir cuándo una corrección requerirá motivo, confirmación o aprobación.
- Precisar cómo se reevaluarán los cálculos, objetivos, estados, alertas y recomendaciones afectados por una corrección.
- Definir el mecanismo para reportar errores en registros que el propietario no tenga permiso de corregir directamente.
- Definir el alcance de los permisos de corrección para usuarios autorizados de personas jurídicas y su disponibilidad en la primera etapa.

---

### RF-039 — Completar información faltante de un registro histórico

- ID: RF-039.
- Nombre: Completar información faltante de un registro histórico.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Gestión e integridad del historial vehicular.
- Etapa prevista: Primera etapa del Propietario; el alcance de la representación de personas jurídicas está pendiente de precisar. La participación sobre registros del Prestador corresponderá a una etapa posterior de integración.
- Estado de la definición: Propuesta; pendiente de definir los campos que podrán completarse y los permisos correspondientes.
- Actor relacionado: Propietario autenticado con autorización para completar el registro o usuario autorizado para esa acción en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Modificación, corrección y conservación de registros históricos definidas en `63.6.5` de `proyecto.md`; acceso de propietarios anteriores conforme a `63.4.15`; autorización de representación conforme a `63.4.17`; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: Pendiente de incorporar a `casos-uso.md`; esta capacidad no aparece en la lista preliminar del punto 29 de `proyecto.md`.
- Dependencias: Existencia de un registro con información faltante; definición de los campos, validaciones y permisos aplicables.

#### Descripción

Vehículos Services deberá permitir que el propietario incorpore información conocida posteriormente a un registro histórico que contenga datos faltantes, cuando el tipo de registro y los permisos correspondientes lo permitan.

Cuando el propietario sea una persona jurídica, la incorporación podrá realizarla un usuario autorizado para el vehículo, el registro y esa acción. La autorización para consultar el historial o crear registros no deberá habilitar por sí sola la incorporación de información a registros existentes.

Completar deberá consistir en agregar información que no estaba registrada, sin sustituir valores existentes. Cuando se requiera rectificar un dato registrado incorrectamente, deberá aplicarse RF-038.

La incorporación posterior deberá conservar la identidad del registro, su relación con el vehículo y su creador original. La plataforma deberá identificar qué información fue completada, por quién y cuándo.

Durante la etapa de integración, el propietario podrá completar campos faltantes de registros creados por un Prestador únicamente cuando las reglas específicas lo autoricen. Esta acción seguirá siendo un requerimiento del Propietario, aunque actúe sobre un registro originado en el módulo del Prestador.

El acceso de consulta que conserve un propietario anterior a la información de su período de propiedad no permitirá completar esos registros.

#### Criterios de aceptación

1. El propietario autenticado podrá incorporar datos únicamente en los campos sin información que estén habilitados para completar y para los que tenga autorización. Cuando el propietario sea una persona jurídica, el usuario deberá contar con autorización vigente para el vehículo, el registro y esa acción.
2. Los datos incorporados deberán cumplir las validaciones del campo y del tipo de registro.
3. Completar un campo no permitirá sobrescribir mediante esta funcionalidad un valor ya registrado.
4. La información agregada quedará asociada al mismo registro, sin crear un evento histórico duplicado.
5. La plataforma conservará la identificación del creador original y registrará qué información fue incorporada, por qué usuario y cuándo.
6. La fecha en que se completa la información no sustituirá automáticamente la fecha del evento al que pertenece el registro.
7. La autorización para completar un campo no otorgará permiso para modificar los demás datos del registro.
8. La plataforma no rellenará los campos restantes con valores supuestos por el hecho de que algunos datos hayan sido completados.
9. El acceso de consulta o el permiso para crear registros no habilitarán por sí solos la incorporación de información a registros existentes.
10. El acceso de consulta conservado por un propietario anterior no permitirá completar registros de su período de propiedad.

#### Decisiones pendientes

- Definir los campos que podrán completarse para cada tipo de registro.
- Precisar los permisos según el origen del registro, su estado y el período de propiedad al que corresponde.
- Definir cómo se actualizarán los resultados derivados cuando la información incorporada permita realizar cálculos que antes no estaban disponibles.
- Definir el alcance de los permisos para usuarios autorizados de personas jurídicas y su disponibilidad en la primera etapa.

---

### RF-040 — Anular un registro histórico

- ID: RF-040.
- Nombre: Anular un registro histórico.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Gestión e integridad del historial vehicular.
- Etapa prevista: Primera etapa del Propietario; el alcance de la representación de personas jurídicas está pendiente de precisar. Las capacidades de anulación del Prestador se definirán para una etapa posterior.
- Estado de la definición: Propuesta; pendiente de definir las condiciones y los permisos de anulación según el tipo de registro.
- Actor relacionado: Propietario autenticado con autorización para anular el registro o usuario autorizado para esa acción en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Modificación, corrección y conservación de registros históricos definidas en `63.6.5` de `proyecto.md`; acceso de propietarios anteriores conforme a `63.4.15`; autorización de representación conforme a `63.4.17`; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: Pendiente de incorporar a `casos-uso.md`; esta capacidad no aparece en la lista preliminar del punto 29 de `proyecto.md`.
- Dependencias: Existencia del registro; definición de las condiciones y permisos para anularlo.

#### Descripción

Vehículos Services deberá permitir que el propietario anule un registro histórico incorporado incorrectamente cuando las reglas y los permisos correspondientes lo autoricen.

Cuando el propietario sea una persona jurídica, la anulación podrá realizarla un usuario autorizado para el vehículo, el registro y esa acción. Los permisos para consultar, crear, completar o corregir registros no deberán habilitar por sí solos su anulación.

La anulación deberá aplicarse cuando el registro completo no deba continuar considerándose un evento válido, por ejemplo, porque corresponde a otro vehículo o representa un evento que no ocurrió. Si el error afecta únicamente un dato corregible, deberá utilizarse RF-038.

El registro anulado deberá dejar de operar como información vigente, conservando internamente su existencia y la trazabilidad de la anulación. Esta acción no deberá borrar físicamente el registro ni conceder al propietario permiso para anular información de otros actores o períodos de propiedad.

El acceso de consulta que conserve un propietario anterior a la información de su período de propiedad no permitirá anular esos registros.

#### Criterios de aceptación

1. El propietario autenticado podrá anular únicamente los registros para los que tenga autorización. Cuando el propietario sea una persona jurídica, el usuario deberá contar con autorización vigente para el vehículo, el registro y esa acción.
2. La plataforma identificará el registro como anulado y dejará de tratarlo como un evento válido en la operación vigente.
3. La plataforma conservará internamente la información del registro, la identificación de su creador original y la identificación de quién realizó la anulación y cuándo.
4. La anulación no eliminará automáticamente otros registros del vehículo.
5. La existencia de documentos, repuestos u otros elementos relacionados se tratará conforme a las reglas de dependencia, sin asumir su eliminación automática.
6. Los permisos para consultar, crear, completar o corregir registros no otorgarán por sí solos permiso para anularlos.
7. Un cambio de propietario no concederá automáticamente autorización para anular registros correspondientes a períodos anteriores.
8. Los resultados derivados del registro se reevaluarán conforme a las reglas aplicables, conservando la trazabilidad de los cambios que correspondan.
9. El acceso de consulta conservado por un propietario anterior no permitirá anular registros de su período de propiedad.

#### Decisiones pendientes

- Definir qué registros podrán anularse y bajo qué condiciones.
- Definir cuándo será obligatorio indicar un motivo, confirmar la acción o solicitar aprobación.
- Precisar el tratamiento de documentos y elementos relacionados, así como de cálculos, ciclos de seguimiento, alertas y recomendaciones afectados.
- Definir si una anulación podrá revertirse y qué permisos y controles requerirá esa reversión.
- Definir el alcance de los permisos de anulación para usuarios autorizados de personas jurídicas y su disponibilidad en la primera etapa.

---

### RF-041 — Gestionar usuarios autorizados de una persona jurídica propietaria

- ID: RF-041.
- Nombre: Gestionar usuarios autorizados de una persona jurídica propietaria.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Gestión de representación y permisos del Propietario.
- Etapa prevista: Por definir dentro del módulo del Propietario; deberá habilitarse antes de permitir que usuarios autorizados actúen en representación de una persona jurídica.
- Estado de la definición: Propuesta; pendiente de definir quién podrá administrar las autorizaciones y cómo se acreditará esa facultad.
- Actores relacionados: Usuario con facultad validada para administrar autorizaciones de una persona jurídica, por definir; usuario que recibe la autorización.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Usuarios autorizados para vehículos de una persona jurídica definidos en `63.4.17` de `proyecto.md`; reglas específicas de representación, asignación, permisos y revocación por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: Pendiente de incorporar a `casos-uso.md`.
- Dependencias: Cuentas de usuario conforme a RF-001; autenticación conforme a RF-002; identificación de la persona jurídica propietaria; relaciones de propiedad válidas de los vehículos; mecanismo para validar quién puede administrar las autorizaciones.

#### Descripción

Vehículos Services deberá permitir que una persona jurídica propietaria, mediante un usuario cuya facultad para administrar autorizaciones haya sido validada, otorgue, consulte, modifique o retire autorizaciones de acceso y gestión sobre determinados vehículos de su propiedad.

Cada autorización deberá identificar al usuario autorizado, la persona jurídica representada, los vehículos asignados y las acciones permitidas. Podrá comprender uno o varios vehículos, sin conceder automáticamente acceso a toda la flota.

La autorización deberá mantenerse separada de la relación de propiedad. El usuario autorizado actuará en representación de la persona jurídica y no se convertirá en propietario del vehículo.

Los permisos aplicables a cada funcionalidad deberán respetar sus requisitos correspondientes. Tener asignado un vehículo o contar con permiso de consulta no deberá habilitar automáticamente todas las acciones sobre él. La facultad para administrar autorizaciones también deberá otorgarse y validarse expresamente.

La modificación o revocación deberá afectar únicamente el alcance seleccionado. Retirar una autorización no deberá eliminar la cuenta personal del usuario, sus vehículos propios ni otras autorizaciones independientes que pueda tener.

Los registros incorporados legítimamente durante la autorización deberán conservarse con la identidad de quien los creó y la representación bajo la cual actuó. El retiro de permisos no deberá eliminar esos registros ni atribuirlos a otro usuario.

Dentro del alcance actual, esta capacidad corresponderá únicamente a propietarios persona jurídica. No habilitará la delegación de la administración de vehículos pertenecientes a una persona natural ni las autorizaciones de acceso del Prestador definidas en RF-013 y RF-014.

#### Criterios de aceptación

1. Solo un usuario cuya facultad para administrar autorizaciones de la persona jurídica haya sido validada podrá otorgarlas, modificarlas o retirarlas dentro de su alcance permitido.
2. Cada autorización permitirá identificar al usuario, la persona jurídica, los vehículos asignados y las acciones habilitadas.
3. Solo podrán asignarse vehículos con una relación de propiedad actual válida con la persona jurídica correspondiente.
4. Un usuario podrá recibir autorización para uno o varios vehículos sin obtener automáticamente acceso a los demás vehículos de la organización.
5. Las acciones permitidas se comprobarán conforme a la autorización vigente y al requisito de la funcionalidad utilizada.
6. La asignación de un vehículo no otorgará automáticamente permiso para administrar autorizaciones de otros usuarios.
7. Después de retirar una autorización, el usuario no podrá realizar nuevas consultas o acciones cuyo permiso dependía exclusivamente de ella.
8. La modificación o revocación no cambiará la propiedad del vehículo, no creará un período de propiedad ni reiniciará su historial.
9. Los registros existentes conservarán su creador original y la representación correspondiente, aunque posteriormente se retire la autorización.
10. La plataforma conservará la trazabilidad de las autorizaciones otorgadas, modificadas o retiradas, incluyendo el responsable, el momento y los cambios realizados.
11. Retirar una autorización no eliminará la cuenta personal del usuario ni modificará automáticamente otras relaciones o permisos independientes.
12. Esta funcionalidad no permitirá que una persona natural propietaria delegue la administración de sus vehículos dentro del alcance actualmente definido.

#### Decisiones pendientes

- Definir cómo se identificará y validará al primer usuario con facultad para administrar autorizaciones de la persona jurídica.
- Definir quién podrá otorgar esa facultad a otros usuarios y cómo se gestionará su sustitución o retiro.
- Definir el mecanismo para incorporar usuarios: vinculación de cuentas existentes, invitación u otro procedimiento aprobado, incluyendo si requerirá aceptación.
- Definir los permisos disponibles, sus combinaciones y si se asignarán individualmente o mediante roles.
- Definir si las autorizaciones tendrán vigencia temporal y cómo se tratarán su vencimiento y reactivación.
- Precisar el tratamiento de operaciones en curso cuando se modifique o retire una autorización.
- Definir la etapa de habilitación para personas jurídicas y mantenerla alineada con los requisitos que permiten actuar en su representación.

---

### RF-042 — Registrar una persona jurídica como propietaria

- ID: RF-042.
- Nombre: Registrar una persona jurídica como propietaria.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Identificación y representación del Propietario.
- Etapa prevista: Por definir dentro del módulo del Propietario; necesaria para habilitar la asociación de vehículos a personas jurídicas.
- Estado de la definición: Propuesta; pendiente de definir los datos de identificación, las validaciones y el procedimiento de registro.
- Actor relacionado: Usuario autenticado que solicita registrar una persona jurídica y actuar en su representación, sujeto a la validación correspondiente.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Identificación del propietario y correspondencia con la tarjeta de propiedad conforme a `63.4.3` y `63.4.4` de `proyecto.md`; representación de personas jurídicas conforme a `63.4.17`; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: Pendiente de incorporar a `casos-uso.md`.
- Dependencias: Cuenta de usuario y autenticación conforme a RF-001 y RF-002; definición de los datos para identificar la persona jurídica; mecanismo para validar la facultad del usuario que solicita representarla.

#### Descripción

Vehículos Services deberá permitir registrar la información de una persona jurídica que será identificada como propietaria de vehículos dentro de la plataforma.

La identidad de la persona jurídica deberá mantenerse separada de la cuenta personal del usuario que solicita su registro. Registrar la organización no deberá convertir al usuario en propietario personal de sus vehículos.

La plataforma deberá obtener los datos obligatorios que se definan para identificar a la persona jurídica y comprobar si ya existe antes de crear un nuevo registro. La coincidencia de un nombre, por sí sola, no deberá considerarse suficiente para determinar su identidad.

Si la persona jurídica ya está registrada, la plataforma deberá conservar su identidad y tramitar la solicitud de representación conforme al procedimiento aprobado, sin crear otra organización ni conceder acceso automático a sus vehículos.

La incorporación de los datos de la organización no deberá acreditar por sí sola que el usuario puede representarla. Las facultades de representación y administración deberán validarse antes de habilitar las acciones que dependan de ellas.

La asociación de cada vehículo y la validación de su propiedad se realizarán conforme a RF-003. La administración de usuarios autorizados se regirá por RF-041. Registrar la persona jurídica no deberá crear automáticamente vehículos, relaciones de propiedad ni autorizaciones para otros usuarios.

#### Criterios de aceptación

1. Un usuario autenticado podrá presentar la información necesaria para solicitar el registro de una persona jurídica conforme al mecanismo habilitado.
2. La plataforma exigirá los datos obligatorios y aplicará las validaciones de identificación aprobadas.
3. Antes de crear un registro, comprobará si la persona jurídica ya existe conforme a los criterios de identificación definidos.
4. Si la persona jurídica ya existe, la solicitud no creará un registro duplicado ni concederá al solicitante acceso automático a su información o sus vehículos.
5. La identidad de la persona jurídica quedará diferenciada de la identidad del usuario que presentó la solicitud.
6. Presentar o registrar los datos de la persona jurídica no otorgará por sí solo facultades para representarla ni administrar autorizaciones.
7. Las acciones de representación se habilitarán únicamente después de completar las validaciones correspondientes.
8. El registro de la persona jurídica no establecerá automáticamente la propiedad de ningún vehículo; cada asociación se validará conforme a RF-003.
9. La plataforma conservará la identificación del solicitante y la trazabilidad del registro y de las validaciones efectuadas.

#### Decisiones pendientes

- Definir los datos obligatorios y opcionales para identificar a la persona jurídica.
- Definir los criterios para detectar organizaciones existentes y tratar coincidencias o información contradictoria.
- Definir cómo se acreditará la facultad del primer usuario que solicite representar a la organización, en coherencia con RF-041.
- Definir los estados de la solicitud y el tratamiento de validaciones pendientes, rechazadas o inconclusas.
- Definir el procedimiento para solicitar representación de una persona jurídica ya registrada, sin exponer información restringida al solicitante.
- Definir cómo se actualizarán o corregirán los datos de identificación y quién podrá hacerlo.
- Definir la etapa de habilitación de propietarios persona jurídica, en coherencia con RF-003 y RF-041.

---

### RF-043 — Gestionar el perfil personal del usuario

- ID: RF-043.
- Nombre: Gestionar el perfil personal del usuario.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Capacidad general compartida — Perfil personal e identificación del usuario.
- Etapa prevista: Primera etapa del Propietario; reutilizable posteriormente por el módulo del Prestador.
- Estado de la definición: Propuesta; los datos personales, documentos admitidos y criterios de identificación están definidos en RN-025. La clasificación de datos editables y las restricciones de corrección están aprobadas en RN-037. Permanecen pendientes las validaciones y los detalles operativos y técnicos correspondientes.
- Actor relacionado: Usuario autenticado que gestiona su propio perfil.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: RN-025 — Cuenta de usuario e identidad del propietario; RN-035 — Revisión manual de conflictos de identificación del propietario; RN-037 — Actualización de datos personales y correcciones mediante soporte, considerando sus estados de definición; gestión del perfil contemplada en el punto 11 de `proyecto.md`; identificación del propietario persona natural conforme a `63.4.3`, `63.4.4` y `63.4.7`.
- Caso de uso preliminar relacionado: Pendiente de incorporar a `casos-uso.md`.
- Dependencias: Cuenta y autenticación conforme a RF-001 y RF-002; datos personales conforme a RN-025; campos editables y correcciones mediante soporte conforme a RN-037; validaciones correspondientes; revisión manual conforme a RN-035 y RF-051 cuando un conflicto de documento impida completar la identificación.

#### Descripción

Vehículos Services deberá permitir que el usuario consulte, complete y actualice los datos de su propio perfil personal conforme a los campos y permisos habilitados.

La creación de una cuenta no deberá exigir desde el inicio todos los datos necesarios para asociar un vehículo. Cuando el usuario solicite actuar como propietario persona natural, la plataforma deberá obtener la información de identificación necesaria para realizar las comparaciones previstas en RF-003.

Para la primera entrega, los nombres, apellidos, tipo y número de documento se solicitarán cuando el usuario vaya a asociar su primer vehículo, conforme a RN-025. Estos datos corresponderán a información declarada por el usuario y se compararán con la tarjeta de propiedad conforme a RF-003. Su registro o coincidencia documental no constituirá una comprobación independiente de la identidad real de quien utiliza la cuenta.

Completar la identificación deberá respetar la unicidad del tipo y número de documento establecida en RN-025. Si esos datos ya están asociados a otra cuenta, no se completará la identificación del propietario. Se mostrará el mensaje aprobado en RN-025, sin fusionar cuentas, trasladar vehículos ni modificar permisos automáticamente. Las correcciones posteriores autorizadas mediante soporte deberán respetar la misma condición de unicidad.

Cuando un conflicto de documento impida completar la identificación, el usuario autenticado podrá solicitar revisión manual conforme a RN-035 y RF-051. La solicitud no aceptará automáticamente los datos en conflicto ni modificará la otra cuenta. Si se autoriza y ejecuta una corrección dentro de los límites de RN-035, el usuario deberá completar nuevamente las comprobaciones normales.

Los datos de identificación personal deberán distinguirse de los datos de contacto y de los utilizados para iniciar sesión. Un nombre visible, una dirección de correo electrónico o la autenticación mediante un proveedor externo no deberán considerarse por sí solos prueba de identidad o propiedad.

Para la primera entrega, el celular de contacto será obligatorio para completar la información del propietario antes de asociar su primer vehículo. No se exigirá para crear inicialmente la cuenta. El usuario autenticado podrá ingresarlo y actualizarlo directamente conforme a RN-037, pero una actualización aceptada no podrá eliminarlo ni dejarlo vacío mientras sea obligatorio.

La ciudad de residencia y la fotografía de perfil serán opcionales. El usuario podrá agregarlas, actualizarlas o retirarlas conforme a RN-037. Su ausencia no impedirá crear la cuenta ni asociar un vehículo cuando se cumplan los demás requisitos.

El celular tendrá inicialmente una finalidad de contacto. No se utilizará por esta funcionalidad como mecanismo de autenticación, recuperación de acceso o prueba de identidad. La fotografía tampoco constituirá prueba de identidad, y cambiar la ciudad de residencia no modificará los datos ni el organismo de tránsito de un vehículo.

La dirección exacta de residencia no se solicitará inicialmente. Su incorporación posterior requerirá una finalidad funcional definida.

Mientras diligencia sus datos de identidad, antes de confirmar su envío, el usuario podrá corregir lo digitado. Una vez confirmados, aceptados y guardados por el sistema, los nombres, apellidos, tipo y número de documento no podrán editarse ni eliminarse directamente desde el perfil, aunque todavía no existan vehículos asociados.

El correo de la cuenta tampoco podrá editarse ni eliminarse directamente después de crearla, incluso mientras permanezca pendiente de verificación.

Las solicitudes de corrección de esos datos se tramitarán mediante soporte conforme a RN-037. No autorizarán automáticamente un cambio ni permitirán sustituir a la persona identificada. Cuando exista un conflicto entre cuentas, se aplicarán RN-025 y RN-035 con sus límites correspondientes.

Gestionar el perfil no deberá transferir vehículos, cambiar su propietario ni modificar la procedencia de los registros históricos. La propiedad de cada vehículo se validará individualmente conforme a RF-003.

El perfil personal deberá mantenerse separado de la información de una persona jurídica registrada conforme a RF-042. Modificarlo no deberá alterar automáticamente la identidad de una organización representada ni las autorizaciones gestionadas mediante RF-041.

Si el usuario tiene también funciones de Prestador de Servicios Vehiculares, esta capacidad conservará una única especificación. La información propia del prestador se gestionará conforme a sus requisitos correspondientes.

#### Criterios de aceptación

1. El usuario autenticado podrá consultar su perfil y completar o actualizar únicamente los campos habilitados para él conforme a RN-025 y RN-037.
2. La plataforma aplicará las validaciones y restricciones definidas para cada campo.
3. Los datos necesarios para identificar al propietario persona natural deberán estar disponibles antes de completar la asociación de un vehículo que requiera utilizarlos.
4. La ausencia de esos datos no impedirá por sí sola crear una cuenta conforme a RF-001.
5. Los datos de contacto o de inicio de sesión no se utilizarán por sí solos como prueba de propiedad de un vehículo.
6. Un cambio en un dato de identificación sujeto a validación no sustituirá automáticamente la identidad del propietario ni sus relaciones existentes.
7. La actualización del perfil no transferirá vehículos ni cambiará la identificación del creador de registros históricos.
8. El usuario no podrá modificar el perfil personal de otra persona mediante esta funcionalidad.
9. Los cambios conservarán la trazabilidad correspondiente, incluyendo el dato modificado, el responsable y el momento, según las reglas aplicables.
10. Modificar el perfil personal no cambiará automáticamente los datos de una persona jurídica ni concederá facultades para representarla.
11. Cuando el usuario vaya a asociar su primer vehículo, la plataforma solicitará los nombres, apellidos, tipo y número de documento establecidos en RN-025.
12. Los datos declarados y su coincidencia con la tarjeta de propiedad no se presentarán como una comprobación independiente de la identidad real del usuario.
13. La plataforma no completará la identificación ni aceptará una corrección que asocie el mismo tipo y número de documento a cuentas diferentes. Se aplicarán el mensaje y las restricciones de RN-025, conservando la información previamente aceptada.
14. Antes de confirmar el envío de sus datos de identidad, el usuario podrá corregir lo digitado. Una vez confirmados, aceptados y guardados, los nombres, apellidos, tipo y número de documento no podrán editarse ni eliminarse directamente, independientemente de que existan vehículos asociados.
15. Si un documento ocupado impide completar la identificación, el usuario podrá solicitar revisión conforme a RF-051. La revisión no aceptará automáticamente los datos ni habilitará cambios fuera de los límites de RN-035.
16. El celular de contacto será obligatorio para completar la información del propietario antes de asociar su primer vehículo, sin exigirlo para crear la cuenta. El usuario podrá actualizarlo directamente, pero no eliminarlo ni dejarlo vacío mediante una actualización aceptada. La ciudad de residencia y la fotografía de perfil serán opcionales y podrán agregarse, actualizarse o retirarse sin impedir la asociación por su ausencia.
17. El celular de contacto no se utilizará inicialmente como mecanismo de autenticación o recuperación. La fotografía de perfil no constituirá prueba de identidad y la actualización de la ciudad no modificará automáticamente información vehicular.
18. El correo de la cuenta no podrá editarse ni eliminarse directamente después de crearla, incluso mientras permanezca pendiente de verificación.
19. La plataforma informará cómo solicitar a soporte la corrección de datos bloqueados conforme a RN-037. La solicitud no modificará automáticamente los datos ni ampliará los permisos del usuario.
20. La dirección exacta de residencia no se solicitará como parte del perfil inicial.

#### Decisiones pendientes

- Detallar las validaciones de formato de los datos declarados, respetando la admisión de cédula de ciudadanía y cédula de extranjería y los criterios de comparación aprobados en RN-025.
- Detallar las validaciones del celular de contacto, la selección de ciudad de residencia y las condiciones de los archivos utilizados como fotografía de perfil.
- Desarrollar los recorridos para consultar el perfil, ingresar inicialmente los datos de identidad y el celular de contacto, actualizar el celular y actualizar o retirar los datos opcionales habilitados.
- Detallar las verificaciones para corregir mediante soporte nombres, apellidos, tipo y número de documento conforme a RN-037, sin sustituir la identidad del usuario ni eludir la unicidad.
- Detallar el procedimiento de corrección del correo mediante soporte, considerando su utilización para autenticación y recuperación de acceso.
- Precisar cómo se repetirán las comprobaciones afectadas por una corrección autorizada de datos personales.
- Definir la visibilidad de los datos personales y el alcance de la trazabilidad conservada.

---

### RF-044 — Registrar costos asociados a intervenciones y repuestos

- ID: RF-044.
- Nombre: Registrar costos asociados a intervenciones y repuestos.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Gestión de costos del vehículo.
- Etapa prevista: Primera etapa del Propietario; el alcance de la representación de personas jurídicas está pendiente de precisar.
- Estado de la definición: Propuesta; pendiente de definir los datos mínimos, el nivel de detalle y las validaciones de los costos.
- Actor relacionado: Propietario autenticado del vehículo o usuario autorizado para registrar costos en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Registro de costos contemplado en el punto 11 de `proyecto.md`; información económica asociada al mantenimiento conforme a `63.7.4` y al repuesto conforme a `63.8.5`; autorización de representación conforme a `63.4.17`; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: Pendiente de incorporar a `casos-uso.md`.
- Dependencias: Relación de propiedad actual válida; autorización para registrar costos; existencia de la intervención o del repuesto al que corresponde el costo; definición de los conceptos económicos, monedas y validaciones aplicables.

#### Descripción

Vehículos Services deberá permitir que el propietario registre información de costos relacionada con mantenimientos, reparaciones, repuestos u otras intervenciones que cuenten con una funcionalidad de registro habilitada.

Cuando el propietario sea una persona jurídica, esta acción podrá realizarla un usuario autorizado para el vehículo y el registro de costos. El permiso para consultar el historial o registrar una intervención no deberá habilitar por sí solo esta acción.

El costo deberá conservar su relación con el vehículo y con el registro al que corresponde. Podrá incorporarse durante el registro inicial de la intervención o del repuesto, o posteriormente cuando los permisos y las reglas lo permitan. Su incorporación no deberá crear una intervención o un repuesto duplicado.

La plataforma deberá distinguir el costo total de una intervención de los importes correspondientes a sus actividades, repuestos u otros conceptos cuando ese detalle se registre. Un importe incluido dentro de un total no deberá tratarse automáticamente como un gasto adicional independiente.

El usuario podrá registrar la información económica conocida conforme a los datos mínimos que se definan. Un costo desconocido no deberá almacenarse automáticamente como cero, ni la ausencia de un desglose deberá obligar a inventar sus componentes.

Los gastos de abastecimiento y recarga se registrarán conforme a RF-029 y se consultarán conforme a RF-031. Este requisito no deberá generar una segunda copia de esos gastos.

La incorporación posterior de un dato económico faltante se regirá por RF-039. La rectificación de un valor registrado incorrectamente se regirá por RF-038, con las validaciones específicas de costos.

#### Criterios de aceptación

1. El propietario autenticado podrá registrar costos para un vehículo con el que tenga una relación de propiedad actual válida, dentro de los registros y campos habilitados. Cuando el propietario sea una persona jurídica, el usuario deberá contar con autorización vigente para esa acción y su alcance.
2. Cada costo permitirá identificar el vehículo, la intervención o el repuesto relacionado, el importe y su moneda.
3. El costo podrá incorporarse durante el registro inicial o posteriormente, sin exigir pantallas independientes ni duplicar el registro relacionado.
4. La plataforma distinguirá el costo total de una intervención de los importes de sus componentes cuando ambos se encuentren registrados.
5. Los importes identificados como incluidos en un total no se sumarán nuevamente a ese mismo total.
6. La ausencia de un costo no se sustituirá automáticamente por cero. Un valor cero proporcionado expresamente se distinguirá de un dato desconocido y se tratará según las validaciones aprobadas.
7. Cuando se permita registrar un costo total sin desglose, la plataforma no distribuirá automáticamente ese importe entre actividades, repuestos u otros conceptos.
8. Registrar un costo no indicará por sí solo que fue pagado ni confirmará que la intervención se realizó; esas condiciones deberán sustentarse en los datos correspondientes.
9. La plataforma conservará la identidad del usuario que incorporó la información y la trazabilidad de sus cambios.
10. Los gastos registrados mediante RF-029 no se duplicarán mediante esta funcionalidad.

#### Decisiones pendientes

- Definir los datos mínimos y si inicialmente se admitirán costos totales, desgloses o ambos.
- Definir los conceptos disponibles y el tratamiento de cantidades, precios unitarios, impuestos, descuentos y otros componentes, cuando se habiliten.
- Definir las monedas admitidas y las validaciones de los importes.
- Precisar cómo se identificarán los costos incluidos en un total y los compartidos entre registros de una misma intervención, para evitar duplicarlos.
- Definir si se distinguirán costos informados, valores cotizados y pagos realizados, sin considerarlos equivalentes.
- Definir los permisos y campos económicos que podrán registrarse, completarse o corregirse según el origen del registro.
- Definir el alcance para usuarios autorizados de personas jurídicas y su disponibilidad en la primera etapa.

---

### RF-045 — Consultar costos de intervenciones y repuestos

- ID: RF-045.
- Nombre: Consultar costos de intervenciones y repuestos.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Gestión de costos del vehículo.
- Etapa prevista: Primera etapa del Propietario; el alcance de la representación de personas jurídicas está pendiente de precisar.
- Estado de la definición: Propuesta; pendiente de definir el alcance inicial de la consulta y las condiciones de acumulación.
- Actor relacionado: Propietario autenticado del vehículo o usuario autorizado para consultar costos en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Información económica asociada al mantenimiento conforme a `63.7.4` y al repuesto conforme a `63.8.5` de `proyecto.md`; privacidad y visibilidad del historial; autorización de representación conforme a `63.4.17`; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: Pendiente de incorporar a `casos-uso.md`.
- Dependencias: Relación de propiedad actual válida; autorización de consulta; información económica registrada conforme a RF-044; reglas para distinguir costos totales, componentes y monedas.

#### Descripción

Vehículos Services deberá permitir que el propietario consulte los costos registrados y accesibles de las intervenciones y repuestos relacionados con uno de sus vehículos.

Cuando el propietario sea una persona jurídica, la consulta podrá realizarla un usuario autorizado para el vehículo y esa funcionalidad. El permiso para consultar otros datos del historial no deberá conceder automáticamente acceso a información económica restringida.

La consulta deberá conservar la relación de cada importe con la intervención, actividad, repuesto u otro concepto al que corresponde. Cuando exista un costo total y un desglose, ambos deberán distinguirse conforme a RF-044.

Las acumulaciones que se habiliten deberán evitar contar nuevamente los importes incluidos en un total. Si la información disponible no permite determinar qué valores son independientes, la plataforma deberá indicar esa limitación en lugar de presentar una suma como válida.

Los resultados deberán identificarse como costos registrados dentro del alcance consultado. No deberán presentarse como la totalidad del costo real del vehículo cuando puedan existir intervenciones, importes o conceptos no registrados.

Los importes en monedas diferentes se mantendrán separados, salvo que exista una regla de conversión expresamente definida.

Los gastos de abastecimiento y recarga conservarán su consulta conforme a RF-031. Si posteriormente se habilita una consulta económica consolidada, deberá referenciar ambos requisitos y evitar duplicar los importes.

#### Criterios de aceptación

1. El propietario autenticado podrá consultar los costos permitidos de un vehículo con el que tenga una relación de propiedad actual válida. Cuando el propietario sea una persona jurídica, el usuario deberá contar con autorización vigente para el vehículo y esa consulta.
2. Cada importe consultado permitirá identificar su moneda y el registro o concepto al que corresponde.
3. La consulta distinguirá el costo total de una intervención de los importes de sus componentes cuando ese detalle esté disponible.
4. Una acumulación no contará como gastos adicionales los importes identificados como incluidos en un total.
5. Si no puede determinarse una acumulación válida con los datos disponibles, la consulta indicará esa limitación sin inventar relaciones entre los importes.
6. Los resultados acumulados identificarán el conjunto de registros considerado y se presentarán como costos registrados.
7. La ausencia de información económica se distinguirá de un valor cero registrado expresamente.
8. Los importes en monedas diferentes no se sumarán directamente sin una regla de conversión aprobada.
9. Consultar costos no modificará los registros económicos ni habilitará por sí solo su incorporación, corrección o anulación.
10. La consulta de un importe no concederá automáticamente acceso a su factura u otros documentos adjuntos; ese acceso respetará RF-010.
11. La consulta no incluirá información económica restringida de otros actores o períodos de propiedad por el solo hecho de formar parte del historial conservado.

#### Decisiones pendientes

- Definir los filtros, agrupaciones y acumulaciones disponibles inicialmente.
- Definir cómo se presentarán los costos sin desglose, los datos faltantes y los casos en que no pueda obtenerse una suma válida.
- Precisar el tratamiento de importes compartidos entre registros de una misma intervención, conforme a RF-044.
- Definir si se habilitarán comparaciones por períodos y bajo qué condiciones.
- Definir si habrá una consulta consolidada con gastos de abastecimiento y recarga, manteniendo las reglas de RF-031.
- Definir la visibilidad de información económica correspondiente a períodos anteriores de propiedad.
- Definir los permisos de consulta para usuarios autorizados de personas jurídicas y su disponibilidad en la primera etapa.

---

### RF-046 — Actualizar información general del vehículo

- ID: RF-046.
- Nombre: Actualizar información general del vehículo.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Gestión de vehículos.
- Etapa prevista: Primera entrega del Propietario para personas naturales; representación de personas jurídicas prevista para una entrega posterior.
- Estado de la definición: Propuesta; el bloqueo de edición y eliminación directa de datos obligatorios y su corrección mediante soporte están aprobados en RN-037. Permanecen pendientes los campos opcionales habilitados para edición directa, sus validaciones y las verificaciones específicas de soporte. La revisión especial de conflictos vehiculares se desarrollará posteriormente conforme a RN-036.
- Actor relacionado: Propietario autenticado del vehículo; personal de soporte autorizado para ejecutar las correcciones aprobadas conforme a RN-037; en una entrega posterior, usuario autorizado para actualizar información general en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: RN-036 — Identificación, coincidencias y comparación documental del vehículo; RN-037 — Actualización de datos personales y correcciones mediante soporte, considerando sus estados de definición; actualización de información autorizada contemplada en el punto 11 de `proyecto.md`; identidad vehicular conforme a `63.1.4`; información general y aplicabilidad de campos conforme a `63.1.5`; autorización de representación conforme a `63.4.17`.
- Caso de uso preliminar relacionado: Pendiente de incorporar a `casos-uso.md`.
- Dependencias: Vehículo registrado conforme a RF-003; relación de propiedad actual válida; autorización para actualizar información; definición de los campos opcionales habilitados y sus validaciones; límites de identificación establecidos en RN-036; procedimiento de corrección mediante soporte conforme a RN-037.

#### Descripción

Vehículos Services deberá permitir que el propietario complete o actualice los campos opcionales habilitados de la información general de uno de sus vehículos.

Cuando el propietario sea una persona jurídica, esta acción podrá realizarla un usuario autorizado para el vehículo y la modificación correspondiente. El permiso de consulta no deberá habilitar por sí solo la actualización. Esta capacidad de representación se habilitará en la entrega posterior correspondiente.

La plataforma deberá distinguir los datos descriptivos de aquellos utilizados para identificar el vehículo, validar su propiedad o determinar reglas funcionales. No deberá asumirse que todos los campos pueden modificarse mediante una edición ordinaria.

Después de confirmar, aceptar y guardar el registro definitivo, los datos obligatorios aplicables definidos en el punto 63.1.5 de `proyecto.md` no podrán editarse ni eliminarse directamente por el propietario. Esta restricción comprenderá la placa, el VIN y los demás datos obligatorios correspondientes al vehículo.

Las solicitudes de corrección de errores de captura en esos datos se tramitarán mediante soporte conforme a RN-037. Contactar a soporte no autorizará automáticamente una modificación. Antes de ejecutarla deberán cumplirse las verificaciones y condiciones aprobadas para el dato afectado.

La modificación de identificadores deberá respetar RN-036. La edición de información general no deberá utilizarse para evitar una coincidencia con otro vehículo ni sobrescribir automáticamente identificadores a partir de una nueva solicitud o tarjeta de propiedad. Los cambios permitidos y sus evidencias deberán definirse antes de habilitar esas correcciones mediante soporte.

La corrección no deberá utilizarse para sustituir la identidad de un vehículo por la de otro, fusionar vehículos o transferir su propiedad.

Durante la primera entrega, esta funcionalidad no habilitará el procedimiento especial de revisión y resolución de conflictos vehiculares aplazado en RN-036. Las correcciones de errores de captura mediante RN-037 deberán mantenerse diferenciadas de ese procedimiento. Tampoco se utilizará la revisión de identificación del propietario de RN-035 y RF-051 para autorizar cambios de placa, VIN o propiedad.

La actualización conservará el identificador interno del vehículo y la continuidad de su historial. Los registros anteriores mantendrán su procedencia y el contexto que corresponda, sin reescribirse automáticamente con los nuevos datos de la información general.

La aplicabilidad y obligatoriedad de los campos deberán respetar el tipo y las características del vehículo conforme a `63.1.5` de `proyecto.md`.

La actualización del kilometraje se regirá por RF-005; la corrección de registros históricos, por RF-038; y el cambio de propietario, por RF-020. Esta funcionalidad no permitirá sobrescribir la lectura inicial ni las anteriores mediante la edición de la información general.

#### Criterios de aceptación

1. El propietario autenticado podrá completar o actualizar únicamente los campos opcionales habilitados de un vehículo con el que tenga una relación de propiedad actual válida. Cuando se habilite la representación de personas jurídicas en la entrega posterior correspondiente, el usuario deberá contar con autorización vigente para el vehículo y esa acción.
2. La plataforma aplicará las validaciones y restricciones correspondientes a cada campo.
3. Después de confirmar, aceptar y guardar el registro definitivo, el propietario no podrá editar ni eliminar directamente los datos obligatorios aplicables definidos en 63.1.5 de `proyecto.md`, incluidos la placa y el VIN.
4. La plataforma no exigirá datos que no apliquen al vehículo y distinguirá esa situación de información aplicable no suministrada.
5. Las correcciones de errores de captura en datos obligatorios requerirán intervención de soporte conforme a RN-037. Solo podrán ejecutarse mediante los permisos y verificaciones aprobados, sin dejar vacíos los datos que continúen siendo obligatorios.
6. Una actualización aceptada conservará el identificador interno del vehículo y sus relaciones históricas.
7. La edición de la información general no transferirá la propiedad ni convertirá el registro en otro vehículo.
8. La plataforma conservará la trazabilidad de los cambios, incluyendo los valores anteriores y nuevos, el usuario responsable y el momento.
9. La actualización no sobrescribirá automáticamente la información de eventos históricos ni modificará el kilometraje mediante un procedimiento distinto de RF-005. Tampoco permitirá sobrescribir la lectura inicial ni las anteriores desde la información general.
10. El acceso de consulta, incluido el conservado por un propietario anterior, no permitirá modificar la información general.
11. Las correcciones autorizadas de identificadores respetarán RN-036 y RN-037. No permitirán eludir coincidencias, fusionar vehículos ni sobrescribir automáticamente los identificadores existentes con los datos de una nueva solicitud. Cuando afecten la placa o el VIN, se repetirán las búsquedas y comparaciones aplicables antes de aceptar el cambio.
12. La primera entrega no permitirá utilizar la edición de información general, la corrección de errores de captura de RN-037 ni la revisión de RN-035 y RF-051 como alternativa al procedimiento especial de revisión y resolución de conflictos vehiculares previsto para una entrega posterior.
13. La plataforma informará cómo solicitar a soporte la corrección de datos obligatorios conforme a RN-037. La solicitud no modificará automáticamente el vehículo ni concederá permisos adicionales.

#### Decisiones pendientes

- Definir qué campos opcionales podrán completarse, actualizarse o retirarse directamente y sus validaciones, respetando el bloqueo aprobado para los datos obligatorios.
- Detallar las correcciones de errores de captura admitidas mediante soporte en la primera entrega, sus evidencias y comprobaciones, conforme a RN-036 y RN-037.
- Definir para una entrega posterior el procedimiento especial para revisar y resolver conflictos de identificación vehicular, así como las correcciones permitidas sobre los registros afectados, respetando RN-036.
- Distinguir la corrección de un dato inicialmente erróneo de un cambio real en las características del vehículo. La habilitación de correcciones de captura no autorizará por sí misma registrar esos cambios reales.
- Precisar el tratamiento de correcciones autorizadas que afecten la clasificación, los campos aplicables, la fuente de energía o las reglas de seguimiento.
- Definir cómo se reevaluarán los resultados derivados afectados por una actualización, conservando su trazabilidad.
- Definir los permisos de actualización para usuarios autorizados de personas jurídicas cuando se aborde la entrega posterior correspondiente.


---

### RF-047 — Consultar prestadores relacionados con un vehículo

- ID: RF-047.
- Nombre: Consultar prestadores relacionados con un vehículo.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Relación y autorización entre Prestador de Servicios Vehiculares y vehículo.
- Etapa prevista: Tercera etapa de integración entre Propietario y Prestador de Servicios Vehiculares.
- Estado de la definición: Conceptual; pendiente de definir la información visible y las opciones de consulta.
- Actor relacionado: Propietario autenticado del vehículo o usuario autorizado para consultar estas relaciones en representación de una persona jurídica propietaria.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Consulta de prestadores contemplada en el punto 11 de `proyecto.md`; autorización, vigencia y finalización de relaciones conforme a `63.5.2`, `63.5.3` y `63.5.4`; autorización de representación conforme a `63.4.17`; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: Pendiente de incorporar a `casos-uso.md`.
- Dependencias: Relación de propiedad actual válida; autorización de consulta; disponibilidad de las relaciones y de la información permitida del prestador en la etapa de integración.

#### Descripción

Vehículos Services deberá permitir que el propietario consulte los Prestadores de Servicios Vehiculares que tengan una relación autorizada con uno de sus vehículos y conozca el estado de esa relación.

Cuando el propietario sea una persona jurídica, la consulta podrá realizarla un usuario autorizado para el vehículo y esa funcionalidad. El permiso de consulta no deberá habilitar por sí solo la autorización o revocación de prestadores.

Cada relación deberá conservar su asociación con el vehículo y el prestador correspondientes. La consulta deberá distinguir una relación activa de una relación finalizada y, cuando se incluya información histórica, identificar el período al que corresponde.

Una solicitud pendiente o rechazada no deberá presentarse como una relación activa. Su revisión y resolución se regirán por RF-013.

Mencionar un taller, técnico o tercero al registrar una intervención no deberá incorporarlo automáticamente como prestador autorizado en esta consulta. Deberá distinguirse quién realizó un trabajo de quién tiene una relación formal y vigente con el vehículo.

La información mostrada del prestador se limitará a los datos cuya consulta esté permitida. La existencia de una relación no deberá implicar acceso irrestricto a información privada del prestador ni acreditar que todas las intervenciones del vehículo fueron realizadas por él.

La autorización y revocación se regirán por RF-013 y RF-014. Consultar una relación no deberá modificar su estado.

#### Criterios de aceptación

1. El propietario autenticado podrá consultar las relaciones permitidas de un vehículo con el que tenga una relación de propiedad actual válida. Cuando el propietario sea una persona jurídica, el usuario deberá contar con autorización vigente para el vehículo y esa consulta.
2. Cada relación mostrada permitirá identificar el vehículo, el prestador y su estado.
3. Si se presentan relaciones finalizadas, se distinguirán de las activas y conservarán la identificación de su período cuando corresponda.
4. Una solicitud pendiente o rechazada no se mostrará como una autorización activa.
5. Un tercero mencionado en una intervención no aparecerá como prestador autorizado únicamente por esa mención.
6. Las relaciones con distintos prestadores se mostrarán de manera independiente, sin confundir sus estados o períodos.
7. La consulta no activará, renovará ni finalizará una relación.
8. El permiso para consultar relaciones no habilitará por sí solo las acciones de RF-013 o RF-014.
9. Después de una transferencia, las relaciones anteriores no se presentarán como autorizaciones activas del nuevo propietario, conforme a RF-020.
10. Si el vehículo no tiene relaciones activas, la plataforma indicará esa situación sin crear relaciones a partir de su historial de intervenciones.

#### Decisiones pendientes

- Definir los datos del prestador y de la relación que estarán disponibles en la consulta.
- Definir si inicialmente se mostrarán solo relaciones activas o también relaciones finalizadas.
- Precisar la visibilidad de relaciones correspondientes a períodos anteriores de propiedad.
- Definir cómo se presentarán las solicitudes pendientes, manteniéndolas diferenciadas de las relaciones autorizadas y en coherencia con RF-013.
- Definir los filtros y opciones de consulta.
- Definir los permisos de consulta para usuarios autorizados de personas jurídicas.

---

### RF-048 — Recuperar acceso a la cuenta

- ID: RF-048.
- Nombre: Recuperar acceso a la cuenta.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Capacidad general compartida — Gestión de cuenta y acceso.
- Etapa prevista: Primera etapa del Propietario en Android e iOS; reutilizable posteriormente por el módulo del Prestador.
- Estado de la definición: Aprobado en su alcance funcional para la primera entrega, conforme al procedimiento de RN-029 y las condiciones de los proveedores externos. La recuperación asistida y los mecanismos alternativos requerirán una definición posterior antes de habilitarse.
- Actor relacionado: Persona que solicita recuperar el acceso a su cuenta.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: RN-026 — Mecanismos de registro y autenticación; RN-027 — Verificación del correo en el registro propio; RN-028 — Datos, contraseña y coincidencias del registro propio; RN-029 — Recuperación de la contraseña propia; RN-030 — Registro y autenticación mediante Google; RN-031 — Vinculación, incorporación y retiro de métodos de acceso; RN-032 — Registro y autenticación mediante Apple, definidas en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: Recuperar acceso a la cuenta; identificador y detalle pendientes en `casos-uso.md`.
- Dependencias: Cuenta registrada conforme a RF-001; mecanismos de autenticación definidos para RF-002; procedimiento de recuperación conforme a RN-029; condiciones de Google y Apple conforme a RN-030 y RN-032; controles de seguridad y gestión de sesiones aplicables, incluyendo RNF-003 y RNF-021 de `requerimientos-no-funcionales.md`.

#### Descripción

Vehículos Services deberá permitir que una persona solicite recuperar el acceso a su cuenta mediante un procedimiento compatible con los mecanismos de autenticación habilitados para ella.

Cuando la cuenta tenga una contraseña administrada por Vehículos Services, la recuperación permitirá restablecerla mediante un código enviado al correo actualmente asociado a la cuenta, conforme a RN-029.

La solicitud podrá iniciarse sin una sesión autenticada. La plataforma deberá comprobar la autorización para realizar el cambio antes de modificar la contraseña. Conocer una placa, datos de un vehículo o información visible del perfil no será suficiente para completar esa comprobación.

El procedimiento deberá aplicar las condiciones de generación, vigencia, uso único, límites, comprobación y tratamiento de errores establecidas en RN-029. La nueva contraseña deberá cumplir RN-028.

Cuando la autenticación dependa exclusivamente de Google o Apple, la plataforma ofrecerá una orientación general hacia la recuperación del proveedor correspondiente, sin modificar sus credenciales ni crear automáticamente una contraseña propia. Si la cuenta dispone de una contraseña propia y métodos externos vinculados, el procedimiento propio permitirá restablecer únicamente la contraseña administrada por Vehículos Services.

La recuperación deberá conservar la cuenta existente y sus relaciones. No deberá crear una cuenta duplicada, transferir vehículos ni conceder nuevas facultades de representación o permisos.

Una cuenta pendiente de verificación que tenga contraseña propia podrá recuperarla mientras su registro provisional se conserve. El restablecimiento no verificará el correo, habilitará la cuenta ni ampliará el plazo establecido en RN-027.

Al completar el restablecimiento de la contraseña propia, se invalidarán las sesiones de Vehículos Services y los demás medios pendientes de recuperación de contraseña de esa cuenta, conforme a RN-029. El usuario deberá volver a iniciar sesión; no se autenticará automáticamente.

Recuperar el acceso no deberá eliminar restricciones vigentes ni reactivar autorizaciones revocadas. Después de la recuperación, el acceso continuará sujeto a las relaciones y permisos correspondientes.

Si la persona perdió el acceso a su correo, Google o Apple, deberá recuperar ese medio mediante su proveedor. La primera entrega no ofrecerá procedimientos alternativos o asistidos que no hayan sido definidos y habilitados.

Incorporar una contraseña a una cuenta que todavía no la tenga será una operación de gestión de métodos conforme a RN-031. No se realizará mediante este procedimiento de recuperación.

Este requisito tendrá una única especificación y podrá referenciarse desde `requerimientos-funcionales-prestador.md`.

#### Criterios de aceptación

1. La persona podrá iniciar una solicitud de recuperación sin disponer de una sesión autenticada.
2. El procedimiento disponible corresponderá a los mecanismos de acceso asociados a la cuenta, conforme a RN-026, RN-029, RN-030 y RN-032.
3. Para una cuenta con contraseña propia, el código se enviará exclusivamente al correo actualmente asociado a ella, sin permitir indicar otro destinatario durante la recuperación.
4. La plataforma no permitirá restablecer la contraseña sin completar las comprobaciones requeridas por RN-029 y validar la nueva contraseña conforme a RN-028.
5. Solicitar o recibir un código no modificará la contraseña, cerrará sesiones ni bloqueará el acceso ordinario.
6. Una solicitud fallida, incompleta o no validada no modificará las credenciales ni concederá acceso a la cuenta.
7. La información pública del perfil o el conocimiento de datos vehiculares no serán suficientes por sí solos para autorizar la recuperación.
8. Los códigos y controles de recuperación permanecerán separados de los utilizados para verificar el registro o incorporar una contraseña, conforme a RN-029 y RN-031.
9. Una cuenta que utilice únicamente Google o Apple no podrá crear una contraseña propia mediante este procedimiento. La plataforma no ofrecerá modificar las credenciales del proveedor.
10. La recuperación conservará la identidad de la cuenta, sus vehículos, su historial y sus relaciones, sin crear registros duplicados.
11. La recuperación no otorgará permisos adicionales, no reactivará autorizaciones revocadas ni eliminará restricciones vigentes.
12. Una cuenta pendiente que tenga contraseña propia podrá restablecerla mientras su registro provisional se conserve, sin verificar automáticamente el correo ni ampliar el plazo de RN-027.
13. Un registro provisional cuyo plazo haya vencido no permitirá completar la recuperación y requerirá iniciar un nuevo registro.
14. Un restablecimiento exitoso invalidará las sesiones de Vehículos Services de la cuenta y los demás medios pendientes de recuperación de contraseña, conforme a RN-029, sin cerrar las sesiones del usuario en Google o Apple.
15. Después del restablecimiento, el usuario deberá iniciar sesión mediante un mecanismo habilitado y vinculado a su cuenta, sin acceso automático.
16. La plataforma enviará un aviso del cambio al correo asociado, sin incluir la contraseña ni el código. Un fallo de ese aviso no revertirá el restablecimiento.
17. Los mensajes y tiempos de respuesta no deberán revelar información restringida sobre la existencia, el estado o los métodos de acceso de una cuenta, conforme a RN-029.
18. Las solicitudes repetidas, los problemas de conexión, los errores de envío y las operaciones simultáneas se resolverán conforme a RN-029, sin duplicar cambios ni superar los límites.
19. La plataforma conservará la trazabilidad del procedimiento conforme a los controles de seguridad aplicables, sin registrar contraseñas ni códigos como parte de ese historial.
20. La primera entrega no permitirá recuperar la cuenta mediante procedimientos alternativos o asistidos que no hayan sido definidos y habilitados.

#### Definiciones posteriores relacionadas

- Documentar el caso de uso de recuperación de acceso en `casos-uso.md`.
- Detallar los mecanismos técnicos y de seguridad necesarios para implementar RN-029 y las orientaciones de recuperación de los proveedores externos.
- Definir y aprobar una recuperación asistida o mecanismos alternativos antes de incorporarlos en una entrega posterior.

---

### RF-049 — Cerrar sesión

- ID: RF-049.
- Nombre: Cerrar sesión.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Capacidad general compartida — Gestión de cuenta y acceso.
- Etapa prevista: Primera etapa del Propietario en Android e iOS; reutilizable posteriormente por el módulo del Prestador.
- Estado de la definición: Aprobado en su alcance funcional, conforme a RN-033. Los mecanismos técnicos deberán detallarse en los documentos correspondientes.
- Actor relacionado: Usuario autenticado.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: RN-033 — Cierre de sesión y protección de información local, definida en `reglas-negocio.md`; RN-029 y RN-031 para los eventos que invalidan sesiones de la cuenta; RN-032 para la revocación de autorizaciones de Apple.
- Caso de uso preliminar relacionado: Cerrar sesión; identificador y detalle pendientes en `casos-uso.md`.
- Dependencias: Sesión iniciada conforme a RF-002; mecanismos de finalización e invalidación de la sesión; tratamiento de información local conforme a RN-033; controles de RNF-003 y RNF-021, definidos en `requerimientos-no-funcionales.md`.

#### Descripción

Vehículos Services deberá permitir que el usuario cierre la sesión desde la aplicación.

Al confirmar el cierre, la aplicación deberá retirar el acceso local. Cuando se complete la invalidación en el backend, la sesión correspondiente deberá dejar de permitir nuevas consultas, acciones protegidas y renovaciones. Para acceder nuevamente a esas funcionalidades, el usuario deberá autenticarse conforme a RF-002.

El cierre deberá impedir que otro usuario del dispositivo acceda a información restringida mediante pantallas que hayan quedado abiertas o mediante la navegación hacia vistas anteriores. El tratamiento de datos privados, preferencias generales y archivos exportados se regirá por RN-033.

Si existen cambios sin guardar, la aplicación deberá advertir que se perderán y permitir cancelar el cierre. Si el usuario confirma, se descartarán sin guardarlos ni enviarlos automáticamente.

Las operaciones en curso y los resultados desconocidos se tratarán conforme a RN-033. Cerrar sesión no revertirá operaciones ya completadas en el servidor ni provocará la repetición automática de operaciones cuyo resultado no se haya confirmado.

Cerrar sesión no deberá eliminar la cuenta, sus vehículos, el historial ni las autorizaciones existentes. Tampoco deberá interpretarse como revocación de una relación con una persona jurídica o un Prestador de Servicios Vehiculares.

La acción se aplicará a la sesión desde la que se solicita. La primera entrega no incluirá una opción manual para cerrar otras sesiones o todas las sesiones de la cuenta. Se conservarán los efectos de invalidación general establecidos en RN-029 y RN-031.

Si no existe conexión o no puede confirmarse la invalidación remota, se retirará el acceso local y se informará que la invalidación en el servidor permanece pendiente. La aplicación deberá reintentarla conforme a RN-033, sin restaurar el acceso ni renovar la sesión anterior.

El tratamiento de notificaciones y el inicio de sesión con otra cuenta en el mismo dispositivo deberán cumplir RN-033, sin exponer información de la cuenta anterior.

Cuando la autenticación utilice Google o Apple, cerrar la sesión de Vehículos Services no deberá presentarse como cierre de las sesiones del proveedor ni retirar su vinculación. El cierre no deberá provocar un reingreso automático.

Este requisito tendrá una única especificación y podrá referenciarse desde `requerimientos-funcionales-prestador.md`.

#### Criterios de aceptación

1. El usuario autenticado podrá solicitar el cierre de su sesión desde la aplicación.
2. Al confirmar el cierre, se retirará el acceso local. Una vez completada la invalidación remota, la sesión no podrá utilizarse para nuevas consultas, acciones protegidas o renovaciones.
3. La navegación hacia pantallas previamente abiertas no permitirá consultar información restringida sin una nueva autenticación.
4. Cerrar sesión no eliminará la cuenta ni modificará la propiedad de vehículos, los registros históricos o las autorizaciones existentes.
5. El cierre manual no finalizará automáticamente sesiones en otros dispositivos. La primera entrega no incluirá una opción manual para cerrarlas, sin modificar los eventos de invalidación general ya aprobados.
6. La aplicación distinguirá el cierre local de la invalidación remota. Si esta última no puede confirmarse, informará que permanece pendiente y no la presentará como completada.
7. Si se utilizó Google o Apple, el cierre se identificará como correspondiente a Vehículos Services, sin afirmar que finalizó las sesiones del proveedor ni retirar su vinculación.
8. Si existen cambios sin guardar, el usuario podrá cancelar el cierre. Si lo confirma, se descartarán conforme a RN-033.
9. Las operaciones en curso y los resultados desconocidos se tratarán conforme a RN-033, sin revertir operaciones completadas ni repetir automáticamente aquellas cuyo resultado no se haya confirmado.
10. Los datos privados locales se retirarán conforme a RN-033. Los archivos exportados expresamente fuera del almacenamiento privado de la aplicación no se eliminarán como consecuencia del cierre.
11. Un cierre sin conexión retirará el acceso local y permitirá reintentar la invalidación remota conforme a RN-033, sin restaurar la sesión anterior.
12. Una cuenta que inicie sesión posteriormente en el dispositivo no podrá ver información ni continuar operaciones de la cuenta anterior.
13. La desvinculación de notificaciones y la protección de su contenido durante un estado pendiente se aplicarán conforme a RN-033.
14. Cerrar sesión no provocará un reingreso automático. Seleccionar nuevamente un proveedor constituirá una nueva acción de autenticación.

#### Definiciones posteriores relacionadas

- Documentar el caso de uso de cierre de sesión en `casos-uso.md`.
- Detallar los mecanismos técnicos de invalidación, protección de datos locales y tratamiento de operaciones conforme a RN-033.
- Definir la duración y renovación general de sesiones conforme a RNF-021, sin modificar el comportamiento aprobado del cierre manual.

---

### RF-050 — Consultar planes y suscripción del Propietario

- ID: RF-050.
- Nombre: Consultar planes y suscripción del Propietario.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Suscripciones del Propietario.
- Etapa prevista: Por definir; su inclusión en la primera implementación está pendiente de evaluación.
- Estado de la definición: Conceptual; pendiente de definir los planes, sus condiciones y el alcance de la suscripción.
- Actor relacionado: Usuario autenticado en el contexto del Propietario; usuario autorizado para consultar la suscripción de una persona jurídica cuando corresponda.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: Modelo de suscripciones y separación entre límites del plan y permisos de acceso conforme al punto 51 de `proyecto.md`; reglas específicas por documentar en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: Pendiente de incorporar a `casos-uso.md`.
- Dependencias: Definición de los planes disponibles para el Propietario; identificación del titular y alcance de la suscripción; información de su estado cuando exista; autorización de consulta.

#### Descripción

Vehículos Services deberá permitir consultar los planes disponibles para el módulo del Propietario y, cuando exista una suscripción asociada al contexto consultado, conocer su plan, estado y condiciones aplicables.

La consulta deberá distinguir las funcionalidades y límites ofrecidos por cada plan de los permisos necesarios para acceder a vehículos, registros y documentos. Disponer de una suscripción no deberá conceder propiedad, representación ni acceso a información restringida.

Los ejemplos de planes básicos o premium contenidos en el proyecto no deberán interpretarse como una oferta comercial aprobada. Los nombres, funcionalidades, límites y condiciones deberán corresponder a la definición de planes que se valide posteriormente.

Cuando el propietario sea una persona jurídica, la consulta de su suscripción podrá realizarla únicamente un usuario autorizado para ese alcance. Tener asignado un vehículo no deberá conceder automáticamente acceso a la información de suscripción de la organización.

La consulta no deberá contratar, renovar, cambiar ni cancelar una suscripción. Esas acciones requerirán una definición funcional independiente si se incorporan al alcance.

Si una persona tiene funciones de Propietario y de Prestador de Servicios Vehiculares, no deberá asumirse que una suscripción del Propietario habilita también capacidades del Prestador. Los planes propios de ese módulo se documentarán en `requerimientos-funcionales-prestador.md`.

#### Criterios de aceptación

1. El usuario podrá consultar los planes del Propietario que estén habilitados para su contexto.
2. Cada plan mostrado permitirá identificar las funcionalidades, límites y condiciones aprobadas que le correspondan.
3. Cuando exista una suscripción consultable, la plataforma mostrará su plan, estado y alcance conforme a la información disponible.
4. La ausencia de una suscripción no se interpretará automáticamente como existencia de un plan gratuito ni como prohibición de todas las funcionalidades; se aplicará la condición expresamente definida.
5. La suscripción no concederá acceso a vehículos o información para los que el usuario no tenga autorización.
6. Cuando se consulte una suscripción de una persona jurídica, el usuario deberá contar con permiso vigente para esa consulta.
7. Consultar un plan o una suscripción no modificará su estado ni iniciará automáticamente una contratación o un cobro.
8. La plataforma no presentará los ejemplos del proyecto como planes disponibles sin una definición aprobada.
9. La consulta distinguirá el alcance del Propietario del correspondiente al Prestador, sin extender automáticamente los beneficios entre ambos módulos.

#### Decisiones pendientes

- Definir los planes disponibles, sus funcionalidades, límites y condiciones comerciales.
- Definir quién será titular de la suscripción y si su alcance será por persona, organización, vehículo u otra unidad aprobada.
- Definir los estados de suscripción y la información que se mostrará para cada uno.
- Definir las funcionalidades disponibles cuando no exista suscripción o esta deje de estar vigente.
- Precisar el tratamiento de información existente cuando cambien los límites o beneficios del plan.
- Definir los permisos de consulta para personas jurídicas.
- Definir la etapa de implementación y si se incorporarán posteriormente contratación, renovación, cambio o cancelación.

---

### RF-051 — Solicitar y dar seguimiento a la revisión de un conflicto de identificación

- ID: RF-051.
- Nombre: Solicitar y dar seguimiento a la revisión de un conflicto de identificación.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Capacidad general compartida — Soporte de identidad y acceso.
- Etapa prevista: Primera entrega del Propietario, independiente del módulo del Prestador.
- Estado de la definición: Alcance funcional aprobado conforme a RN-035. Los casos de uso, controles técnicos y precisiones operativas deberán completarse antes de su implementación.
- Actores relacionados: Usuario autenticado cuya identificación está bloqueada por coincidencia de documento con otra cuenta; personal de soporte autorizado para revisar y atender la solicitud.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: RN-025 — Cuenta de usuario e identidad del propietario; RN-035 — Revisión manual de conflictos de identificación del propietario; RN-037 — Actualización de datos personales y correcciones mediante soporte, para distinguir el alcance de ambos procedimientos, definidas en `reglas-negocio.md`.
- Caso de uso preliminar relacionado: Pendiente de incorporar a `casos-uso.md`.
- Dependencias: Cuenta y autenticación conforme a RF-001 y RF-002; detección del conflicto conforme a RN-025, RF-003 y RF-043; personal de soporte autorizado; controles de comprobación adicional y protección de evidencias conforme a RN-035.

#### Descripción

Vehículos Services deberá permitir que un usuario autenticado solicite una revisión manual cuando su tipo y número de documento aparezcan asociados a otra cuenta y esa coincidencia impida completar su identificación como propietario.

Desde el mensaje de documento ocupado, el usuario podrá acceder a la opción de solicitar revisión, explicar el conflicto y adjuntar su documento de identificación y la tarjeta de propiedad del vehículo que pretende asociar.

La plataforma deberá registrar la solicitud y permitir que el usuario consulte su estado, los requerimientos de información adicional y el resultado.

El personal de soporte autorizado deberá disponer de las capacidades necesarias para consultar las solicitudes, evaluar las evidencias, solicitar información adicional y registrar su decisión conforme a RN-035. El solicitante no podrá resolver su propio caso.

La comprobación adicional incluirá una videollamada en vivo mediante un canal externo autorizado, conforme a RN-035. La aplicación deberá conservar el registro de su realización y resultado, sin exigir una funcionalidad de videollamada integrada ni grabar la sesión inicialmente.

La primera respuesta de soporte deberá emitirse dentro del plazo establecido en RN-035. Ese plazo no implicará una resolución definitiva del conflicto.

Durante la revisión, la identificación y la asociación bloqueadas permanecerán sin completar. La solicitud no modificará automáticamente la cuenta existente, sus permisos ni sus vehículos.

Cuando se autorice una corrección sobre una identificación registrada incorrectamente en una cuenta sin vehículos asociados, se aplicarán los permisos, avisos y controles de trazabilidad establecidos en RN-035.

Después de la corrección, el solicitante deberá completar nuevamente las comprobaciones normales de identificación y asociación. La aprobación de la revisión no asociará automáticamente el vehículo.

Los conflictos entre cuentas cuya corrección afectaría a una cuenta con vehículos asociados no se resolverán mediante esta revisión ordinaria. Se tratarán conforme a los límites y al procedimiento especial pendiente de RN-035.

La revisión no permitirá fusionar cuentas, cambiar contraseñas, vincular métodos de acceso, transferir vehículos ni eliminar o reatribuir historiales.

Esta capacidad deberá mantenerse diferenciada de las solicitudes de corrección de errores de captura previstas en RN-037. No constituirá un procedimiento general para corregir el correo, los datos personales o los datos obligatorios del vehículo.

La posibilidad de contactar a soporte sin iniciar sesión conforme a RN-037 no sustituirá la autenticación ni las comprobaciones requeridas para la revisión de conflictos de este requerimiento.

Si una solicitud de corrección revela un conflicto de documento entre cuentas, se aplicarán RN-025 y RN-035 con sus límites. No se utilizará RN-037 para eludir esas condiciones.

Esta revisión tampoco autorizará cambios de placa, VIN u otros datos del vehículo para resolver conflictos vehiculares.

Esta capacidad deberá estar disponible desde la primera entrega del Propietario sin depender del módulo del Prestador de Servicios Vehiculares.

#### Criterios de aceptación

1. El usuario autenticado podrá acceder a la solicitud de revisión desde el mensaje de documento ocupado que bloquea su identificación como propietario.
2. La solicitud deberá incluir una explicación del conflicto, el documento de identificación y la tarjeta de propiedad del vehículo, conforme a RN-035.
3. La plataforma registrará la solicitud y la vinculará con la cuenta del solicitante y el conflicto correspondiente.
4. El usuario podrá consultar el estado de su solicitud conforme a los estados definidos en RN-035.
5. Cuando soporte requiera información adicional, el usuario podrá consultar lo solicitado y aportar la información correspondiente.
6. El solicitante no podrá consultar información privada de la otra cuenta ni resolver su propio caso.
7. Únicamente el personal autorizado podrá consultar las evidencias, registrar decisiones y ejecutar las correcciones permitidas.
8. La revisión aplicará la comprobación adicional establecida en RN-035. Recibir archivos no bastará por sí solo para aprobar una corrección.
9. Se registrarán la realización y el resultado de la videollamada, sin grabarla inicialmente ni exigir su integración dentro de la aplicación.
10. La primera respuesta de soporte se emitirá dentro del plazo de RN-035, conforme al calendario operativo que se defina.
11. Mientras el conflicto permanezca sin resolver, la identificación y la asociación solicitadas no se completarán.
12. Una aprobación identificará la corrección autorizada y respetará el límite de que la cuenta cuya identificación se corrige no tenga vehículos asociados.
13. La corrección se ejecutará con permisos específicos y conservará responsable, motivo, evidencias consideradas y cambios realizados, conforme a RN-035.
14. Cuando se proponga una corrección sobre una cuenta existente, se aplicará el aviso previsto en RN-035 sin compartir datos privados del solicitante.
15. Una aprobación no asociará automáticamente el vehículo. El usuario deberá completar nuevamente las comprobaciones normales.
16. Un rechazo mostrará una explicación que no revele información privada de la otra cuenta.
17. La solicitud y su revisión no fusionarán cuentas, cambiarán credenciales, vincularán métodos de acceso, transferirán vehículos ni eliminarán o reatribuirán historiales.
18. Un conflicto que requiera el procedimiento especial para cuentas con vehículos asociados no se presentará como resuelto mediante esta revisión ordinaria.
19. Los archivos y registros del caso tendrán acceso restringido y cumplirán las condiciones de protección y conservación que se definan conforme a RN-035.
20. La disponibilidad de esta capacidad no dependerá de la implementación del módulo del Prestador.
21. Las solicitudes de corrección de errores de captura de RN-037 conservarán su procedimiento independiente. No ampliarán los permisos de esta revisión ni sustituirán sus condiciones de autenticación y comprobación cuando exista un conflicto entre cuentas.
22. La revisión no permitirá modificar placa, VIN u otros datos del vehículo para resolver conflictos vehiculares.

#### Definiciones posteriores relacionadas

- Documentar los casos de uso del solicitante y del personal de soporte.
- Detallar las pantallas, estados de interacción y presentación de resultados.
- Concretar los permisos y la designación del personal de soporte.
- Definir los controles de comprobación adicional y el canal autorizado de videollamada.
- Precisar las transiciones de estado y los recorridos de solicitud y entrega de información adicional.
- Concretar el calendario operativo y el seguimiento del plazo de primera respuesta.
- Detallar los avisos, la ejecución de correcciones y el tratamiento de fallos.
- Definir la protección, conservación y eliminación de los archivos y registros del caso.
- Mantener identificadas las limitaciones del procedimiento especial todavía pendiente en RN-035.
- Detallar la clasificación y derivación de solicitudes entre la revisión de conflictos de RN-035 y las correcciones de errores de captura de RN-037, respetando las condiciones de cada procedimiento.

---
### RF-052 — Solicitar la corrección de datos mediante soporte

- ID: RF-052.
- Nombre: Solicitar la corrección de datos mediante soporte.
- Tipo: Requerimiento funcional.
- Módulo o capacidad: Capacidad general compartida — Soporte para corrección de datos de cuenta, propietario y vehículo.
- Etapa prevista: Primera entrega del Propietario.
- Estado de la definición: Alcance general, condiciones iniciales de comprobación y plazo de primera respuesta aprobados conforme a RN-037. Pendientes los controles específicos, los recorridos, los permisos de ejecución y los detalles operativos y técnicos necesarios para habilitar el procedimiento.
- Actores relacionados: Persona que solicita corregir datos de su cuenta o identidad; propietario que solicita corregir datos obligatorios de su vehículo; personal de soporte autorizado.
- Prioridad: Por definir.
- Reglas de negocio relacionadas: RN-025 — Cuenta de usuario e identidad del propietario; RN-027 — Verificación del correo en el registro propio; RN-035 — Revisión manual de conflictos de identificación del propietario; RN-036 — Identificación, coincidencias y comparación documental del vehículo; RN-037 — Actualización de datos personales y correcciones mediante soporte.
- Requerimientos relacionados: RF-001 — Crear cuenta de usuario; RF-003 — Agregar vehículo como propietario; RF-043 — Gestionar el perfil personal del usuario; RF-046 — Actualizar información general del vehículo; RF-051 — Solicitar y dar seguimiento a la revisión de un conflicto de identificación.
- Caso de uso preliminar relacionado: Pendiente de incorporar a `casos-uso.md`.
- Dependencias: Canal de soporte disponible; personal autorizado; controles y evidencias definidos para cada tipo de corrección; mecanismos de ejecución, protección de información y trazabilidad conforme a RN-037; calendario operativo para verificar el plazo de primera respuesta.

#### Descripción

Vehículos Services deberá informar al usuario cómo solicitar a soporte la corrección de datos que no puede editar directamente, conforme a RN-037.

Esta capacidad comprenderá las solicitudes de corrección de errores de captura en:

- Correo electrónico de la cuenta.
- Nombres y apellidos.
- Tipo y número de documento de identificación.
- Datos obligatorios aplicables del vehículo.

La aplicación deberá mostrar el correo de soporte vigente y la condición de que el asunto comience con `Soporte App`, conforme a RN-037. Esa regla conservará la definición principal del canal y su dirección inicial.

Las indicaciones de contacto deberán estar disponibles durante el registro pendiente y desde las secciones correspondientes de cuenta, perfil e información del vehículo.

Si el error impide verificar el correo o iniciar sesión, el solicitante deberá poder consultar las indicaciones y comunicarse con soporte sin acceder a una cuenta habilitada.

La solicitud se tramitará inicialmente por correo electrónico. Este requerimiento no establecerá por sí mismo un sistema de solicitudes y seguimiento dentro de la aplicación.

Soporte deberá comprobar la vinculación del solicitante con la cuenta o el vehículo afectado, evaluar el error y aplicar las verificaciones correspondientes antes de autorizar una corrección.

Enviar un correo no será suficiente para autorizar cambios, verificar una cuenta, habilitar acceso o establecer propiedad.

Cuando se solicite corregir el correo de la cuenta y el solicitante pueda autenticarse, se comprobará su acceso mediante la aplicación y el control del nuevo correo antes de ejecutar el cambio. Esta comprobación no permitirá que el usuario edite directamente el correo.

Si el solicitante no puede autenticarse, soporte realizará una revisión adicional de la información disponible conforme a RN-037. Si no permite vincularlo suficientemente con la cuenta, no se ejecutará la corrección. En un registro sin datos de identidad ni vehículos, presentar un documento de identificación no demostrará por sí solo esa vinculación.

Si la cuenta permanece pendiente de verificación, se respetará adicionalmente RN-027. La corrección por soporte no sustituirá la verificación requerida para habilitarla.

Para corregir nombres, apellidos, tipo o número de documento, se revisará el documento de identidad y se realizará una comprobación adicional mediante videollamada conforme a RN-037. Las correcciones deberán conservar la identidad de la persona y respetar la unicidad establecida en RN-025.

Para corregir datos obligatorios del vehículo, se revisarán la tarjeta de propiedad, la relación del solicitante con el vehículo y la información existente necesaria para sustentar que se trata del mismo vehículo.

Las correcciones de datos del vehículo deberán conservar su identificador interno y respetar RN-036. Si afectan la placa o el VIN, deberán repetirse las búsquedas de coincidencias y las comparaciones aplicables antes de aceptar el cambio.

Únicamente el personal autorizado podrá ejecutar una corrección aprobada, mediante los mecanismos que se definan. La modificación conservará los valores anteriores y nuevos y la trazabilidad establecida en RN-037.

La primera respuesta de soporte deberá emitirse en un máximo de tres días hábiles desde la recepción de la solicitud, conforme al calendario operativo que se defina. Ese plazo no implicará una resolución definitiva.

Se comunicará al solicitante si la corrección fue aprobada, rechazada o requiere información adicional, sin revelar datos privados de terceros. Una aprobación no se presentará como una modificación ejecutada hasta que el cambio se haya completado.

Si la solicitud revela un conflicto de identificación entre cuentas, se aplicarán RN-025, RN-035 y RF-051 con sus condiciones y límites.

Este procedimiento no permitirá fusionar cuentas o vehículos, sustituir identidades, transferir propiedad ni resolver los conflictos vehiculares previstos para una entrega posterior.

#### Criterios de aceptación

1. La aplicación mostrará el correo de soporte vigente y la instrucción de comenzar el asunto con `Soporte App`, conforme a RN-037.
2. Las indicaciones estarán disponibles desde el registro pendiente y las secciones correspondientes de cuenta, perfil e información del vehículo.
3. Consultar las indicaciones y solicitar ayuda por un correo incorrecto no requerirá iniciar sesión ni verificar ese correo.
4. La solicitud inicial se tramitará mediante correo electrónico. La aplicación no presentará la solicitud como recibida o atendida únicamente por mostrar las instrucciones o facilitar la preparación del mensaje.
5. El canal publicado podrá actualizarse cuando se establezca un correo propio de soporte, manteniendo su correspondencia con RN-037.
6. El usuario no podrá editar ni eliminar directamente los datos bloqueados por RN-037 mediante esta funcionalidad.
7. Recibir una solicitud no modificará automáticamente datos ni concederá acceso, propiedad o permisos adicionales.
8. Antes de ejecutar una corrección, soporte deberá comprobar la vinculación del solicitante con la cuenta o el vehículo y aplicar las verificaciones aprobadas para el dato afectado.
9. No se solicitarán contraseñas ni códigos de verificación como evidencias para soporte. Las comprobaciones que los requieran se realizarán mediante los mecanismos autorizados de la plataforma, sin comunicarlos al personal de soporte.
10. La corrección de un correo durante el registro propio pendiente conservará la misma cuenta y respetará los controles, la verificación y el plazo de conservación de RN-027. Contactar a soporte no reiniciará esos tiempos.
11. Las correcciones de identificación personal no sustituirán a una persona por otra ni permitirán utilizar un tipo y número de documento ya asociados a otra cuenta.
12. Las correcciones de datos vehiculares conservarán la identidad interna y el historial. Si afectan placa o VIN, se repetirán las búsquedas de coincidencias y las comparaciones aplicables conforme a RN-036.
13. Únicamente el personal autorizado podrá ejecutar las correcciones aprobadas. Se conservarán los valores anteriores y nuevos, el motivo, las comprobaciones, el responsable y la fecha y hora, conforme a RN-037.
14. La corrección no reescribirá automáticamente la procedencia ni el contenido de los registros históricos.
15. Si se detecta un conflicto de identificación entre cuentas, se aplicarán RN-035 y RF-051 sin ampliar sus permisos ni omitir sus comprobaciones.
16. La solicitud no permitirá fusionar cuentas o vehículos, transferir propiedad ni resolver conflictos vehiculares excluidos de la primera entrega.
17. El celular de contacto conservará su actualización directa, sin poder eliminarlo ni dejarlo vacío mientras sea obligatorio. La ciudad de residencia y la fotografía de perfil conservarán su gestión opcional directa conforme a RF-043 y RN-037, sin exigir soporte para actualizarlas.
18. Las solicitudes y evidencias cumplirán las condiciones de acceso, protección y conservación que se definan antes de habilitar el procedimiento.
19. Para corregir el correo cuando el solicitante pueda autenticarse, se comprobarán el acceso a la cuenta mediante la aplicación y el control del nuevo correo antes de ejecutar el cambio. El usuario no obtendrá por ello permiso para editar directamente el correo.
20. Cuando el solicitante no pueda autenticarse, se realizará la revisión adicional prevista en RN-037. Si las evidencias no permiten vincularlo suficientemente con la cuenta, no se ejecutará la corrección. Presentar un documento de identidad no bastará por sí solo para vincularlo con un registro que todavía no tenga datos de identidad ni vehículos.
21. Las correcciones de nombres, apellidos, tipo o número de documento incluirán la revisión del documento de identidad y una comprobación adicional mediante videollamada, aplicando los controles específicos que se definan conforme a RN-037.
22. Las correcciones de datos obligatorios del vehículo incluirán la revisión de la tarjeta de propiedad, de la relación del solicitante con el vehículo y de la información existente necesaria para sustentar que se trata del mismo vehículo.
23. La primera respuesta de soporte se emitirá en un máximo de tres días hábiles desde la recepción de la solicitud, conforme al calendario operativo definido. Este plazo no se presentará como una garantía de resolución definitiva.
24. Se comunicará si la corrección fue aprobada, rechazada o requiere información adicional, sin revelar datos privados de terceros. La aprobación no se presentará como un cambio ejecutado hasta que la modificación se haya completado.

#### Definiciones posteriores relacionadas

- Documentar los casos de uso de solicitud, evaluación y ejecución de correcciones.
- Detallar las indicaciones de contacto y su presentación cuando el usuario no pueda iniciar sesión.
- Detallar la información inicial necesaria para cada solicitud, las evidencias admitidas y los controles específicos de comprobación por tipo de dato, respetando RN-037.
- Definir el mecanismo para comprobar el acceso a la cuenta mediante la aplicación sin exponer credenciales al personal de soporte.
- Detallar la revisión adicional para solicitudes sin acceso disponible, incluyendo registros sin datos de identidad ni vehículos.
- Definir el mecanismo de comprobación del control del nuevo correo y los efectos de la corrección sobre autenticación, recuperación y sesiones.
- Detallar el canal de videollamada y los controles de comprobación de identidad y validación documental.
- Precisar las correcciones admitidas de datos personales y vehiculares, manteniendo los límites de RN-025, RN-035, RN-036 y RN-037.
- Definir los permisos y mecanismos para ejecutar las correcciones autorizadas.
- Detallar el seguimiento operativo de solicitudes y la comunicación de resultados, sin asumir un seguimiento integrado en la aplicación.
- Concretar el calendario, horario, zona horaria y forma de contabilizar los días hábiles para verificar el plazo de primera respuesta aprobado en RN-037.
- Establecer la protección, conservación y eliminación de solicitudes y evidencias.
- Detallar la trazabilidad y las comprobaciones posteriores a las correcciones.

---

## 4. Alcance de la primera entrega del Propietario

### 4.1 Tipos de propietario incluidos

La primera entrega del módulo del Propietario atenderá a personas naturales que gestionen vehículos de su propia propiedad, previa comparación de sus datos declarados con la tarjeta de propiedad y cumplimiento de las demás condiciones de asociación aplicables, conforme a RN-025 y RF-003. Esta comparación no constituirá una comprobación independiente de la identidad real del usuario ni de la autenticidad o vigencia de la tarjeta de propiedad.

Para esta primera entrega, únicamente se admitirán vehículos y documentos de Colombia.

Una persona natural podrá tener uno o varios vehículos asociados a su nombre. La propiedad de cada vehículo deberá validarse individualmente.

Dentro del alcance actualmente definido, esta entrega no habilitará la delegación de la administración de vehículos de una persona natural a otros usuarios.

Las capacidades generales necesarias para el funcionamiento del Propietario se incluirán según el alcance funcional que se acuerde para esta entrega.

El registro de personas jurídicas como propietarias, la validación de sus representantes y la gestión de sus usuarios autorizados se incorporarán en una entrega posterior del módulo del Propietario. RF-042 y RF-041 permanecerán documentados con sus identificadores originales.

Las condiciones de representación de personas jurídicas presentes en otros requerimientos se conservarán para esa entrega posterior y no constituirán una dependencia obligatoria de la primera entrega.

La primera entrega deberá funcionar de manera independiente del módulo del Prestador de Servicios Vehiculares. Las capacidades de autorización, revocación y consulta de relaciones con prestadores correspondientes a RF-013, RF-014 y RF-047 se habilitarán en la etapa de integración.

Una persona natural que también sea prestador de servicios podrá utilizar las capacidades del Propietario para gestionar sus propios vehículos. Esto no habilitará anticipadamente las funcionalidades del Prestador ni otorgará permisos adicionales sobre vehículos ajenos.

Esta definición establece los tipos de propietario incluidos. La selección de funcionalidades de la primera entrega se establecerá en los puntos siguientes.

Las tecnologías y la arquitectura se definirán en el documento correspondiente antes de iniciar la implementación.


---

### 4.2 Funcionalidades propuestas para la primera entrega

La primera entrega deberá permitir que un propietario persona natural registre sus vehículos, gestione la información asociada y consulte el seguimiento de sus mantenimientos, sin depender del módulo del Prestador de Servicios Vehiculares.

La siguiente selección constituye una propuesta de alcance funcional. Su aprobación no resolverá automáticamente las decisiones pendientes de cada requerimiento ni sustituirá las definiciones de reglas de negocio, casos de uso, arquitectura y diseño necesarias antes de implementarlo.

#### Cuenta, identidad y acceso

Se propone incluir:

- RF-001 — Crear cuenta de usuario.
- RF-002 — Iniciar sesión.
- RF-043 — Gestionar el perfil personal del usuario.
- RF-048 — Recuperar acceso a la cuenta.
- RF-049 — Cerrar sesión.
- RF-051 — Solicitar y dar seguimiento a la revisión de un conflicto de identificación.
- RF-052 — Solicitar la corrección de datos mediante soporte.

Los mecanismos de registro, autenticación, recuperación, gestión de métodos y sesiones deberán respetar las condiciones aprobadas en RN-026 a RN-034. Los datos declarados necesarios para comparar al propietario con la tarjeta de propiedad deberán estar disponibles antes de completar la asociación de un vehículo, conforme a RN-025.

La revisión manual de conflictos de identificación se incluirá desde la primera entrega conforme a RN-035 y RF-051. Requerirá personal de soporte autorizado y los controles de comprobación adicional correspondientes, sin depender del módulo del Prestador ni asociar vehículos automáticamente.

El celular de contacto será obligatorio para completar la información del propietario antes de asociar su primer vehículo, sin exigirlo para crear inicialmente la cuenta. El usuario podrá actualizarlo directamente, pero no eliminarlo ni dejarlo vacío mediante una actualización aceptada. La ciudad de residencia y la fotografía de perfil serán opcionales y podrán agregarse, actualizarse o retirarse conforme a RN-037 y RF-043. El correo de la cuenta y los datos de identidad confirmados y guardados no podrán editarse ni eliminarse directamente por el usuario.

Las solicitudes de corrección de errores de captura se atenderán mediante soporte conforme a RN-037 y RF-052, incluyendo los casos en que un correo incorrecto impida verificar la cuenta o iniciar sesión. Este procedimiento se mantendrá separado de la revisión de conflictos entre cuentas de RN-035 y RF-051. Su inclusión requerirá completar las verificaciones, permisos y mecanismos operativos y técnicos correspondientes antes de habilitarlo.

#### Gestión de vehículos y kilometraje

Se propone incluir:

- RF-003 — Agregar vehículo como propietario.
- RF-004 — Consultar vehículos propios.
- RF-005 — Actualizar kilometraje del vehículo.
- RF-046 — Actualizar información general del vehículo.

La asociación deberá validar la propiedad de cada vehículo. Las modificaciones de información general no deberán permitir sustituir su identidad ni transferir su propiedad.

Después de confirmar, aceptar y guardar el registro definitivo, los datos obligatorios aplicables del vehículo no podrán editarse ni eliminarse directamente por el propietario. Sus errores de captura se tramitarán mediante soporte conforme a RN-036, RN-037 y RF-052. Esta corrección no habilitará la revisión especial de conflictos vehiculares ni la transferencia de propiedad previstas para entregas posteriores.

La actualización del kilometraje continuará mediante nuevos registros conforme a RF-005, sin sobrescribir la lectura inicial ni las anteriores desde la información general del vehículo.

#### Intervenciones, repuestos e historial

Se propone incluir:

- RF-006 — Registrar mantenimiento realizado.
- RF-008 — Registrar reparación realizada.
- RF-009 — Registrar repuesto.
- RF-007 — Consultar historial vehicular.
- RF-038 — Corregir un registro histórico.
- RF-039 — Completar información faltante de un registro histórico.
- RF-040 — Anular un registro histórico.

Los mantenimientos y las reparaciones se conservarán como registros independientes. Cuando correspondan a una misma visita o intervención relacionada, esa vinculación no deberá duplicar actividades ni costos.

Las operaciones sobre registros históricos deberán respetar los permisos aplicables y conservar la trazabilidad definida en sus requerimientos.

El propietario podrá registrar intervenciones realizadas por sí mismo o por terceros conforme a las reglas correspondientes, sin exigir que esos terceros estén registrados como prestadores en la plataforma.

#### Documentos y costos

Se propone incluir:

- RF-010 — Adjuntar documento o evidencia.
- RF-044 — Registrar costos asociados a intervenciones y repuestos.
- RF-045 — Consultar costos de intervenciones y repuestos.

Los archivos deberán contar con los controles de acceso y procesamiento correspondientes. Los costos deberán distinguir totales y componentes para evitar sumarlos más de una vez.

#### Seguimiento de mantenimientos

Se propone incluir:

- RF-033 — Establecer una regla de seguimiento para una actividad de mantenimiento.
- RF-034 — Modificar una regla de seguimiento.
- RF-011 — Consultar próximos mantenimientos.
- RF-035 — Renovar el ciclo de seguimiento de una actividad.

Antes de implementar este bloque deberán definirse el origen de las reglas, quién podrá establecerlas o modificarlas y cómo se obtendrán las referencias válidas.

La falta de información suficiente no deberá producir objetivos inventados. Registrar una intervención y evaluar su efecto sobre el seguimiento serán comportamientos relacionados, con las condiciones particulares definidas para cada uno.

#### Alertas, recomendaciones y notificaciones

Se propone incluir:

- RF-012 — Consultar alertas.
- RF-018 — Consultar recomendaciones.
- RF-037 — Configurar preferencias de notificación.
- RF-036 — Recibir notificaciones.

Se habilitarán únicamente los tipos de alerta, recomendación y comunicación cuyas reglas, datos necesarios y condiciones de funcionamiento hayan sido definidos y aprobados.

Antes de implementar las notificaciones deberán establecerse los canales incluidos, destinatarios, preferencias y reglas de envío.

#### Condiciones de la propuesta

Los bloques anteriores representan capacidades funcionales de la entrega y no un orden obligatorio de pantallas ni una secuencia estrictamente lineal de desarrollo.

Los requerimientos no funcionales aplicables deberán incorporarse durante el diseño, desarrollo y validación de cada bloque. Sus objetivos y condiciones pendientes deberán concretarse antes de verificar el cumplimiento de la entrega.

Los requerimientos no incluidos en esta selección permanecerán en el documento. Su ubicación en entregas posteriores deberá acordarse expresamente.

La selección propuesta deberá contrastarse con la viabilidad técnica y la capacidad de trabajo antes de cerrar el alcance y elaborar el plan definitivo de implementación.

---

### 4.3 Funcionalidades previstas para entregas posteriores

Las siguientes capacidades permanecerán dentro del proyecto, pero no formarán parte del alcance inicial establecido en 4.2.

Su aplazamiento no implicará eliminar sus requerimientos, modificar sus identificadores ni considerarlos implementados. Las decisiones pendientes deberán resolverse antes de desarrollar la entrega correspondiente.

#### Abastecimiento, recarga y métricas

Se contemplarán para una entrega posterior del Propietario:

- RF-029 — Registrar abastecimiento o recarga del vehículo.
- RF-030 — Consultar consumo y rendimiento del vehículo.
- RF-031 — Consultar gastos de abastecimiento y recarga.
- RF-032 — Consultar métricas de abastecimiento por períodos.

El registro de abastecimientos o recargas deberá estar disponible antes de obtener resultados que dependan de sus datos. Las reglas de cálculo deberán distinguir fuentes de energía, unidades, información incompleta y condiciones necesarias para obtener cada indicador.

#### Preparación de viajes

Se contemplarán para una entrega posterior del Propietario:

- RF-021 — Registrar viaje para su preparación.
- RF-022 — Registrar destino de viaje.
- RF-023 — Registrar distancia estimada del viaje.
- RF-024 — Consultar preparación para viaje.
- RF-025 — Generar checklist previo al viaje.
- RF-026 — Consultar recomendaciones previas al viaje.
- RF-027 — Identificar mantenimientos pendientes antes del viaje.
- RF-028 — Registrar resultado de revisión previa al viaje.

Estas capacidades utilizarán la información y las reglas aplicables del vehículo. La evaluación de mantenimientos durante el recorrido dependerá de las condiciones de seguimiento y de una distancia estimada válida cuando corresponda.

#### Reportes vehiculares

Se contemplará para una entrega posterior del Propietario:

- RF-019 — Generar reporte vehicular.

Antes de implementarlo deberán definirse su contenido, formato, permisos y tratamiento de información incompleta o restringida.

#### Transferencia de propiedad

Se contemplará para una entrega posterior del Propietario:

- RF-020 — Transferir vehículo a un nuevo propietario.

Antes de implementarlo deberán resolverse las condiciones de autorización, aceptación, validación del nuevo propietario y conservación de los períodos de propiedad.

Durante la primera entrega, agregar o actualizar un vehículo no deberá utilizarse como mecanismo alternativo para transferir su propiedad. Cuando exista una relación de propiedad vigente con otro propietario, la asociación solicitada permanecerá sin completar, conforme a RN-036 y RF-003.

#### Revisión especial de conflictos vehiculares

Se contemplará para una entrega posterior el procedimiento especial de revisión y resolución de conflictos vehiculares previsto en RN-036.

Su definición deberá abordar las coincidencias contradictorias entre vehículos existentes y las diferencias entre los identificadores registrados y los obtenidos de una tarjeta de propiedad que impliquen conflictos entre identidades vehiculares o relaciones de propiedad, incluyendo las autorizaciones, evidencias, cambios permitidos y conservación de la identidad e historial del vehículo.

Esta capacidad todavía no tendrá un requerimiento funcional independiente definido. Su especificación e identificación deberán establecerse cuando se desarrolle el alcance de la entrega correspondiente.

Durante la primera entrega, el usuario podrá corregir los datos de su solicitud que todavía no hayan sido aceptados y guardados como información definitiva, o presentar una nueva captura y repetir las comprobaciones conforme a RN-036 y RF-003. Si persiste un conflicto que requiera la revisión especial, la asociación permanecerá sin completar.

Las correcciones de errores de captura mediante soporte conforme a RN-037 y RF-052 sí formarán parte de la primera entrega. Su inclusión no habilitará la revisión especial de conflictos vehiculares ni permitirá fusionar vehículos, sustituir su identidad o transferir su propiedad.

La revisión de conflictos de identificación del propietario prevista en RN-035 y RF-051 también formará parte de la primera entrega, dentro de sus límites aprobados. No permitirá resolver conflictos vehiculares ni autorizar cambios de placa, VIN o propiedad.

#### Personas jurídicas y usuarios autorizados

Se contemplarán para una entrega posterior del Propietario:

- RF-042 — Registrar una persona jurídica como propietaria.
- RF-041 — Gestionar usuarios autorizados de una persona jurídica propietaria.

Su incorporación requerirá definir la validación del primer representante, las facultades de administración y los permisos sobre vehículos y acciones.

También deberán habilitarse y verificarse las condiciones de representación previstas en los demás requerimientos que formen parte de esa entrega.

#### Planes y suscripciones

Se contemplará para una entrega posterior del Propietario:

- RF-050 — Consultar planes y suscripción del Propietario.

Su implementación dependerá de la definición de los planes, el titular, el alcance de la suscripción y los estados aplicables.

La primera entrega no deberá incorporar restricciones comerciales basadas en planes todavía sin definir. Los controles de propiedad, identidad y autorización serán independientes de las suscripciones.

#### Integración con el Prestador de Servicios Vehiculares

Se contemplarán para la etapa de integración:

- RF-013 — Autorizar Prestador de Servicios Vehiculares para un vehículo.
- RF-014 — Revocar acceso de un Prestador de Servicios Vehiculares.
- RF-047 — Consultar prestadores relacionados con un vehículo.

Su implementación requerirá las capacidades correspondientes del Prestador y las reglas de relación, permisos y visibilidad entre ambos módulos.

La primera entrega del Propietario no dependerá de estas funcionalidades para registrar intervenciones realizadas por terceros.

#### Organización de las entregas posteriores

El orden de presentación de estos grupos no establece su prioridad ni obliga a implementarlos en una misma entrega.

Su secuencia se acordará considerando valor para el usuario, dependencias, viabilidad técnica y capacidad de trabajo.

Cualquier incorporación de estas capacidades a la primera entrega requerirá actualizar expresamente su alcance y revisar las dependencias y condiciones de aceptación afectadas.


---

### 4.4 Decisiones necesarias para concretar la primera entrega

La selección funcional de 4.2 deberá completarse con las decisiones necesarias para diseñar, implementar y verificar sus requerimientos.

Este punto organizará dichas decisiones por sus dependencias. Las listas específicas permanecerán en cada RF y RNF, evitando duplicar su definición.

Cada decisión deberá quedar documentada en el documento correspondiente y vinculada con los requerimientos afectados. No deberá considerarse resuelta únicamente porque exista una propuesta o porque una tecnología permita determinado comportamiento.

#### Identidad, acceso y propiedad

Las condiciones funcionales de registro, verificación del correo, contraseña propia, recuperación, autenticación mediante Google y Apple, gestión de métodos de acceso, cierre de sesión y vigencia de sesiones están aprobadas en RN-026 a RN-034 de `reglas-negocio.md`. Sus casos de uso y mecanismos técnicos deberán detallarse respetando esas condiciones.

También están definidos en RN-025 los nombres, apellidos, tipo y número de documento que se solicitarán cuando el usuario vaya a asociar su primer vehículo. La primera entrega admitirá únicamente vehículos y documentos de Colombia y comparará los datos declarados con la tarjeta de propiedad, sin realizar una comprobación independiente de la identidad real del usuario.

Los documentos de identificación admitidos, los criterios de comparación del propietario y la unicidad de su cuenta están aprobados en RN-025. El bloqueo de edición y eliminación directa del correo y de los datos de identidad confirmados y guardados se establece en RN-025 y RN-037. Su desarrollo deberá respetar esas condiciones, sin presentarlas nuevamente como decisiones pendientes.

El celular de contacto será obligatorio para completar la información del propietario antes de asociar su primer vehículo, sin exigirlo para crear inicialmente la cuenta. Podrá actualizarse directamente, pero no eliminarse ni dejarse vacío mediante una actualización aceptada. La ciudad de residencia y la fotografía de perfil serán opcionales y editables conforme a RN-037 y RF-043. La dirección exacta de residencia no se solicitará inicialmente. Permanecen pendientes las validaciones y los detalles de interacción correspondientes.

Las condiciones iniciales de identificación del vehículo, detección de coincidencias por placa y VIN, normalización y comparación documental están aprobadas en RN-036. El propietario deberá ingresar el VIN y comprobarse su correspondencia con la tarjeta de propiedad. El número de chasis y el número de motor serán información complementaria opcional y su ausencia, falta de ingreso o imposibilidad de lectura no impedirán por sí solas completar el registro o la asociación.

También están aprobadas en RN-036 las condiciones de validación básica de captura, mensajes, corrección de datos de la solicitud, repetición de comprobaciones y tratamiento inicial de inconsistencias. Después de confirmar y guardar el registro definitivo, los datos obligatorios del vehículo no podrán editarse ni eliminarse directamente por el propietario, conforme a RN-037.

Las correcciones de errores de captura mediante soporte formarán parte de la primera entrega conforme a RN-037 y RF-052. Están aprobados el canal inicial, las restricciones, la clasificación de datos, las condiciones iniciales de comprobación por tipo de corrección y el plazo máximo de tres días hábiles para la primera respuesta, sin garantía de resolución definitiva en ese plazo.

Para corregir el correo cuando el solicitante pueda autenticarse, se comprobarán el acceso a la cuenta mediante la aplicación y el control del nuevo correo. Si no puede autenticarse, se realizará la revisión adicional prevista en RN-037 y no se ejecutará la corrección cuando no pueda sustentarse suficientemente su vinculación con la cuenta. Las correcciones de identidad incluirán revisión documental y comprobación adicional mediante videollamada; las vehiculares, las comprobaciones documentales y de correspondencia previstas en esa regla. Permanecen pendientes los controles específicos y los mecanismos operativos y técnicos necesarios para aplicar estas condiciones.

Si persiste un conflicto que requiera la revisión especial de conflictos vehiculares, la asociación permanecerá sin completar conforme a RN-036. Esa revisión especial, la transferencia de propiedad y la validación avanzada de patrones por categoría se desarrollarán posteriormente y no condicionarán la primera entrega.

La revisión manual ordinaria de conflictos de identificación está aprobada para la primera entrega conforme a RN-035 y RF-051. Incluye una comprobación adicional de identidad y conserva los límites definidos para las correcciones sobre cuentas sin vehículos asociados. Su alcance permanecerá diferenciado de las correcciones de errores de captura de RN-037 y RF-052.

Antes de cerrar los recorridos de registro, autenticación y asociación de vehículos, deberán definirse:

- Los casos de uso y mecanismos técnicos de registro, autenticación, recuperación, gestión de métodos de acceso y cierre y vigencia de sesiones, conforme a las reglas aprobadas.
- Las validaciones de formato y los mecanismos técnicos de comprobación de los datos personales declarados, respetando los campos, documentos admitidos, criterios de comparación y momento de solicitud establecidos en RN-025.
- Las validaciones y los recorridos de ingreso y actualización del celular de contacto obligatorio y de gestión de la ciudad y fotografía de perfil opcionales, conforme a RN-037 y RF-043.
- La implementación técnica de la validación básica de placa y VIN aprobada en RN-036, las validaciones correspondientes a los datos complementarios cuando el propietario decida incorporarlos y las de los demás datos obligatorios según el tipo de vehículo, respetando el carácter opcional del número de chasis y del número de motor. La validación avanzada de patrones por categoría se desarrollará posteriormente y no se considerará parte de la validación básica inicial.
- Los recorridos y mecanismos técnicos de comparación documental, aplicando las condiciones aprobadas en RN-025 y RN-036 y completando sus precisiones pendientes, conforme a RF-003.
- Los recorridos y mecanismos técnicos para aplicar el tratamiento aprobado de vehículos existentes, coincidencias, información contradictoria y validaciones inconclusas, conforme a RN-025, RN-036 y RF-003.
- Las evidencias admitidas y los controles específicos para aplicar las comprobaciones de corrección mediante soporte aprobadas en RN-037 y RF-052, incluyendo correo incorrecto, falta de acceso a la cuenta y correcciones de datos personales o vehiculares.
- Los mecanismos para comprobar el acceso a la cuenta mediante la aplicación y el control del nuevo correo, sin exponer contraseñas ni códigos al personal de soporte.
- Los permisos, mecanismos de ejecución, trazabilidad, seguimiento operativo y comunicación de resultados de las correcciones mediante soporte, sin asumir un sistema de seguimiento integrado en la aplicación.
- Los efectos de una corrección de correo sobre autenticación, recuperación y sesiones, y las comprobaciones posteriores necesarias cuando una corrección afecte datos utilizados para validar identidad o información vehicular.
- La designación y capacitación de soporte, los controles de comprobación adicional, los canales de videollamada y la protección de evidencias necesarios para los procedimientos de RN-035 y RN-037.
- El calendario, horario, zona horaria y forma de contabilizar los días hábiles para verificar los plazos de primera respuesta establecidos en RN-035 y RN-037.
- La clasificación y derivación de solicitudes entre la revisión de conflictos de RN-035 y las correcciones de RN-037, sin ampliar los permisos ni omitir las comprobaciones de cada procedimiento.
- Los permisos y condiciones de acceso a cada operación y recurso.

Estas decisiones afectarán principalmente a RF-001, RF-002, RF-003, RF-043, RF-048, RF-049, RF-051 y RF-052, además de los controles de acceso y sesiones correspondientes.

#### Información del vehículo y registros históricos

Antes de cerrar el modelo de datos y los casos de uso de registro, deberán definirse:

- Los campos opcionales de la información general del vehículo habilitados para edición directa y sus validaciones, respetando el bloqueo de los datos obligatorios y las correcciones mediante soporte de RN-037 y RF-046.
- Las unidades y validaciones aplicables a las lecturas.
- La información mínima para mantenimientos, reparaciones y repuestos.
- La relación entre intervenciones, actividades, repuestos y evidencias.
- Los permisos, campos y condiciones para corregir, completar o anular registros.
- La conservación de información anterior y el efecto de los cambios sobre resultados derivados.

Estas decisiones afectarán principalmente a RF-005, RF-006, RF-008, RF-009, RF-038, RF-039, RF-040 y RF-046.

#### Documentos y costos

Antes de implementar estas capacidades, deberán definirse:

- Los archivos admitidos, límites, validaciones y permisos.
- El tratamiento de archivos rechazados, pendientes de procesamiento, reemplazados o retirados.
- Los conceptos económicos, monedas y validaciones.
- La relación entre costos totales y componentes para evitar duplicidades.
- El tratamiento de costos desconocidos o incompletos.

Estas decisiones afectarán principalmente a RF-010, RF-044 y RF-045 y a los RNF de protección y procesamiento de archivos.

#### Reglas y seguimiento de mantenimientos

Antes de implementar los cálculos y la evolución de ciclos, deberán definirse:

- El origen de las reglas y las facultades para establecerlas o modificarlas.
- La identificación de las actividades sujetas a seguimiento.
- Las referencias válidas y el tratamiento de información insuficiente.
- Los cálculos por kilometraje, tiempo y combinación de ambos.
- La aplicación de cambios de reglas a ciclos existentes y futuros.
- El efecto de intervenciones históricas y de registros corregidos, completados o anulados.

Estas decisiones afectarán principalmente a RF-033, RF-034, RF-035 y RF-011, así como a la consistencia y trazabilidad de resultados derivados.

#### Alertas, recomendaciones y notificaciones

Antes de habilitar cada tipo de resultado o comunicación, deberán definirse:

- Las condiciones que lo originan y los datos necesarios para evaluarlas.
- Los estados y criterios de actualización de alertas.
- El contenido y las limitaciones de las recomendaciones.
- Los canales, destinatarios y preferencias de notificación.
- Las condiciones de envío, frecuencia, reintento y prevención de duplicados.

Estas decisiones afectarán principalmente a RF-012, RF-018, RF-036 y RF-037.

#### Arquitectura, diseño y calidad

Antes de iniciar la implementación de cada bloque, deberán estar suficientemente definidas las decisiones técnicas que lo condicionan, incluyendo:

- Tecnologías de la aplicación móvil, backend y base de datos.
- Componentes, responsabilidades y contratos de comunicación.
- Almacenamiento y protección de datos y archivos.
- Comportamiento ante conectividad limitada o interrumpida.
- Flujos, pantallas y estados de interacción.
- Compatibilidad, usabilidad y accesibilidad.
- Objetivos verificables de rendimiento, disponibilidad y recuperación.
- Auditoría, monitoreo, respaldo y criterios de liberación.

Estas decisiones se desarrollarán en el documento de arquitectura y diseño y se vincularán con los RF y RNF aplicables.

#### Forma de resolución

Las reglas funcionales se documentarán en `reglas-negocio.md`; los recorridos y excepciones, en `casos-uso.md`; y las decisiones técnicas y de interfaz, en el documento de arquitectura y diseño.

Cuando una decisión cambie el comportamiento o alcance de un requerimiento, se ajustará también su definición principal en el documento de requerimientos.

Una decisión que afecte varias capacidades deberá resolverse antes de cerrar los diseños que dependan de ella. Las capacidades independientes podrán continuar su definición.

Antes de implementar un bloque, sus decisiones necesarias deberán estar resueltas y sus criterios de aceptación deberán permitir verificarlo. Antes de liberar la entrega, deberán cumplirse los criterios funcionales y de calidad aprobados para ella.

---

