# Vehículos Services — Reglas de negocio

## 1. Propósito y alcance

Este documento contendrá la definición detallada de las reglas que determinan las condiciones, validaciones, restricciones y cálculos aplicables a Vehículos Services.

Su desarrollo inicial comprenderá las reglas necesarias para la primera entrega del módulo del Propietario, dirigida a personas naturales, y las capacidades generales necesarias para su funcionamiento independiente del Prestador de Servicios Vehiculares.

Las reglas correspondientes a personas jurídicas, entregas posteriores del Propietario y la integración con el Prestador se desarrollarán cuando se aborde su definición. Su documentación no implicará que pertenezcan a la primera entrega ni que estén aprobadas para implementación.

### Relación con los demás documentos

`proyecto.md` conservará la visión, el alcance, los conceptos y las definiciones generales del proyecto, incluyendo las reglas iniciales del punto 26.

`requerimientos-funcionales-propietario.md` y `requerimientos-funcionales-prestador.md` establecerán los comportamientos esperados de cada módulo y las capacidades generales compartidas.

`requerimientos-no-funcionales.md` establecerá las condiciones de calidad aplicables a cada módulo, capacidad y entrega.

`reglas-negocio.md` desarrollará las condiciones bajo las cuales los comportamientos serán válidos, permitidos o calculables, sin reproducir íntegramente los requerimientos.

`casos-uso.md` desarrollará los recorridos de interacción, precondiciones, postcondiciones, alternativas y excepciones, referenciando las reglas aplicables.

`arquitectura.md`, `modelo-datos.md`, `seguridad.md` y `ux-ui.md` establecerán las decisiones técnicas, estructuras de información, controles y diseño correspondientes. Las elecciones de lenguaje, framework, base de datos e infraestructura no se documentarán como reglas de negocio.

### Conservación y coherencia de las definiciones

Las reglas deberán mantener coherencia con las definiciones aprobadas del proyecto y con el alcance de cada entrega.

Cada regla tendrá una definición detallada principal en este documento. Los demás documentos deberán referenciarla cuando corresponda, evitando mantener versiones independientes del mismo criterio.

Cuando una regla desarrolle una definición general existente, deberá identificar su relación con ella. No deberá introducir condiciones incompatibles ni modificar silenciosamente decisiones aprobadas.

Si se identifica una contradicción o un cambio necesario, deberá señalarse y acordarse el ajuste antes de considerar aprobada la regla afectada.

## 2. Identificación y estructura de las reglas

### 2.1 Identificación única

Las reglas utilizarán la nomenclatura RN-001, RN-002 y sucesivas, conforme al punto 26 de `proyecto.md` y a su estructura documental.

Los identificadores RN-001 a RN-024 se conservarán para las reglas ya identificadas. Su desarrollo detallado mantendrá la correspondencia con la regla original.

Las reglas nuevas utilizarán identificadores disponibles a partir de RN-025, previa comprobación de que no hayan sido asignados. Su incorporación deberá explicar si desarrollan una definición existente o introducen una condición nueva pendiente de aprobación.

La numeración será única para el proyecto y no se reiniciará por módulo, documento o entrega. El orden de documentación o implementación no determinará el identificador.

Los identificadores existentes no se reasignarán a otros conceptos. Cuando una regla sea sustituida, dividida o consolidada, deberá conservarse la trazabilidad de ese cambio.

La nomenclatura RN corresponderá a reglas de negocio y será independiente de RF para requerimientos funcionales y RNF para requerimientos no funcionales.

### 2.2 Información de cada regla

Cada regla deberá documentar:

- ID.
- Nombre.
- Módulo o capacidad.
- Etapa o entrega prevista.
- Estado de la definición.
- Descripción.
- Condiciones de aplicación.
- Datos necesarios.
- Resultado esperado.
- Restricciones y tratamiento de información insuficiente, cuando corresponda.
- Requerimientos relacionados.
- Referencias a las definiciones generales del proyecto, cuando existan.
- Decisiones pendientes, cuando existan.

Según su naturaleza, también deberá documentar:

- Actores y permisos relacionados.
- Cálculos, unidades, precisión y redondeo.
- Estados y transiciones.
- Excepciones.
- Referencias temporales.
- Efecto de correcciones, complementos, anulaciones o cambios de reglas.
- Casos de uso relacionados.
- Ejemplos que ayuden a interpretar o verificar su aplicación.

La información necesaria todavía sin resolver se identificará como pendiente. Los campos que no correspondan podrán indicarse como “No aplica”.

Los ejemplos ilustrarán la regla y no sustituirán su definición. Sus valores no se considerarán parámetros obligatorios salvo que hayan sido establecidos expresamente como tales.

### 2.3 Estado de la definición

Se utilizarán los siguientes estados:

- Propuesta: existe una formulación concreta pendiente de aprobación.
- Pendiente de definición: falta establecer una condición necesaria para completar la regla.
- Por validar: la formulación requiere comprobar su coherencia, viabilidad o aplicación antes de aprobarse.
- Aprobada: su definición ha sido aceptada expresamente para el alcance indicado.

El estado de definición no representará el estado de implementación. Una regla aprobada podrá estar prevista para una entrega posterior.

La documentación de una propuesta no implicará su aprobación. Las decisiones pendientes que afecten el comportamiento esperado deberán resolverse antes de considerar aprobada la regla.

### 2.4 Trazabilidad y definición principal

Cada regla deberá vincularse con los RF y RNF a los que afecte, utilizando sus identificadores originales.

Las reglas iniciales desarrolladas aquí conservarán sus identificadores y señalarán su punto de origen en `proyecto.md`. El punto 26 mantendrá su presentación general, coherente con el desarrollo detallado.

Una regla podrá aplicar a varios requerimientos sin copiarse dentro de cada uno. Los casos de uso y documentos técnicos deberán referenciar su identificador.

Las condiciones compartidas entre módulos conservarán una definición principal. Las condiciones particulares se documentarán expresamente cuando exista una diferencia real de comportamiento o alcance.

Cuando una regla nueva aprobada incorpore o modifique una definición general, un alcance o una decisión del proyecto, se ajustará el punto correspondiente de `proyecto.md`. No será necesario reproducir en el punto 26 todas las reglas detalladas posteriores.

Cuando se modifique una regla aprobada, deberá registrarse el cambio y revisarse su efecto sobre los requerimientos, casos de uso, resultados derivados y decisiones técnicas relacionados.

## 3. Reglas de identidad y acceso

Las reglas iniciales RN-001 a RN-024 mantienen su referencia general en el punto 26 de `proyecto.md`; su especificación detallada todavía no está incorporada en este documento.

RN-025 contiene las condiciones aprobadas de alcance inicial, datos personales, documentos admitidos, comparación documental, unicidad de la cuenta del propietario y restricciones ordinarias de modificación de su identificación.

La revisión manual ordinaria de conflictos de identificación está definida en RN-035 y forma parte de la primera entrega del Propietario. Los procedimientos especiales de cambio de identificación y resolución de conflictos que afecten a cuentas con vehículos asociados permanecen pendientes, conforme a las decisiones señaladas en RN-025 y RN-035.

### RN-025 — Cuenta de usuario e identidad del propietario

- ID: RN-025.
- Nombre: Cuenta de usuario e identidad del propietario.
- Módulo o capacidad: Identidad y acceso.
- Etapa prevista: Primera entrega del Propietario; regla general reutilizable en etapas posteriores.
- Estado de la definición: Alcance inicial, datos personales, documentos admitidos, criterios de comparación, unicidad de la cuenta y restricciones ordinarias de modificación aprobados. La revisión manual ordinaria de conflictos se desarrolla en RN-035. La clasificación de datos editables y las correcciones mediante soporte se desarrollan en RN-037, con sus detalles de verificación pendientes. Permanecen pendientes los procedimientos especiales de resolución de conflictos entre cuentas que afecten a cuentas con vehículos asociados.
- Requerimientos relacionados: RF-001, RF-002, RF-003, RF-043 y RF-051, definidos en `requerimientos-funcionales-propietario.md`; RNF-002 y RNF-005, definidos en `requerimientos-no-funcionales.md`.
- Reglas de negocio relacionadas: RN-026 — Mecanismos de registro y autenticación; RN-028 — Datos, contraseña y coincidencias del registro propio; RN-030 — Registro y autenticación mediante Google; RN-031 — Vinculación, incorporación y retiro de métodos de acceso; RN-032 — Registro y autenticación mediante Apple; RN-035 — Revisión manual de conflictos de identificación del propietario; RN-037 — Actualización de datos personales y correcciones mediante soporte.
- Referencias generales: Registro del propietario conforme a `63.2.3`; validación de propiedad y coincidencia del propietario conforme a `63.4.3` y `63.4.4`; validación individual de vehículos de una persona natural conforme a `63.4.7` de `proyecto.md`.
- Casos de uso relacionados: Pendientes de documentar en `casos-uso.md`.

#### Descripción

La cuenta de usuario permitirá acceder a la plataforma mediante los mecanismos de autenticación habilitados.

La identidad declarada del propietario corresponderá a los datos personales suministrados por el usuario que solicita actuar como titular de un vehículo. Su correspondencia con el propietario indicado en la tarjeta de propiedad deberá evaluarse conforme al procedimiento aplicable.

Crear una cuenta o iniciar sesión no acreditará por sí solo la identidad del propietario ni la propiedad de un vehículo.

Un propietario únicamente podrá tener una cuenta. El correo electrónico de registro deberá ser único y un mismo tipo y número de documento no podrá utilizarse para identificar al propietario en cuentas diferentes.

El acceso mediante contraseña propia, Google o Apple podrá corresponder a métodos vinculados a esa misma cuenta conforme a RN-031. Utilizar diferentes mecanismos de acceso no deberá implicar la creación de cuentas independientes para el mismo propietario.

Para la primera entrega, únicamente se admitirán vehículos y documentos de Colombia. Los tipos de documento de identificación admitidos para el propietario serán cédula de ciudadanía y cédula de extranjería. Otros tipos de documento quedarán fuera de esta primera entrega.

La comprobación inicial consistirá en comparar los datos personales declarados por el usuario con la información del propietario indicada en la tarjeta de propiedad.

Esta comparación no constituirá una comprobación independiente de que la persona que utiliza la cuenta sea quien aparece en el documento, ni acreditará por sí sola la autenticidad o vigencia de la tarjeta de propiedad. Los resultados y mensajes de la plataforma deberán respetar esta limitación.

Los nombres, apellidos, tipo y número de documento se solicitarán cuando el usuario vaya a asociar su primer vehículo, sin exigirlos para crear la cuenta. Antes de completar la asociación, deberán estar disponibles y cumplir las validaciones aplicables a los datos y a su comparación con la tarjeta de propiedad.

#### Condiciones de aplicación

Esta regla aplicará al crear una cuenta, gestionar la información personal y utilizarla para solicitar la asociación de un vehículo.

Un usuario podrá tener una cuenta sin vehículos asociados. La ausencia de vehículos no impedirá por sí sola el acceso a su cuenta y a las capacidades que no requieran una relación de propiedad.

En las solicitudes posteriores de asociación de vehículos se utilizarán los datos personales disponibles, sujetos a las condiciones de actualización y revisión correspondientes. La comparación documental deberá realizarse individualmente para cada vehículo.

La unicidad se comprobará en los siguientes momentos:

- Durante el registro, se comprobará si el correo ya está asociado a una cuenta, conforme a las reglas del mecanismo utilizado.
- Cuando el usuario solicite completar su identificación como propietario y asociar el primer vehículo, se comprobará si el mismo tipo y número de documento ya están asociados a otra cuenta.
- Los cambios posteriores de identificación deberán respetar esa misma condición de unicidad.

La comparación de identificación deberá cumplir estas condiciones:

- El tipo y número de documento declarados deberán coincidir exactamente con los indicados en la tarjeta de propiedad.
- Del número de documento únicamente se eliminarán espacios accidentales al inicio y al final.
- Se conservarán los ceros iniciales y no se aceptarán coincidencias aproximadas del número de documento.
- Para comparar nombres y apellidos, se admitirán diferencias de mayúsculas, tildes y espacios repetidos.
- Los nombres omitidos, abreviaturas o palabras diferentes no se considerarán automáticamente equivalentes.
- Se conservarán los textos originales declarados y obtenidos del documento. Las transformaciones utilizadas para comparar no deberán reemplazarlos.

#### Datos necesarios

- Identificador interno de la cuenta.
- Correo electrónico de registro.
- Nombres declarados por el usuario.
- Apellidos declarados por el usuario.
- Tipo de documento declarado por el usuario.
- Número de documento declarado por el usuario.
- Información del propietario indicada en la tarjeta de propiedad.
- Resultado de las comprobaciones de unicidad del correo y del documento.
- Resultado de las validaciones y comparaciones necesarias para la asociación del vehículo.
- Referencias que permitan vincular la cuenta con los datos utilizados en dicha comparación.

Los mecanismos de captura, las validaciones de formato y las evidencias concretas deberán detallarse respetando los documentos admitidos y los criterios de comparación aprobados en esta regla.

#### Actores y permisos

El usuario podrá gestionar su propio perfil conforme a RF-043 y a la clasificación de datos editables establecida en RN-037.

La edición del perfil no otorgará permiso para cambiar la identidad del titular de una cuenta, modificar la propiedad de un vehículo ni atribuir registros históricos a otra persona.

El usuario no podrá editar ni eliminar directamente el correo de la cuenta, los nombres, apellidos, tipo y número de documento una vez confirmados, aceptados y guardados por el sistema. Las solicitudes de corrección se tramitarán mediante soporte conforme a RN-037.

#### Restricciones y tratamiento de información insuficiente

Un nombre visible, correo electrónico o número de teléfono no deberá considerarse, por sí solo, prueba suficiente de identidad o propiedad.

Los datos personales declarados tampoco deberán presentarse como una identidad comprobada de manera independiente por la plataforma.

Cuando falten datos o existan inconsistencias que impidan validar la correspondencia documental requerida, la asociación del vehículo no deberá considerarse completada.

Si la información está incompleta o resulta ilegible, se solicitará completar los datos, corregir lo que todavía no haya sido confirmado o presentar una nueva captura, según corresponda. Cuando el error afecte datos de identidad ya confirmados y guardados, su corrección requerirá soporte conforme a RN-037. Mientras no se disponga de la información necesaria para aplicar los criterios de comparación, la asociación permanecerá sin completar.

Si existen nombres omitidos, abreviaturas o palabras diferentes que impidan obtener una coincidencia conforme a esta regla, no se completará automáticamente la asociación.

Si el correo indicado durante el registro ya pertenece a una cuenta, no se creará otra cuenta con ese correo. El tratamiento de la cuenta existente y la continuidad de un registro pendiente respetarán RN-028, RN-030 o RN-032, según corresponda.

Si el tipo y número de documento ya están asociados a otra cuenta, no se completará la identificación como propietario ni la asociación solicitada desde la nueva cuenta.

Como el documento se solicita después de crear la cuenta, una persona podría haber creado otra cuenta utilizando un correo diferente antes de que se detecte la coincidencia. Esa situación no autorizará a identificar al mismo propietario en ambas cuentas ni a asociar vehículos desde la cuenta adicional.

Ante una coincidencia que impida continuar, se mostrará el siguiente mensaje:

“No pudimos continuar porque el correo electrónico o el documento indicado ya está registrado. Si ya tienes una cuenta, inicia sesión o recupera el acceso. Si ingresaste algún dato incorrectamente, revísalo e inténtalo nuevamente”.

El mensaje no mostrará el correo de la cuenta existente, su titular, sus vehículos ni otros datos asociados a ella.

El usuario podrá corregir un dato ingresado incorrectamente conforme a las condiciones aplicables, iniciar sesión en su cuenta existente o utilizar las opciones de recuperación correspondientes. La posibilidad de corregir lo digitado antes de confirmarlo no habilitará la edición directa de datos de identidad ya confirmados y guardados.

La coincidencia no permitirá fusionar cuentas, trasladar vehículos, reemplazar credenciales ni modificar permisos automáticamente. La incorporación de métodos de acceso a la cuenta existente se realizará conforme a RN-031.

Si se detecta una cuenta adicional, no se eliminará ni fusionará automáticamente. Esa cuenta no podrá completar la identificación con el documento ocupado ni asociar vehículos como ese propietario.

Cuando el conflicto de documento no pueda resolverse mediante las opciones disponibles, el usuario autenticado podrá solicitar una revisión manual conforme a RN-035 y RF-051. La presentación de la solicitud no completará la identificación ni la asociación bloqueadas.

La revisión manual incluirá la comprobación adicional de identidad y respetará los permisos, evidencias y límites de RN-035. Si se autoriza y ejecuta una corrección, el solicitante deberá completar nuevamente las comprobaciones normales de identificación y asociación.

Los conflictos entre cuentas cuya corrección afectaría a una cuenta con vehículos asociados requerirán el procedimiento especial pendiente de RN-035. Mientras no puedan resolverse conforme a un procedimiento aprobado, la identificación y la asociación solicitadas permanecerán sin completar.

La corrección de un error de captura mediante RN-037 no deberá utilizarse para eludir esos límites ni resolver automáticamente un conflicto entre cuentas.

La comparación satisfactoria de los datos del propietario para un vehículo no acreditará automáticamente la propiedad de otros vehículos solicitados por el mismo usuario.

#### Resultado esperado

La plataforma distinguirá:

- La cuenta utilizada para acceder.
- La identidad declarada de la persona que solicita actuar como propietario.
- El resultado de las comprobaciones de unicidad del correo y del documento.
- El resultado de la comparación con el propietario indicado en la tarjeta de propiedad.
- La relación de propiedad establecida para cada vehículo conforme al procedimiento aplicable.

Un propietario conservará una única cuenta, que podrá tener varios métodos de acceso vinculados y uno o varios vehículos asociados.

Una comparación documental satisfactoria no deberá presentarse como una comprobación independiente de la identidad real de la persona que utiliza la cuenta.

Los permisos sobre vehículos se otorgarán conforme a las relaciones y condiciones correspondientes, sin derivarlos únicamente de la existencia de una cuenta o de una sesión autenticada.

#### Efecto de cambios en la información personal

Modificar datos del perfil no deberá transferir vehículos ni reemplazar la identidad atribuida a acciones históricas.

Mientras diligencia los datos personales, antes de confirmar su envío, el usuario podrá corregir lo digitado.

Una vez confirmados, aceptados y guardados por el sistema, los nombres, apellidos, tipo y número de documento no podrán editarse ni eliminarse directamente por el usuario, independientemente de que todavía no tenga vehículos asociados. Las solicitudes de corrección se tramitarán mediante soporte conforme a RN-037.

El correo de la cuenta quedará sujeto a esa restricción desde la creación del registro pendiente de verificación. Un error en ese correo podrá comunicarse a soporte sin exigir acceso a la cuenta.

El celular de contacto será obligatorio para completar la información del propietario antes de asociar su primer vehículo, sin exigirlo para crear inicialmente la cuenta. Podrá actualizarse directamente, pero no eliminarse ni dejarse vacío mediante una actualización aceptada. La ciudad de residencia y la fotografía de perfil serán opcionales y podrán agregarse, actualizarse o retirarse conforme a RN-037. Estas actualizaciones no sustituirán la identidad del propietario ni modificarán las relaciones de propiedad.

Cuando una corrección autorizada afecte los datos utilizados para comparar la identidad declarada con la información de propiedad, deberán realizarse las comprobaciones aplicables antes de considerar satisfactoria la correspondencia con la nueva información.

Un cambio de identificación no deberá permitir utilizar un tipo y número de documento ya asociados a otra cuenta ni eludir las comprobaciones de unicidad.

Las correcciones relacionadas con conflictos de identificación entre cuentas se realizarán conforme a RN-035 y sus límites. Las correcciones de errores de captura contempladas en RN-037 no ampliarán automáticamente el alcance de esa revisión.

#### Decisiones pendientes

- Detallar las validaciones de formato de los datos personales y los mecanismos de captura y comparación, respetando las condiciones aprobadas.
- Detallar las verificaciones y el procedimiento de corrección mediante soporte de nombres, apellidos, tipo y número de documento conforme a RN-037, contemplando las relaciones de propiedad existentes.
- Detallar las comprobaciones necesarias cuando una corrección autorizada afecte los datos utilizados en comparaciones documentales anteriores.
- Definir el procedimiento especial para conflictos entre cuentas cuya corrección afectaría a cuentas con vehículos asociados, conforme a RN-035.
- Definir las condiciones posteriores de conservación o cierre de una cuenta adicional, sin eliminarla ni fusionarla automáticamente por la coincidencia.

---

### RN-026 — Mecanismos de registro y autenticación

- ID: RN-026.
- Nombre: Mecanismos de registro y autenticación.
- Módulo o capacidad: Identidad y acceso.
- Etapa prevista: Primera entrega del Propietario en Android e iOS; incorporación de otros proveedores en entregas posteriores.
- Estado de la definición: Aprobado en su alcance funcional para la primera entrega del Propietario. Los mecanismos técnicos de implementación deberán detallarse en los documentos correspondientes.
- Requerimientos relacionados: RF-001, RF-002, RF-048 y RF-049, definidos en `requerimientos-funcionales-propietario.md`; RNF-003 y RNF-021, definidos en `requerimientos-no-funcionales.md`.
- Reglas de negocio relacionadas: RN-027 — Verificación del correo en el registro propio; RN-028 — Datos, contraseña y coincidencias del registro propio; RN-029 — Recuperación de la contraseña propia; RN-030 — Registro y autenticación mediante Google; RN-031 — Vinculación, incorporación y retiro de métodos de acceso; RN-032 — Registro y autenticación mediante Apple, definidas en `reglas-negocio.md`.
- Referencias generales: Mecanismos de registro y autenticación contemplados en `63.2.3` de `proyecto.md`.
- Casos de uso relacionados: CU-001 Crear cuenta y CU-002 Iniciar sesión; detalle pendiente en `casos-uso.md`.

#### Descripción

La primera entrega del Propietario de Vehículos Services permitirá crear una cuenta e iniciar sesión en Android e iOS mediante:

- Registro propio con correo electrónico y contraseña.
- Registro y autenticación mediante Google.
- Registro y autenticación mediante Apple.

En el registro propio, los datos iniciales, las validaciones del correo, las condiciones de la contraseña y el tratamiento de coincidencias con cuentas existentes deberán cumplir RN-028.

Vehículos Services gestionará las credenciales propias conforme a las condiciones funcionales aprobadas y los controles de seguridad correspondientes. Su recuperación se realizará mediante RF-048 y el procedimiento definido en RN-029.

La verificación del correo será obligatoria antes de habilitar el uso de la cuenta creada mediante registro propio y se realizará conforme a RN-027.

Mientras ese registro permanezca pendiente de verificación, el acceso se limitará a las acciones permitidas por RN-027. La corrección del correo, la continuidad del registro y la conservación y eliminación del registro provisional se regirán por esa misma regla.

La recuperación de la contraseña de una cuenta pendiente no verificará automáticamente el correo, habilitará la cuenta ni ampliará el plazo de conservación del registro provisional.

En el acceso mediante Google o Apple, la plataforma utilizará la autenticación del proveedor y la información que este permita compartir con autorización del usuario. Vehículos Services no solicitará ni gestionará las contraseñas de esos proveedores.

Las condiciones de registro y habilitación mediante Google se regirán por RN-030. Las correspondientes a Apple se regirán por RN-032. La comprobación adicional del correo se aplicará cuando corresponda conforme a esas reglas.

La recuperación de las credenciales de Google o Apple corresponderá al proveedor. Una cuenta que utilice únicamente un proveedor externo no podrá incorporar una contraseña propia mediante el procedimiento de recuperación de Vehículos Services.

Cuando una cuenta tenga una contraseña propia y proveedores externos vinculados mediante el procedimiento aprobado, RN-029 permitirá restablecer únicamente la contraseña administrada por Vehículos Services, sin modificar las vinculaciones externas.

La incorporación y el retiro de métodos se realizarán conforme a RN-031.

La incorporación de otros proveedores de identidad se contemplará para entregas posteriores. Su habilitación requerirá definir sus condiciones de registro, autenticación, recuperación y vinculación con cuentas existentes.

#### Condiciones de aplicación

Esta regla aplicará al crear una cuenta, iniciar sesión y determinar el procedimiento de recuperación correspondiente al mecanismo utilizado.

La disponibilidad de los tres mecanismos no implicará que todas las cuentas los tengan vinculados. El usuario utilizará un mecanismo habilitado y asociado a su cuenta.

Una cuenta podrá disponer de contraseña propia, Google y Apple vinculados, siempre que cada método se haya incorporado mediante su procedimiento correspondiente.

Una solicitud de registro no deberá incorporar automáticamente un mecanismo a una cuenta existente. Se aplicarán las condiciones de RN-028, RN-030 y RN-032, según corresponda.

La recuperación de acceso tampoco deberá incorporar, retirar ni modificar los métodos vinculados a una cuenta.

Estas capacidades se definirán para el funcionamiento independiente del módulo del Propietario. Su posible reutilización posterior no implicará incorporar funcionalidades del Prestador en la primera entrega.

#### Datos necesarios

- Identificador interno de la cuenta.
- Mecanismos de acceso vinculados y mecanismo utilizado.
- Correo electrónico y elementos de verificación aplicables al registro propio, conforme a RN-027 y RN-028.
- Referencia estable de identidad proporcionada por Google o Apple y datos autorizados necesarios para el registro externo.
- Información necesaria para aplicar la recuperación de la contraseña propia conforme a RN-029.
- Información necesaria para incorporar o retirar métodos conforme a RN-031.

Los identificadores técnicos, almacenamiento y controles de las credenciales se definirán en los documentos de arquitectura y seguridad.

#### Restricciones

La autenticación mediante cualquiera de los mecanismos no acreditará por sí sola la propiedad de un vehículo ni concederá permisos adicionales.

La información recibida de Google o Apple no deberá asumirse como completa para identificar legalmente al propietario. Los datos faltantes necesarios para asociar un vehículo se obtendrán conforme a las condiciones de identificación y validación correspondientes.

La coincidencia de un correo entre mecanismos no autorizará por sí sola la vinculación de cuentas o métodos de acceso. Se aplicará RN-031.

Las solicitudes de registro que coincidan con cuentas existentes no deberán sobrescribir credenciales, crear cuentas duplicadas ni revelar información restringida de esas cuentas, conforme a las reglas del mecanismo correspondiente.

La recuperación conservará la cuenta, sus relaciones, permisos y restricciones, conforme a RN-029.

La incorporación o el retiro de métodos conservará la cuenta y sus relaciones y deberá mantener al menos un método habilitado y utilizable, conforme a RN-031.

La plataforma no deberá presentar otros proveedores como disponibles mientras no estén implementados y habilitados.

#### Resultado esperado

El usuario dispondrá de registro propio, Google y Apple en la primera entrega del Propietario para Android e iOS.

La plataforma identificará la cuenta mediante el mecanismo correspondiente y aplicará los permisos derivados de sus relaciones vigentes, independientemente del método utilizado para autenticarse.

Cada registro cumplirá sus condiciones de comprobación y habilitación antes de permitir el acceso ordinario.

Cuando sea necesario recuperar el acceso, se aplicará el procedimiento correspondiente a los mecanismos asociados a la cuenta.

La gestión de métodos se realizará desde la misma cuenta mediante RN-031, sin vinculaciones automáticas ni pérdida de sus relaciones.

#### Definiciones técnicas posteriores

La implementación deberá detallar:

- La integración de los mecanismos aprobados en Android e iOS.
- La validación de la autenticación y su correspondencia con la cuenta interna.
- La protección de las credenciales y de la información recibida de los proveedores.
- La aplicación de las reglas de registro, comprobación del correo, recuperación y gestión de métodos.
- Los controles de seguridad y gestión de sesiones.
- Los casos de uso correspondientes.

Estas definiciones deberán respetar los comportamientos aprobados en RN-027, RN-028, RN-029, RN-030, RN-031 y RN-032.

---

### RN-027 — Verificación del correo en el registro propio

- ID: RN-027.
- Nombre: Verificación del correo en el registro propio.
- Módulo o capacidad: Identidad y acceso.
- Etapa prevista: Primera etapa del Propietario.
- Estado de la definición: Aprobado en su alcance funcional. La corrección del correo registrado requerirá soporte conforme a RN-037, cuyas verificaciones específicas permanecen pendientes de detalle. Los mecanismos técnicos de implementación deberán detallarse en los documentos correspondientes.
- Requerimientos relacionados: RF-001 y RF-002 de requerimientos-funcionales-propietario.md; RNF-003, RNF-020 y RNF-021 de requerimientos-no-funcionales.md.
- Reglas de negocio relacionadas: RN-026, RN-025 y RN-037, considerando el estado de definición de cada regla.
- Referencias del proyecto: Punto 63.2.3 y disposiciones aplicables del punto 67 de proyecto.md.
- Casos de uso relacionados: CU-001 y CU-002, sujetos a su documentación detallada en casos-uso.md.

#### Descripción

Cuando una persona cree su cuenta mediante el registro propio con correo electrónico y contraseña, deberá verificar el control del correo informado antes de acceder a las funcionalidades habilitadas para una cuenta registrada.

La verificación se realizará mediante un código numérico de seis dígitos enviado al correo utilizado en el registro. El usuario deberá introducirlo en la aplicación.

El envío del código no completará la verificación. Esta se completará únicamente cuando el sistema compruebe correctamente un código válido.

Esta regla aplica al registro propio con correo electrónico y contraseña. Su aplicación no deberá extenderse automáticamente al registro mediante Google, cuyas condiciones se establecerán conforme a la RN-026.

#### Condiciones de aplicación

- La cuenta creada mediante registro propio permanecerá pendiente de verificación hasta comprobar correctamente el código.
- Mientras permanezca pendiente, el usuario únicamente podrá realizar las acciones necesarias para completar el registro, introducir el código, solicitar uno nuevo o consultar las indicaciones para contactar a soporte conforme a RN-037.
- Una vez creado el registro pendiente, el usuario no podrá editar ni eliminar directamente el correo registrado. Su corrección requerirá soporte conforme a RN-037.
- La cuenta pendiente no podrá gestionar vehículos, consultar información privada de una cuenta habilitada ni utilizar otras funcionalidades que requieran haber completado el registro.
- La verificación del correo no sustituirá otras validaciones o restricciones aplicables a la cuenta.
- La corrección del correo de una cuenta ya habilitada se tramitará conforme a RN-037. Sus verificaciones específicas y efectos sobre el acceso deberán detallarse por separado; no se considerarán resueltos por esta regla de registro inicial.

#### Composición del código

- El código deberá contener exactamente seis dígitos numéricos, del 0 al 9.
- Los ceros iniciales formarán parte del código y deberán conservarse. Por ejemplo, 038251 no podrá interpretarse como 38251.
- La aplicación deberá permitir escribir o pegar el código completo.
- Un valor que no contenga exactamente seis dígitos numéricos deberá rechazarse antes de comparar su contenido con el código vigente.
- El rechazo por formato no incrementará el contador de intentos fallidos de comprobación.

#### Vigencia del código

- Cada código tendrá una vigencia de 10 minutos contados desde su generación.
- El código podrá utilizarse antes de cumplirse los 10 minutos, siempre que no haya sido consumido o invalidado y se cumplan las demás condiciones de esta regla.
- Al cumplirse los 10 minutos, el código se considerará vencido.
- Una demora en la entrega del correo no reiniciará ni ampliará la vigencia.
- El mensaje enviado deberá informar que el código vence 10 minutos después de su generación.
- El vencimiento del código no eliminará la cuenta ni verificará el correo.
- Cuando el código venza, el usuario podrá solicitar otro, respetando los controles de generación establecidos en esta regla.

#### Uso único del código

- Cada código podrá completar una sola verificación.
- Cuando la comprobación sea exitosa, el código deberá quedar consumido y no podrá utilizarse nuevamente, aunque todavía no hayan transcurrido los 10 minutos.
- La presentación de un código consumido no deberá producir una nueva verificación ni modificar el estado de la cuenta.
- El uso único no impedirá corregir errores de escritura dentro del límite de intentos fallidos establecido en esta regla.
- Si la verificación se completó, pero la aplicación no recibió la respuesta, se deberá recuperar el resultado registrado sin ejecutar una segunda verificación.

#### Generación de un nuevo código

- Para una misma cuenta, deberá existir como máximo un código válido a la vez, asociado al correo que esté pendiente de verificación.
- Cuando se genere un nuevo código, el código anterior deberá quedar invalidado, aunque todavía no haya vencido ni se haya utilizado.
- El nuevo código tendrá su propia vigencia de 10 minutos contados desde su generación.
- La generación de un nuevo código no ampliará la vigencia del anterior.
- Si una solicitud es rechazada o falla antes de generar un nuevo código, el código anterior conservará su estado, salvo que haya vencido, sido consumido o invalidado por otra condición, incluida una corrección del correo autorizada mediante soporte.
- La entrega tardía del correo correspondiente a un código anterior no deberá restablecer su validez.
- El usuario deberá utilizar el código de la solicitud más reciente que efectivamente haya generado uno nuevo para el correo actualmente asociado al registro pendiente.

#### Tiempo mínimo entre generaciones

- Deberán transcurrir al menos 60 segundos desde la última generación de un código para la misma cuenta antes de permitir generar otro.
- Una solicitud realizada antes de cumplir ese tiempo deberá rechazarse, indicando cuánto falta para poder solicitar nuevamente.
- Una solicitud rechazada no deberá generar un código, invalidar el anterior ni reiniciar el tiempo de espera.
- Cumplir los 60 segundos no garantizará una nueva generación si se alcanzó otro límite aplicable.
- El tiempo mínimo entre generaciones será independiente de la vigencia de 10 minutos.
- Una corrección del correo autorizada mediante soporte durante el registro pendiente no reiniciará este tiempo de espera.
- El control deberá aplicarse en el backend. Cerrar y abrir la aplicación o utilizar otro dispositivo no deberá permitir evadirlo.

#### Límite de generación de códigos

- Se permitirá generar como máximo 5 códigos en un período móvil de 60 minutos para la misma cuenta pendiente de verificación.
- El código inicial enviado durante el registro se incluirá en este límite.
- Para evaluar una nueva solicitud, se contabilizarán los códigos generados durante los 60 minutos anteriores.
- Una generación que haya cumplido exactamente 60 minutos dejará de formar parte del período contabilizado.
- Si ya se generaron 5 códigos dentro del período, no se permitirá generar otro hasta que el número contabilizado sea inferior a 5 y también se cumpla la espera mínima de 60 segundos.
- Las solicitudes rechazadas o que fallen antes de generar un código no incrementarán el contador ni invalidarán el código vigente.
- Un código generado contará dentro del límite aunque posteriormente falle su envío o no pueda confirmarse su entrega.
- Alcanzar el límite de generación no impedirá comprobar un código que siga vigente y cumpla las demás condiciones.
- Alcanzar este límite no eliminará la cuenta ni verificará el correo.
- Una corrección del correo autorizada mediante soporte no reiniciará el contador. Las generaciones realizadas para correos anteriores de la misma cuenta seguirán contabilizándose mientras permanezcan dentro del período móvil.
- La aplicación deberá informar cuándo podrá solicitarse otro código, considerando tanto la espera mínima como el límite del período móvil.
- El control deberá aplicarse en el backend y no podrá reiniciarse al cambiar de dispositivo o volver a abrir la aplicación.
- El límite de generación será independiente del límite de intentos fallidos de comprobación.

#### Límite de intentos fallidos de comprobación

- Cada código vigente permitirá como máximo 5 intentos fallidos de comprobación.
- Se considerará fallido un intento cuando el código introducido cumpla el formato requerido, pero no coincida con el código vigente asociado a la cuenta y al correo pendiente de verificación.
- Cada comparación fallida deberá incrementar el contador correspondiente al código vigente.
- Al alcanzar el quinto intento fallido, el código vigente deberá quedar invalidado, aunque todavía no hayan transcurrido los 10 minutos.
- Si el usuario introduce el código correcto antes de acumular 5 intentos fallidos, la verificación podrá completarse.
- Si se han acumulado 4 intentos fallidos y la siguiente comprobación es correcta, la verificación deberá completarse, siempre que el código conserve su validez y se cumplan las demás condiciones.
- Un código invalidado por alcanzar el límite no podrá completar la verificación, aunque posteriormente se introduzca correctamente.
- Para continuar después de alcanzar el límite, el usuario deberá solicitar un nuevo código, respetando los controles de generación.
- Cada nuevo código comenzará con su propio contador de intentos fallidos en cero.
- Si no existe un código vigente, la solicitud deberá rechazarse sin incrementar un contador de comparación. La aplicación deberá indicar si corresponde solicitar otro código o consultar el estado del registro.
- Si existe un código vigente y se presenta otro valor de seis dígitos que no coincida con él, se contabilizará un intento fallido, aunque ese valor corresponda a un código anterior.
- La invalidación por intentos fallidos no eliminará la cuenta ni verificará el correo.
- El contador deberá controlarse en el backend. Cerrar y abrir la aplicación o utilizar otro dispositivo no deberá reiniciarlo.

#### Corrección del correo durante el registro pendiente

- Antes de confirmar el envío del formulario de creación de cuenta, el usuario podrá corregir el correo digitado.
- Una vez creado el registro pendiente, el usuario no podrá editar ni eliminar directamente ese correo.
- Si detecta un error, deberá solicitar su corrección mediante el canal y las condiciones de RN-037.
- La solicitud de ayuda no dependerá de haber verificado el correo ni de poder iniciar sesión.
- Informar una dirección de correo o conocerla no será suficiente para autorizar su modificación.
- Soporte deberá aplicar las verificaciones que se definan conforme a RN-037 antes de autorizar y ejecutar una corrección.
- La corrección deberá conservar la misma cuenta y no deberá crear una cuenta adicional.
- El nuevo correo deberá cumplir las validaciones de formato y disponibilidad aplicables al registro.
- Si el nuevo correo ya está asociado a otra cuenta, el cambio deberá rechazarse sin vincular ni fusionar cuentas automáticamente.
- Si el cambio es rechazado, se conservarán el correo anterior y el estado del código asociado, considerando su vigencia y las demás condiciones aplicables.
- Al ejecutar un cambio efectivo de correo autorizado mediante soporte, se deberá invalidar el código asociado al correo anterior.
- La cuenta continuará pendiente de verificación hasta comprobar correctamente un código enviado al nuevo correo. La corrección por soporte no sustituirá esta verificación del registro propio.
- Si los controles de generación lo permiten, se generará y enviará un nuevo código al correo corregido.
- Si los controles impiden generar otro código en ese momento, el cambio de correo podrá completarse, pero el usuario deberá esperar hasta que se permita solicitar el nuevo código.
- La aplicación deberá informar que el correo fue corregido y, cuando corresponda, cuánto debe esperar para solicitar el código.
- Cambiar el correo no reiniciará la espera mínima entre generaciones ni el contador del período móvil de 60 minutos.
- Los códigos enviados al correo anterior no podrán verificar el correo corregido, aunque se reciban después del cambio.
- Esta corrección no habilitará por sí misma la cuenta ni concederá permisos adicionales.
- Las verificaciones y efectos de una corrección sobre una cuenta ya habilitada se detallarán conforme a RN-037, sin asumir que este procedimiento de registro pendiente los resuelve.

#### Continuidad del registro

- Cerrar la aplicación no cancelará el registro pendiente ni reiniciará los tiempos o contadores.
- Mientras el registro provisional se conserve, el usuario podrá retomarlo al autenticarse con las credenciales de la cuenta pendiente.
- Al retomar el proceso, la aplicación deberá consultar el estado actual de la cuenta y permitir únicamente las acciones correspondientes.
- Si el código sigue vigente, podrá comprobarse conforme a esta regla.
- Si ya no existe un código vigente, podrá solicitarse otro cuando los controles lo permitan.
- Si el correo ya fue verificado, la aplicación deberá continuar desde el estado confirmado por el backend, sin exigir repetir la verificación.
- Si el error en el correo impide retomar el registro, el usuario podrá contactar a soporte conforme a RN-037. Esto no habilitará acceso sin las comprobaciones correspondientes.

#### Solicitudes repetidas y problemas de conexión

- Si una operación se completó en el backend, la pérdida de la respuesta no deberá revertir su resultado.
- Si la verificación fue exitosa, el correo permanecerá verificado y el código consumido, aunque la aplicación no haya recibido la confirmación.
- Al recuperar la conexión, la aplicación deberá consultar el estado de la cuenta y continuar desde el resultado registrado.
- La repetición de una misma operación por falta de respuesta deberá recuperar su resultado sin generar otro código, duplicar una comprobación ni incrementar nuevamente los contadores.
- Una nueva acción independiente del usuario se considerará una nueva solicitud y deberá cumplir los controles aplicables.
- Si la solicitud no llegó a procesarse, no deberá consumir el código ni contabilizar un intento fallido.
- Si una comparación sí fue procesada y resultó fallida, su contabilización se conservará aunque la aplicación no haya recibido la respuesta.
- Un problema de conexión no ampliará la vigencia del código.
- La aplicación deberá informar cuando no pueda confirmar el resultado de una operación, sin presentar el registro como verificado hasta obtener el estado correspondiente.
- El mecanismo técnico para distinguir una operación repetida de una solicitud nueva deberá definirse en arquitectura.

#### Errores de envío del correo

- Si la operación falla antes de generar un código, no se contabilizará una generación y el código anterior conservará su estado, considerando las demás condiciones aplicables.
- Si el código ya fue generado, contará dentro de los límites y el código anterior quedará invalidado, aunque posteriormente falle el envío.
- Un fallo de envío o la falta de confirmación de entrega no verificará el correo ni habilitará la cuenta.
- La aplicación deberá informar el problema conocido y permitir solicitar otro código cuando los controles lo permitan.
- La aplicación no deberá afirmar que el usuario recibió el correo cuando únicamente se tenga constancia de su generación o envío.
- Si el código finalmente llega, podrá utilizarse solamente si conserva su validez y corresponde al correo actualmente pendiente de verificación.

#### Solicitudes simultáneas

- Los controles deberán aplicarse a la cuenta, independientemente del número de dispositivos o solicitudes concurrentes.
- Las operaciones simultáneas no deberán permitir superar los límites, mantener más de un código válido ni completar dos veces la verificación.
- Si una corrección autorizada mediante soporte y una verificación se procesan simultáneamente, se deberá conservar un resultado consistente:
  - Si primero se completa la verificación, no se ejecutará la modificación como una corrección de registro pendiente. La solicitud deberá evaluarse conforme a las condiciones aplicables a una cuenta ya habilitada de RN-037.
  - Si primero se ejecuta la corrección del correo, el código asociado al correo anterior no podrá completar la verificación.
- El mecanismo técnico para garantizar esta consistencia deberá definirse en arquitectura.

#### Conservación del registro pendiente

- El registro provisional se conservará durante 30 días calendario contados desde su creación.
- Al cumplirse ese plazo sin completar la verificación, se deberá eliminar el registro provisional y liberar el correo para permitir un nuevo registro.
- Solicitar códigos, retomar el proceso o corregir el correo mediante soporte no reiniciará ni ampliará este plazo.
- La aplicación deberá informar esta condición durante el registro.
- Una vez cumplido el plazo, el registro provisional no podrá verificarse mediante un código anterior. El usuario deberá iniciar un nuevo registro.
- Esta eliminación aplicará únicamente al registro que permanezca pendiente de verificación. No aplicará a una cuenta que haya completado la verificación antes del vencimiento del plazo.
- La conservación de registros técnicos de seguridad se definirá por separado y no implicará conservar activa la cuenta provisional.

#### Información necesaria para aplicar la regla

El sistema deberá disponer de la información necesaria para determinar:

- La cuenta asociada al proceso de verificación.
- La fecha y hora de creación del registro provisional y su plazo de conservación.
- El correo actualmente pendiente de verificación.
- El estado de verificación del correo.
- El código presentado por el usuario.
- La referencia al código vigente y los datos necesarios para comprobarlo de forma segura.
- La fecha y hora de generación y vencimiento.
- Si el código fue consumido o invalidado.
- La última generación y el momento a partir del cual podrá generarse otro código.
- Las generaciones necesarias para evaluar el período móvil de 60 minutos, incluidas las realizadas antes de una corrección del correo autorizada mediante soporte.
- El número de intentos fallidos asociado al código vigente.
- El resultado de las operaciones necesario para resolver solicitudes repetidas sin duplicar sus efectos.
- La referencia a la corrección autorizada mediante soporte, cuando se haya modificado el correo del registro pendiente.

La forma técnica de proteger, almacenar y comprobar esta información deberá definirse en los documentos de arquitectura y seguridad correspondientes.

#### Resultado de la comprobación

- Mientras no exista una comprobación exitosa y el registro provisional se conserve, la cuenta permanecerá pendiente de verificación y mantendrá las restricciones correspondientes.
- La comprobación deberá validar la conservación del registro, la asociación con la cuenta y el correo actual, la coincidencia del código, su vigencia, su estado y el límite de intentos fallidos.
- Cuando la comprobación sea exitosa, se deberá registrar la verificación del correo y consumir el código.
- La cuenta podrá acceder a las funcionalidades correspondientes, considerando los permisos y las demás restricciones aplicables.
- Enviar o generar un código no deberá modificar el correo a verificado.
- Un código incorrecto, vencido, consumido, invalidado o asociado a otra cuenta o correo no deberá habilitar la cuenta.
- Consultar o recuperar el resultado de una verificación ya completada no constituirá una nueva utilización del código.

#### Restricciones de negocio

- Verificar el correo acreditará el control de esa dirección dentro del proceso de registro.
- No acreditará por sí mismo la identidad legal de la persona, la propiedad de un vehículo ni la representación de un tercero.
- No deberá crear vehículos, relaciones de propiedad ni permisos adicionales.
- El acceso limitado al proceso de verificación no deberá permitir evadir las restricciones de una cuenta pendiente.
- Contactar a soporte no verificará automáticamente el correo ni habilitará la cuenta.

#### Definiciones técnicas posteriores

El comportamiento funcional de verificación establecido en esta regla queda aprobado. Su implementación deberá detallar en los documentos correspondientes:

- La generación, protección y comprobación segura de los códigos.
- El control de tiempos, contadores y estados en el backend.
- La autenticación limitada de las cuentas pendientes.
- La identificación de operaciones repetidas y la resolución de solicitudes simultáneas.
- El mecanismo de envío de correos y el tratamiento técnico de sus resultados.
- La integración con el procedimiento de corrección mediante soporte de RN-037, cuyas verificaciones específicas deberán definirse antes de habilitarlo.
- La eliminación de registros provisionales vencidos.
- La conservación de registros técnicos conforme a las definiciones de seguridad aplicables.

Estas definiciones deberán respetar los comportamientos y límites establecidos en esta regla.

---

### RN-028 — Datos, contraseña y coincidencias del registro propio

- ID: RN-028.
- Nombre: Datos, contraseña y coincidencias del registro propio.
- Módulo o capacidad: Identidad y acceso.
- Etapa prevista: Primera entrega del Propietario; reutilizable posteriormente por otros módulos.
- Estado de la definición: Aprobado en su alcance funcional. Los mecanismos técnicos de implementación deberán detallarse en los documentos correspondientes.
- Requerimientos relacionados: RF-001, RF-002, RF-043 y RF-048, definidos en `requerimientos-funcionales-propietario.md`.
- Reglas de negocio relacionadas: RN-025 — Cuenta de usuario e identidad del propietario; RN-026 — Mecanismos de registro y autenticación; RN-027 — Verificación del correo en el registro propio; RN-029 — Recuperación de la contraseña propia; RN-030 — Registro y autenticación mediante Google; RN-031 — Vinculación, incorporación y retiro de métodos de acceso; RN-032 — Registro y autenticación mediante Apple, considerando el estado de definición de cada regla.
- Referencias generales: Registro de usuario contemplado en `63.2.3` de `proyecto.md`.
- Caso de uso relacionado: CU-001 Crear cuenta; detalle pendiente en `casos-uso.md`.

#### Descripción

El registro propio de Vehículos Services deberá solicitar los datos necesarios para crear una cuenta con correo electrónico y contraseña, sin exigir desde ese momento toda la información utilizada posteriormente para identificar al propietario o validar la propiedad de un vehículo.

La creación del registro deberá aplicar las validaciones del correo y de la contraseña establecidas en esta regla, comprobar las coincidencias con cuentas existentes y respetar la verificación obligatoria definida en RN-027.

#### Datos obligatorios del registro propio

- El usuario deberá indicar un correo electrónico y una contraseña.
- Se solicitará la confirmación de la contraseña para comprobar que ambos valores coincidan.
- La confirmación de la contraseña no se conservará como un dato adicional de la cuenta.
- La creación de la cuenta no exigirá inicialmente documento de identidad, teléfono, dirección ni datos de un vehículo.
- Los datos necesarios para identificar al propietario se definirán y solicitarán en el proceso correspondiente, conforme a RN-025 y RF-043.
- No disponer de esos datos personales durante el registro no impedirá crear una cuenta que cumpla las condiciones aplicables.
- Crear la cuenta no acreditará por sí solo la identidad del propietario ni la propiedad de un vehículo.

#### Validación del correo electrónico

- El registro deberá admitir una sola dirección de correo electrónico.
- La dirección deberá cumplir las validaciones de formato correspondientes.
- Los espacios accidentales al inicio y al final deberán eliminarse antes de utilizar la dirección en el registro.
- No deberán eliminarse los puntos ni los sufijos de la dirección, como `+algo`, para asumir que dos direcciones corresponden a una misma persona.
- La similitud entre direcciones no deberá utilizarse por sí sola para vincular cuentas ni atribuirlas a una misma persona.
- La verificación del control del correo y su corrección durante el registro pendiente deberán cumplir RN-027.
- La validación de formato no sustituirá la verificación del control del correo.

#### Longitud y composición de la contraseña

- La contraseña deberá tener entre 15 y 128 caracteres, incluidos ambos límites.
- Se permitirán letras, números, símbolos y espacios.
- No se exigirán combinaciones obligatorias de mayúsculas, minúsculas, números o símbolos.
- La contraseña deberá comprobarse completa, sin truncarla.
- No deberán eliminarse espacios ni recortarse la contraseña silenciosamente.
- La contraseña y su confirmación deberán coincidir para completar la solicitud de registro.
- Cuando no se cumplan estas condiciones, la aplicación deberá informar qué debe corregirse sin exponer la contraseña.

#### Rechazo de contraseñas inseguras

- La contraseña propuesta deberá comprobarse contra una lista de valores comunes o comprometidos.
- Si aparece en esa lista, deberá rechazarse y solicitarse otra.
- La aplicación deberá explicar el motivo del rechazo sin mostrar ni registrar la contraseña.
- La fuente, actualización y mecanismo de comprobación de la lista deberán definirse en los documentos técnicos y de seguridad correspondientes.

#### Interacción con la contraseña

- La aplicación deberá permitir pegar la contraseña y utilizar gestores de contraseñas.
- El usuario podrá mostrar temporalmente el contenido mediante una acción explícita.
- No se exigirán cambios periódicos de contraseña por el solo transcurso del tiempo.
- Se exigirá un cambio cuando exista evidencia de que la contraseña fue comprometida.
- Los mecanismos técnicos de protección de las credenciales deberán definirse en los documentos correspondientes.

#### Coincidencia con una cuenta habilitada

- Si el correo indicado ya está asociado a una cuenta habilitada, no se deberá crear otra cuenta con ese correo.
- La solicitud de registro no deberá reemplazar la contraseña ni modificar las credenciales de la cuenta existente.
- La aplicación deberá ofrecer las opciones de iniciar sesión o recuperar el acceso mediante el mensaje establecido en el apartado “Mensajes ante coincidencias”.
- No deberán revelarse datos personales, el estado de la cuenta ni los métodos de acceso asociados a ella.

#### Coincidencia con un registro pendiente

- Si el correo ya está asociado a un registro pendiente que todavía se conserve, una nueva solicitud no deberá sobrescribir ese registro ni su contraseña.
- El usuario podrá retomar el registro únicamente después de autenticarse con las credenciales de la cuenta pendiente, conforme a RN-027.
- Repetir una solicitud de registro no deberá generar automáticamente nuevos códigos de verificación.
- La generación de códigos deberá realizarse mediante las acciones permitidas y los controles establecidos en RN-027.
- Si el registro provisional ya venció, se aplicará el tratamiento definido en RN-027 antes de permitir un nuevo registro.

#### Coincidencia con una cuenta que utiliza Google o Apple

- Un intento de registro propio con un correo asociado a una cuenta que utiliza Google o Apple no deberá añadir automáticamente una contraseña a esa cuenta.
- Tampoco deberá vincular métodos de acceso ni crear una cuenta duplicada con ese correo.
- Incorporar el acceso mediante contraseña a una cuenta existente requerirá el procedimiento establecido en RN-031.
- La coincidencia del correo no será suficiente para autorizar esa incorporación.

#### Mensajes ante coincidencias

Cuando una coincidencia de correo impida completar el registro, la aplicación deberá informar que el dato indicado ya está registrado y ofrecer las opciones correspondientes, conforme al lineamiento de unicidad de RN-025.

Se mostrará el siguiente mensaje:

“No pudimos continuar porque el correo electrónico o el documento indicado ya está registrado. Si ya tienes una cuenta, inicia sesión o recupera el acceso. Si ingresaste algún dato incorrectamente, revísalo e inténtalo nuevamente”.

Durante el registro propio, este mensaje responderá a la coincidencia del correo. La comprobación del documento se realizará posteriormente, al completar la identificación del propietario, conforme a RN-025.

El mensaje no deberá mostrar el correo de la cuenta existente, su titular, sus vehículos ni otros datos asociados a ella. Tampoco deberá informar públicamente si la cuenta está habilitada, pendiente de verificación o utiliza Google o Apple.

Mostrar el mensaje no autorizará el acceso, la recuperación, la modificación de credenciales ni la vinculación de métodos. Cada operación deberá cumplir su procedimiento correspondiente.

#### Contraseña olvidada durante el registro pendiente

- La recuperación se atenderá mediante RF-048 y las condiciones establecidas en RN-029.
- Recuperar la contraseña deberá conservar la misma cuenta pendiente.
- La recuperación no deberá verificar automáticamente el correo ni habilitar la cuenta.
- Tampoco deberá reiniciar ni ampliar el plazo de conservación establecido en RN-027.
- Después de recuperar la contraseña, el acceso continuará limitado a las acciones permitidas para el registro pendiente.
- Los casos de uso y mecanismos técnicos de recuperación deberán detallarse por separado, respetando RN-029.

#### Resultado esperado

El registro propio deberá:

- Solicitar únicamente los datos iniciales establecidos en esta regla.
- Aplicar las condiciones aprobadas del correo y la contraseña.
- Evitar la creación de cuentas duplicadas por coincidencia del correo.
- Impedir que una solicitud de registro sobrescriba credenciales o vincule métodos de acceso de una cuenta existente.
- Mantener separadas la creación de la cuenta, la verificación del correo y la validación de identidad y propiedad.
- Respetar las condiciones de continuidad y conservación del registro pendiente definidas en RN-027.

#### Definiciones posteriores relacionadas

Las condiciones funcionales de recuperación, gestión de métodos y registro mediante Google y Apple ya se desarrollan en RN-029, RN-031, RN-030 y RN-032, respectivamente.

Deberán desarrollarse por separado:

- Los casos de uso y mecanismos técnicos de recuperación de acceso correspondientes a RF-048 y RN-029.
- Los casos de uso y mecanismos técnicos para vincular, incorporar o retirar métodos de acceso, conforme a RN-031.
- Los datos y validaciones necesarios para identificar al propietario conforme a RN-025 y RF-043.
- Los casos de uso y mecanismos técnicos del registro mediante Google y Apple, conforme a RN-030 y RN-032.
- Los mecanismos técnicos para validar correos, proteger credenciales y comprobar contraseñas comunes o comprometidas.

Estas definiciones deberán respetar las condiciones aprobadas en esta regla.


---

### RN-029 — Recuperación de la contraseña propia

- ID: RN-029.
- Nombre: Recuperación de la contraseña propia.
- Módulo o capacidad: Identidad y acceso.
- Etapa prevista: Primera entrega del Propietario; reutilizable posteriormente por otros módulos.
- Estado de la definición: Aprobado en su alcance funcional. Los mecanismos técnicos de implementación deberán detallarse en los documentos correspondientes.
- Requerimientos relacionados: RF-001, RF-002, RF-048 y RF-049, definidos en `requerimientos-funcionales-propietario.md`.
- Reglas de negocio relacionadas: RN-026 — Mecanismos de registro y autenticación; RN-027 — Verificación del correo en el registro propio; RN-028 — Datos, contraseña y coincidencias del registro propio; RN-030 — Registro y autenticación mediante Google; RN-032 — Registro y autenticación mediante Apple.
- Requerimientos no funcionales relacionados: RNF-003 y RNF-021, definidos en `requerimientos-no-funcionales.md`.
- Caso de uso relacionado: Recuperar acceso a la cuenta; identificador y detalle pendientes en `casos-uso.md`.

#### Descripción

Vehículos Services deberá permitir restablecer la contraseña administrada por la plataforma mediante un código enviado al correo actualmente asociado a la cuenta.

El procedimiento deberá comprobar la autorización para realizar el cambio antes de modificar la contraseña. Conocer el correo, una placa, datos de un vehículo o información del perfil no será suficiente para autorizarlo.

La recuperación deberá conservar la misma cuenta, sus relaciones y sus restricciones. No deberá crear otra cuenta ni incorporar automáticamente un método de acceso.

#### Inicio de la recuperación

- La solicitud podrá iniciarse sin disponer de una sesión autenticada.
- El solicitante deberá indicar el correo de la cuenta.
- Cuando exista una cuenta que tenga contraseña propia y pueda utilizar este procedimiento, el código se enviará exclusivamente al correo actualmente asociado a ella.
- No se permitirá indicar un destinatario alternativo durante la recuperación.
- Solicitar la recuperación no modificará la contraseña, cerrará sesiones ni bloqueará el acceso ordinario.
- Recibir el código tampoco producirá esos efectos.
- Una cuenta pendiente de verificación podrá utilizar el procedimiento mientras su registro provisional se conserve conforme a RN-027.

#### Respuesta a la solicitud

La aplicación deberá utilizar una respuesta general que no revele si la cuenta existe, su estado o sus métodos de acceso.

Un mensaje permitido será:

“Si la cuenta dispone de recuperación por correo, recibirás instrucciones”.

La aplicación podrá mostrar una orientación general hacia la recuperación del proveedor externo, sin confirmar públicamente que una cuenta determinada utiliza Google o Apple.

Los controles técnicos deberán evitar que las diferencias en los tiempos de respuesta permitan deducir información restringida sobre las cuentas.

#### Código de recuperación

- El código deberá contener exactamente seis dígitos numéricos, del 0 al 9.
- Los ceros iniciales deberán conservarse.
- Su vigencia será de 10 minutos contados desde su generación.
- Al cumplirse los 10 minutos, se considerará vencido.
- Las demoras de envío o entrega no reiniciarán ni ampliarán la vigencia.
- El código será de uso único y quedará consumido cuando se complete el restablecimiento.
- Para una misma cuenta, deberá existir como máximo un código de recuperación válido a la vez.
- Generar un nuevo código invalidará el anterior del mismo proceso de recuperación.
- El código deberá estar asociado a la cuenta, al correo destinatario y a la finalidad de restablecer la contraseña propia.

#### Límites de generación

- Deberán transcurrir al menos 60 segundos desde la última generación de un código de recuperación para la cuenta antes de permitir generar otro.
- Se permitirá generar como máximo 5 códigos de recuperación por cuenta en un período móvil de 60 minutos.
- El primer código solicitado se incluirá en ese límite.
- Para evaluar una nueva solicitud, se contabilizarán las generaciones de recuperación realizadas durante los 60 minutos anteriores.
- Una generación que haya cumplido exactamente 60 minutos dejará de formar parte del período contabilizado.
- Una nueva generación requerirá cumplir tanto la espera mínima como el límite del período móvil.
- Una solicitud rechazada o que falle antes de generar un código no incrementará el contador, reiniciará la espera ni invalidará el código vigente.
- Un código generado contará dentro de los límites aunque posteriormente falle el envío o no pueda confirmarse su entrega.
- Alcanzar el límite de generación no impedirá utilizar un código de recuperación que conserve su validez.
- Los límites se aplicarán en el backend y no podrán reiniciarse cambiando de dispositivo o cerrando y abriendo la aplicación.

#### Límites de comprobación

- Cada código de recuperación vigente permitirá como máximo 5 comparaciones fallidas.
- Se considerará fallida una comparación cuando el valor presentado cumpla el formato de seis dígitos, pero no coincida con el código vigente de recuperación de la cuenta.
- Al alcanzar la quinta comparación fallida, el código deberá quedar invalidado.
- Si existen 4 comparaciones fallidas y la siguiente es correcta, el restablecimiento podrá completarse si se cumplen las demás condiciones.
- Un valor con formato inválido deberá rechazarse antes de compararlo y no incrementará el contador de comparaciones fallidas.
- Si no existe un código vigente, la solicitud deberá rechazarse sin incrementar un contador de comparación.
- Cada nuevo código de recuperación comenzará con su propio contador en cero.
- Estos controles limitarán el proceso de recuperación y no bloquearán por sí mismos el inicio de sesión ordinario de la cuenta.

#### Separación respecto de la verificación del registro

- Los códigos de recuperación y los códigos de verificación del registro serán autorizaciones distintas.
- Un código de recuperación no podrá verificar el correo del registro.
- Un código de verificación del registro no podrá restablecer la contraseña.
- Los contadores, tiempos de espera y límites de generación de ambos procesos serán independientes.
- Generar un código de recuperación no invalidará por sí mismo un código de verificación del registro, ni viceversa.
- Restablecer la contraseña de una cuenta pendiente no modificará su correo a verificado ni ampliará el plazo de conservación establecido en RN-027.

#### Restablecimiento de la contraseña

- El usuario deberá presentar el código de recuperación, la nueva contraseña y su confirmación.
- La nueva contraseña deberá cumplir las condiciones aprobadas en RN-028.
- El código deberá conservar su vigencia, no estar consumido ni invalidado y corresponder a la cuenta y al correo destinatario aplicables.
- Las comprobaciones requeridas y el cambio de contraseña deberán resolverse como una sola operación consistente.
- La contraseña anterior se conservará mientras el restablecimiento no se complete.
- Si la nueva contraseña o su confirmación incumplen las condiciones correspondientes, no se modificará la contraseña ni se consumirá el código.
- Corregir la nueva contraseña no reiniciará ni ampliará la vigencia del código.
- No deberá crearse una autorización reutilizable que permita omitir la comprobación del código al completar el cambio.

#### Efectos del restablecimiento exitoso

Cuando se complete el restablecimiento, la plataforma deberá:

- Guardar la nueva contraseña conforme a los mecanismos de protección definidos.
- Consumir el código utilizado.
- Invalidar los demás medios pendientes de recuperación de contraseña de esa cuenta.
- Invalidar todas las sesiones de Vehículos Services de la cuenta, independientemente del método con el que se hayan iniciado.
- Solicitar que el usuario vuelva a iniciar sesión mediante un mecanismo habilitado y vinculado a su cuenta.
- Mantener las restricciones, relaciones y permisos vigentes.

El procedimiento no iniciará sesión automáticamente.

Invalidar las sesiones de Vehículos Services no cerrará las sesiones del usuario en Google o Apple ni modificará sus credenciales con esos proveedores.

#### Comunicación al titular

- Al completar el cambio, se enviará un aviso al correo asociado a la cuenta.
- El aviso informará que la contraseña fue restablecida.
- No deberá incluir la contraseña ni el código de recuperación.
- Si falla el envío del aviso, se conservará el cambio realizado y no se restaurará la contraseña anterior.

#### Cuentas pendientes de verificación

- La recuperación podrá completarse únicamente mientras el registro provisional se conserve conforme a RN-027.
- El cambio conservará la misma cuenta pendiente.
- La cuenta seguirá pendiente de verificación del correo.
- No se reiniciará ni ampliará su plazo de conservación.
- Después del cambio, el usuario deberá autenticarse nuevamente y su acceso seguirá limitado a las acciones permitidas por RN-027.
- Si el plazo del registro provisional ya venció, no se permitirá completar la recuperación y será necesario iniciar un nuevo registro.

#### Cuentas que utilizan Google o Apple

- Cuando una cuenta utilice únicamente proveedores externos, este procedimiento no permitirá crear una contraseña propia.
- La recuperación de las credenciales de Google o Apple deberá realizarse mediante el procedimiento del proveedor correspondiente.
- Vehículos Services podrá ofrecer una orientación general hacia ese procedimiento.
- Cuando una cuenta tenga una contraseña propia y proveedores externos vinculados mediante un procedimiento aprobado, esta regla permitirá restablecer únicamente la contraseña administrada por Vehículos Services.
- El restablecimiento no incorporará, retirará ni modificará las vinculaciones con Google o Apple.

#### Pérdida de acceso al medio de recuperación

En la primera entrega no se ofrecerá una recuperación alternativa basada en:

- Placas o información de vehículos.
- Documentos vehiculares.
- Preguntas personales.
- Un nuevo correo indicado por el solicitante.

Cuando el usuario no tenga acceso al correo, Google o Apple, deberá recuperar el medio correspondiente mediante su proveedor.

Una recuperación asistida o un mecanismo alternativo requerirá una definición posterior antes de habilitarse.

#### Errores, repeticiones y solicitudes simultáneas

- Si una solicitud no llegó a procesarse, no deberá modificar la contraseña, consumir el código ni incrementar contadores.
- Si una comparación fallida fue procesada, su contabilización se conservará aunque la aplicación no haya recibido la respuesta.
- La repetición de una misma operación por pérdida de respuesta deberá recuperar su resultado sin duplicar cambios ni contadores.
- Una nueva acción independiente del usuario se considerará una nueva solicitud y deberá cumplir los controles correspondientes.
- Si el restablecimiento se completó, la pérdida de la respuesta no deberá revertirlo. La aplicación deberá recuperar el resultado y dirigir al inicio de sesión.
- Un error anterior a completar el restablecimiento conservará la contraseña existente.
- Si el código ya fue generado, un fallo de envío no restablecerá la validez del código anterior.
- Las solicitudes simultáneas no deberán permitir superar límites, mantener más de un código de recuperación válido ni utilizar una autorización dos veces.
- El restablecimiento deberá comprobar el estado vigente de la cuenta y del registro provisional, cuando corresponda, antes de confirmar el cambio.
- Los mecanismos técnicos de identificación de operaciones repetidas y resolución de concurrencia deberán definirse en arquitectura.

#### Conservación de relaciones y restricciones

La recuperación deberá conservar:

- La identidad de la cuenta.
- Los vehículos y sus relaciones de propiedad.
- El historial y la atribución de los registros.
- Los permisos y restricciones vigentes.
- Los demás métodos de acceso vinculados.

No deberá:

- Crear una cuenta duplicada.
- Transferir vehículos.
- Conceder permisos adicionales.
- Reactivar autorizaciones revocadas.
- Eliminar restricciones vigentes.
- Habilitar automáticamente una cuenta pendiente de verificación.

#### Información necesaria para aplicar la regla

El sistema deberá disponer de la información necesaria para determinar:

- La cuenta y el correo asociados al procedimiento.
- Si la cuenta tiene contraseña propia.
- El estado de la cuenta y la conservación del registro provisional, cuando corresponda.
- La referencia al código de recuperación vigente y los datos necesarios para comprobarlo de forma segura.
- Las fechas de generación y vencimiento.
- El estado de consumo o invalidación del código.
- Las generaciones necesarias para evaluar la espera y el período móvil.
- El número de comparaciones fallidas.
- El resultado de las operaciones necesario para resolver solicitudes repetidas.
- Las sesiones que deban invalidarse al completar el restablecimiento.

La trazabilidad deberá proteger la información de la cuenta y no deberá registrar contraseñas ni códigos como parte del historial del procedimiento.

#### Definiciones técnicas posteriores

La implementación deberá detallar en los documentos correspondientes:

- La generación, protección y comprobación segura de los códigos.
- El almacenamiento protegido de las contraseñas.
- La aplicación de límites y controles frente a solicitudes automatizadas.
- La protección de información en mensajes y tiempos de respuesta.
- La identificación de operaciones repetidas y el tratamiento de concurrencia.
- La invalidación de sesiones de Vehículos Services.
- El envío de códigos y avisos.
- La trazabilidad y conservación de registros técnicos.

Estas definiciones deberán respetar los comportamientos aprobados en esta regla.

---

### RN-030 — Registro y autenticación mediante Google

- ID: RN-030.
- Nombre: Registro y autenticación mediante Google.
- Módulo o capacidad: Identidad y acceso.
- Etapa prevista: Primera entrega del Propietario; reutilizable posteriormente por otros módulos.
- Estado de la definición: Aprobado en su alcance funcional. Los mecanismos técnicos de implementación deberán detallarse en los documentos correspondientes.
- Requerimientos relacionados: RF-001, RF-002, RF-043 y RF-048, definidos en `requerimientos-funcionales-propietario.md`.
- Reglas de negocio relacionadas: RN-025 — Cuenta de usuario e identidad del propietario; RN-026 — Mecanismos de registro y autenticación; RN-027 — Verificación del correo en el registro propio; RN-028 — Datos, contraseña y coincidencias del registro propio; RN-029 — Recuperación de la contraseña propia; RN-031 — Vinculación, incorporación y retiro de métodos de acceso; RN-032 — Registro y autenticación mediante Apple, considerando el estado de definición de cada regla.
- Referencias generales: Registro del propietario contemplado en `63.2.3` de `proyecto.md`.
- Casos de uso relacionados: CU-001 Crear cuenta y CU-002 Iniciar sesión; detalle pendiente en `casos-uso.md`.

#### Descripción

Vehículos Services deberá permitir crear una cuenta y autenticarse mediante Google.

La plataforma deberá comprobar la autenticación proporcionada por Google antes de crear la cuenta o conceder acceso. No solicitará ni gestionará la contraseña del proveedor.

La cuenta de Vehículos Services se asociará al identificador estable de la identidad de Google. El correo recibido no deberá utilizarse por sí solo para identificar la cuenta ni autorizar una vinculación.

El uso de Google deberá respetar la unicidad de la cuenta del propietario establecida en RN-025. Incorporar Google como método de acceso a una cuenta existente se realizará conforme a RN-031 y no deberá crear otra cuenta para el mismo propietario.

#### Información necesaria y opcional

Para completar el registro mediante Google deberán estar disponibles:

- El identificador estable de la identidad autenticada.
- El correo electrónico necesario para el registro.
- La información del proveedor necesaria para evaluar las condiciones de comprobación del correo.

El nombre y la fotografía del perfil serán opcionales. Su ausencia no impedirá por sí sola completar el registro.

No se solicitará acceso a Gmail, contactos, archivos o calendario para crear la cuenta o iniciar sesión.

La información utilizada deberá limitarse a los datos necesarios y autorizados para el registro, autenticación y perfil.

El registro mediante Google no exigirá una contraseña propia ni datos vehiculares.

#### Validación de la autenticación

- La autenticación deberá comprobarse mediante los mecanismos oficiales del proveedor y los controles técnicos correspondientes.
- No será suficiente recibir desde la aplicación un correo, nombre o identificador sin comprobar la autenticación que los respalda.
- Si la autenticación falla, se cancela o no puede validarse, no se completará el registro ni se concederá acceso.
- Si faltan elementos obligatorios para el registro, no se completará la creación de la cuenta.
- La validación técnica deberá realizarse en el backend conforme a la arquitectura y los controles de seguridad definidos.

#### Identificación de la cuenta

- Si el identificador estable de Google ya está vinculado a una cuenta de Vehículos Services, la autenticación deberá corresponder a esa cuenta.
- No se creará otra cuenta por el solo hecho de que cambie el correo recibido para una identidad de Google ya vinculada.
- El correo podrá utilizarse para detectar coincidencias durante un registro nuevo, pero no sustituirá al identificador estable del proveedor.
- Una identidad de Google podrá estar vinculada a una sola cuenta de Vehículos Services.
- Inicialmente, cada cuenta de Vehículos Services podrá vincular una sola identidad de Google.
- Una coincidencia no deberá producir una fusión de cuentas ni una transferencia de vehículos o información.

#### Comprobación del control del correo

Cuando Google permita acreditar el control actual del correo conforme a las condiciones aplicables del proveedor, podrá aceptarse esa comprobación para habilitar el registro:

- Para direcciones Gmail, deberán cumplirse las condiciones de autenticación aplicables.
- Para Google Workspace, deberá comprobarse que el proveedor informa el correo como verificado y que la identidad corresponde a una organización administrada por Google.

Una dirección externa utilizada para crear una cuenta de Google no se considerará comprobada únicamente porque el proveedor la presente como verificada.

Cuando la dirección no cumpla las condiciones anteriores, Vehículos Services deberá comprobar adicionalmente su control antes de habilitar la cuenta.

Esta distinción deberá basarse en la información validada del proveedor y no únicamente en el texto del dominio informado por la aplicación.

#### Comprobación adicional del correo

Para el registro mediante Google que requiera comprobación adicional, se adoptarán expresamente las siguientes condiciones de RN-027:

- Composición, vigencia y uso único del código.
- Invalidación del código anterior al generar uno nuevo.
- Espera mínima y límite de generación.
- Límite de intentos fallidos de comprobación.
- Acceso restringido mientras la comprobación esté pendiente.
- Tratamiento de errores, solicitudes repetidas y operaciones simultáneas.
- Conservación y eliminación del registro provisional.

No se duplicarán los valores de esos controles en esta regla. Su definición se conservará en RN-027.

La cuenta permanecerá pendiente hasta comprobar correctamente el correo. Durante ese estado no podrá gestionar vehículos ni consultar sus registros.

Para retomar el registro pendiente, deberá comprobarse la autenticación mediante la identidad de Google asociada a esa cuenta. No se exigirá una contraseña propia que no haya sido incorporada mediante un procedimiento aprobado.

Esta referencia no convertirá el registro mediante Google en un registro propio ni habilitará automáticamente sus demás procedimientos.

#### Coincidencias durante un registro nuevo

Si la identidad de Google todavía no está vinculada, pero el correo coincide con una cuenta existente:

- No se creará una cuenta duplicada.
- No se vinculará Google automáticamente.
- No se habilitará un registro pendiente por el solo hecho de autenticarse con Google.
- No se modificarán las credenciales ni los métodos de acceso de la cuenta existente.
- El usuario deberá acceder a la cuenta existente y realizar la vinculación conforme a RN-031.

Se mostrará el mensaje de coincidencia establecido en RN-025 y RN-028. La respuesta no deberá revelar públicamente datos personales, vehículos, el estado ni los métodos asociados a la cuenta existente.

Si el usuario creó una cuenta mediante Google con un correo diferente y posteriormente declara un tipo y número de documento asociados a otra cuenta, se aplicará RN-025: no se completará su identificación como propietario ni la asociación solicitada desde esa cuenta.

#### Acceso posterior

Cuando la identidad de Google ya esté vinculada, la plataforma deberá:

- Comprobar la autenticación del proveedor.
- Identificar la cuenta correspondiente.
- Aplicar su estado de habilitación, restricciones y permisos.
- Limitar el acceso al proceso pendiente cuando todavía corresponda completar el registro.

Autenticarse mediante Google no eliminará restricciones de la cuenta ni concederá permisos adicionales.

#### Cambios en la información de Google

Los cambios posteriores en el correo, nombre u otros datos del proveedor no deberán reemplazar automáticamente:

- El correo de contacto o recuperación de Vehículos Services.
- La identidad personal validada.
- Las relaciones de propiedad.
- La atribución de registros históricos.
- Otros datos del perfil sujetos a sus propias condiciones de modificación.

La vinculación se conservará mediante el identificador estable de Google.

Los cambios de información de la cuenta se realizarán conforme a RF-043 y las reglas correspondientes.

#### Fallos, cancelaciones y pérdida de acceso

- Una operación fallida o cancelada no deberá completar parcialmente un registro o una vinculación.
- La indisponibilidad de Google no habilitará automáticamente otro mecanismo.
- El usuario podrá utilizar otro método únicamente si ya está habilitado y vinculado a su cuenta.
- Si Google es el único método disponible y el usuario pierde el acceso, se aplicará la orientación de recuperación establecida en RN-029.
- Vehículos Services no modificará las credenciales de Google ni creará una contraseña propia mediante recuperación.

#### Restricciones de identidad y propiedad

La autenticación mediante Google y la comprobación del correo no acreditarán por sí solas:

- La identidad legal del propietario.
- La propiedad de un vehículo.
- La representación de una empresa.
- La autorización para actuar como Prestador de Servicios Vehiculares.

El nombre y la fotografía recibidos del proveedor no se utilizarán como prueba suficiente de esas condiciones.

Los datos necesarios para identificar al propietario y validar cada vehículo se obtendrán mediante los procedimientos correspondientes.

#### Definiciones técnicas posteriores

La implementación deberá detallar:

- La integración oficial con Google para Android e iOS.
- La comprobación de la autenticación y de los datos del proveedor en el backend.
- La asociación entre la identidad de Google y la cuenta interna.
- La evaluación de las condiciones de control del correo.
- La aplicación de RN-027 cuando corresponda la comprobación adicional.
- El tratamiento técnico de errores, cancelaciones y solicitudes simultáneas.
- La protección de la información utilizada para autenticación.

La incorporación y el retiro de métodos de acceso se desarrollan en RN-031.

Esta regla no define el registro mediante Apple, cuyas condiciones se desarrollan en RN-032.

---

### RN-031 — Vinculación, incorporación y retiro de métodos de acceso

- ID: RN-031.
- Nombre: Vinculación, incorporación y retiro de métodos de acceso.
- Módulo o capacidad: Identidad y acceso.
- Etapa prevista: Primera entrega del Propietario; reutilizable posteriormente por otros módulos.
- Estado de la definición: Aprobado en su alcance funcional para contraseña propia, Google y Apple. Los mecanismos técnicos de implementación deberán detallarse en los documentos correspondientes.
- Requerimientos relacionados: RF-001, RF-002, RF-043, RF-048 y RF-049, definidos en `requerimientos-funcionales-propietario.md`.
- Reglas de negocio relacionadas: RN-026 — Mecanismos de registro y autenticación; RN-027 — Verificación del correo en el registro propio; RN-028 — Datos, contraseña y coincidencias del registro propio; RN-029 — Recuperación de la contraseña propia; RN-030 — Registro y autenticación mediante Google; RN-032 — Registro y autenticación mediante Apple.
- Referencias generales: Mecanismos de registro y autenticación contemplados en `63.2.3` de `proyecto.md`.
- Caso de uso relacionado: Gestionar métodos de acceso; identificador y detalle pendientes en `casos-uso.md`.

#### Descripción

Vehículos Services deberá permitir incorporar o retirar métodos de acceso de una cuenta existente mediante un procedimiento que compruebe el control de los métodos correspondientes.

Estas operaciones deberán conservar la misma cuenta y no deberán crear cuentas duplicadas, fusionar cuentas ni transferir vehículos o información.

La disponibilidad de un mecanismo en la plataforma no implicará que esté vinculado a todas las cuentas.

Una cuenta podrá disponer de contraseña propia, Google y Apple vinculados. Cada método deberá incorporarse mediante su procedimiento.

#### Condiciones generales

- La operación deberá iniciarse desde una cuenta autenticada y habilitada.
- No se permitirá incorporar ni retirar métodos mientras la cuenta permanezca pendiente de completar su registro.
- El usuario deberá confirmar expresamente la operación.
- Tener una sesión abierta no será suficiente para autorizar el cambio.
- Se deberá realizar una nueva comprobación del método correspondiente dentro del procedimiento.
- Una comprobación fallida, incompleta o cancelada no deberá modificar los métodos vinculados.
- La operación deberá conservar al menos un método de acceso habilitado y utilizable.

#### Vinculación de Google

Para incorporar Google a una cuenta existente se deberá:

- Comprobar nuevamente el control de un método ya vinculado a la cuenta.
- Autenticar la identidad de Google que el usuario desea incorporar.
- Validar esa autenticación conforme a RN-030.
- Comprobar que la identidad de Google no esté vinculada a otra cuenta.
- Obtener la confirmación expresa del usuario.

Una identidad de Google podrá estar vinculada a una sola cuenta de Vehículos Services.

Inicialmente, cada cuenta de Vehículos Services podrá vincular una sola identidad de Google.

Si la identidad ya está vinculada a otra cuenta, se rechazará la operación sin fusionar cuentas, transferir relaciones ni modificar las vinculaciones existentes.

Si la cuenta ya dispone de otra identidad de Google vinculada, no se reemplazará automáticamente mediante una nueva solicitud de vinculación.

#### Vinculación de Apple

Para incorporar Apple a una cuenta existente se deberá:

- Comprobar nuevamente el control de un método ya vinculado a la cuenta.
- Autenticar la identidad de Apple que el usuario desea incorporar.
- Validar esa autenticación conforme a RN-032.
- Comprobar que la identidad de Apple no esté vinculada a otra cuenta.
- Obtener la confirmación expresa del usuario.

Una identidad de Apple podrá estar vinculada a una sola cuenta de Vehículos Services.

Inicialmente, cada cuenta de Vehículos Services podrá vincular una sola identidad de Apple.

Si la identidad ya está vinculada a otra cuenta, se rechazará la operación sin fusionar cuentas, transferir relaciones ni modificar las vinculaciones existentes.

Si la cuenta ya dispone de otra identidad de Apple vinculada, no se reemplazará automáticamente mediante una nueva solicitud de vinculación.

Utilizar una dirección privada de Apple no impedirá por sí solo realizar la vinculación.

#### Correos diferentes entre métodos

El correo de Google o Apple podrá ser distinto del correo asociado a la cuenta de Vehículos Services.

La diferencia no impedirá por sí sola la vinculación, siempre que se compruebe el control de la cuenta existente y de la identidad externa que se incorpora.

La coincidencia entre correos tampoco sustituirá esas comprobaciones.

Vincular Google o Apple no deberá cambiar automáticamente el correo de contacto o recuperación de la cuenta.

#### Incorporación de una contraseña propia

Una cuenta que utilice un proveedor externo podrá incorporar una contraseña propia mediante una acción específica de gestión de métodos.

Para completar la operación se deberá:

- Comprobar nuevamente la autenticación mediante un proveedor vinculado.
- Comprobar el control del correo asociado a la cuenta de Vehículos Services mediante el código específico de incorporación.
- Solicitar una contraseña y su confirmación.
- Aplicar las condiciones de contraseña establecidas en RN-028.
- Obtener la confirmación expresa del usuario.

No se utilizará una nueva solicitud de registro para incorporar la contraseña.

Tampoco se utilizará el procedimiento de recuperación de RN-029, porque este restablece una contraseña propia existente y no incorpora un método nuevo.

Antes de guardar el cambio se deberán comprobar la nueva autenticación con el proveedor vinculado, el código vigente, la contraseña y su confirmación.

Si la operación no se completa, se conservarán los métodos anteriores.

#### Código para incorporar una contraseña

- El código se enviará exclusivamente al correo asociado a la cuenta de Vehículos Services.
- No se permitirá indicar otro destinatario dentro de la operación.
- Contendrá exactamente seis dígitos numéricos y conservará los ceros iniciales.
- Tendrá una vigencia de 10 minutos contados desde su generación.
- Al cumplirse los 10 minutos, se considerará vencido.
- Las demoras de entrega no reiniciarán ni ampliarán su vigencia.
- Será de uso único y se consumirá únicamente cuando se complete la incorporación de la contraseña.
- Para la misma cuenta existirá como máximo un código válido de incorporación de contraseña a la vez.
- Generar otro código de esta finalidad invalidará el anterior.

Este código autorizará únicamente incorporar una contraseña propia. No podrá utilizarse para verificar un registro, recuperar una contraseña existente ni autorizar otras modificaciones.

Los códigos, contadores y tiempos de este proceso serán independientes de los procesos definidos en RN-027 y RN-029.

#### Límites del código de incorporación

- Deberán transcurrir al menos 60 segundos desde la última generación de un código de incorporación para la cuenta antes de permitir generar otro.
- Se permitirá generar como máximo 5 códigos de incorporación por cuenta en un período móvil de 60 minutos.
- El primer código generado se incluirá en ese límite.
- Para evaluar una nueva solicitud, se contabilizarán las generaciones de esta finalidad realizadas durante los 60 minutos anteriores.
- Una generación que haya cumplido exactamente 60 minutos dejará de formar parte del período contabilizado.
- Una nueva generación requerirá cumplir tanto la espera mínima como el límite del período móvil.
- Una solicitud rechazada o que falle antes de generar un código no incrementará el contador, reiniciará la espera ni invalidará el código vigente.
- Un código generado contará dentro de los límites aunque posteriormente falle el envío.
- Cada código vigente permitirá como máximo 5 comparaciones fallidas.
- Se considerará fallida una comparación cuando el valor presentado cumpla el formato requerido, pero no coincida con el código vigente de incorporación de la cuenta.
- La quinta comparación fallida invalidará el código.
- Un valor con formato inválido se rechazará antes de compararlo y no incrementará el contador.
- Si no existe un código vigente, la solicitud se rechazará sin incrementar un contador de comparación.
- Cada nuevo código comenzará con su propio contador de comparaciones fallidas en cero.
- Los controles se aplicarán en el backend y no se reiniciarán al cambiar de dispositivo o volver a abrir la aplicación.

Si la nueva contraseña o su confirmación incumplen RN-028, no se incorporará el método ni se consumirá el código. Corregir esos datos no ampliará la vigencia.

#### Correo privado sin entrega disponible

Cuando el correo asociado sea una dirección privada de Apple, el envío deberá cumplir las condiciones de RN-032.

Si el usuario desactivó la retransmisión o no recibe el código:

- No se omitirá la comprobación.
- No se aceptará otro destinatario dentro de la operación.
- No se incorporará la contraseña sin completar las comprobaciones.
- El usuario podrá seguir utilizando un método externo vinculado que conserve su disponibilidad.

El cambio del correo de una cuenta habilitada deberá realizarse mediante su procedimiento específico.

#### Retiro de un método

- El usuario deberá seleccionar el método que desea retirar.
- Se deberá comprobar nuevamente el control de un método que permanecerá vinculado y disponible.
- La comprobación deberá corresponder a la misma cuenta.
- Se deberá obtener la confirmación expresa del retiro.
- No se permitirá retirar el último método disponible.
- La autenticación mediante el método que se desea retirar no sustituirá la comprobación del método que permanecerá.
- Si no puede comprobarse el método restante, la operación no deberá completarse.
- Después del retiro, el método eliminado no podrá utilizarse para acceder a esa cuenta.
- El retiro no eliminará la cuenta ni modificará las credenciales del proveedor externo.

#### Efectos de una operación exitosa

Cuando se complete la incorporación o el retiro de un método, se deberá:

- Registrar el cambio en la misma cuenta.
- Consumir el código de incorporación cuando corresponda.
- Invalidar las sesiones anteriores de Vehículos Services de esa cuenta.
- Solicitar un nuevo inicio de sesión mediante un método que permanezca habilitado y vinculado.
- Enviar un aviso al correo asociado a la cuenta.

La invalidación de sesiones de Vehículos Services no cerrará las sesiones del usuario en Google o Apple ni modificará sus credenciales con esos proveedores.

El aviso no deberá contener contraseñas, códigos ni elementos secretos de autenticación.

Si falla el envío del aviso, se conservará la operación completada.

#### Conservación de la cuenta y sus relaciones

La incorporación o el retiro de un método deberá conservar:

- El identificador de la cuenta.
- La identidad personal y sus validaciones existentes.
- Los vehículos y las relaciones de propiedad.
- El historial y la atribución de los registros.
- Las autorizaciones y restricciones vigentes.
- Los demás métodos vinculados que no formen parte del cambio.

Estas operaciones no deberán:

- Crear una cuenta duplicada.
- Fusionar cuentas existentes.
- Transferir vehículos.
- Conceder permisos adicionales.
- Reactivar autorizaciones revocadas.
- Eliminar restricciones de la cuenta.
- Sustituir automáticamente el correo de contacto o recuperación.

#### Errores y operaciones incompletas

- Si una comprobación falla o el usuario cancela, se conservarán los métodos existentes.
- No deberán aplicarse cambios parciales que dejen la cuenta sin un método disponible.
- Una indisponibilidad del proveedor no permitirá omitir las comprobaciones ni utilizar un método que no esté vinculado.
- La pérdida de acceso a un método se atenderá conforme a las condiciones de recuperación correspondientes; no autorizará por sí sola su sustitución.
- La repetición de una misma operación por pérdida de respuesta deberá recuperar su resultado sin duplicar cambios ni contadores.
- Una nueva acción independiente del usuario se considerará una nueva solicitud y deberá cumplir los controles correspondientes.
- Si una comparación fallida fue procesada, se conservará su contabilización aunque la aplicación no haya recibido la respuesta.
- Si una operación se completó, la pérdida de la respuesta no deberá revertirla.
- Las solicitudes simultáneas no deberán superar los límites ni utilizar dos veces una autorización.
- Un fallo de conexión o de envío no ampliará la vigencia del código.

#### Información necesaria para aplicar la regla

El sistema deberá disponer de la información necesaria para determinar:

- La cuenta sobre la que se realiza la operación.
- Su estado de habilitación.
- Los métodos actualmente vinculados.
- El método que se desea incorporar o retirar.
- El resultado de las nuevas comprobaciones de autenticación.
- La identidad estable de Google o Apple, cuando corresponda.
- La confirmación del usuario.
- El correo destinatario del código de incorporación.
- La referencia al código vigente y los datos necesarios para comprobarlo de forma segura.
- Las fechas de generación y vencimiento y el estado de consumo o invalidación.
- Los contadores necesarios para aplicar los límites.
- Los métodos que permanecerán disponibles después del cambio.
- Las sesiones que deban invalidarse.
- El resultado de las operaciones necesario para resolver solicitudes repetidas.

La trazabilidad deberá identificar la operación y su resultado sin registrar contraseñas, códigos ni otros secretos de autenticación.

#### Definiciones técnicas posteriores

La implementación deberá detallar:

- Los mecanismos de nueva autenticación con los métodos vinculados.
- La generación, protección y comprobación del código de incorporación.
- La aplicación de tiempos, límites y contadores independientes.
- La protección y almacenamiento de las credenciales.
- La consistencia de los cambios y el tratamiento de solicitudes simultáneas o repetidas.
- La invalidación de sesiones.
- El envío de códigos y avisos, incluyendo las direcciones privadas de Apple.
- Los casos de uso correspondientes.

Estas definiciones deberán respetar las condiciones funcionales aprobadas en esta regla.

---

### RN-032 — Registro y autenticación mediante Apple

- ID: RN-032.
- Nombre: Registro y autenticación mediante Apple.
- Módulo o capacidad: Identidad y acceso.
- Etapa prevista: Primera entrega del Propietario en Android e iOS; reutilizable posteriormente por otros módulos.
- Estado de la definición: Aprobado en su alcance funcional. Los mecanismos técnicos de implementación deberán detallarse en los documentos correspondientes.
- Requerimientos relacionados: RF-001, RF-002, RF-043 y RF-048, definidos en `requerimientos-funcionales-propietario.md`.
- Reglas de negocio relacionadas: RN-025 — Cuenta de usuario e identidad del propietario; RN-026 — Mecanismos de registro y autenticación; RN-027 — Verificación del correo en el registro propio; RN-028 — Datos, contraseña y coincidencias del registro propio; RN-029 — Recuperación de la contraseña propia; RN-031 — Vinculación, incorporación y retiro de métodos de acceso, considerando el estado de definición de cada regla.
- Referencias generales: Registro del propietario contemplado en `63.2.3` de `proyecto.md`.
- Casos de uso relacionados: CU-001 Crear cuenta y CU-002 Iniciar sesión; detalle pendiente en `casos-uso.md`.

#### Descripción

Vehículos Services deberá permitir crear una cuenta e iniciar sesión mediante Apple en Android e iOS desde la primera entrega del Propietario.

La integración deberá permitir acceder a la misma cuenta desde ambas plataformas mediante la identidad de Apple vinculada, sin exigir incorporar otro método de acceso.

La plataforma deberá comprobar la autenticación proporcionada por Apple antes de crear la cuenta o conceder acceso. No solicitará ni gestionará la contraseña del proveedor.

La asociación se realizará mediante el identificador estable de Apple validado por el backend. El correo no deberá utilizarse como único identificador ni autorizar por sí solo una vinculación.

El uso de Apple deberá respetar la unicidad de la cuenta del propietario establecida en RN-025. Incorporar Apple como método de acceso a una cuenta existente se realizará conforme a RN-031 y no deberá crear otra cuenta para el mismo propietario.

#### Información del registro

Para completar el registro deberán estar disponibles:

- El identificador estable de la identidad autenticada.
- El correo autorizado por Apple.
- La información necesaria para comprobar la autenticación y el estado de verificación del correo.

El nombre será opcional.

No se exigirá una contraseña propia, fotografía ni datos vehiculares para crear la cuenta mediante Apple.

La información recibida no acreditará por sí sola la identidad legal del propietario ni la propiedad de un vehículo.

#### Uso de un correo privado

- El usuario podrá compartir su correo personal o utilizar la dirección privada de retransmisión proporcionada por Apple.
- La dirección privada deberá aceptarse como correo del registro.
- No se exigirá revelar el correo personal para completar la creación de la cuenta.
- La dirección autorizada se utilizará para las comunicaciones correspondientes de Vehículos Services.
- No se intentará deducir el correo personal a partir de la dirección privada.

El uso de una dirección privada no eliminará la comprobación posterior de unicidad del tipo y número de documento conforme a RN-025.

#### Validación de la autenticación

- La autenticación deberá comprobarse en el backend mediante los mecanismos oficiales del proveedor y los controles técnicos correspondientes.
- Recibir un correo o identificador desde la aplicación sin validar la autenticación que lo respalda no será suficiente.
- Una autenticación fallida, cancelada o no comprobable no deberá completar el registro ni conceder acceso.
- Si faltan elementos obligatorios para crear la cuenta, el registro no deberá completarse.
- La validación deberá corresponder a la integración autorizada de Vehículos Services.

#### Comprobación del correo

Cuando la autenticación validada de Apple confirme el correo como verificado, podrá aceptarse esa comprobación para completar la condición de control del correo.

Cuando no pueda confirmarse, Vehículos Services deberá realizar una comprobación adicional antes de habilitar la cuenta.

Para esa comprobación adicional se adoptarán expresamente las condiciones pertinentes de RN-027:

- Composición, vigencia y uso único del código.
- Invalidación del código anterior al generar uno nuevo.
- Espera mínima y límite de generación.
- Límite de intentos fallidos.
- Acceso restringido mientras la comprobación esté pendiente.
- Tratamiento de errores, repeticiones y operaciones simultáneas.
- Conservación y eliminación del registro provisional.

Esta referencia no convertirá el registro mediante Apple en un registro propio ni exigirá una contraseña que no haya sido incorporada.

Para retomar un registro pendiente, deberá comprobarse la autenticación mediante la identidad de Apple asociada a esa cuenta.

#### Conservación de la información inicial

- La plataforma deberá conservar los datos necesarios obtenidos durante el registro.
- En accesos posteriores no se exigirá que Apple vuelva a proporcionar el nombre o todos los datos iniciales cuando la identidad ya esté vinculada y la información necesaria esté disponible.
- La identificación de la cuenta deberá continuar basándose en el identificador estable del proveedor.
- La ausencia de un nombre en una autenticación posterior no impedirá por sí sola acceder a una cuenta existente.

#### Coincidencias y exclusividad

Si el identificador de Apple ya está vinculado, la autenticación deberá corresponder a esa cuenta de Vehículos Services.

Si todavía no está vinculado, pero el correo coincide con una cuenta existente:

- No se creará una cuenta duplicada.
- No se fusionarán cuentas.
- No se vinculará Apple automáticamente.
- No se habilitará un registro pendiente por el solo hecho de autenticarse con Apple.
- El usuario deberá acceder a la cuenta existente y realizar la vinculación conforme a RN-031.

Una identidad de Apple podrá estar vinculada a una sola cuenta de Vehículos Services.

Inicialmente, cada cuenta de Vehículos Services podrá vincular una sola identidad de Apple.

Se mostrará el mensaje de coincidencia establecido en RN-025 y RN-028. La respuesta no deberá revelar públicamente datos personales, vehículos, el estado ni los métodos de acceso de una cuenta existente.

Si el usuario creó una cuenta mediante Apple con un correo diferente, incluida una dirección privada, y posteriormente declara un tipo y número de documento asociados a otra cuenta, se aplicará RN-025: no se completará su identificación como propietario ni la asociación solicitada desde esa cuenta.

#### Vinculación y retiro de Apple

La incorporación y el retiro de Apple se regirán por RN-031.

Se requerirán:

- Una cuenta habilitada.
- Confirmación expresa del usuario.
- Nuevas comprobaciones de los métodos correspondientes.
- Conservación de al menos un método de acceso habilitado y utilizable.

La incorporación no modificará automáticamente el correo de contacto o recuperación.

El retiro no eliminará la cuenta, transferirá vehículos ni modificará las credenciales del usuario en Apple.

Una cuenta podrá disponer de contraseña propia, Google y Apple vinculados. Cada método deberá incorporarse mediante su procedimiento; disponer de uno no habilitará automáticamente los demás.

#### Acceso y restricciones

Una autenticación válida mediante Apple deberá identificar la cuenta correspondiente y aplicar su estado, restricciones y permisos.

No deberá:

- Conceder propiedad sobre vehículos.
- Otorgar facultades de representación.
- Eliminar restricciones vigentes.
- Reactivar autorizaciones revocadas.
- Habilitar otras formas de acceso que no estén vinculadas.

#### Recuperación de acceso

- Vehículos Services no modificará la contraseña de Apple.
- Una cuenta que utilice únicamente Apple deberá recuperar el acceso mediante el proveedor.
- La plataforma podrá ofrecer una orientación general hacia ese procedimiento.
- Si la cuenta tiene una contraseña propia vinculada, podrá restablecerla conforme a RN-029.
- La recuperación no incorporará automáticamente una contraseña propia ni modificará la vinculación con Apple.

#### Cambios y revocación de la autorización

- Los cambios en la información del proveedor no deberán sobrescribir automáticamente el perfil, correo de contacto, correo de recuperación o identidad validada de Vehículos Services.
- La asociación con la cuenta se conservará mediante el identificador estable correspondiente.
- Si Apple revoca la autorización, no se permitirán nuevos accesos mediante esa autorización.
- Se invalidarán las sesiones de Vehículos Services correspondientes a la autorización revocada.
- La revocación no eliminará la cuenta, sus vehículos, historial ni relaciones.
- Otros métodos vinculados podrán utilizarse conforme a sus condiciones de acceso.

#### Comunicaciones mediante correo privado

La integración deberá configurar los remitentes necesarios para enviar códigos y avisos mediante el servicio de retransmisión de Apple.

Un fallo de entrega no deberá verificar un correo ni autorizar una operación.

Si el usuario desactivó la retransmisión o no recibe un código necesario:

- No se omitirá la comprobación.
- No se aceptará otro destinatario dentro de esa operación.
- Podrá seguir utilizando su método externo si conserva su disponibilidad.
- El cambio de correo de una cuenta habilitada deberá seguir su procedimiento específico.

#### Definiciones técnicas posteriores

La implementación deberá detallar:

- La integración oficial con Apple para Android e iOS.
- La correspondencia de la identidad del proveedor con la misma cuenta interna en ambas plataformas.
- La comprobación de la autenticación en el backend.
- La conservación de los datos iniciales.
- La configuración del correo privado y de los remitentes autorizados.
- La comprobación adicional del correo cuando corresponda.
- El tratamiento de fallos, cancelaciones y revocaciones.
- La invalidación de sesiones afectadas.
- La aplicación de RN-031 a las operaciones de vinculación y retiro.

Estas definiciones deberán respetar las condiciones funcionales aprobadas en esta regla.

---

### RN-033 — Cierre de sesión y protección de información local

- ID: RN-033.
- Nombre: Cierre de sesión y protección de información local.
- Módulo o capacidad: Identidad y acceso.
- Etapa prevista: Primera entrega del Propietario en Android e iOS; reutilizable posteriormente por otros módulos.
- Estado de la definición: Aprobado en su alcance funcional. Los mecanismos técnicos de implementación deberán detallarse en los documentos correspondientes.
- Requerimientos relacionados: RF-002 y RF-049, definidos en `requerimientos-funcionales-propietario.md`.
- Reglas de negocio relacionadas: RN-029 — Recuperación de la contraseña propia; RN-031 — Vinculación, incorporación y retiro de métodos de acceso; RN-032 — Registro y autenticación mediante Apple.
- Requerimientos no funcionales relacionados: RNF-003 y RNF-021, definidos en `requerimientos-no-funcionales.md`.
- Caso de uso relacionado: Cerrar sesión; identificador y detalle pendientes en `casos-uso.md`.

#### Descripción

Vehículos Services deberá permitir cerrar la sesión desde la aplicación, retirar el acceso local y finalizar la autorización de esa sesión en el backend.

El cierre deberá impedir que otra persona que utilice el dispositivo acceda a información privada de la cuenta mediante pantallas anteriores, datos conservados por la aplicación o elementos de sesión.

Cerrar sesión no eliminará la cuenta ni modificará sus vehículos, historial, permisos o métodos de acceso vinculados.

#### Alcance del cierre manual

- El cierre se aplicará únicamente a la sesión desde la que se solicita.
- La primera entrega no incluirá una opción manual para cerrar otras sesiones o todas las sesiones de la cuenta.
- Se mantendrán los cierres generales ya aprobados para recuperación de contraseña y cambios de métodos de acceso.
- Los demás dispositivos conservarán sus sesiones, salvo que corresponda una invalidación por otro evento aprobado.

#### Cambios sin guardar

- Si existen cambios sin guardar, la aplicación deberá advertir que se perderán al cerrar sesión.
- El usuario podrá cancelar el cierre y continuar con esos cambios.
- Si confirma el cierre, los cambios se descartarán.
- La aplicación no deberá guardarlos ni enviarlos automáticamente como consecuencia del cierre.

#### Operaciones en curso

- Al confirmar el cierre, la aplicación deberá detener nuevos envíos de operaciones de la sesión.
- Deberá intentar cancelar los envíos o tareas pendientes que puedan cancelarse.
- Una operación ya completada en el servidor conservará su resultado.
- Cerrar sesión no deberá revertir operaciones completadas.
- Si una operación fue enviada, pero no se recibió su respuesta, no deberá presentarse como exitosa ni repetirse automáticamente al iniciar sesión nuevamente.
- Después de una nueva autenticación, el resultado desconocido deberá consultarse mediante el mecanismo correspondiente y conforme a los permisos vigentes.

#### Cierre con conexión

Cuando pueda completarse la comunicación con el backend:

- Se deberá invalidar la sesión correspondiente.
- Se retirarán del dispositivo los elementos que permitan utilizar o renovar esa sesión.
- El backend deberá rechazar nuevas operaciones protegidas realizadas con la sesión invalidada.
- La sesión invalidada no podrá renovarse.
- Para volver a acceder a funcionalidades protegidas, el usuario deberá autenticarse nuevamente conforme a RF-002.

#### Cierre sin conexión o con invalidación pendiente

Si no existe conexión o no puede confirmarse la invalidación en el backend:

- La aplicación deberá retirar inmediatamente el acceso local después de confirmar el cierre.
- No permitirá seguir consultando información privada ni realizando acciones mediante la sesión anterior.
- Deberá informar que la invalidación en el servidor permanece pendiente.
- Reintentará la invalidación cuando recupere la conexión.
- El reintento no deberá restaurar el acceso local ni renovar la sesión anterior.
- No deberá afirmar que la invalidación remota se completó mientras no pueda confirmarla.

Un mensaje permitido será:

“Sesión cerrada en este dispositivo; la invalidación en el servidor está pendiente”.

El cierre local y la invalidación remota deberán mantenerse diferenciados. Retirar el acceso del dispositivo no acreditará por sí solo que el servidor recibió la solicitud.

#### Información mínima para completar la invalidación

Mientras la invalidación remota permanezca pendiente, podrá conservarse únicamente el elemento mínimo protegido necesario para completar esa solicitud.

Ese elemento no deberá permitir que la aplicación:

- Consulte información de la cuenta.
- Ejecute operaciones protegidas distintas de la invalidación.
- Renueve la sesión anterior.
- Restablezca el acceso local.

El mecanismo técnico deberá definirse en arquitectura y seguridad, respetando estas restricciones.

#### Tratamiento de información local

Al cerrar sesión, la aplicación deberá retirar los datos privados de la cuenta de:

- Pantallas abiertas.
- Memoria utilizada por la sesión.
- Cachés de información privada.
- Borradores y cambios descartados.

Podrán conservarse preferencias generales que no expongan información de la cuenta, como idioma o apariencia.

La navegación hacia pantallas anteriores no deberá permitir recuperar información privada sin una nueva autenticación.

El tratamiento técnico de los datos locales deberá respetar los controles de seguridad aplicables.

#### Archivos exportados por el usuario

El cierre no deberá borrar archivos que el usuario haya guardado expresamente fuera del almacenamiento privado de la aplicación.

La aplicación no deberá presentar el cierre como una garantía de eliminación de esas copias externas.

Esta condición no permitirá conservar accesible información privada dentro de la aplicación después del cierre.

#### Inicio de sesión con otra cuenta

Si otra cuenta inicia sesión en el mismo dispositivo:

- No podrá visualizar información privada de la cuenta anterior.
- No podrá continuar sus borradores u operaciones.
- No heredará sus autorizaciones ni elementos de sesión.
- Los resultados pendientes de operaciones anteriores no deberán mostrarse en el contexto de la nueva cuenta.

#### Notificaciones del dispositivo

- Se deberá desvincular la sesión cerrada del envío de notificaciones dirigidas a esa cuenta en el dispositivo.
- Al completarse la desvinculación, esas notificaciones deberán detenerse para el dispositivo correspondiente.
- Si la desvinculación permanece pendiente, la aplicación no deberá mostrar contenido privado recibido para la sesión cerrada.
- El cierre no deberá desactivar las notificaciones de otros dispositivos que conserven sesiones válidas.

#### Interacción con Google y Apple

- El cierre corresponderá a la sesión de Vehículos Services.
- No deberá presentarse como cierre de las sesiones del usuario en Google o Apple.
- No retirará la vinculación con el proveedor.
- No modificará sus credenciales.
- Cerrar sesión no deberá provocar un reingreso automático.
- Seleccionar nuevamente un proveedor será una nueva acción de autenticación, sujeta a RF-002 y a las reglas correspondientes.

#### Conservación de la cuenta y sus relaciones

Cerrar sesión deberá conservar:

- La cuenta.
- Los vehículos y sus relaciones de propiedad.
- El historial y los registros asociados.
- Los permisos y autorizaciones existentes.
- Los métodos de acceso vinculados.

No deberá interpretarse como eliminación de la cuenta, transferencia de propiedad o revocación de una relación de representación.

#### Definiciones técnicas posteriores

La implementación deberá detallar:

- La invalidación de la sesión en el backend.
- El retiro de elementos de acceso y datos privados del dispositivo.
- El mecanismo restringido para completar una invalidación pendiente.
- El tratamiento de operaciones en curso y resultados desconocidos.
- La protección frente a navegación hacia pantallas anteriores.
- La separación de información entre cuentas utilizadas en el mismo dispositivo.
- La desvinculación de notificaciones.
- La interacción con los mecanismos de autenticación externos.
- El caso de uso de cierre de sesión.

La duración y renovación general de sesiones se definirán conforme a RNF-021. Este punto establece el comportamiento del cierre manual y no sustituye esas definiciones.

---
### RN-034 — Vigencia de sesiones y control de intentos de autenticación

- ID: RN-034.
- Nombre: Vigencia de sesiones y control de intentos de autenticación.
- Módulo o capacidad: Identidad y acceso.
- Etapa prevista: Primera entrega del Propietario en Android e iOS; reutilizable posteriormente por otros módulos.
- Estado de la definición: Aprobado en su alcance funcional. Los mecanismos técnicos de implementación deberán detallarse en los documentos correspondientes.
- Requerimientos relacionados: RF-001, RF-002, RF-048 y RF-049, definidos en `requerimientos-funcionales-propietario.md`.
- Reglas de negocio relacionadas: RN-027 — Verificación del correo en el registro propio; RN-029 — Recuperación de la contraseña propia; RN-030 — Registro y autenticación mediante Google; RN-031 — Vinculación, incorporación y retiro de métodos de acceso; RN-032 — Registro y autenticación mediante Apple; RN-033 — Cierre de sesión y protección de información local.
- Requerimientos no funcionales relacionados: RNF-003 y RNF-021, definidos en `requerimientos-no-funcionales.md`.
- Caso de uso relacionado: CU-002 Iniciar sesión; detalle pendiente en `casos-uso.md`.

#### Descripción

Vehículos Services deberá mantener las sesiones dentro de límites definidos de duración e inactividad y controlar los intentos fallidos de autenticación mediante contraseña propia.

La vigencia de una sesión no sustituirá las comprobaciones de habilitación de la cuenta ni sus permisos sobre vehículos y otros recursos.

Los controles deberán aplicarse en el backend. La información conservada en el dispositivo no permitirá ampliar plazos, renovar sesiones invalidadas ni recuperar permisos retirados.

#### Permanencia de la sesión

- Cerrar y volver a abrir la aplicación no equivaldrá a cerrar sesión.
- La aplicación podrá conservar el acceso entre usos mientras la sesión siga vigente y se cumplan las demás condiciones aplicables.
- La conservación deberá proteger los elementos de sesión conforme a los controles de seguridad.
- Una sesión cerrada mediante RF-049 y RN-033 no deberá restablecerse automáticamente al abrir la aplicación.

#### Duración máxima

- Cada sesión tendrá una duración máxima de 30 días contados desde la autenticación que la creó.
- Al cumplirse ese plazo, la sesión vencerá aunque exista actividad reciente.
- Para continuar utilizando funcionalidades protegidas, el usuario deberá autenticarse nuevamente.
- La actividad y la renovación técnica no reiniciarán el plazo máximo de la sesión.
- Los días se contabilizarán como períodos de 24 horas.

#### Vencimiento por inactividad

- La sesión vencerá después de 7 días consecutivos sin actividad del usuario reconocida por el backend.
- El plazo se contará desde la creación de la sesión o desde su última actividad válida, según corresponda.
- Se aplicará el límite que se cumpla primero: inactividad o duración máxima.
- Al cumplirse exactamente el plazo correspondiente, la sesión se considerará vencida.

#### Actividad válida

Se considerarán actividad válida las consultas o acciones autenticadas iniciadas por el usuario y reconocidas por el backend.

No reiniciarán el plazo de inactividad:

- La recepción de notificaciones.
- Las tareas automáticas.
- Las renovaciones en segundo plano.
- La sola conservación de la aplicación o de elementos de sesión en el dispositivo.

#### Renovación de elementos de sesión

- Podrán renovarse los elementos técnicos de una sesión vigente sin exigir nuevamente las credenciales.
- La renovación deberá comprobar la vigencia y el estado de la sesión.
- No deberá reiniciar su duración máxima ni contabilizarse por sí sola como actividad del usuario.
- No podrá renovar ni reactivar una sesión vencida, cerrada o invalidada.
- No deberá recuperar permisos o autorizaciones retirados.
- Los tiempos y mecanismos de los elementos técnicos se definirán en arquitectura y seguridad.

#### Sesiones simultáneas

- La misma cuenta podrá utilizarse en varios dispositivos.
- Cada sesión tendrá sus propios tiempos de creación, actividad y vencimiento.
- Iniciar sesión en otro dispositivo no cerrará automáticamente las sesiones existentes.
- El cierre manual se aplicará conforme a RN-033.
- Los eventos que invalidan varias sesiones conservarán los efectos definidos en sus reglas correspondientes.
- Los controles técnicos contra abuso deberán respetar este comportamiento.

#### Registros pendientes de habilitación

- Los límites de sesión también se aplicarán a los accesos permitidos durante un registro pendiente.
- La sesión permanecerá restringida conforme a RN-027, RN-030 o RN-032.
- Una sesión vigente no habilitará la gestión de vehículos mientras el registro no cumpla las condiciones correspondientes.
- La creación, actividad o renovación de una sesión no ampliará el plazo de conservación del registro provisional.
- Al vencer o eliminarse ese registro, no podrá continuarse su proceso mediante una sesión conservada anteriormente.

#### Operaciones que requieren nueva autenticación

Una sesión vigente no sustituirá la nueva comprobación exigida por RN-031 para incorporar o retirar métodos de acceso.

Las operaciones deberán cumplir las comprobaciones específicas de su regla antes de modificar la cuenta.

#### Invalidación y permisos

- Se aplicarán los eventos y efectos de invalidación establecidos en RN-029, RN-031, RN-032 y RN-033.
- Una vez registrada la invalidación en el backend, deberán rechazarse las siguientes operaciones protegidas y renovaciones de las sesiones afectadas.
- La aplicación retirará el acceso correspondiente cuando detecte el vencimiento o invalidación.
- Cada operación protegida deberá comprobar los permisos vigentes.
- Una sesión válida no permitirá conservar autorizaciones retiradas ni continuar accediendo a un vehículo mediante información previamente almacenada.
- La vigencia de la sesión y la autorización sobre los recursos deberán mantenerse diferenciadas.

#### Falta de conexión

- La falta de conexión no ampliará los plazos de duración o inactividad.
- La aplicación no deberá presentar una sesión como renovada sin completar la renovación correspondiente.
- Al recuperar la conexión, se comprobará el estado de la sesión antes de aceptar operaciones protegidas.
- El cierre solicitado sin conexión se tratará conforme a RN-033.
- Estas condiciones no incorporarán por sí mismas funcionalidades de consulta o trabajo sin conexión.

#### Vencimiento y operaciones pendientes

Cuando se detecte el vencimiento de una sesión:

- Se informará que es necesario iniciar sesión nuevamente.
- Se retirará el acceso a información privada.
- Se descartarán los cambios locales sin guardar, sin enviarlos automáticamente.
- Las operaciones ya completadas en el servidor conservarán su resultado.
- Una operación enviada cuyo resultado no se haya confirmado no deberá repetirse automáticamente.
- Su resultado deberá comprobarse mediante el procedimiento correspondiente después de una nueva autenticación y conforme a los permisos vigentes.

El vencimiento no eliminará la cuenta, sus vehículos ni su historial.

#### Intentos fallidos con contraseña propia

- Se permitirán como máximo 5 intentos fallidos de contraseña por cuenta en un período móvil de 15 minutos.
- Se considerará fallido un intento cuando la comprobación haya sido procesada y determine que la contraseña presentada es incorrecta.
- Para evaluar el límite, se contabilizarán los fallos ocurridos durante los 15 minutos anteriores.
- Un fallo que haya cumplido exactamente 15 minutos dejará de formar parte del período contabilizado.
- El quinto fallo dentro del período iniciará una restricción temporal de 15 minutos contados desde ese fallo.
- Durante la restricción no se permitirán nuevos intentos de autenticación mediante contraseña para esa cuenta.
- Las solicitudes realizadas durante la restricción no ampliarán su duración.
- Un inicio de sesión correcto mediante contraseña reiniciará el contador de fallos correspondiente.
- Los controles se aplicarán por cuenta en el backend y no podrán evadirse cambiando de dispositivo.

#### Alcance de la restricción temporal

La restricción afectará únicamente los nuevos intentos de acceso mediante contraseña propia.

No deberá:

- Eliminar la cuenta.
- Cerrar sesiones existentes.
- Bloquear Google o Apple que ya estén vinculados.
- Modificar los permisos o relaciones de la cuenta.
- Sustituir los controles independientes de recuperación de contraseña.

Los fallos de conexión y los errores de autenticación de proveedores externos no se contabilizarán como contraseñas propias incorrectas.

Los intentos de comprobación de códigos mantendrán sus controles independientes.

#### Mensajes de autenticación

- Los mensajes no deberán revelar públicamente si un correo corresponde a una cuenta existente, sus métodos vinculados o su estado.
- Los problemas de conexión deberán distinguirse de una comprobación de credenciales incorrectas, sin exponer información de la cuenta.
- Las respuestas durante una restricción deberán respetar esas mismas condiciones de confidencialidad.

#### Definiciones técnicas posteriores

La implementación deberá detallar:

- La protección de los elementos de sesión.
- Los mecanismos y tiempos de renovación técnica.
- El control de duración máxima y actividad en el backend.
- La aplicación de invalidaciones antes de aceptar operaciones.
- La comprobación de permisos vigentes.
- La separación de sesiones entre dispositivos.
- Los contadores y restricciones de intentos fallidos.
- Los controles contra solicitudes automatizadas.
- El tratamiento técnico de vencimientos y resultados desconocidos.
- Los mensajes y la trazabilidad, sin registrar secretos de autenticación.

Estas definiciones deberán respetar los tiempos y comportamientos aprobados en esta regla.

---

### RN-035 — Revisión manual de conflictos de identificación del propietario

- ID: RN-035.
- Nombre: Revisión manual de conflictos de identificación del propietario.
- Módulo o capacidad: Capacidad general compartida — Soporte de identidad y acceso.
- Etapa prevista: Primera entrega del Propietario, independiente del módulo del Prestador.
- Estado de la definición: Procedimiento funcional aprobado. Pendientes los controles técnicos de comprobación, protección de evidencias y las precisiones operativas indicadas en esta regla.
- Requerimientos relacionados: RF-001, RF-003, RF-043 y RF-051, definidos en `requerimientos-funcionales-propietario.md`.
- Reglas de negocio relacionadas: RN-025 — Cuenta de usuario e identidad del propietario; RN-031 — Vinculación, incorporación y retiro de métodos de acceso; RN-037 — Actualización de datos personales y correcciones mediante soporte.
- Referencias generales: Cuenta única conforme a `63.2.3`; comparación documental y asociación conforme a `63.4.3`, `63.4.4` y `63.4.7` de `proyecto.md`.
- Casos de uso relacionados: Pendientes de documentar en `casos-uso.md`.

#### Descripción

Vehículos Services deberá permitir que un usuario autenticado solicite una revisión manual cuando su tipo y número de documento aparezcan asociados a otra cuenta y esa coincidencia impida completar su identificación como propietario.

La revisión será atendida por personal de soporte autorizado y permitirá evaluar si existe una identificación registrada incorrectamente.

Este procedimiento será una excepción al recorrido ordinario de comparación de datos declarados. Incluirá una comprobación adicional de identidad y no sustituirá las validaciones necesarias para asociar un vehículo.

Esta revisión de conflictos entre cuentas deberá distinguirse de las solicitudes de corrección de errores de captura previstas en RN-037. La disponibilidad de ese canal de soporte no ampliará las acciones autorizadas por esta regla.

La disponibilidad de esta revisión no dependerá de la implementación del módulo del Prestador de Servicios Vehiculares.

#### Condiciones de aplicación

- La solicitud deberá originarse en un conflicto de identificación detectado conforme a RN-025.
- El solicitante deberá estar autenticado en su cuenta.
- Desde el mensaje de documento ocupado podrá acceder a la opción de solicitar revisión.
- Deberá explicar el conflicto y presentar las evidencias iniciales requeridas.
- Mientras se revisa el caso, la identificación y la asociación bloqueadas no deberán completarse.
- Presentar la solicitud no modificará automáticamente la otra cuenta, sus datos, permisos ni vehículos.

La posibilidad de contactar a soporte sin iniciar sesión para solicitar una corrección conforme a RN-037 no sustituirá las condiciones de autenticación y comprobación de esta revisión de conflictos.

Cuando una solicitud de corrección revele que el documento está asociado a otra cuenta, deberá aplicarse esta regla y sus límites. No se tratará únicamente como una corrección de datos para evitar las comprobaciones del conflicto.

#### Datos necesarios

- Identificador de la solicitud.
- Cuenta del solicitante.
- Tipo y número de documento en conflicto.
- Explicación del solicitante.
- Documento de identificación presentado.
- Tarjeta de propiedad del vehículo que pretende asociar.
- Referencia interna a la cuenta con la que existe la coincidencia.
- Estado de la solicitud y fechas relevantes.
- Responsable asignado.
- Registro de las comprobaciones realizadas.
- Información adicional solicitada y recibida.
- Decisión, justificación y cambios autorizados o ejecutados.

La información de la otra cuenta se utilizará únicamente dentro del proceso autorizado de revisión y no se mostrará al solicitante.

#### Actores y permisos

La revisión será realizada por personal de soporte designado por los administradores de Vehículos Services.

Cada responsable utilizará una cuenta individual con permisos específicos para consultar los casos, evaluar evidencias y realizar las acciones autorizadas.

El usuario que solicita la revisión no podrá resolver su propio caso.

Los permisos de soporte deberán limitarse a las operaciones necesarias para este procedimiento. No otorgarán facultades generales para modificar vehículos, credenciales o historiales.

#### Evidencias y comprobación adicional

Como evidencias iniciales se solicitarán:

- El documento de identificación del solicitante.
- La tarjeta de propiedad del vehículo.
- Una explicación del conflicto.

Estos archivos no serán suficientes por sí solos para acreditar quién utiliza la cuenta.

Se realizará una videollamada en vivo para comparar a la persona con la fotografía del documento y solicitar que presente el documento original.

Inicialmente, la videollamada podrá realizarse mediante un canal externo autorizado, sin desarrollar esta capacidad dentro de la aplicación.

El personal responsable deberá estar capacitado para realizar las comprobaciones y reconocer inconsistencias o posibles manipulaciones.

La videollamada no se considerará por sí sola prueba de autenticidad del documento. Deberán aplicarse los controles de validación documental y de manipulación que se definan antes de habilitar el procedimiento.

La revisión deberá considerar las evidencias, los datos declarados y la información relevante de ambas cuentas. Si la información es insuficiente o contradictoria, no se aprobará una corrección.

#### Acciones permitidas y límites

El responsable podrá:

- Solicitar información adicional.
- Rechazar la solicitud con una justificación.
- Autorizar una corrección o desvinculación sustentada de una identificación registrada incorrectamente en una cuenta sin vehículos asociados.

Una corrección aprobada deberá ejecutarse con permisos específicos y conservar su justificación y trazabilidad.

Después de resolver la coincidencia, el solicitante deberá completar nuevamente las comprobaciones normales de identificación y asociación. La revisión no asociará automáticamente el vehículo.

Si la cuenta cuya identificación se pretende corregir tiene vehículos asociados:

- No se modificará directamente su identificación mediante esta revisión ordinaria.
- No se trasladarán sus vehículos.
- El caso requerirá un procedimiento especial de resolución.
- Mientras ese procedimiento no esté definido o no exista evidencia suficiente, el conflicto permanecerá sin resolver.

Esta limitación corresponde a la resolución de un conflicto de identificación entre cuentas. Las solicitudes de corrección de errores de captura sobre la propia cuenta se evaluarán conforme a RN-037, sin utilizar ese procedimiento para sustituir a una persona, ocupar un documento asociado a otra cuenta o eludir los límites de esta revisión.

La revisión no permitirá:

- Fusionar cuentas.
- Cambiar contraseñas.
- Vincular o retirar métodos de acceso.
- Transferir vehículos.
- Modificar permisos sobre vehículos.
- Eliminar o reatribuir historiales.
- Modificar la placa, el VIN u otros datos del vehículo para resolver conflictos vehiculares.

Las operaciones de recuperación y gestión de métodos de acceso conservarán sus procedimientos independientes.

Cuando se proponga una corrección sobre una cuenta existente, se avisará a esa cuenta sin compartir datos privados del solicitante.

#### Estados y seguimiento

La solicitud utilizará los siguientes estados:

- Recibida.
- En revisión.
- Requiere información.
- Aprobada.
- Rechazada.

La aplicación permitirá al solicitante consultar el estado y el resultado de su solicitud.

Cuando se requiera información adicional, se indicará qué debe aportar.

Una aprobación deberá identificar la corrección autorizada y no implicará que el vehículo haya quedado asociado.

Un rechazo deberá incluir una explicación que no revele información privada de la otra cuenta.

Los conflictos que requieran un procedimiento especial no deberán presentarse como resueltos por esta revisión ordinaria.

#### Plazo de atención

La primera respuesta de soporte deberá emitirse en un máximo de tres días hábiles desde la recepción de la solicitud.

Este plazo corresponderá a la primera respuesta y no constituirá una promesa de resolución definitiva.

El calendario, horario, zona horaria y forma de contabilizar los días hábiles deberán concretarse antes de implementar y verificar esta condición.

Este plazo aplicará a las solicitudes de revisión reguladas por RN-035. No establecerá automáticamente el plazo de atención de las solicitudes de corrección de RN-037.

#### Evidencias y trazabilidad

Los archivos y datos del caso tendrán acceso restringido.

Se registrarán:

- El responsable de la revisión.
- Las evidencias consideradas.
- Las comprobaciones realizadas.
- La realización y el resultado de la videollamada.
- Las solicitudes de información adicional.
- El motivo de la decisión.
- Las correcciones autorizadas y ejecutadas.
- Las fechas y los avisos correspondientes.

Inicialmente no se grabará la videollamada.

La conservación y eliminación de las evidencias deberán definirse en los documentos de seguridad correspondientes.

#### Resultado esperado

El usuario dispondrá de un mecanismo de revisión manual del conflicto desde la primera entrega.

La revisión podrá permitir una corrección sustentada dentro de los límites aprobados, sin conceder automáticamente propiedad ni acceso a vehículos.

La cuenta única del propietario, la privacidad de ambas cuentas y la integridad de los historiales deberán conservarse.

La revisión de conflictos entre cuentas permanecerá diferenciada de la corrección de errores de captura de RN-037 y de la revisión especial de conflictos vehiculares prevista para una entrega posterior.

#### Decisiones y definiciones pendientes

- Designar al personal de soporte y concretar sus permisos y capacitación.
- Definir los controles de validación documental y detección de manipulación necesarios para la comprobación adicional.
- Seleccionar y configurar el canal autorizado de videollamada.
- Precisar los recorridos, transiciones de estado y tratamiento de información adicional.
- Concretar el calendario operativo para el plazo de primera respuesta.
- Definir el envío de avisos a la cuenta afectada y el tratamiento de fallos de entrega.
- Definir los mecanismos técnicos de corrección, consistencia y trazabilidad.
- Establecer la conservación y eliminación de las evidencias.
- Definir el procedimiento especial para conflictos cuya corrección afectaría a una cuenta con vehículos asociados.
- Detallar la clasificación y derivación de solicitudes entre RN-035 y RN-037, respetando las condiciones y límites de cada procedimiento.


---

### RN-036 — Identificación, coincidencias y comparación documental del vehículo

- ID: RN-036.
- Nombre: Identificación, coincidencias y comparación documental del vehículo.
- Módulo o capacidad: Gestión de vehículos y relación Propietario ↔ Vehículo.
- Etapa prevista: Primera entrega del Propietario para personas naturales y vehículos y documentos de Colombia.
- Estado de la definición: Condiciones iniciales de identificación, validación básica de captura, detección de coincidencias, comparación documental, mensajes y corrección de datos aprobadas. VIN obligatorio; número de chasis y número de motor opcionales. Tratamiento de inconsistencias aprobado para la primera entrega, con los límites establecidos en esta regla. La corrección de errores de captura después de registrar el vehículo se tramitará mediante soporte conforme a RN-037, con sus verificaciones específicas pendientes. La revisión especial de conflictos vehiculares y la validación avanzada de patrones por categoría se desarrollarán posteriormente. Permanecen pendientes los detalles técnicos y las demás definiciones expresamente señaladas.
- Requerimientos relacionados: RF-003 — Agregar vehículo como propietario; RF-004 — Consultar vehículos propios; RF-046 — Actualizar información general del vehículo, definidos en `requerimientos-funcionales-propietario.md`.
- Reglas de negocio relacionadas: RN-025 — Cuenta de usuario e identidad del propietario; RN-035 — Revisión manual de conflictos de identificación del propietario, cuyo alcance no comprende la resolución de conflictos vehiculares; RN-037 — Actualización de datos personales y correcciones mediante soporte.
- Referencias generales: Información obligatoria conforme a `63.1.5`; registro y conservación de la identidad vehicular conforme a `63.1.6`; comparación documental conforme a `63.4.3` y `63.4.5` de `proyecto.md`.
- Casos de uso relacionados: CU-003 Registrar vehículo; detalle pendiente en `casos-uso.md`.

#### Descripción

Vehículos Services deberá identificar el vehículo que se pretende registrar o asociar, comprobar si ya existe y comparar sus identificadores obligatorios con la información obtenida de la tarjeta de propiedad.

Cada vehículo tendrá un identificador interno permanente, independiente de su propietario y de sus datos descriptivos.

Una coincidencia con un vehículo existente no deberá provocar la creación de otra identidad vehicular ni de un historial independiente.

La comparación del vehículo deberá mantenerse diferenciada de la comparación del propietario. Ambas deberán cumplir sus condiciones antes de completar la asociación correspondiente.

#### Condiciones de aplicación

Esta regla aplicará durante la solicitud de registro o asociación de un vehículo.

La información obligatoria se regirá por `63.1.5` y `63.1.6` de `proyecto.md`. Esta regla no permitirá completar el registro definitivo cuando falte información requerida.

Para la primera entrega, los identificadores obligatorios utilizados para comprobar la correspondencia documental del vehículo serán:

- Placa.
- VIN.

El propietario deberá ingresar el VIN y la plataforma deberá comprobar su correspondencia con el VIN informado en la tarjeta de propiedad.

Si el usuario no puede suministrar el VIN, este resulta ilegible en el documento o no puede comprobarse su correspondencia, el registro definitivo y la asociación permanecerán sin completar. Cuando corresponda, se solicitará una nueva captura.

El número de chasis y el número de motor serán información complementaria opcional.

Su ausencia, falta de ingreso o imposibilidad de lectura no impedirán por sí solas completar el registro o la asociación. No se exigirá capturarlos ni compararlos únicamente porque aparezcan en la tarjeta de propiedad.

VIN, número de chasis y número de motor se conservarán en campos separados. No se copiarán automáticamente valores entre ellos ni se utilizarán los datos opcionales para sustituir el VIN obligatorio.

Antes de confirmar el envío de los datos del registro vehicular, el usuario podrá corregir lo digitado o presentar una nueva captura. Si una comprobación rechaza datos de la solicitud que todavía no hayan sido aceptados y guardados como información definitiva del vehículo, podrá corregirlos y repetir el proceso. Estas acciones no habilitarán la edición de datos ya confirmados y guardados.

Después de una corrección o sustitución del documento, deberán repetirse las comprobaciones documentales y la búsqueda de coincidencias utilizando la información actualizada.

El vehículo no se creará definitivamente ni se establecerá la relación de propiedad hasta superar las comprobaciones obligatorias. Repetir una solicitud no deberá generar vehículos, historiales o relaciones duplicados.

Una vez confirmado, aceptado y guardado el registro definitivo, el propietario no podrá editar ni eliminar directamente los datos obligatorios aplicables del vehículo. Las solicitudes de corrección de errores de captura se tramitarán mediante soporte conforme a RN-037.

Los criterios de identificación del vehículo no constituirán por sí solos una validación de propiedad ni de identidad del usuario.

#### Datos necesarios

- Identificador interno del vehículo, cuando ya exista.
- Tipo y categoría del vehículo.
- Placa indicada en la solicitud.
- VIN ingresado por el propietario.
- Placa y VIN obtenidos de la tarjeta de propiedad.
- Número de chasis, si se incorpora como información complementaria.
- Número de motor, si se incorpora como información complementaria.
- Valores originales y valores utilizados para comparar.
- Resultado de la validación básica de captura.
- Resultados de las búsquedas de coincidencias.
- Resultado de la comparación documental.
- Relación de propiedad vigente, cuando exista.
- Referencia al documento utilizado y al resultado de su procesamiento.

Cada identificador se conservará en su campo correspondiente. No se asumirá que VIN, número de chasis y número de motor son intercambiables.

La falta de información complementaria no se interpretará como un incumplimiento de los datos obligatorios.

#### Normalización y comparación

Para comparar los identificadores obligatorios:

- Se ignorarán diferencias de mayúsculas y minúsculas.
- Se eliminarán únicamente espacios accidentales al inicio y al final.
- Se conservarán los ceros iniciales.
- No se eliminarán otros caracteres para producir una coincidencia.
- No se aceptarán coincidencias aproximadas como resultado satisfactorio.
- Se conservarán los valores originales declarados y obtenidos del documento.
- Los valores utilizados para comparar no reemplazarán silenciosamente los originales.

La placa y el VIN serán obligatorios y admitirán únicamente letras o números, sin espacios internos ni signos.

Un campo vacío o compuesto únicamente por espacios no se considerará informado.

Para la primera entrega no se impondrá un patrón único de placa para todas las categorías de vehículos. La comparación deberá comprobar la correspondencia con la placa indicada en la tarjeta de propiedad, aplicando la normalización aprobada.

La longitud de 17 caracteres se utilizará como referencia estándar del VIN, pero una longitud diferente no será por sí sola motivo de rechazo cuando el valor corresponda al campo VIN de la tarjeta de propiedad y supere las demás comprobaciones aplicables.

El VIN deberá compararse con el campo VIN del documento. No se sustituirá por el número de chasis ni por el número de motor.

Se utilizarán los siguientes mensajes según la situación:

- Cuando falten la placa o el VIN: “Ingresa la placa y el VIN para continuar”.
- Cuando existan caracteres no admitidos: “Revisa el campo indicado. Ingresa únicamente sus letras y números, sin espacios internos ni signos”.
- Cuando los datos ingresados no correspondan con el documento: “La placa o el VIN ingresados no coinciden con la tarjeta de propiedad. Revisa los datos”.
- Cuando no pueda leerse la información obligatoria: “No pudimos leer la información obligatoria. Adjunta una imagen más clara de la tarjeta de propiedad”.

Cuando pueda determinarse el campo afectado, la plataforma deberá identificarlo para facilitar su corrección.

Estas condiciones establecerán una validación básica de captura y correspondencia. La validación avanzada de patrones por categoría se desarrollará posteriormente y no se considerará implementada por cumplir esta regla.

#### Detección de un vehículo existente

Antes de crear un vehículo, la plataforma deberá buscar coincidencias por:

- Placa.
- VIN.

Una coincidencia en cualquiera de estos identificadores impedirá crear automáticamente otro vehículo hasta comprobar la correspondencia.

El número de chasis y el número de motor no serán requisitos para ejecutar esta búsqueda ni sustituirán la comprobación por placa y VIN.

Cuando los identificadores correspondan a un vehículo existente, se conservarán su identificador interno y su historial. La solicitud continuará mediante las reglas de relación Propietario ↔ Vehículo, sin crear una unidad independiente.

Cuando no existan coincidencias, la creación podrá continuar únicamente si se cumplen las demás condiciones de registro, identificación y asociación aplicables.

#### Comparación con la tarjeta de propiedad

La plataforma deberá comprobar la correspondencia entre la placa y el VIN de la solicitud y los obtenidos de la tarjeta de propiedad.

Una coincidencia de nombres, marca, línea, modelo o características descriptivas no sustituirá la comparación de los identificadores obligatorios.

Si falta información obligatoria o el documento no permite leerla, se solicitará completar los datos, corregir la solicitud dentro de los límites establecidos o presentar una nueva captura. No se inventarán identificadores ni se completará el registro definitivo.

La falta de lectura del número de chasis o del número de motor no impedirá por sí sola completar la comparación obligatoria ni la asociación.

La correspondencia documental del vehículo no acreditará por sí sola la autenticidad o vigencia de la tarjeta de propiedad.

El resultado de esta comparación no se presentará como una comprobación contra RUNT ni como una autenticación del documento.

#### Coincidencias contradictorias

Si la placa y el VIN apuntan a vehículos existentes diferentes:

- No se creará automáticamente un vehículo nuevo.
- No se fusionarán los registros.
- No se escogerá automáticamente uno de los vehículos.
- No se completará la asociación.
- Se conservarán los registros existentes.

Si una búsqueda identifica un vehículo existente, pero la placa o el VIN contradicen la solicitud o la tarjeta de propiedad:

- No se sobrescribirán automáticamente los identificadores del vehículo existente.
- No se completará la asociación mientras la inconsistencia permanezca sin resolver.
- Se conservarán la identidad y el historial existentes.

La información obligatoria incompleta o contradictoria no se interpretará como ausencia de coincidencias para permitir crear un duplicado.

El usuario podrá corregir errores en los datos de su solicitud o presentar una nueva captura, conforme a las condiciones de esta regla. Estas acciones no modificarán los identificadores de vehículos existentes.

Si, después de las comprobaciones con la información corregida, la inconsistencia persiste, la asociación permanecerá sin completar.

Para la primera entrega no se habilitará un procedimiento especial de revisión manual que permita resolver conflictos entre vehículos existentes o con otra relación de propiedad vigente. Su definición y habilitación corresponderán a una entrega posterior.

La corrección de errores de captura sobre el propio vehículo mediante soporte, contemplada en RN-037, deberá mantenerse diferenciada de esa revisión especial. No permitirá fusionar vehículos, sustituir su identidad, transferir su propiedad ni resolver identificadores que apunten a vehículos existentes diferentes.

La revisión de RN-035 se limitará a conflictos de identificación del propietario. No autorizará cambios de placa, VIN, identidad vehicular ni relaciones de propiedad.

Ante una inconsistencia con un registro existente se mostrará:

“No pudimos completar la asociación porque se detectó una inconsistencia con un registro existente. Revisa los datos ingresados y la tarjeta de propiedad. Si son correctos y el problema continúa, esta solicitud no podrá completarse con las opciones disponibles en esta primera entrega”.

Este mensaje corresponderá a las solicitudes de asociación bloqueadas por las inconsistencias descritas. No eliminará la posibilidad de solicitar a soporte la corrección de un error de captura del propio vehículo dentro de los límites de RN-037.

Si el conflicto requiere la revisión especial prevista para una entrega posterior, la asociación permanecerá sin completar aunque los datos y el documento presentados sean correctos.

#### Relación de propiedad existente

Cuando el vehículo ya esté asociado al propietario que realiza la solicitud:

- Se informará que el vehículo ya está registrado.
- Se permitirá consultar el vehículo existente conforme a RF-004.
- No se creará otro vehículo, historial ni relación de propiedad por repetir la solicitud.

Cuando el vehículo tenga una relación de propiedad vigente con otro propietario:

- No se sustituirá esa relación automáticamente.
- No se concederá acceso por conocer sus identificadores.
- No se utilizará el registro como una transferencia de propiedad.
- La solicitud permanecerá sin completar.
- Se mostrará el mensaje de inconsistencia con un registro existente establecido en esta regla.
- Si corregir los datos de la solicitud o presentar una nueva captura no resuelve la situación, no podrá completarse la asociación mediante las opciones de la primera entrega.

La transferencia de propiedad y el procedimiento especial para revisar estos conflictos se desarrollarán posteriormente.

La detección de una coincidencia no deberá revelar información privada del propietario actual ni permitir consultar recursos sin autorización.

#### Resultado esperado

La plataforma deberá:

- Conservar una identidad interna permanente por vehículo.
- Exigir el VIN y comprobar su correspondencia con la tarjeta de propiedad.
- Aplicar la validación básica de captura y los mensajes establecidos.
- Detectar coincidencias por placa y VIN antes de crear una unidad nueva.
- Conservar el número de chasis y el número de motor como información opcional, sin exigirlos para completar el registro o la asociación.
- Mantener separados los campos de VIN, número de chasis y número de motor.
- Permitir corregir los datos de la solicitud o presentar una nueva captura dentro de los límites establecidos para información todavía no aceptada y guardada como definitiva.
- Repetir las comprobaciones documentales y la búsqueda de coincidencias después de esas correcciones.
- Impedir la edición o eliminación directa de los datos obligatorios del vehículo después de confirmar y guardar su registro definitivo.
- Tramitar las solicitudes de corrección de errores de captura mediante soporte conforme a RN-037.
- Evitar duplicidades de vehículos e historiales.
- Mantener separados los conflictos de identificación del vehículo y los de identificación del propietario.
- Impedir asociaciones automáticas cuando existan datos obligatorios insuficientes, contradictorios o relaciones de propiedad que no puedan sustituirse.
- Informar cuando una solicitud no pueda completarse con las opciones disponibles en la primera entrega.
- Conservar la identidad y el historial del vehículo a través de sus distintos períodos de propiedad.

#### Efecto sobre modificaciones posteriores

Los datos de una nueva solicitud no deberán sobrescribir automáticamente los identificadores de un vehículo existente.

La actualización de información general se regirá por RF-046 y sus reglas correspondientes. No deberá utilizarse para sustituir la identidad del vehículo, evitar una coincidencia o transferir su propiedad.

Los errores de captura en datos obligatorios de un vehículo ya registrado requerirán una solicitud de corrección mediante soporte conforme a RN-037.

Los cambios permitidos sobre identificadores vehiculares, sus verificaciones y su documentación deberán definirse antes de habilitar esas correcciones mediante soporte.

La corrección de los datos de una solicitud de registro no constituirá autorización para modificar los identificadores de un vehículo existente.

Las correcciones autorizadas deberán conservar el identificador interno, la trazabilidad y el historial del vehículo. Cuando afecten la placa o el VIN, deberán repetirse las búsquedas y comparaciones aplicables antes de aceptar el cambio.

#### Decisiones y definiciones pendientes

- Detallar la implementación técnica de la validación básica de placa y VIN, respetando las condiciones aprobadas.
- Definir las validaciones de los datos complementarios cuando el propietario decida incorporarlos, sin convertirlos en requisitos de asociación.
- Detallar los mecanismos técnicos de búsqueda y comparación, respetando la obligatoriedad del VIN y los criterios aprobados.
- Desarrollar en los casos de uso y en el diseño de interacción los recorridos de corrección, nueva captura y repetición de comprobaciones, aplicando los mensajes y límites aprobados.
- Detallar las correcciones de errores de captura admitidas mediante soporte en la primera entrega, sus evidencias y comprobaciones, conforme a RN-037.
- Definir para una entrega posterior el procedimiento especial de revisión y resolución de coincidencias contradictorias entre vehículos existentes.
- Definir para una entrega posterior la resolución de diferencias que impliquen conflictos entre identidades vehiculares o relaciones de propiedad, distinguiéndolas de los errores de captura corregibles mediante RN-037.
- Desarrollar posteriormente la transferencia de propiedad y el procedimiento especial para solicitudes que involucren otra relación de propiedad vigente.
- Desarrollar posteriormente la validación avanzada de patrones por categoría, diferenciándola de la validación básica incluida inicialmente.

---

### RN-037 — Actualización de datos personales y correcciones mediante soporte

- ID: RN-037.
- Nombre: Actualización de datos personales y correcciones mediante soporte.
- Módulo o capacidad: Perfil personal, cuenta de usuario y gestión de vehículos.
- Etapa prevista: Primera entrega del Propietario.
- Estado de la definición: Clasificación de datos editables, restricciones de modificación, canal inicial de soporte, condiciones iniciales de comprobación y plazo de primera respuesta aprobados. Pendientes los controles específicos de comprobación, los recorridos y los mecanismos operativos y técnicos del procedimiento de corrección.
- Requerimientos relacionados: RF-001 — Crear cuenta de usuario; RF-003 — Agregar vehículo como propietario; RF-043 — Gestionar el perfil personal del usuario; RF-046 — Actualizar información general del vehículo; RF-052 — Solicitar la corrección de datos mediante soporte.
- Reglas de negocio relacionadas: RN-025 — Cuenta de usuario e identidad del propietario; RN-027 — Verificación del correo en el registro propio; RN-035 — Revisión manual de conflictos de identificación del propietario; RN-036 — Identificación, coincidencias y comparación documental del vehículo.

#### Descripción

Vehículos Services deberá distinguir entre los datos que el usuario puede actualizar directamente y aquellos cuya corrección requiere intervención de soporte.

La posibilidad de actualización no dependerá únicamente de que un campo sea obligatorio u opcional. Deberá considerar su finalidad y su utilización para identificar la cuenta, al propietario o al vehículo.

Las restricciones se aplicarán después de que el usuario confirme el ingreso correspondiente y el sistema acepte y guarde los datos. Mientras diligencia el formulario, antes de confirmar su envío, podrá corregir lo digitado.

#### Datos personales editables

Para la primera entrega, el número de celular de contacto será obligatorio para completar la información del propietario antes de asociar su primer vehículo. No se exigirá para crear inicialmente la cuenta.

El usuario autenticado podrá ingresar y actualizar directamente su celular de contacto, respetando las validaciones correspondientes. Una actualización aceptada no podrá eliminarlo ni dejarlo vacío mientras sea un dato obligatorio.

El perfil también podrá incluir como información opcional:

- Ciudad de residencia.
- Fotografía de perfil.

El usuario autenticado podrá agregar, actualizar o retirar estos datos opcionales de su propio perfil. Su ausencia no impedirá crear la cuenta ni asociar un vehículo cuando se cumplan los demás requisitos.

El número de celular tendrá inicialmente una finalidad de contacto. No se considerará por sí solo un mecanismo de autenticación, recuperación de acceso o comprobación de identidad.

Si posteriormente se habilita alguno de esos usos, deberán definirse sus verificaciones y las condiciones para cambiar el número antes de permitirlo.

La fotografía de perfil no constituirá prueba de identidad.

La ciudad de residencia no modificará automáticamente la información del vehículo, su organismo de tránsito ni sus relaciones de propiedad.

La dirección exacta de residencia no formará parte de los datos solicitados inicialmente. Su incorporación posterior deberá responder a una finalidad funcional definida.

Las preferencias de notificación podrán configurarse conforme a sus requerimientos y reglas correspondientes.

#### Datos de cuenta e identidad sujetos a soporte

Después de confirmar y guardar los datos correspondientes, el usuario no podrá editar ni eliminar directamente:

- El correo electrónico de la cuenta.
- Los nombres.
- Los apellidos.
- El tipo de documento de identificación.
- El número de documento de identificación.

Las solicitudes de corrección deberán tramitarse mediante soporte.

El correo quedará sujeto a esta restricción desde la creación del registro pendiente de verificación. Si se ingresó incorrectamente, la solicitud de ayuda no dependerá de haber verificado ese correo ni de poder iniciar sesión.

Esta regla no cambiará el momento en que se solicitan los datos personales del propietario: los nombres, apellidos, tipo y número de documento se obtendrán cuando corresponda conforme a RN-025, sin exigirlos por esta regla durante la creación inicial de la cuenta.

#### Datos obligatorios del vehículo sujetos a soporte

Después de confirmar y guardar el registro del vehículo, el propietario no podrá editar ni eliminar directamente los datos obligatorios aplicables definidos en el punto 63.1.5 de `proyecto.md`.

Las solicitudes de corrección de esos datos deberán tramitarse mediante soporte.

Esta restricción comprenderá la placa y el VIN, además de los demás datos obligatorios aplicables al vehículo.

La edición de información complementaria opcional se regirá por RF-046 y las condiciones que se aprueben para esos campos. Esta regla no los convertirá en obligatorios.

La actualización del kilometraje o lectura de uso continuará mediante nuevos registros conforme a RF-005. No permitirá sobrescribir la lectura inicial ni las anteriores mediante la edición de la información general del vehículo.

#### Canal inicial de soporte

Para la primera entrega, el correo de soporte será:

`soquendo61@gmail.com`

El asunto de las solicitudes deberá comenzar con:

`Soporte App`

Por ejemplo:

`Soporte App — Corrección de correo electrónico`

Cuando se defina un correo propio de soporte, se actualizará la dirección utilizada y publicada por la aplicación y sus referencias correspondientes.

El cambio del correo de soporte no modificará por sí mismo las condiciones de autorización y corrección establecidas en esta regla.

#### Solicitud y autorización de la corrección

El usuario deberá poder solicitar ayuda por correo incluso cuando el error le impida verificar su cuenta o iniciar sesión.

El envío de una solicitud no autorizará automáticamente una modificación.

Antes de ejecutar una corrección, soporte deberá comprobar la vinculación del solicitante con la cuenta o el vehículo afectado y evaluar la información que sustente el cambio.

No se considerará que conocer un correo, documento de identificación, placa o VIN sea suficiente por sí solo para autorizar una corrección.

Se aplicarán las siguientes condiciones según la solicitud:

- Para corregir el correo cuando el solicitante pueda autenticarse, se comprobará su acceso a la cuenta mediante la aplicación y el control del nuevo correo antes de ejecutar el cambio. Estas comprobaciones no habilitarán la edición directa del correo por el usuario.
- Para corregir el correo cuando el solicitante no pueda autenticarse, soporte realizará una revisión adicional de la información disponible. Si no permite vincular suficientemente al solicitante con la cuenta, no se ejecutará la corrección.
- Cuando el registro inicial no disponga todavía de datos de identidad ni vehículos asociados, presentar un documento de identificación no demostrará por sí solo la vinculación con esa cuenta ni autorizará el cambio de correo.
- Para corregir nombres, apellidos, tipo o número de documento, se revisará el documento de identidad y se realizará una comprobación adicional mediante videollamada. La corrección deberá corresponder a la misma persona y respetar la unicidad establecida en RN-025.
- Para corregir datos obligatorios del vehículo, se revisarán la tarjeta de propiedad, la relación del solicitante con el vehículo y la información existente necesaria para sustentar que se trata del mismo vehículo.
- Si la corrección afecta la placa o el VIN, se repetirán además las búsquedas de coincidencias y las comparaciones aplicables conforme a RN-036 antes de aceptar el cambio.
- Si se detecta un conflicto entre vehículos existentes o con otra relación de propiedad vigente, no se utilizará este procedimiento para resolverlo. Se aplicarán los límites de RN-036.
- Si se detecta un conflicto de identificación entre cuentas, se aplicarán RN-025 y RN-035 con sus condiciones y límites.

No se solicitarán contraseñas ni códigos de verificación como evidencia para soporte. Las comprobaciones que requieran credenciales o códigos se realizarán mediante los mecanismos autorizados de la plataforma, sin comunicarlos al personal de soporte.

La revisión de documentos y la videollamada no se considerarán por sí solas una garantía de autenticidad documental. Los controles específicos deberán definirse antes de habilitar las correcciones que dependan de ellos.

Cuando el correo se corrija en una cuenta de registro propio pendiente de verificación, se respetará RN-027. La intervención de soporte no sustituirá la verificación requerida para habilitarla.

Si la información es insuficiente o contradictoria, soporte solicitará información adicional o rechazará la corrección con la justificación correspondiente.

#### Límites del procedimiento

La corrección mediante soporte tendrá como finalidad atender errores de captura comprobados.

No deberá utilizarse para:

- Sustituir a una persona identificada por otra.
- Fusionar cuentas.
- Fusionar vehículos.
- Transferir la propiedad de un vehículo.
- Sustituir la identidad de un vehículo por la de otro.
- Alterar datos para forzar una coincidencia.
- Resolver conflictos entre vehículos existentes mediante cambios no autorizados por RN-036.

Las correcciones de placa o VIN deberán respetar la conservación de la identidad vehicular y las condiciones de búsqueda y comparación de RN-036.

La revisión especial de conflictos vehiculares y la transferencia de propiedad conservarán su alcance previsto para entregas posteriores.

Los conflictos de identificación del propietario cubiertos por RN-035 seguirán ese procedimiento y sus límites. La existencia de un correo de soporte no ampliará automáticamente las acciones autorizadas por dicha regla.

#### Atención y comunicación del resultado

La primera respuesta de soporte deberá emitirse en un máximo de tres días hábiles desde la recepción de la solicitud.

Este plazo corresponderá a la primera respuesta y no constituirá una promesa de resolución definitiva.

El calendario, horario, zona horaria y forma de contabilizar los días hábiles deberán concretarse antes de implementar y verificar esta condición.

Se comunicará al solicitante si la corrección fue aprobada, rechazada o requiere información adicional, sin revelar datos privados de terceros.

Una aprobación identificará la corrección autorizada. No deberá presentarse como ejecutada hasta que la modificación se haya completado.

La forma de seguimiento y comunicación deberá detallarse conforme a RF-052. Esta regla no exigirá por sí misma un sistema de seguimiento integrado en la aplicación.

#### Conservación y trazabilidad

Una corrección autorizada deberá conservar la identidad interna de la cuenta o del vehículo y la continuidad de sus relaciones e historial.

Deberá registrarse:

- Dato corregido.
- Valor anterior.
- Valor nuevo.
- Motivo de la corrección.
- Referencia a las comprobaciones que sustentaron la decisión.
- Responsable de la modificación.
- Fecha y hora de ejecución.

La corrección no deberá reescribir automáticamente la procedencia ni el contenido de los registros históricos.

El acceso a las solicitudes, evidencias y registros de corrección deberá respetar los permisos y las condiciones de protección de información aplicables.

#### Operaciones con procedimientos propios

Esta regla no sustituirá:

- La recuperación y gestión de contraseñas.
- La vinculación o retiro de métodos de acceso.
- La actualización del kilometraje mediante nuevos registros.
- La configuración de preferencias de notificación.
- Los procedimientos de corrección de registros históricos.

Estas operaciones conservarán sus requerimientos, verificaciones y restricciones correspondientes.

#### Decisiones y definiciones pendientes

- Detallar las validaciones del celular de contacto, ciudad de residencia y fotografía de perfil.
- Detallar las evidencias y los controles específicos de comprobación por tipo de corrección, respetando las condiciones aprobadas en esta regla.
- Definir el mecanismo para comprobar mediante la aplicación el acceso del solicitante a la cuenta y comunicar el resultado autorizado a soporte sin exponer credenciales.
- Detallar la revisión adicional para solicitudes sin acceso a la cuenta, incluyendo los casos de correo incorrecto y ausencia de datos de identidad o vehículos registrados.
- Definir el mecanismo de comprobación del control del nuevo correo.
- Detallar el canal de videollamada y los controles de comprobación de identidad y validación documental para las correcciones de datos personales.
- Precisar las condiciones para corregir datos personales sin sustituir la identidad del usuario ni vulnerar la unicidad establecida en RN-025.
- Detallar las correcciones admitidas sobre datos obligatorios del vehículo, respetando los límites de RN-036 y distinguiendo errores de captura de cambios reales en sus características.
- Definir los permisos y mecanismos mediante los cuales soporte podrá ejecutar correcciones autorizadas.
- Detallar el seguimiento de las solicitudes y la comunicación de sus resultados.
- Concretar el calendario operativo para verificar el plazo de primera respuesta de tres días hábiles.
- Establecer la protección y conservación de las evidencias.
- Definir los efectos de una corrección sobre sesiones, medios de recuperación y resultados derivados cuando corresponda.
- Desarrollar los casos de uso y los detalles operativos y técnicos de RF-052, conservando la separación respecto de RF-051.

---