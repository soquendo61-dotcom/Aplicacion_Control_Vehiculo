# Proyecto: Vehículos Services

## Documento maestro de definición del proyecto

---

# 1. Información general

## 1.1 Nombre del proyecto

Vehículos Services

## 1.2 Descripción general

Plataforma multiplataforma para la gestión, trazabilidad, seguimiento, historial, mantenimiento y acompañamiento del ciclo de vida de vehículos.

La solución estará disponible inicialmente para dispositivos Android e iOS y permitirá centralizar la información relacionada con el ciclo de vida de uno o varios vehículos, sus mantenimientos, reparaciones, repuestos, inspecciones, kilometraje, costos, documentos, talleres y demás eventos relevantes durante su ciclo de vida.

La plataforma tendrá dos frentes principales:

- Propietarios / Clientes.
- Prestadores de Servicios Vehiculares.

El sistema permitirá que ambos actores interactúen con la información del vehículo de acuerdo con los permisos y suscripciones contratadas.

## 1.3 Estado del proyecto

Iniciando levantamiento de requerimientos.

## 1.4 Responsables

- Santiago Oquendo Maillane.
- David Oquendo

## 1.5 Fecha de inicio

31/08/2026

## 1.6 Tipo de solución

Aplicación multiplataforma:

- Android
- iOS
- Backend/API.
- Base de datos centralizada.
- Servicios de notificaciones.
- Servicios de almacenamiento de documentos y archivos.
- Panel administrativo, sujeto a definición posterior.

La solución deberá contar con una plataforma tecnológica centralizada que permita almacenar, procesar y sincronizar la información entre los diferentes usuarios.

---
# 2. Visión del proyecto

Construir una plataforma que permita digitalizar el ciclo de vida del mantenimiento de un vehículo, centralizando su información histórica y utilizando dicha información para anticipar necesidades de mantenimiento, generar alertas, generar recomendaciones y facilitar la interacción entre propietarios y Prestadores de Servicios Vehiculares.

La aplicación no deberá limitarse a funcionar como un simple registro de mantenimientos.

La visión es construir un historial digital del vehículo que pueda acompañarlo durante todo su ciclo de vida.

Adicionalmente, la plataforma deberá evolucionar hacia una herramienta de acompañamiento que permita al propietario utilizar la información histórica del vehículo para tomar decisiones antes de situaciones específicas, como la preparación de un viaje largo.

Por ejemplo, el propietario podrá indicar que realizará un viaje hacia determinada ciudad o que recorrerá una cantidad estimada de kilómetros. La aplicación podrá utilizar el estado y el historial registrado del vehículo para generar una lista de aspectos que deberían ser revisados antes del viaje.

Esta funcionalidad deberá considerar elementos como:

- Estado y antigüedad de mantenimientos recientes.
- Kilometraje actual.
- Próximos mantenimientos.
- Mantenimientos vencidos.
- Sistema de frenos.
- Estado de neumáticos.
- Presión de neumáticos.
- Niveles de fluidos.
- Aceite de motor.
- Refrigerante.
- Líquido de frenos.
- Estado de batería.
- Luces.
- Elementos de seguridad.
- Kit de carretera.
- Extintor.
- Otros elementos que sean definidos mediante reglas de negocio.

La aplicación deberá diferenciar entre una recomendación basada en reglas y una inspección mecánica profesional.

Conceptualmente:

```text
                 VEHÍCULO
                     │
                     ↓
            HISTORIAL VEHICULAR
                     │
       ┌─────────────┼─────────────┐
       ↓             ↓             ↓
  Mantenimientos  Repuestos   Reparaciones
       │             │             │
       └─────────────┼─────────────┘
                     ↓
             REGLAS DE NEGOCIO
                     ↓
             MOTOR DE CÁLCULO
                     ↓
          ALERTAS / RECOMENDACIONES
                     ↓
PROPIETARIO ↔ PRESTADOR DE SERVICIOS VEHICULARES
                     ↓
              NUEVO SERVICIO
                     ↓
          ACTUALIZACIÓN DEL
               HISTORIAL
                     ↓
                   CICLO
```

Para el escenario de viaje:

```text
        PROPIETARIO
             │
             ↓
      INFORMA VIAJE
             │
      ┌──────┴──────┐
      ↓             ↓
   DESTINO       DISTANCIA
      │             │
      └──────┬──────┘
             ↓
     INFORMACIÓN DEL
         VEHÍCULO
             ↓
       HISTORIAL +
      KILOMETRAJE +
     MANTENIMIENTOS +
      REGLAS DE VIAJE
             ↓
      MOTOR DE ANÁLISIS
             ↓
    CHECKLIST DE VIAJE
             ↓
 RECOMENDACIONES DE REVISIÓN
             ↓
      PROPIETARIO INFORMADO
             ↓
        VIAJE PREPARADO
```

---

# 3. Contexto del proyecto

Se requiere desarrollar una plataforma multiplataforma orientada a construir y administrar el ciclo de vida digital de uno o varios vehículos.

La idea del proyecto surge a partir de una problemática frecuente relacionada con la administración y seguimiento del mantenimiento de los vehículos.

Actualmente, gran parte de los propietarios no cuenta con un mecanismo centralizado que les permita conocer de manera sencilla el historial de mantenimiento de su vehículo, los trabajos realizados, los repuestos utilizados, los costos asociados, los Prestadores de Servicios Vehiculares que han intervenido, revisado, diagnosticado, inspeccionado o evaluado el vehículo y, especialmente, qué actividades deberían realizarse próximamente.

La información suele encontrarse dispersa entre facturas físicas, mantenimientos, reparaciones, cambios de repuestos, conversaciones de WhatsApp, correos electrónicos, documentos, diferentes Prestadores de Servicios Vehiculares o simplemente depender de la memoria del propietario.

- Facturas físicas.
- Documentos digitales.
- Fotografías.
- Conversaciones con talleres.
- Registros manuales.
- Correos electrónicos.
- Aplicaciones diferentes.
- Memoria del propietario.

Esta situación genera una problemática importante para personas que no poseen conocimientos técnicos de mecánica y dificulta que el propietario pueda conocer en cualquier momento el estado histórico de su vehículo.

La problemática principal que busca resolver la app "Vehículos Services" está relacionada con la falta de conocimiento, control y trazabilidad que muchos propietarios tienen sobre el ciclo de vida y mantenimiento de sus vehículos.

Una persona puede ser propietaria de un vehículo durante varios años sin tener conocimientos técnicos de mecánica suficientes para determinar por sí misma qué mantenimiento debe realizar, cuándo debe realizarlo o qué componentes deberían ser revisados.

Entre las preguntas que normalmente pueden surgir se encuentran: 

- ¿Cuándo fue el último cambio de aceite?
- ¿Cada cuánto se realiza el cambio de aceite?
- ¿Cuándo se cambiaron las pastillas de freno?
- ¿Se han cambiado los discos de freno?
- ¿Cuándo se realizó la última afinación?
- ¿Qué repuestos importantes han sido reemplazados?
- ¿Qué reparaciones se han realizado?
- ¿Qué mantenimientos preventivos se han ejecutado?
- ¿Qué taller realizó cada intervención?
- ¿Cuánto dinero se ha invertido en mantenimiento?
- ¿Qué trabajos se han realizado recientemente?
- ¿Cuál era el kilometraje al momento de cada intervención?
- ¿Qué debería revisar antes de realizar un viaje largo?
- ¿El vehículo tiene algún mantenimiento próximo o vencido antes del viaje?
- ¿Qué elementos de seguridad debería verificar antes de salir?

En muchos casos, el propietario no tiene una respuesta clara para estas preguntas.

Esta situación puede provocar que algunos mantenimientos se realicen únicamente cuando aparece un problema, cuando el vehículo presenta síntomas o cuando el propietario recuerda que ha pasado determinado tiempo desde la última intervención.

Adicionalmente, existe una situación particular que puede presentarse cuando el propietario planea realizar un viaje largo.

Una persona puede conocer el destino o la distancia aproximada de su viaje, pero no necesariamente conocer qué aspectos de su vehículo debería revisar antes de emprenderlo.

Por ejemplo, un propietario puede preguntarse:

- ¿Debo revisar los frenos?
- ¿Debo revisar el aceite?
- ¿Debo revisar el refrigerante?
- ¿Las llantas todavía tienen suficiente vida útil?
- ¿La presión de las llantas es adecuada?
- ¿Cuándo fue la última revisión de frenos?
- ¿Tengo algún mantenimiento vencido?
- ¿La batería ha sido revisada recientemente?
- ¿Tengo el kit de carretera completo?
- ¿El extintor está disponible y vigente?
- ¿Las luces funcionan correctamente?

Vehículos Services deberá utilizar la información disponible del vehículo para ayudar al propietario a identificar estos aspectos antes de realizar el viaje.

El propietario podrá indicar:

```text
Destino: Cartagena

o

Distancia estimada: 650 km
```

A partir de esta información, y dependiendo de las reglas que se definan, la plataforma podrá generar una lista de revisión previa al viaje.

Por ejemplo:

```text
PREPARACIÓN PARA VIAJE

Vehículo: HWG123

Kilometraje actual: 75.300 km

Elementos recomendados para revisar:

[ ] Nivel de aceite
[ ] Nivel de refrigerante
[ ] Líquido de frenos
[ ] Estado de pastillas de freno
[ ] Estado de discos
[ ] Presión de neumáticos
[ ] Vida útil de neumáticos
[ ] Luces
[ ] Batería
[ ] Kit de carretera
[ ] Extintor
[ ] Mantenimiento pendiente
```

La aplicación deberá utilizar esta información como una herramienta de orientación y prevención, sin presentar los resultados como una certificación de seguridad ni como un diagnóstico mecánico.

Vehículos Services busca solucionar esta problemática mediante la construcción de un historial digital y centralizado del vehículo, acompañado de mecanismos de seguimiento, cálculo, alertas y recomendaciones.

El propietario podrá consultar en cualquier momento la información histórica de su vehículo y conocer qué intervenciones se han realizado, cuándo fueron realizadas, qué repuestos fueron utilizados, qué taller realizó el servicio, cuál era el kilometraje y cuánto dinero se ha invertido.

Adicionalmente, la aplicación utilizará la información registrada para ayudar al propietario a identificar qué actividades de mantenimiento deberían revisarse o realizarse próximamente.

Por ejemplo:

Propietario registra:

Vehículo: HWG123

Kilometraje actual: 75.000 km

Último cambio de aceite:

70.000 km

15/08/2026

Regla:

Cada 5.000 km o 3 meses

El sistema podrá determinar:

Próximo kilometraje:

75.000 km

Próxima fecha:

15/11/2026

Estado:

Próximo mantenimiento

De esta manera, el propietario no necesita recordar manualmente todos los mantenimientos realizados ni conocer en detalle las reglas técnicas de cada servicio para tener una referencia sobre qué debería revisar.

La aplicación deberá convertirse en una herramienta de consulta y acompañamiento permanente del vehículo.

El usuario podrá abrir la aplicación y consultar de manera sencilla:

```text
¿Qué se le ha hecho a mi vehículo?

        ↓

¿Qué se le está haciendo actualmente?

        ↓

¿Qué debería revisar próximamente?

        ↓

¿Qué mantenimientos están vencidos?

        ↓

¿Cuánto he invertido?

        ↓

¿Qué taller realizó cada servicio?

        ↓

¿Qué debería revisar antes de un 
```


Relación con los Prestadores de Servicios Vehiculares

Esta misma información tendrá un valor importante para los Prestadores de Servicios Vehiculares.

Cuando un propietario autorice a un Prestador de Servicios Vehiculares para consultar la información de su vehículo, el prestador podrá visualizar información actualizada y relevante de acuerdo con los permisos otorgados y con la naturaleza de los servicios que presta.

Por ejemplo:

Vehículo: HWG123

Cliente: Juan

Kilometraje actual: 75.300 km

Último servicio:

Cambio de pastillas de freno

Fecha: 15/02/2026

Kilometraje: 60.000 km

Tiempo transcurrido:

6 meses

A partir de esta información, un Prestador de Servicios Vehiculares que realice actividades de mantenimiento podrá identificar oportunidades de seguimiento y, de acuerdo con sus criterios técnicos, comunicarse con el propietario para recomendar una revisión.

Por ejemplo:

"Han transcurrido aproximadamente seis meses desde el último servicio de frenos. Se recomienda realizar una revisión del sistema para verificar el estado de las pastillas, discos y demás componentes."

De esta manera, el prestador que corresponda no dependerá exclusivamente de que el cliente recuerde regresar.

La plataforma permitirá establecer una relación continua entre:

```text
PROPIETARIO

     ↕

VEHÍCULO

     ↕

HISTORIAL

     ↕

PRESTADOR DE SERVICIOS VEHICULARES
```

Cuando el propietario actualice información como el kilometraje, dicha información podrá estar disponible en línea para los talleres que cuenten con autorización.

Esto permitirá que el taller tenga mayor visibilidad sobre la evolución del vehículo y pueda tomar decisiones de seguimiento basadas en información actualizada.

Beneficio adicional: venta o transferencia del vehículo

La información acumulada durante el ciclo de vida del vehículo también podrá utilizarse cuando el propietario decida venderlo.

En ese escenario, el propietario podrá generar un reporte consolidado con información como:

Historial de mantenimientos.

Reparaciones realizadas.

Repuestos reemplazados.

Kilometrajes registrados.

Fechas de intervención.

Talleres que realizaron los servicios.

Costos registrados.

Documentos y facturas disponibles.

Esto permitirá presentar al potencial comprador una trazabilidad organizada del vehículo.

Sin embargo, la venta del vehículo representa solamente uno de los posibles usos del historial y no constituye el objetivo principal de la aplicación.

El objetivo principal de Vehículos Services es acompañar al propietario durante todo el ciclo de vida del vehículo, ayudándolo a conocer, controlar y mantener actualizada la información relacionada con su vehículo y proporcionándole herramientas para anticipar sus necesidades de mantenimiento.

De forma complementaria, la plataforma deberá ayudar al propietario a prepararse ante situaciones específicas que requieran una revisión del vehículo, como viajes largos.

La propuesta de valor puede resumirse en:

```text
              VEHÍCULO

                  ↓

        HISTORIAL DIGITAL

                  ↓

       INFORMACIÓN CENTRALIZADA

                  ↓

        CÁLCULO Y SEGUIMIENTO

                  ↓

       ALERTAS Y RECOMENDACIONES

                  ↓

        PROPIETARIO INFORMADO

                  ↓

         MEJOR MANTENIMIENTO

                  ↓

       MAYOR VIDA ÚTIL DEL VEHÍCULO

                  ↓

         MEJOR TRAZABILIDAD

                  ↓

      PREPARACIÓN PARA SITUACIONES

          COMO VIAJES LARGOS

                  ↓

       VALOR ADICIONAL AL VENDER
```

Por parte del taller:

```text
         VEHÍCULO DEL CLIENTE

                  ↓

          HISTORIAL ACTUALIZADO

                  ↓

        VISIBILIDAD DEL VEHÍCULO

                  ↓

       IDENTIFICACIÓN DE SERVICIOS

                  ↓

        SEGUIMIENTO AL CLIENTE

                  ↓

         COMUNICACIÓN OPORTUNA

                  ↓

        NUEVAS VISITAS AL TALLER

                  ↓

        FIDELIZACIÓN DEL CLIENTE
```

Por lo tanto, Vehículos Services debe entenderse como una plataforma de gestión y acompañamiento del ciclo de vida del vehículo, y no únicamente como una herramienta para almacenar el historial o facilitar la venta del automóvil.

---

# 4. Situación actual

El proyecto se encuentra en etapa inicial de levantamiento y definición de requerimientos.

Actualmente no existe una solución propia implementada que centralice en una única plataforma:

- Información del vehículo.
- Historial de mantenimiento.
- Reparaciones.
- Repuestos.
- Kilometraje.
- Costos.
- Prestadores de Servicios Vehiculares.
- Documentos.
- Próximos mantenimientos.
- Alertas.
- Seguimiento entre propietario y Prestadores de Servicios Vehiculares.
- Preparación y recomendaciones previas a viajes.

Como parte del levantamiento de requerimientos se deberá documentar con mayor detalle la situación actual de propietarios y Prestadores de Servicios Vehiculares, identificando procesos, necesidades, problemas y oportunidades de automatización.

---

# 5. Problema identificado

## 5.1 Problema del propietario

El propietario puede perder fácilmente la trazabilidad del mantenimiento del vehículo debido a que la información histórica no se encuentra centralizada.

La ausencia de información estructurada puede ocasionar:

- Olvido de mantenimientos periódicos.
- Realización tardía de mantenimientos.
- Dificultad para conocer cuándo se realizó una intervención.
- Dificultad para identificar los repuestos instalados.
- Pérdida de facturas y documentos.
- Desconocimiento de los costos históricos.
- Dificultad para identificar el Prestador de Servicios Vehiculares que realizó una intervención, servicio, diagnóstico, inspección, evaluación o peritaje.
- Falta de información al momento de vender el vehículo.
- Dificultad para demostrar el mantenimiento realizado.
- Falta de conocimiento sobre los próximos mantenimientos requeridos.
- Dependencia de la memoria del propietario.
- Falta de visibilidad sobre el estado general del vehículo.
- Falta de orientación sobre los elementos que deberían revisarse antes de un viaje largo.

## 5.2 Problema del Prestador de Servicios Vehiculares

Desde la perspectiva de los Prestadores de Servicios Vehiculares pueden existir diferentes necesidades y problemáticas dependiendo de la naturaleza de los servicios que prestan.

En el caso de los Prestadores de Servicios Vehiculares que realizan actividades de mantenimiento, reparación o servicios recurrentes sobre un vehículo, existe una problemática relacionada con la continuidad y fidelización del cliente.

Una vez realizado un servicio, el prestador puede perder el seguimiento sobre el vehículo y depender de que el cliente recuerde cuándo debe regresar o realizar una nueva revisión.

Por ejemplo, un taller puede realizar:

```text
Cambio de pastillas de freno

Fecha: 15/02/2026

Kilometraje: 60.000 km
```

Después de varios meses, puede ser recomendable realizar una revisión del sistema de frenos.

Sin una herramienta de seguimiento, el Prestador de Servicios Vehiculares que realiza este tipo de actividades puede no disponer de mecanismos adecuados para identificar estos casos y contactar oportunamente al cliente.

Esto representa una oportunidad perdida de servicio y una dificultad para mantener una relación continua con el propietario.

Otros tipos de Prestadores de Servicios Vehiculares, como centros de peritaje, centros de diagnóstico, centros de inspección u otros prestadores especializados, podrán presentar necesidades diferentes de acuerdo con la naturaleza de los servicios que realizan.

Estas necesidades deberán ser identificadas y definidas posteriormente durante el levantamiento detallado correspondiente a cada tipo de prestador.

---

# 6. Necesidad

Se requiere desarrollar una solución tecnológica que permita centralizar y administrar la información relacionada con los vehículos, su mantenimiento y los diferentes eventos generados durante su ciclo de vida.

La solución deberá permitir que los propietarios gestionen sus vehículos y consulten su historial, mientras que los Prestadores de Servicios Vehiculares autorizados podrán registrar y consultar información correspondiente a los servicios, intervenciones, diagnósticos, inspecciones, evaluaciones o peritajes que realicen sobre dichos vehículos, de acuerdo con la naturaleza de los servicios que prestan y los permisos que posteriormente sean definidos.

El sistema deberá proporcionar mecanismos para:

- Registrar información.
- Consultar información.
- Actualizar información.
- Mantener historial.
- Calcular próximos mantenimientos.
- Generar alertas.
- Generar recomendaciones.
- Facilitar seguimiento.
- Facilitar la comunicación entre propietarios y Prestadores de Servicios Vehiculares.
- Generar reportes.
- Preparar al propietario para viajes largos.
- Generar listas de revisión previas a un viaje.
- Identificar mantenimientos pendientes antes de un viaje.

La solución deberá convertir la información histórica del vehículo en información útil para la toma de decisiones.

---

# 7. Oportunidad

Existe una oportunidad para desarrollar una solución especializada que centralice la gestión del ciclo de vida del vehículo y conecte la información del propietario con la información generada por los diferentes Prestadores de Servicios Vehiculares.

La plataforma podrá evolucionar posteriormente hacia un ecosistema de servicios vehiculares que permita:

- Mantener un historial vehicular centralizado.
- Facilitar la interacción y comunicación entre propietarios y Prestadores de Servicios Vehiculares, cuando corresponda según la naturaleza del servicio.
- Mejorar la trazabilidad de los servicios, intervenciones, diagnósticos, inspecciones, evaluaciones y peritajes realizados sobre el vehículo.
- Facilitar la programación y seguimiento de mantenimientos.
- Generar indicadores.
- Analizar costos.
- Facilitar la consulta del historial antes de comprar o vender un vehículo.
- Facilitar la transferencia del historial ante un cambio de propietario.
- Preparar al propietario para viajes.
- Generar listas de revisión previas a viajes.
- Integrar posteriormente servicios de mapas, rutas y distancias.
- Generar recomendaciones contextuales según el uso del vehículo.

La afirmación de que "no existe actualmente una aplicación que haga esto" se considera inicialmente una hipótesis y deberá ser validada posteriormente mediante un análisis de mercado y competencia.

---

# 8. Objetivos

## 8.1 Objetivo general

Desarrollar una plataforma multiplataforma para Android e iOS que permita gestionar de manera centralizada la información relacionada con los vehículos y su ciclo de vida, proporcionando trazabilidad sobre los servicios, intervenciones, mantenimientos, reparaciones, diagnósticos, inspecciones, evaluaciones y demás eventos registrados sobre el vehículo, y automatizando el seguimiento de futuras necesidades de mantenimiento.

La aplicación deberá transformar la información histórica registrada sobre cada vehículo en información útil para la toma de decisiones, permitiendo al propietario conocer el estado de su vehículo y anticipar sus necesidades de mantenimiento.

Adicionalmente, deberá proporcionar a los Prestadores de Servicios Vehiculares autorizados herramientas acordes con la naturaleza de los servicios que prestan y con los permisos otorgados sobre cada vehículo. En el caso de los prestadores que realizan actividades de mantenimiento o servicios recurrentes, la plataforma podrá proporcionar herramientas para realizar seguimiento de los vehículos atendidos y mantener una relación continua con sus clientes.

Como capacidad complementaria, la plataforma deberá permitir al propietario indicar la realización de un viaje y recibir recomendaciones de revisión basadas en la información disponible del vehículo, el kilometraje, el historial de mantenimiento y las reglas definidas para preparación de viajes.

## 8.2 Objetivos específicos

1. Permitir registrar y administrar uno o varios vehículos asociados a un propietario.

2. Centralizar el historial de mantenimientos, servicios, intervenciones, diagnósticos, inspecciones, evaluaciones y demás eventos registrados sobre el vehículo.

3. Registrar el kilometraje actual e histórico del vehículo.

4. Registrar mantenimientos preventivos y correctivos.

5. Registrar reparaciones.

6. Registrar repuestos utilizados.

7. Registrar costos.

8. Asociar cada servicio, intervención, diagnóstico, inspección, evaluación o peritaje con el Prestador de Servicios Vehiculares correspondiente, cuando aplique.

9. Adjuntar documentos, facturas y evidencias.

10. Calcular próximos mantenimientos.

11. Generar alertas y notificaciones.

12. Generar recomendaciones basadas en reglas.

13. Permitir a los Prestadores de Servicios Vehiculares registrar información correspondiente a los servicios, intervenciones, diagnósticos, inspecciones, evaluaciones o peritajes que realicen, de acuerdo con la naturaleza de los servicios que prestan y los permisos definidos.

14. Permitir a los Prestadores de Servicios Vehiculares que realizan actividades de mantenimiento o servicios recurrentes efectuar seguimiento de los vehículos atendidos y de sus clientes, de acuerdo con los permisos definidos.

15. Mantener control de acceso sobre la información.

16. Mantener trazabilidad de modificaciones.

17. Generar reportes consolidados del historial.

18. Preparar la plataforma para un modelo de suscripción.

19. Mantener la información disponible en línea para usuarios autorizados.

20. Crear una base tecnológica preparada para acompañar el ciclo de vida completo del vehículo.

21. Permitir registrar un viaje indicando destino o distancia estimada.

22. Analizar la información disponible del vehículo antes de un viaje.

23. Identificar mantenimientos vencidos o próximos a vencer que puedan requerir atención antes del viaje.

24. Generar una lista de verificación previa al viaje.

25. Generar recomendaciones relacionadas con fluidos, frenos, neumáticos, luces, batería y elementos de seguridad.

26. Diferenciar las recomendaciones automáticas de una inspección o diagnóstico profesional.

---

# 9. Alcance

## 9.1 Incluido inicialmente

El alcance inicial contempla:

- Aplicación Android.
- Aplicación iOS.
- Gestión de usuarios.
- Gestión de propietarios.
- Gestión de Prestadores de Servicios Vehiculares.
- Gestión de vehículos.
- Registro de kilometraje.
- Historial de kilometraje.
- Gestión de mantenimientos.
- Gestión de reparaciones.
- Gestión de repuestos.
- Gestión de costos.
- Gestión de documentos.
- Historial vehicular.
- Asociación entre vehículos y Prestadores de Servicios Vehiculares.
- Control de acceso.
- Cálculo de próximos mantenimientos.
- Reglas por kilometraje.
- Reglas por tiempo.
- Reglas por kilometraje y tiempo.
- Alertas.
- Notificaciones.
- Recomendaciones.
- Seguimiento de vehículos.
- Reportes.
- Preparación para viajes.
- Registro de destino o distancia estimada.
- Checklist previo al viaje.
- Recomendaciones de revisión antes de viajes.
- Identificación de mantenimientos pendientes antes de un viaje.

### Enfoque modular y progresivo del desarrollo

La inclusión de los diferentes componentes dentro del alcance de Vehículos Services no deberá interpretarse como que todos serán desarrollados simultáneamente.

El desarrollo de la solución se realizará de manera modular y progresiva, contemplando inicialmente el frente correspondiente al Propietario y posteriormente el frente correspondiente al Prestador de Servicios Vehiculares.

Conceptualmente:

```text
PRIMERA ETAPA
MÓDULO PROPIETARIO
        ↓
Desarrollo de las funcionalidades necesarias
para que el propietario pueda gestionar
sus vehículos y la información asociada
de manera independiente
        ↓
SEGUNDA ETAPA
MÓDULO PRESTADOR DE SERVICIOS VEHICULARES
        ↓
Desarrollo de las funcionalidades propias
del prestador
        ↓
TERCERA ETAPA
INTEGRACIÓN
        ↓
PROPIETARIO ↔ VEHÍCULO ↔ PRESTADOR
```

La primera etapa deberá permitir que el Propietario utilice las funcionalidades que le correspondan sin depender de que el módulo del Prestador de Servicios Vehiculares se encuentre implementado.

Esto significa que las funcionalidades correspondientes al Propietario deberán poder operar de manera independiente durante esta etapa. Cuando una funcionalidad permita registrar información asociada al vehículo, su funcionamiento no deberá depender obligatoriamente de la existencia de un Prestador de Servicios Vehiculares registrado o relacionado con el vehículo, salvo que la naturaleza específica de la funcionalidad posteriormente definida requiera dicha participación.

La segunda etapa corresponderá al desarrollo de las funcionalidades propias del Prestador de Servicios Vehiculares, incluyendo las capacidades que posteriormente sean definidas para su operación dentro de Vehículos Services.

La tercera etapa contemplará la integración entre ambos frentes, permitiendo que Propietarios y Prestadores de Servicios Vehiculares interactúen alrededor de los mismos vehículos, servicios, registros e historial, de acuerdo con las relaciones, autorizaciones, permisos y reglas de negocio previamente definidas.

La incorporación posterior del módulo del Prestador de Servicios Vehiculares no deberá requerir reconstruir ni reiniciar la información previamente registrada desde el módulo del Propietario. La información existente deberá poder continuar formando parte del ciclo de vida digital del vehículo y relacionarse con las nuevas funcionalidades cuando corresponda.

Por lo tanto, conceptualmente:

```text
MÓDULO PROPIETARIO
        ↓
FUNCIONA DE MANERA INDEPENDIENTE
        ↓
VEHÍCULOS + INFORMACIÓN + HISTORIAL
        ↓
SE INCORPORA POSTERIORMENTE
MÓDULO PRESTADOR
        ↓
INTEGRACIÓN ENTRE AMBOS FRENTES
        ↓
MISMO VEHÍCULO
MISMO CICLO DE VIDA DIGITAL
HISTORIAL CONTINUO
```

La distribución definitiva de funcionalidades entre etapas, su priorización, dependencias, criterios de implementación y alcance específico será desarrollada posteriormente durante la definición del MVP, roadmap y planificación del desarrollo.

El alcance definitivo deberá establecerse después de completar el levantamiento funcional y la priorización del MVP.

## 9.2 Fuera del alcance inicial

Inicialmente se consideran fuera del MVP:

- Marketplace de vehículos.
- Venta directa de vehículos.
- Venta directa de repuestos.
- Pagos dentro de la aplicación.
- Financiación.
- Contratación directa de seguros.
- Diagnóstico automático mediante inteligencia artificial.
- Integración con fabricantes.
- Integración con sistemas gubernamentales.
- Telemetría en tiempo real mediante dispositivos IoT.
- Integración directa con computadores del vehículo.
- Gestión avanzada de flotas empresariales.
- Navegación GPS completa.
- Planificación avanzada de rutas.
- Cálculo automático de rutas mediante mapas externos.

Estas funcionalidades podrán evaluarse para futuras versiones.

La funcionalidad de preparación para viajes no deberá interpretarse como un sistema de navegación. Inicialmente tendrá como objetivo utilizar la información del vehículo para generar recomendaciones y verificaciones previas al viaje.

---

# 10. Actores y usuarios

## 10.1 Tipos de usuario

Inicialmente se contemplan dos frentes principales de acceso a Vehículos Services:

### Propietario / Cliente

Usuario que accede a Vehículos Services como propietario de uno o varios vehículos o para gestionar los vehículos sobre los cuales cuente con las autorizaciones correspondientes.

### Prestador de Servicios Vehiculares

Entidad representada dentro de Vehículos Services que presta servicios relacionados con la revisión, mantenimiento, diagnóstico, reparación, inspección, peritaje o intervención de vehículos.

El Prestador de Servicios Vehiculares podrá corresponder a diferentes tipos de prestadores, de acuerdo con la clasificación que posteriormente sea definida y con la naturaleza de los servicios que realiza.

El Prestador de Servicios Vehiculares deberá diferenciarse de las personas que acceden a la plataforma en su representación.

Por lo tanto, conceptualmente:

```text
PRESTADOR DE SERVICIOS VEHICULARES
        ↓
Entidad / establecimiento / empresa
        ↓
USUARIOS AUTORIZADOS
        ↓
Personas que acceden a Vehículos Services
en representación del prestador
```

La existencia de un usuario asociado a un Prestador de Servicios Vehiculares no deberá implicar que dicho usuario sea individualmente el prestador.

Los tipos específicos de usuarios asociados a un prestador, sus funciones, niveles de acceso y permisos serán definidos posteriormente.

---

# 11. Propietario

El propietario deberá poder:

- Crear una cuenta.
- Iniciar sesión.
- Gestionar su perfil.
- Registrar vehículos.
- Consultar vehículos.
- Actualizar información autorizada.
- Solicitar a soporte la corrección de errores en los datos que no pueda editar directamente.
- Registrar kilometraje.
- Consultar historial.
- Registrar mantenimientos.
- Registrar reparaciones.
- Registrar repuestos.
- Registrar costos.
- Adjuntar documentos.
- Consultar próximos mantenimientos.
- Consultar mantenimientos vencidos.
- Consultar recomendaciones.
- Consultar Prestadores de Servicios Vehiculares relacionados con el vehículo.
- Autorizar Prestadores de Servicios Vehiculares.
- Revocar accesos.
- Recibir notificaciones.
- Generar reportes del vehículo.
- Registrar un viaje.
- Indicar ciudad destino.
- Indicar distancia estimada.
- Consultar recomendaciones previas al viaje.
- Consultar checklist de preparación para viaje.
- Registrar manualmente el resultado de una revisión, cuando esta funcionalidad sea definida.
- Consultar qué mantenimientos deberían atenderse antes del viaje.

Para la primera entrega, el celular de contacto será obligatorio para completar la información del propietario antes de asociar su primer vehículo, sin exigirlo para crear inicialmente la cuenta. El usuario podrá actualizarlo directamente, pero no eliminarlo ni dejarlo vacío mediante una actualización aceptada.

La ciudad de residencia y la fotografía de perfil serán datos opcionales que el usuario podrá agregar, actualizar o retirar. La dirección exacta de residencia no se solicitará inicialmente.

Después de confirmar, aceptar y guardar los datos correspondientes, el usuario no podrá editar ni eliminar directamente el correo de la cuenta, los nombres, apellidos, tipo y número de documento de identificación ni los datos obligatorios aplicables del vehículo. Los errores de captura se tramitarán mediante soporte conforme a RN-037 — Actualización de datos personales y correcciones mediante soporte, de `reglas-negocio.md`, y RF-052 de `requerimientos-funcionales-propietario.md`.

La actualización del kilometraje continuará mediante nuevos registros conforme a su requerimiento específico, sin permitir sobrescribir la lectura inicial ni las anteriores desde la información general del vehículo. La contraseña y los métodos de acceso conservarán sus procedimientos específicos de gestión y recuperación.

Las correcciones mediante soporte no permitirán sustituir identidades, fusionar cuentas o vehículos ni transferir propiedad. Los conflictos entre cuentas y los conflictos vehiculares conservarán sus procedimientos y límites correspondientes.


---

# 12. Prestador de Servicios Vehiculares

El Prestador de Servicios Vehiculares deberá poder acceder a funcionalidades de acuerdo con su tipo, la naturaleza de los servicios que presta, las autorizaciones otorgadas y los permisos que posteriormente sean definidos.

De manera general, la plataforma deberá permitir:

- Crear una cuenta o registrar la información correspondiente al Prestador de Servicios Vehiculares.
- Gestionar la información del Prestador de Servicios Vehiculares.
- Registrar o relacionar clientes, cuando corresponda.
- Registrar o relacionar vehículos, cuando corresponda.
- Solicitar acceso a vehículos.
- Consultar vehículos autorizados.
- Consultar la información del historial para la cual cuente con autorización.
- Registrar información correspondiente a los servicios, intervenciones, diagnósticos, inspecciones, evaluaciones o peritajes que realice.
- Registrar el kilometraje correspondiente a una intervención, servicio, inspección, evaluación o peritaje, cuando aplique.
- Registrar costos asociados a los servicios realizados, cuando aplique.
- Adjuntar facturas, documentos o evidencias relacionadas con los servicios realizados, cuando aplique.
- Consultar sus propias intervenciones y registros históricos sobre los vehículos autorizados.
- Consultar el kilometraje actual del vehículo cuando exista una relación autorizada.
- Consultar únicamente la información básica del propietario habilitada para la relación.
- Contactar propietarios mediante los mecanismos que posteriormente sean habilitados, cuando corresponda.

Las funcionalidades disponibles no deberán ser necesariamente iguales para todos los tipos de Prestadores de Servicios Vehiculares.

Por ejemplo, un Prestador de Servicios Vehiculares que realice actividades de mantenimiento o reparación podrá, de acuerdo con las autorizaciones y permisos definidos:

- Registrar mantenimientos.
- Registrar reparaciones.
- Registrar repuestos utilizados.
- Registrar diagnósticos.
- Programar próximos mantenimientos.
- Generar recomendaciones relacionadas con los servicios realizados.
- Consultar oportunidades de seguimiento.
- Identificar mantenimientos próximos o vencidos.
- Consultar, cuando corresponda, que un vehículo tiene una preparación de viaje pendiente o una recomendación de revisión.

Por otra parte, un Prestador de Servicios Vehiculares dedicado al peritaje podrá requerir funcionalidades diferentes, relacionadas con el registro de la evaluación realizada, sus resultados, documentos y evidencias.

De igual manera, otros tipos de Prestadores de Servicios Vehiculares podrán disponer de funcionalidades específicas de acuerdo con la naturaleza de los servicios que presten.

La definición detallada de las funcionalidades disponibles para cada tipo de Prestador de Servicios Vehiculares, así como sus usuarios asociados, roles, autorizaciones y permisos, será desarrollada posteriormente en los apartados correspondientes.

---

# 13. Relación propietario - Prestador de Servicios Vehiculares

La relación entre el propietario y un Prestador de Servicios Vehiculares deberá estar basada en el vehículo.

```text
                         VEHÍCULO

                            │

              ┌─────────────┴─────────────┐
              │                           │

         PROPIETARIO            PRESTADOR DE SERVICIOS
                                    VEHICULARES

              │                           │

        Controla el              Presta servicios,
         vehículo                  interviene,
                                  revisa, evalúa,
                               diagnostica o inspecciona
                                    el vehículo

              │                           │

              └─────────────┬─────────────┘

                            ↓

                    HISTORIAL VEHICULAR
```

Un vehículo podrá relacionarse con diferentes Prestadores de Servicios Vehiculares durante su ciclo de vida.

La naturaleza de dicha relación podrá variar dependiendo del tipo de prestador y de los servicios realizados sobre el vehículo.

Por ejemplo, un mismo vehículo podrá recibir diferentes intervenciones de distintos talleres:

```text
Vehículo HWG123

│

├── Taller ABC
│   ├── Cambio de aceite
│   └── Filtros
│
├── Taller XYZ
│   ├── Frenos
│   └── Alineación
│
└── Taller DEF
    └── Suspensión
```

De igual manera, el vehículo podrá relacionarse con otros tipos de Prestadores de Servicios Vehiculares.

Por ejemplo:

```text
Vehículo HWG123

│

├── Taller mecánico
│   └── Mantenimiento
│
├── Centro de diagnóstico
│   └── Diagnóstico
│
├── Centro de peritaje
│   └── Peritaje
│
└── Taller especializado
    └── Reparación
```

El historial deberá conservarse independientemente del Prestador de Servicios Vehiculares que haya realizado cada servicio, intervención, revisión, diagnóstico, inspección, evaluación o peritaje.

---

# 14. Procesos de negocio

## 14.1 Proceso actual

Pendiente de levantamiento detallado.

Se deberá documentar cómo actualmente:

- El propietario registra sus mantenimientos.
- El propietario consulta su historial.
- El propietario controla el kilometraje.
- El propietario recibe recomendaciones.
- El propietario se prepara para viajes largos.
- Los diferentes Prestadores de Servicios Vehiculares realizan y registran los servicios correspondientes a su actividad.
- Los Prestadores de Servicios Vehiculares que realizan actividades de mantenimiento o servicios recurrentes hacen seguimiento de clientes.
- Los Prestadores de Servicios Vehiculares que realizan actividades de mantenimiento o servicios recurrentes identifican próximos servicios.
- Los Prestadores de Servicios Vehiculares se comunican con los propietarios cuando corresponda.

Los procesos específicos podrán variar dependiendo del tipo de Prestador de Servicios Vehiculares y de la naturaleza de los servicios que realice.

## 14.2 Proceso propuesto

El siguiente flujo representa inicialmente el proceso relacionado con el registro del vehículo, seguimiento de mantenimiento y participación de un Prestador de Servicios Vehiculares que realiza actividades de mantenimiento o servicios recurrentes:

```text
1. Usuario crea cuenta

        ↓

2. Registra vehículo

        ↓

3. Registra información inicial

        ↓

4. Registra kilometraje

        ↓

5. Registra historial existente

        ↓

6. Sistema almacena información

        ↓

7. Motor calcula próximos mantenimientos

        ↓

8. Sistema genera alertas

        ↓

9. Propietario actualiza kilometraje

        ↓

10. Sistema recalcula condiciones

        ↓

11. Prestador de Servicios Vehiculares autorizado
    consulta únicamente la información permitida: sus propias intervenciones, kilometraje actual y demás información expresamente habilitada

        ↓

12. Prestador identifica oportunidad de servicio

        ↓

13. Prestador realiza seguimiento

        ↓

14. Cliente realiza servicio

        ↓

15. Prestador registra intervención

        ↓

16. Historial se actualiza

        ↓

17. Sistema recalcula mantenimientos

        ↓

18. Propietario solicita preparación para viaje

        ↓

19. Sistema analiza información del vehículo

        ↓

20. Sistema genera checklist y recomendaciones

        ↓

21. Propietario realiza verificaciones

        ↓

22. Continúa el ciclo
```

Este flujo no deberá interpretarse como el proceso único aplicable a todos los Prestadores de Servicios Vehiculares.

Los procesos correspondientes a otros tipos de prestadores, como centros de peritaje, centros de diagnóstico, centros de inspección u otros servicios especializados, deberán definirse posteriormente de acuerdo con la naturaleza de sus actividades.

---

# 15. Ciclo de vida digital del vehículo

El vehículo deberá ser considerado como el principal activo de información de la plataforma.

El historial deberá acompañar al vehículo durante su ciclo de vida, de acuerdo con las reglas de propiedad y transferencia que se definan.

```text
Compra del vehículo

        ↓

Registro en la aplicación

        ↓

Registro de información inicial

        ↓

Historial existente

        ↓

Mantenimiento preventivo

        ↓

Reparación

        ↓

Cambio de repuesto

        ↓

Nuevo mantenimiento

        ↓

Actualización de kilometraje

        ↓

Alertas

        ↓

Seguimiento

        ↓

Preparación para viajes

        ↓

Nuevo servicio

        ↓

Actualización del historial

        ↓

Venta del vehículo

        ↓

Transferencia

        ↓

Nuevo propietario

        ↓

Continúa el historial
```

---

# 16. Historial vehicular

El historial vehicular será uno de los componentes principales de la plataforma.

Cada vehículo deberá contar con un historial estructurado que permita registrar la información, eventos, documentos, intervenciones y demás registros relevantes asociados al vehículo durante su ciclo de vida.

El historial podrá contener:

- Mantenimientos.
- Reparaciones.
- Repuestos.
- Inspecciones.
- Diagnósticos.
- Peritajes.
- Evaluaciones.
- Kilometraje.
- Costos.
- Prestadores de Servicios Vehiculares relacionados con los eventos registrados.
- Pólizas de seguros.
- SOAT o documentos equivalentes según el país.
- Revisión técnico-mecánica o documentos equivalentes según el país.
- Impuestos asociados al vehículo.
- Documentos.
- Facturas.
- Observaciones.
- Fechas.
- Evidencias fotográficas.
- Revisiones previas a viajes.
- Resultados de verificaciones realizadas por el propietario, cuando esta funcionalidad sea definida.
- Otros registros o interacciones relevantes asociados al vehículo que posteriormente sean definidos.

La información deberá mantenerse de manera cronológica.

---

# 17. Gestión del kilometraje

El kilometraje será un dato dinámico y relevante para múltiples procesos del sistema.

Vehículos Services deberá mantener un kilometraje actual para cada vehículo y permitir su actualización a partir de nuevas lecturas de kilometraje, de acuerdo con las reglas de procedencia, validación y consistencia que posteriormente sean definidas.

Cuando se registre una nueva lectura que pueda representar una actualización del kilometraje actual, el sistema deberá:

1. Registrar la nueva lectura y la información disponible sobre su contexto.
2. Validar que la lectura sea consistente con la información existente del vehículo.
3. Determinar si la lectura puede actualizar el kilometraje actual.
4. Actualizar el kilometraje actual cuando corresponda.
5. Conservar la lectura de acuerdo con las reglas aplicables al historial de kilometraje.
6. Recalcular los procesos dependientes del kilometraje cuando la actualización del kilometraje actual así lo requiera.
7. Actualizar los estados correspondientes.
8. Generar alertas o recomendaciones cuando corresponda.
9. Actualizar la información disponible para los Prestadores de Servicios Vehiculares autorizados, de acuerdo con los permisos definidos.
10. Utilizar el kilometraje actual resultante como referencia para futuras recomendaciones de preparación para viajes.

Conceptualmente:

```text
NUEVA LECTURA
        ↓
REGISTRO
        ↓
VALIDACIÓN
        ↓
¿PUEDE ACTUALIZAR
EL KILOMETRAJE ACTUAL?
        │
    ┌───┴───┐
    ↓       ↓
   SÍ       NO
    │       │
    ↓       ↓
ACTUALIZA   NO MODIFICA
KM ACTUAL   AUTOMÁTICAMENTE
    │       EL KM ACTUAL
    ↓
PROCESOS DEPENDIENTES
DEL KILOMETRAJE
```

Una nueva lectura no deberá considerarse automáticamente como un nuevo kilometraje actual.

Las lecturas podrán originarse en diferentes contextos durante el ciclo de vida del vehículo. La definición detallada de sus fuentes, procedencia, validación, consistencia, conservación histórica y trazabilidad deberá desarrollarse dentro de `63.9 KILOMETRAJE`.

Vehículos Services deberá solicitar periódicamente al propietario la actualización del kilometraje del vehículo con el propósito de mantener una referencia suficientemente reciente para los procesos que dependan de la distancia recorrida.

La periodicidad, condiciones y mecanismos específicos utilizados para estas solicitudes deberán definirse posteriormente dentro de los componentes funcionales correspondientes.

La actualización del kilometraje actual deberá reflejarse para los Prestadores de Servicios Vehiculares que tengan autorización para consultar dicha información sobre el vehículo, de acuerdo con los permisos definidos.

---


# 18. Motor de mantenimiento

La plataforma deberá contar con un componente encargado de determinar las condiciones de mantenimiento de cada vehículo.

El motor deberá utilizar información como:

- Fecha de última intervención.
- Kilometraje de última intervención.
- Kilometraje actual.
- Intervalo recomendado por kilometraje.
- Intervalo recomendado por tiempo.
- Historial.
- Clasificación o naturaleza del mantenimiento, cuando corresponda.
- Criterio de seguimiento aplicable, cuando corresponda.
- Reglas específicas.
- Configuraciones del vehículo.

El flujo conceptual será:

```text
Historial

    +

Kilometraje actual

    +

Fecha actual

    +

Reglas

    ↓

Motor de mantenimiento

    ↓

Estado

    ↓

Alerta / recomendación
```

Este motor podrá ser utilizado como uno de los componentes principales para la funcionalidad de preparación para viajes.

Cuando el propietario solicite una revisión previa a un viaje, el sistema podrá utilizar los resultados del motor de mantenimiento para identificar:

- Mantenimientos vencidos.
- Mantenimientos próximos a vencer.
- Mantenimientos que podrían coincidir con el kilometraje estimado del viaje.
- Servicios relacionados con componentes relevantes para el viaje.

---

# 19. Criterios de seguimiento del mantenimiento

Vehículos Services deberá permitir que los mantenimientos o actividades que requieran seguimiento puedan controlarse mediante diferentes criterios, según las reglas que correspondan a cada caso.

Estos criterios deberán indicar mediante qué condición se controla cuándo corresponde realizar nuevamente una determinada intervención.

Conceptualmente:

```text
MANTENIMIENTO / ACTIVIDAD
        ↓
¿REQUIERE SEGUIMIENTO?
        │
    ┌───┴───┐
    ↓       ↓
   SÍ       NO
    │       │
    ↓       ↓
CRITERIO   PERMANECE COMO
DE         EVENTO HISTÓRICO
SEGUIMIENTO SIN GENERAR
           NECESARIAMENTE
           UNA PRÓXIMA
           INTERVENCIÓN
```

Cuando exista seguimiento, inicialmente podrán contemplarse criterios basados en:

- Kilometraje.
- Tiempo.
- Kilometraje y tiempo.
- Otros criterios que posteriormente puedan ser definidos.

Estos criterios no deberán confundirse con la clasificación o naturaleza del mantenimiento.

Por lo tanto:

```text
PREVENTIVO
PERIÓDICO
CORRECTIVO
        ↓
CLASIFICACIÓN O NATURALEZA

        ≠

KILOMETRAJE
TIEMPO
KILOMETRAJE + TIEMPO
        ↓
CRITERIOS DE SEGUIMIENTO
```

La clasificación deberá permitir identificar la naturaleza o contexto general de la intervención, mientras que el criterio de seguimiento deberá determinar mediante qué condición se controla su recurrencia cuando corresponda.

## 19.1 Seguimiento por kilometraje

Un mantenimiento o actividad podrá requerir seguimiento con base en el kilometraje recorrido por el vehículo.

Ejemplo:

```text
Cambio de aceite
        ↓
Seguimiento por kilometraje
        ↓
Cada 5.000 km
```

En estos casos, el kilometraje deberá actuar como uno de los elementos utilizados para determinar cuándo corresponde realizar nuevamente la intervención.

La definición detallada del kilometraje de referencia, intervalos, próximos objetivos, kilómetros transcurridos, kilómetros restantes, validaciones y demás cálculos deberá desarrollarse posteriormente dentro de los componentes correspondientes a Kilometraje y Reglas de Mantenimiento.

## 19.2 Seguimiento por tiempo

Un mantenimiento o actividad podrá requerir seguimiento con base en el tiempo transcurrido.

Ejemplo:

```text
Servicio específico
        ↓
Seguimiento por tiempo
        ↓
Cada 6 meses
```

En estos casos, el tiempo deberá actuar como uno de los elementos utilizados para determinar cuándo corresponde realizar nuevamente la intervención.

La definición detallada de fechas de referencia, intervalos, próximas fechas objetivo, tiempo transcurrido, tiempo restante y demás cálculos deberá desarrollarse posteriormente dentro de Reglas de Mantenimiento.

## 19.3 Seguimiento por kilometraje y tiempo

Un mantenimiento o actividad podrá requerir seguimiento mediante la combinación de kilometraje y tiempo.

Ejemplo:

```text
Cambio de aceite
        ↓
Seguimiento por
kilometraje y tiempo
        ↓
Cada 5.000 km
        o
Cada 3 meses
```

En estos casos deberán poder coexistir ambas condiciones:

```text
KILOMETRAJE
      +
TIEMPO
      ↓
REGLA DE SEGUIMIENTO
```

La existencia simultánea de ambos criterios no deberá definir por sí sola cuál condición tendrá prioridad.

La regla exacta para determinar cómo deberán evaluarse conjuntamente las condiciones, cuál deberá prevalecer, cuándo se considerará próxima o vencida una intervención y qué acciones deberá generar el sistema deberá definirse posteriormente dentro de Reglas de Mantenimiento.

No todos los mantenimientos o actividades deberán requerir obligatoriamente un criterio de seguimiento.

Podrán existir intervenciones que representen únicamente eventos realizados sobre el vehículo y que deban conservarse dentro del historial sin generar automáticamente una próxima intervención.

Conceptualmente:

```text
INTERVENCIÓN REALIZADA
        ↓
REGISTRO HISTÓRICO
        ↓
¿REQUIERE RECURRENCIA?
        │
    ┌───┴───┐
    ↓       ↓
   SÍ       NO
    │       │
    ↓       ↓
CRITERIO   SIN PRÓXIMO
DE         OBJETIVO
SEGUIMIENTO AUTOMÁTICO
```

Como principio general:

```text
CLASIFICACIÓN
        ↓
¿QUÉ NATURALEZA O CONTEXTO
TIENE EL MANTENIMIENTO?

CRITERIO DE SEGUIMIENTO
        ↓
¿MEDIANTE QUÉ CONDICIÓN
SE CONTROLA SU RECURRENCIA?
```

La definición detallada de intervalos, fuentes de información, cálculos, combinaciones de condiciones, tolerancias, estados, próximos objetivos, alertas y recomendaciones deberá desarrollarse posteriormente dentro de Kilometraje, Reglas de Mantenimiento y los demás componentes funcionales correspondientes.

---

# 20. Estado de mantenimiento

Inicialmente se contemplan:

```text
VIGENTE

    ↓

PRÓXIMO A VENCER

    ↓

VENCIDO
```

Los criterios exactos de cada estado deberán definirse mediante reglas de negocio.

---

# 21. Recomendaciones

La plataforma deberá diferenciar entre:

### Información histórica

Información sobre algo que efectivamente ocurrió.

### Regla de mantenimiento

Condición configurada para determinar cuándo revisar o realizar una actividad.

### Recomendación automática

Resultado generado por el sistema a partir de las reglas.

### Diagnóstico o evaluación profesional

Diagnóstico, evaluación o concepto emitido por un Prestador de Servicios Vehiculares o profesional competente, de acuerdo con la naturaleza de la revisión realizada.

### Servicio realizado

Intervención efectivamente ejecutada.

Estas categorías deberán mantenerse separadas en el modelo de información.

La plataforma no deberá presentar una recomendación automática como si fuera un diagnóstico, evaluación o concepto profesional.

## 21.1 Recomendaciones para preparación de viajes

La plataforma deberá incorporar una funcionalidad orientada a ayudar al propietario a prepararse para viajes largos.

El propietario podrá indicar:

- Ciudad o destino.
- Distancia estimada del viaje.
- Información adicional que pueda ser definida posteriormente.

Ejemplo:

```text
Preparación para viaje

Destino: Cartagena

o

Distancia estimada: 650 km
```

El sistema deberá analizar, según las reglas de negocio definidas, información como:

- Kilometraje actual.
- Historial de mantenimiento.
- Últimos mantenimientos realizados.
- Próximos mantenimientos.
- Mantenimientos vencidos.
- Tiempo transcurrido desde determinadas intervenciones.
- Kilometraje recorrido desde determinadas intervenciones.
- Información disponible sobre neumáticos.
- Información disponible sobre frenos.
- Información disponible sobre fluidos.
- Información disponible sobre batería.
- Información disponible sobre elementos de seguridad.

A partir de esta información, el sistema podrá generar una lista de revisión previa al viaje.

Ejemplo:

```text
CHECKLIST PREVIO AL VIAJE

Vehículo: HWG123

[ ] Revisar nivel de aceite
[ ] Revisar nivel de refrigerante
[ ] Revisar líquido de frenos
[ ] Revisar estado de pastillas
[ ] Revisar estado de discos
[ ] Revisar presión de neumáticos
[ ] Revisar vida útil de neumáticos
[ ] Revisar luces
[ ] Revisar batería
[ ] Revisar kit de carretera
[ ] Verificar extintor
[ ] Revisar mantenimientos pendientes
```

La aplicación deberá poder diferenciar entre:

```text
REVISIÓN RECOMENDADA

y

REVISIÓN REQUERIDA POR UN PROFESIONAL
```

Las recomendaciones deberán estar basadas en reglas y datos disponibles.

La aplicación no deberá afirmar que un vehículo está en condiciones seguras para realizar un viaje únicamente con base en información registrada digitalmente.

Cuando una condición requiera inspección física, la aplicación deberá recomendar que sea revisada por un Prestador de Servicios Vehiculares o profesional competente para realizar el tipo de revisión requerida.

En una evolución posterior, esta funcionalidad podrá integrarse con servicios de mapas para obtener automáticamente la distancia entre el punto de origen y el destino, calcular la distancia estimada del viaje y mejorar las recomendaciones.

---

# 22. Notificaciones

La aplicación deberá contemplar notificaciones orientadas a poner en conocimiento del Propietario determinada información, condición, evento, recomendación, solicitud o situación funcional cuando las reglas aplicables determinen que corresponde comunicarla.

Las notificaciones deberán mantenerse diferenciadas de los elementos funcionales que puedan originarlas. La existencia de una alerta, recomendación, evento o cambio de información no deberá significar automáticamente que deba generarse una notificación.

Inicialmente se contemplan situaciones comunicables relacionadas con:

- Solicitud de actualización de kilometraje.
- Recordatorio de mantenimiento próximo.
- Condiciones de mantenimiento próximo a vencer.
- Condiciones de mantenimiento vencido.
- Recomendaciones de revisión.
- Recordatorios relacionados con servicios anteriores.
- Comunicaciones relacionadas con Prestadores de Servicios Vehiculares autorizados, cuando corresponda.
- Recordatorios para preparar un vehículo antes de un viaje.
- Alertas o condiciones relacionadas con mantenimientos que podrían coincidir con un viaje próximo.

Estas situaciones no deberán interpretarse como una definición definitiva de los tipos de notificación ni significar que cada una de ellas deba generar automáticamente una comunicación.

Los principios funcionales relacionados con el origen, destinatarios, canales, frecuencia, repetición, trazabilidad y preferencias de las notificaciones se desarrollan en `63.13 NOTIFICACIONES`.

Los tipos específicos de notificación, reglas particulares de comunicación, frecuencias concretas, canales tecnológicos, configuraciones definitivas y demás detalles funcionales o técnicos deberán definirse posteriormente cuando corresponda.
---

# 23. Reportes

La plataforma deberá permitir generar información consolidada del historial del vehículo.

Inicialmente se contempla un reporte de historial vehicular que pueda contener:

- Información general.
- Kilometraje actual.
- Historial de kilometraje.
- Mantenimientos.
- Reparaciones.
- Repuestos.
- Inspecciones.
- Diagnósticos.
- Peritajes.
- Evaluaciones.
- Fechas.
- Kilometrajes.
- Prestadores de Servicios Vehiculares relacionados con los eventos registrados.
- Costos.
- Documentos relacionados.
- Historial de recomendaciones.
- Información de revisiones previas a viajes, cuando corresponda.

Uno de los casos de uso principales será la generación de un reporte para apoyar el proceso de venta del vehículo.

Adicionalmente, en una evolución posterior podrán generarse reportes específicos relacionados con:

- Estado de mantenimiento.
- Costos históricos.
- Próximos mantenimientos.
- Preparación para viajes.
- Historial de revisiones.

---

# 24. Venta y transferencia del vehículo

La plataforma deberá contemplar conceptualmente el escenario en el que un vehículo cambie de propietario.

El objetivo será que el historial pueda permanecer asociado al vehículo, independientemente del cambio de propietario, de acuerdo con las reglas de negocio que se definan.

```text
Propietario A

      │

      │ vende vehículo

      ↓

   VEHÍCULO

      │

      │ conserva historial

      ↓

Propietario B
```

Este proceso deberá considerar:

- Transferencia de propiedad.
- Validación de identidad.
- Autorización del propietario actual.
- Aceptación del nuevo propietario.
- Conservación del historial.
- Privacidad.
- Acceso de Prestadores de Servicios Vehiculares.
- Auditoría.

La funcionalidad podrá considerarse una funcionalidad posterior al MVP.

---

# 25. Control de acceso y permisos

El propietario deberá ser considerado inicialmente como el responsable principal de la autorización de acceso a la información de su vehículo.

Los Prestadores de Servicios Vehiculares podrán acceder únicamente a la información permitida de los vehículos para los cuales cuenten con la relación y autorización correspondiente.

La autorización de un Prestador de Servicios Vehiculares sobre un vehículo no deberá otorgarle acceso al historial completo del vehículo ni a la información generada por otros Prestadores de Servicios Vehiculares.

Las capacidades disponibles para un Prestador de Servicios Vehiculares no deberán ser necesariamente iguales para todos los tipos de prestadores y podrán depender de la naturaleza de los servicios que realiza.

Conceptualmente:

```text
PRESTADOR DE SERVICIOS VEHICULARES AUTORIZADO

Puede, de acuerdo con sus permisos y con la naturaleza
de los servicios que presta:

- Consultar información autorizada del vehículo.
- Consultar el kilometraje del vehículo habilitado para su acceso.
- Consultar la información básica autorizada del propietario.
- Consultar sus propias intervenciones y registros correspondientes
  a los servicios realizados sobre el vehículo.
- Registrar información correspondiente a los servicios,
  intervenciones, diagnósticos, inspecciones, evaluaciones
  o peritajes que realice.
- Adjuntar documentos o evidencias correspondientes
  a sus propias intervenciones, cuando corresponda.
- Realizar seguimiento sobre sus propios servicios,
  cuando corresponda.
- Generar recomendaciones relacionadas con los servicios
  realizados por el mismo prestador, cuando corresponda.
- Comunicarse con el propietario mediante los mecanismos
  habilitados, cuando corresponda.

No puede:

- Consultar el historial completo del vehículo.
- Consultar intervenciones o registros realizados por otro
  Prestador de Servicios Vehiculares.
- Consultar costos, precios, facturas, diagnósticos,
  documentos, evidencias, observaciones u otra información
  generada por otro Prestador de Servicios Vehiculares.
- Modificar directamente registros históricos realizados
  por otro Prestador de Servicios Vehiculares.
- Eliminar el historial del vehículo.
- Cambiar el propietario del vehículo.
- Acceder a información privada para la cual no cuente
  con autorización.
```

La autorización sobre un vehículo no deberá implicar acceso irrestricto a toda su información ni habilitar automáticamente todas las funcionalidades disponibles para los Prestadores de Servicios Vehiculares.

La existencia de información generada por diferentes Prestadores de Servicios Vehiculares dentro del historial del mismo vehículo no deberá significar que dicha información sea visible para todos ellos.

Cada Prestador de Servicios Vehiculares deberá poder consultar únicamente sus propias intervenciones y la información del vehículo y del propietario expresamente habilitada para su relación.

Inicialmente se contempla que la información básica del propietario disponible para el prestador corresponda a:

- Nombre.
- Correo electrónico.
- Número de celular.

La definición definitiva de la información visible, los permisos específicos, las excepciones y la matriz de permisos será desarrollada posteriormente en los apartados correspondientes.
---

# 26. Reglas de negocio iniciales

## RN-001 — Kilometraje actual

El sistema deberá mantener un kilometraje actual para cada vehículo.

## RN-002 — Historial de kilometraje

Cada actualización del kilometraje deberá conservarse como registro histórico.

## RN-003 — Consistencia del kilometraje

El sistema deberá validar la consistencia de las nuevas lecturas de kilometraje antes de utilizarlas para modificar el kilometraje actual del vehículo.

Una nueva lectura no deberá actualizar automáticamente el kilometraje actual sin la validación correspondiente.

Las reglas funcionales para la validación y el tratamiento de posibles inconsistencias deberán regirse por lo definido en `63.9.3 Validación y consistencia del kilometraje`.

## RN-004 — Próximo mantenimiento

El sistema deberá poder determinar el próximo objetivo de mantenimiento de acuerdo con las reglas configuradas y la información disponible.

La existencia de una regla configurada no deberá significar automáticamente que pueda determinarse un próximo objetivo de mantenimiento.

Cuando no exista información suficiente para determinar dicho objetivo, el sistema no deberá inventar, asumir ni completar los datos faltantes.

El próximo objetivo solamente deberá determinarse cuando exista una regla aplicable y se disponga de la información necesaria para evaluarla, de acuerdo con el criterio de seguimiento correspondiente.

## RN-005 — Mantenimiento por kilometraje

El sistema deberá poder determinar mantenimientos cuyo intervalo dependa del kilometraje.

## RN-006 — Mantenimiento por tiempo

El sistema deberá poder determinar mantenimientos cuyo intervalo dependa del tiempo.

## RN-007 — Mantenimiento por ambas condiciones

El sistema deberá poder determinar mantenimientos cuyo intervalo dependa de tiempo y kilometraje.

## RN-008 — Estado de mantenimiento

El sistema deberá poder determinar el estado de los mantenimientos o actividades que requieran seguimiento, de acuerdo con las reglas aplicables y la información disponible.

La existencia de un mantenimiento o actividad registrada no deberá significar automáticamente que deba asignársele un estado de seguimiento.

Estados iniciales:

- Vigente.
- Próximo a vencer.
- Vencido.

## RN-009 — Recomendación automática

Una recomendación generada por el sistema deberá identificarse como recomendación automática y no como diagnóstico.

## RN-010 — Diagnóstico

Los diagnósticos deberán ser registrados por usuarios autorizados de Prestadores de Servicios Vehiculares habilitados para realizar este tipo de servicio.

## RN-011 — Historial

Los registros, eventos, servicios, intervenciones y demás información que corresponda al ciclo de vida del vehículo deberán formar parte de su historial cuando, de acuerdo con su naturaleza y las reglas aplicables, deban conservarse como información histórica.

## RN-012 — Prestador de Servicios Vehiculares

Un Prestador de Servicios Vehiculares solamente podrá consultar información de los vehículos para los cuales tenga una relación y autorización vigente, y únicamente dentro del alcance permitido por Vehículos Services.

La autorización sobre un vehículo no deberá otorgar al prestador acceso al historial completo del vehículo ni a las intervenciones o información generada por otros Prestadores de Servicios Vehiculares.

El Prestador de Servicios Vehiculares podrá consultar:

- Sus propias intervenciones y registros históricos realizados sobre el vehículo.
- La información general del vehículo que se encuentre habilitada para su acceso.
- El kilometraje del vehículo habilitado para su consulta.
- La información básica autorizada del propietario, contemplando inicialmente nombre, correo electrónico y número de celular.

Un Prestador de Servicios Vehiculares no deberá poder consultar las intervenciones realizadas por otros prestadores ni la información asociada a estas, incluyendo costos, precios, facturas, diagnósticos, documentos, evidencias, observaciones u otros registros generados por dichos prestadores.

La existencia de información de diferentes Prestadores de Servicios Vehiculares dentro del historial del mismo vehículo no deberá significar que dicha información sea visible para todos ellos.

## RN-013 — Propietario

El Propietario deberá conservar el control sobre las autorizaciones de acceso que otorgue a terceros respecto de la información de su vehículo, de acuerdo con las reglas de acceso y permisos definidas por Vehículos Services.

## RN-014 — Integridad histórica

Los registros históricos incorporados al historial del vehículo deberán conservar su integridad, trazabilidad y asociación con el actor que los generó.

Un registro podrá ser creado directamente por el propietario cuando corresponda, independientemente de que el vehículo tenga o no una relación activa con un Prestador de Servicios Vehiculares.

Cuando un registro corresponda a un servicio o intervención realizada por un Prestador de Servicios Vehiculares, deberá poder conservarse la identificación del prestador relacionado con dicho servicio, independientemente de quién haya creado inicialmente el registro, cuando corresponda.

La identificación del Prestador de Servicios Vehiculares que realizó el servicio no deberá confundirse con la identificación del actor que creó el registro.

Por ejemplo:

```text
CAMBIO DE ACEITE
        ↓
SERVICIO REALIZADO POR:
ABC ACEITES
        ↓
REGISTRO CREADO POR:
PROPIETARIO
```

## RN-015 — Auditoría

Las modificaciones relevantes deberán conservar información suficiente para determinar quién realizó el cambio y cuándo.

## RN-016 — Preparación para viaje

El sistema deberá permitir que el propietario solicite recomendaciones de preparación para un viaje.

## RN-017 — Información del viaje

El sistema deberá permitir registrar inicialmente un destino o una distancia estimada.

## RN-018 — Análisis previo al viaje

El sistema deberá analizar la información disponible del vehículo para identificar aspectos que deberían ser revisados antes del viaje.

## RN-019 — Checklist de viaje

El sistema podrá generar una lista de verificación basada en las reglas configuradas y en la información disponible.

## RN-020 — Mantenimientos antes del viaje

El sistema deberá identificar mantenimientos vencidos o próximos a vencer que puedan requerir atención antes del viaje y, cuando exista información suficiente, mantenimientos cuyo próximo objetivo pueda alcanzarse durante el recorrido estimado del viaje.

## RN-021 — Recomendación de inspección

Cuando la información disponible no sea suficiente para determinar el estado real de un componente, el sistema deberá indicarlo y, cuando corresponda de acuerdo con la información disponible y las reglas aplicables, podrá recomendar una inspección física.

## RN-022 — No diagnóstico

Las recomendaciones de preparación para viajes no deberán presentarse como diagnóstico mecánico ni como certificación de seguridad del vehículo.

## RN-023 — Distancia del viaje

Cuando el usuario registre una distancia estimada, el sistema podrá utilizarla como referencia para determinar si determinados mantenimientos podrían alcanzarse durante el viaje.

## RN-024 — Información incompleta

Cuando no exista información suficiente sobre un componente o mantenimiento, el sistema deberá indicarlo y no deberá inventar, asumir ni completar información que no pueda determinarse a partir de los datos disponibles.

La ausencia de información suficiente no deberá interpretarse automáticamente como que el componente o mantenimiento se encuentra en buen estado, mal estado, vigente, vencido o en cualquier otra condición que no pueda determinarse.



---

# 27. Requerimientos funcionales

Los requerimientos funcionales deberán documentarse utilizando una nomenclatura única:

```text
RF-001

RF-002

RF-003

...
```

Cada requerimiento deberá contener la información necesaria para definir de manera clara la capacidad, comportamiento o resultado funcional esperado del sistema.

Como mínimo, deberá contemplar:

- Identificador.
- Nombre.
- Descripción.
- Actor o actores relacionados, cuando corresponda.
- Reglas de negocio relacionadas.
- Criterios de aceptación.
- Prioridad.
- Dependencias, cuando existan.

Los flujos de interacción, precondiciones, flujos alternativos y demás detalles propios de los casos de uso deberán desarrollarse en su documentación correspondiente cuando sean necesarios.

Los requerimientos relacionados con la preparación para viajes deberán contemplar, según corresponda:

- Registro del viaje.
- Destino.
- Distancia estimada.
- Consulta de kilometraje actual.
- Consulta de historial.
- Consulta de mantenimientos.
- Evaluación de reglas.
- Generación de checklist.
- Generación de recomendaciones.
- Identificación de información faltante.
- Recomendación de revisión profesional cuando corresponda.

---

# 28. Requerimientos no funcionales

Se deberán definir requerimientos relacionados con:

- Seguridad.
- Rendimiento.
- Disponibilidad.
- Escalabilidad.
- Compatibilidad Android.
- Compatibilidad iOS.
- Usabilidad.
- Accesibilidad.
- Auditoría.
- Trazabilidad.
- Recuperación ante fallos.
- Respaldo.
- Protección de datos.
- Observabilidad.
- Logging.
- Monitoreo.
- Tiempo de respuesta.
- Mantenibilidad.

Adicionalmente, las funcionalidades de recomendaciones deberán considerar:

- Consistencia de reglas.
- Trazabilidad de recomendaciones.
- Identificación de la información utilizada para generar una recomendación.
- Capacidad de actualizar reglas sin modificar necesariamente el código de la aplicación.

---

# 29. Casos de uso preliminares

```text
CU-001 Crear cuenta

CU-002 Iniciar sesión

CU-003 Registrar vehículo

CU-004 Consultar vehículo

CU-005 Actualizar kilometraje

CU-006 Registrar mantenimiento

CU-007 Consultar historial

CU-008 Registrar reparación

CU-009 Registrar repuesto

CU-010 Adjuntar documento

CU-011 Consultar próximos mantenimientos

CU-012 Consultar alertas

CU-013 Autorizar Prestador de Servicios Vehiculares

CU-014 Revocar acceso de Prestador de Servicios Vehiculares

CU-015 Solicitar acceso a vehículo

CU-016 Registrar servicio, intervención, diagnóstico, inspección, evaluación o peritaje desde Prestador de Servicios Vehiculares

CU-017 Consultar vehículo desde Prestador de Servicios Vehiculares

CU-018 Consultar recomendaciones

CU-019 Generar reporte vehicular

CU-020 Transferir vehículo

CU-021 Registrar viaje

CU-022 Registrar destino de viaje

CU-023 Registrar distancia estimada

CU-024 Consultar preparación para viaje

CU-025 Generar checklist previo al viaje

CU-026 Consultar recomendaciones previas al viaje

CU-027 Identificar mantenimientos pendientes antes del viaje

CU-028 Registrar resultado de revisión previa al viaje
```

Esta lista deberá refinarse durante el levantamiento detallado.

---

# 30. Arquitectura de solución

En esta etapa se contempla una arquitectura conceptual de referencia que permita identificar los principales componentes y responsabilidades generales que podría requerir Vehículos Services.

Esta definición no deberá interpretarse como la arquitectura técnica definitiva de la plataforma ni como una selección final de tecnologías, servicios o mecanismos de implementación.

De manera conceptual se contemplan componentes relacionados con:

- Aplicación móvil.
- Backend.
- APIs.
- Lógica de negocio.
- Persistencia.
- Almacenamiento de documentos.
- Notificaciones.
- Autenticación.
- Suscripciones.
- Monitoreo.

Arquitectura conceptual:

```text
                    ┌─────────────────────┐
                    │      USUARIOS       │
                    └──────────┬──────────┘
                               │
                    ┌──────────┴──────────┐
                    ↓                     ↓
              ┌───────────┐         ┌───────────┐
              │  Android  │         │    iOS    │
              └─────┬─────┘         └─────┬─────┘
                    │                     │
                    └──────────┬──────────┘
                               ↓
                         ┌─────────────┐
                         │ API/BACKEND │
                         └──────┬──────┘
                                │
              ┌─────────────────┼─────────────────┐
              ↓                 ↓                 ↓
       ┌─────────────┐   ┌─────────────┐   ┌─────────────┐
       │  Negocio    │   │ Seguridad   │   │ Notificación│
       │  vehicular  │   │   /Auth     │   │   servicio  │
       └──────┬──────┘   └─────────────┘   └─────────────┘
              │
              ├──────────────┐
              ↓              ↓
       ┌─────────────┐ ┌─────────────┐
       │ Base datos  │ │Documentos / │
       │             │ │  archivos   │
       └─────────────┘ └─────────────┘
```

La arquitectura definitiva, la distribución técnica de responsabilidades, las tecnologías, los mecanismos de integración y demás decisiones de implementación deberán establecerse posteriormente durante el diseño técnico correspondiente.

La funcionalidad de preparación para viajes deberá integrarse conceptualmente con las capacidades existentes de vehículos, kilometraje, historial, mantenimientos y reglas, sin definir en esta etapa la forma técnica definitiva en que dicha integración será implementada.

---

# 31. Definición tecnológica

Esta sección tendrá como objetivo establecer cómo será construida técnicamente la plataforma.

Las decisiones deberán documentarse y justificarse.

No se deberán seleccionar tecnologías únicamente por preferencia personal.

La evaluación deberá considerar:

- Seguridad.
- Escalabilidad.
- Rendimiento.
- Costos.
- Mantenibilidad.
- Experiencia del equipo.
- Comunidad.
- Documentación.
- Integraciones.
- Disponibilidad de talento.
- Complejidad operacional.
- Evolución futura.

---

# 32. Tecnología de aplicación móvil

Se deberá seleccionar la tecnología para desarrollar Android e iOS.

Alternativas iniciales:

- Flutter.
- React Native.
- Desarrollo nativo Android.
- Desarrollo nativo iOS.

### Decisión

Pendiente de definición.

### Criterios

- Desarrollo multiplataforma.
- Rendimiento.
- Mantenibilidad.
- Comunidad.
- Librerías.
- Integración con servicios nativos.
- Notificaciones push.
- Cámara.
- Gestión de archivos.
- Seguridad.
- Evolución futura.
- Integración futura con servicios de ubicación y mapas.

---

# 33. Tecnología Backend

Se deberá definir el lenguaje y framework que serán utilizados para desarrollar los servicios backend.

Alternativas iniciales:

- Python.
- Java.
- C#.
- Node.js.
- Otros.

### Lenguaje

Pendiente de definición.

### Framework

Pendiente de definición.

### Criterios

- Rendimiento.
- Seguridad.
- Escalabilidad.
- Mantenibilidad.
- Experiencia del equipo.
- Integración con bases de datos.
- Integración con servicios externos.
- Desarrollo de APIs.
- Autenticación.
- Autorización.
- Procesamiento de reglas de negocio.
- Capacidad para implementar y evolucionar la lógica y las reglas de negocio definidas por Vehículos Services.

---

# 34. Base de datos

La plataforma deberá contar con mecanismos de persistencia que permitan conservar la información necesaria para el funcionamiento de Vehículos Services.

A nivel conceptual, deberá contemplarse la persistencia de información relacionada como mínimo con:

- Usuarios.
- Propietarios.
- Prestadores de Servicios Vehiculares.
- Vehículos.
- Historial.
- Kilometrajes.
- Mantenimientos.
- Reparaciones.
- Repuestos.
- Costos.
- Documentos relacionados.
- Permisos.
- Autorizaciones.
- Alertas.
- Notificaciones.
- Suscripciones.
- Auditoría.
- Viajes registrados.
- Recomendaciones de viaje.
- Checklist de viaje.

Esta lista representa conceptos e información que deberán poder persistirse y no deberá interpretarse como una definición anticipada de tablas, entidades físicas o estructuras definitivas de almacenamiento.

La estructura definitiva deberá establecerse posteriormente mediante el diseño del modelo de datos correspondiente.

### Motor de base de datos

Pendiente de definición.

### Alternativas iniciales

- PostgreSQL.
- SQL Server.
- MySQL/MariaDB.
- Oracle.

### Modelo de datos

Se deberá desarrollar:

1. Modelo conceptual.
2. Modelo lógico.
3. Modelo físico.
4. Diccionario de datos.
5. Reglas de integridad.
6. Índices.
7. Estrategia de auditoría.
8. Estrategia de respaldo.

---

# 35. API

A nivel conceptual, se contempla el uso de APIs como mecanismo de comunicación e integración entre las aplicaciones móviles y los servicios backend de Vehículos Services.

La definición definitiva del mecanismo de comunicación, el tipo de API, los protocolos, formatos y demás decisiones técnicas de integración deberá establecerse posteriormente durante el diseño técnico correspondiente.

Las capacidades de integración deberán contemplar, según corresponda:

- Autenticación.
- Autorización.
- Gestión de usuarios.
- Gestión de vehículos.
- Gestión de mantenimientos.
- Gestión de kilometraje.
- Gestión de Prestadores de Servicios Vehiculares.
- Gestión de historial.
- Gestión de documentos.
- Gestión de notificaciones.
- Gestión de suscripciones.
- Generación de reportes.
- Gestión de viajes.
- Consulta de recomendaciones.
- Consulta de checklist de viaje.

### Tipo de API

Pendiente de definición.

REST API será evaluada como alternativa inicial.

### Formato

JSON será evaluado como formato principal de intercambio.

### Documentación

Los mecanismos de integración que sean definidos deberán contar con la documentación técnica correspondiente.

En caso de utilizarse APIs compatibles con este tipo de especificación, se evaluará OpenAPI/Swagger como alternativa para su documentación.

---

# 36. Infraestructura

La infraestructura necesaria para ejecutar Vehículos Services deberá definirse posteriormente de acuerdo con la arquitectura, las tecnologías seleccionadas, los requerimientos funcionales y no funcionales y las necesidades operativas de la plataforma.

A nivel conceptual, deberán contemplarse capacidades de infraestructura relacionadas con:

- Ejecución de los servicios de aplicación.
- Persistencia de información.
- Almacenamiento.
- Comunicación e integración entre componentes.
- Notificaciones.
- Autenticación y seguridad.
- Monitoreo.
- Registro de eventos y logs.
- Respaldo y recuperación.

La forma técnica en que estas capacidades serán implementadas, distribuidas y desplegadas deberá establecerse durante el diseño técnico correspondiente.

Como referencia conceptual:

```text
USUARIOS / APLICACIONES
          ↓
SERVICIOS DE LA PLATAFORMA
          ↓
LÓGICA Y CAPACIDADES DE NEGOCIO
          ↓
PERSISTENCIA / ALMACENAMIENTO
          ↓
SERVICIOS COMPLEMENTARIOS
```

Este esquema representa únicamente una separación conceptual de responsabilidades y no deberá interpretarse como una topología definitiva de infraestructura, despliegue o comunicación entre componentes.

---

# 37. Proveedor Cloud

El modelo de infraestructura que utilizará Vehículos Services deberá definirse posteriormente como parte del diseño técnico de la plataforma.

En caso de determinarse que la solución utilizará infraestructura Cloud, deberá evaluarse y seleccionarse el proveedor que mejor se ajuste a las necesidades del proyecto.

Alternativas iniciales:

- Microsoft Azure.
- Amazon Web Services.
- Google Cloud Platform.
- Otros proveedores que puedan resultar adecuados durante la evaluación.

### Decisión

Pendiente de definición.

### Criterios

- Costos.
- Escalabilidad.
- Seguridad.
- Disponibilidad.
- Servicios administrados.
- Integración.
- Facilidad de operación.
- Capacidad de crecimiento.

---

# 38. Servidores y servicios

La forma en que serán ejecutados y desplegados los diferentes componentes y capacidades técnicas de Vehículos Services deberá definirse posteriormente como parte del diseño técnico de la plataforma.

La definición deberá contemplar, según corresponda:

- Servicios de aplicación.
- Mecanismos de comunicación e integración.
- Persistencia de información.
- Almacenamiento.
- Servicios de procesamiento.
- Servicios de notificaciones.
- Servicios de monitoreo.
- Servicios de autenticación y seguridad.
- Otros componentes técnicos que resulten necesarios de acuerdo con la arquitectura definitiva.

La solución podrá evaluar diferentes alternativas de ejecución y despliegue, incluyendo servidores, máquinas virtuales, contenedores, servicios administrados, servicios Cloud u otros mecanismos que resulten adecuados.

La selección definitiva deberá realizarse de acuerdo con la arquitectura, las tecnologías seleccionadas, los requerimientos funcionales y no funcionales y las necesidades operativas de Vehículos Services.

### Decisión

Pendiente de definición.


---
# 39. Ambientes

Vehículos Services deberá contemplar la separación de ambientes necesaria para soportar de forma segura y controlada las diferentes etapas de desarrollo, validación, pruebas y operación de la plataforma.

Como referencia inicial podrán contemplarse:

```text
DESARROLLO

    ↓

QA / PRUEBAS

    ↓

STAGING

    ↓

PRODUCCIÓN
```

La cantidad definitiva de ambientes, su propósito, configuración, nivel de aislamiento y los recursos asociados a cada uno deberán establecerse posteriormente de acuerdo con la arquitectura, infraestructura y estrategia de desarrollo y despliegue que sean definidas.

Cuando corresponda, los ambientes deberán contemplar mecanismos adecuados de separación para elementos como:

- Configuración.
- Credenciales.
- Variables de entorno.
- Datos.
- Servicios y recursos de infraestructura.

Los datos productivos no deberán utilizarse directamente en ambientes de desarrollo o pruebas sin los mecanismos de protección, control y tratamiento que correspondan.
---

# 40. Control de versiones

El código fuente deberá administrarse mediante un sistema de control de versiones.

### Tecnología

Pendiente de definición.

Git será evaluado como estándar.

Se deberá definir la estrategia para:

- Aplicación móvil.
- Backend.
- Infraestructura.
- Scripts de base de datos.
- Documentación.

---

# 41. CI/CD

Vehículos Services deberá contemplar una estrategia de integración y despliegue que permita soportar de manera controlada la construcción, validación, pruebas y liberación de los componentes de la plataforma.

Como referencia conceptual, dicha estrategia podrá contemplar etapas como:

```text
Commit

  ↓

Validación

  ↓

Build

  ↓

Pruebas automáticas

  ↓

Análisis de calidad

  ↓

Empaquetado

  ↓

Despliegue
```

Este flujo representa únicamente una referencia inicial y no deberá interpretarse como la definición definitiva del proceso de integración y despliegue.

Las etapas definitivas, automatizaciones, controles, herramientas y mecanismos de despliegue deberán establecerse posteriormente de acuerdo con la arquitectura, tecnologías, infraestructura y ambientes que sean definidos.

La herramienta de CI/CD será definida posteriormente.

---

# 42. Seguridad

Vehículos Services deberá contemplar la seguridad como un requisito transversal orientado a proteger la información, los accesos y las operaciones relacionadas con Propietarios, Prestadores de Servicios Vehiculares, vehículos y demás información gestionada por la plataforma.

A nivel conceptual, se deberán contemplar aspectos relacionados con:

- Autenticación.
- Autorización.
- Gestión y control de acceso.
- Gestión segura de sesiones.
- Protección de credenciales.
- Protección de información sensible.
- Protección de las comunicaciones.
- Protección de los mecanismos de integración.
- Auditoría y trazabilidad.
- Registro de eventos relevantes de seguridad.
- Protección de documentos.
- Gestión de permisos y autorizaciones.
- Revocación de accesos.
- Protección de datos.

La solución deberá aplicar el principio de mínimo privilegio, de manera que cada actor pueda acceder únicamente a la información y funcionalidades que le correspondan de acuerdo con su relación, autorización y permisos aplicables.

Los mecanismos técnicos específicos de seguridad, incluyendo protocolos, tecnologías de autenticación, gestión de sesiones, cifrado, protección de comunicaciones, protección de APIs u otros mecanismos, deberán definirse posteriormente durante el diseño técnico y de seguridad correspondiente.

---

# 43. Almacenamiento de documentos

Vehículos Services deberá permitir adjuntar documentos y evidencias relacionados con el vehículo y con los diferentes registros de su ciclo de vida, cuando corresponda.

Ejemplos:

- Facturas.
- Órdenes de servicio.
- Fotografías.
- Diagnósticos.
- Evidencias.
- Documentos del vehículo.

Los documentos adjuntos deberán considerarse información complementaria. La información estructurada registrada en Vehículos Services deberá mantenerse como fuente principal para la operación, consulta, seguimiento y evaluación de las funcionalidades de la plataforma.

La existencia de un documento adjunto no deberá ser obligatoria para registrar una intervención, mantenimiento, reparación u otro evento, salvo que posteriormente se defina una regla específica que así lo requiera.

El almacenamiento de un documento no deberá otorgar automáticamente acceso a otros actores. Su consulta deberá respetar las reglas de acceso, permisos, autorizaciones y privacidad aplicables.

En particular, los documentos incorporados directamente por el Propietario no deberán hacerse visibles automáticamente a un Prestador de Servicios Vehiculares únicamente por existir una relación o autorización sobre el vehículo.

El mecanismo técnico utilizado para almacenar y gestionar los documentos deberá definirse posteriormente.

Se podrá evaluar el uso de almacenamiento de objetos u otras alternativas adecuadas durante el diseño técnico.

### Servicio

Pendiente de definición.

---

# 44. Notificaciones

Vehículos Services deberá contemplar la capacidad de generar y comunicar notificaciones cuando determinada información, condición, evento, recomendación, solicitud o situación funcional deba ponerse en conocimiento de un destinatario válido de acuerdo con las reglas aplicables.

Las notificaciones deberán mantenerse diferenciadas de los elementos funcionales que puedan originarlas. La existencia de una alerta, recomendación, evento, cambio de información u otra condición no deberá significar automáticamente que deba generarse una notificación.

Inicialmente podrán contemplarse situaciones comunicables relacionadas con:

- Solicitudes de actualización de kilometraje.
- Mantenimientos próximos.
- Mantenimientos vencidos.
- Recomendaciones de revisión.
- Recordatorios relacionados con servicios anteriores.
- Comunicaciones relacionadas con Prestadores de Servicios Vehiculares autorizados, cuando corresponda.
- Preparación para viajes.
- Condiciones relacionadas con mantenimientos que podrían coincidir con un viaje próximo.
- Otros eventos o situaciones relevantes que posteriormente se definan.

Estas situaciones no deberán interpretarse como una definición definitiva de los tipos de notificación ni significar que cada una de ellas deba generar automáticamente una comunicación.

Los canales y mecanismos utilizados para comunicar las notificaciones deberán definirse posteriormente. Podrán evaluarse mecanismos como notificaciones push u otras alternativas adecuadas, sin que su inclusión en esta etapa represente una decisión tecnológica definitiva.

Los principios funcionales relacionados con el origen, destinatarios, canales, frecuencia, repetición, trazabilidad y preferencias de las notificaciones se desarrollan en `63.13 NOTIFICACIONES`.

---

# 45. Sincronización en línea

Vehículos Services deberá permitir que la información incorporada o actualizada por un actor autorizado pueda quedar disponible para los demás actores que tengan autorización para consultarla, de acuerdo con las reglas de acceso, permisos y visibilidad aplicables.

La sincronización de información no deberá significar que todos los actores relacionados con un vehículo puedan consultar automáticamente toda su información.

Cuando se registre o actualice información que pueda afectar otros procesos funcionales, el sistema deberá evaluarla de acuerdo con las reglas aplicables antes de utilizarla para actualizar información vigente, determinar condiciones, ejecutar evaluaciones o generar otros resultados funcionales.

Por ejemplo:

```text
PROPIETARIO
     │
     │ Registra una nueva lectura
     │ de kilometraje: 75.300 km
     ↓
VEHÍCULOS SERVICES
     │
     ├── Registra la información y su procedencia
     │
     ├── Evalúa su consistencia
     │
     ├── Determina si corresponde actualizar
     │   el kilometraje actual
     │
     └── Evalúa las reglas aplicables
              │
              ↓
INFORMACIÓN ACTUALIZADA
SEGÚN CORRESPONDA
              │
              ↓
DISPONIBLE PARA ACTORES AUTORIZADOS
SEGÚN SUS PERMISOS Y ALCANCE
```

Por ejemplo, si el Propietario registra una lectura válida de `75.300 km` y esta corresponde al kilometraje actual del vehículo, dicho valor podrá utilizarse posteriormente para evaluar reglas de mantenimiento y podrá ser consultado por un Prestador de Servicios Vehiculares cuando tenga autorización para acceder a esa información.

La disponibilidad de información actualizada no deberá modificar las reglas de privacidad ni otorgar nuevos permisos de acceso.

Los mecanismos técnicos utilizados para realizar la sincronización, propagación o actualización de la información deberán definirse posteriormente durante el diseño técnico correspondiente.

---

# 46. Motor de reglas

Vehículos Services deberá contemplar la capacidad de evaluar y aplicar las reglas funcionales definidas para el seguimiento del vehículo, sus mantenimientos y demás procesos que requieran este tipo de evaluación.

Esta capacidad deberá poder considerar, según la regla y el contexto correspondiente, información relacionada con:

- Kilometraje.
- Fecha.
- Intervalos.
- Historial.
- Tipo de mantenimiento.
- Configuración del vehículo.
- Información de viajes.
- Distancia estimada del viaje.
- Reglas específicas de preparación para viajes.
- Otros datos que posteriormente sean definidos como necesarios para una regla determinada.

La evaluación de las reglas podrá permitir determinar, cuando corresponda:

- Estados.
- Condiciones.
- Próximos objetivos de mantenimiento.
- Alertas.
- Recomendaciones.
- Otros resultados funcionales definidos por las reglas aplicables.

La existencia o evaluación de una regla no deberá significar automáticamente que deba generarse un estado, alerta, recomendación u otro resultado. Cada resultado deberá producirse únicamente cuando exista información suficiente y se cumplan las condiciones definidas por las reglas correspondientes.

Cuando no exista información suficiente para realizar una evaluación determinada, Vehículos Services no deberá inventar, asumir ni completar los datos faltantes.

La forma técnica en que esta capacidad será implementada, incluyendo la existencia o no de un componente independiente para la ejecución de reglas, deberá definirse posteriormente durante el diseño técnico de la plataforma.

---

# 47. Auditoría

Vehículos Services deberá mantener trazabilidad sobre las operaciones y modificaciones relevantes realizadas sobre la información gestionada por la plataforma.

Cuando corresponda, la trazabilidad deberá permitir identificar:

- Qué operación o modificación fue realizada.
- Quién realizó la operación o modificación.
- Cuándo fue realizada.
- Sobre qué información o registro fue realizada.
- Qué información cambió.
- Valor anterior, cuando aplique.
- Valor nuevo, cuando aplique.
- Origen o contexto de la operación, cuando sea necesario para conservar su trazabilidad.

La auditoría deberá permitir diferenciar, cuando corresponda, entre el actor relacionado con el hecho registrado y el actor que incorporó, modificó o corrigió la información en Vehículos Services.

Por ejemplo:

```text
INTERVENCIÓN REALIZADA POR:
Prestador de Servicios Vehiculares A

REGISTRO INCORPORADO POR:
Propietario

MODIFICACIÓN POSTERIOR REALIZADA POR:
Propietario
```

Estos actores representan responsabilidades diferentes y deberán conservarse de forma independiente cuando corresponda.

Las correcciones o modificaciones de información histórica relevante no deberán eliminar silenciosamente la trazabilidad necesaria para comprender qué información existía anteriormente y qué cambio fue realizado.

La información de auditoría deberá protegerse de acuerdo con las reglas de seguridad, acceso y conservación que posteriormente sean definidas.

Los mecanismos técnicos utilizados para implementar la auditoría, incluyendo estructuras de almacenamiento, logs, eventos u otros mecanismos, deberán definirse posteriormente durante el diseño técnico correspondiente.

---

# 48. Monitoreo y observabilidad

Vehículos Services deberá contemplar mecanismos de monitoreo y observabilidad que permitan detectar, analizar y dar seguimiento a errores, fallos y problemas técnicos u operativos de la plataforma.

Según corresponda a la arquitectura y tecnologías que posteriormente sean definidas, se deberán contemplar aspectos relacionados con:

- Logs.
- Métricas.
- Monitoreo.
- Alertas técnicas u operativas.
- Errores de aplicación.
- Errores de comunicación o integración.
- Errores relacionados con la persistencia o acceso a la información.
- Disponibilidad.
- Rendimiento.
- Otros eventos técnicos relevantes para la operación de la plataforma.

Las alertas técnicas u operativas contempladas en este punto deberán mantenerse diferenciadas de las alertas funcionales relacionadas con vehículos, mantenimientos u otras condiciones de negocio definidas por Vehículos Services.

La información obtenida mediante los mecanismos de monitoreo y observabilidad deberá permitir apoyar la identificación, análisis y diagnóstico de problemas técnicos sin definir en esta etapa una implementación tecnológica específica.

Las herramientas, métricas específicas, umbrales, mecanismos de recolección, almacenamiento y visualización de esta información deberán definirse posteriormente durante el diseño técnico correspondiente.

---

# 49. Respaldo y recuperación

Se deberá establecer una estrategia para:

- Backups.
- Frecuencia.
- Retención.
- Restauración.
- Recuperación ante fallos.
- Recuperación ante pérdida de información.

La estrategia deberá considerar especialmente la información histórica de los vehículos.

---

# 50. Escalabilidad

La arquitectura deberá permitir aumentar progresivamente:

- Número de usuarios.
- Número de vehículos.
- Número de Prestadores de Servicios Vehiculares.
- Cantidad de mantenimientos.
- Cantidad de documentos.
- Cantidad de notificaciones.
- Cantidad de consultas.
- Cantidad de viajes registrados.
- Cantidad de recomendaciones generadas.

La solución deberá evitar dependencias arquitectónicas que dificulten el crecimiento futuro.

---

# 51. Suscripciones

La plataforma deberá diseñarse considerando un modelo de suscripción para Propietarios y Prestadores de Servicios Vehiculares.

Conceptualmente:

```text
PROPIETARIO / PRESTADOR DE SERVICIOS VEHICULARES

   ↓

PLAN DE SUSCRIPCIÓN

   ↓

FUNCIONALIDADES HABILITADAS

   ↓

PERMISOS Y LÍMITES ASOCIADOS AL PLAN
```

Los planes podrán habilitar diferentes funcionalidades y límites.

Los permisos o límites asociados a un plan de suscripción deberán mantenerse diferenciados de las reglas de acceso, autorización y privacidad de la información. La existencia de una suscripción no deberá otorgar automáticamente acceso a información para la cual el actor no tenga la autorización correspondiente.

Ejemplo conceptual:

```text
PROPIETARIO

Plan básico

├── Registro de vehículo
├── Información básica
└── Funcionalidades limitadas

Plan premium

├── Historial completo
├── Reportes
├── Alertas avanzadas
├── Seguimiento
├── Preparación para viajes
└── Funcionalidades adicionales
```

Para Prestadores de Servicios Vehiculares:

```text
PRESTADOR DE SERVICIOS VEHICULARES

Plan básico

├── Clientes limitados
├── Vehículos limitados
└── Funcionalidades limitadas

Plan profesional

├── Clientes
├── Vehículos
├── Historial
├── Seguimiento
├── Alertas
├── Comunicación
├── Reportes
└── Funcionalidades adicionales
```

Estos ejemplos son conceptuales y no representan todavía los planes definitivos.

La arquitectura deberá permitir incorporar nuevos planes y modificar funcionalidades habilitadas sin requerir cambios estructurales importantes.

---

# 52. Tiendas de aplicaciones

La solución deberá considerar los procesos de publicación en:

- Google Play Store.
- Apple App Store.

Se deberán definir posteriormente:

- Cuentas de desarrollador.
- Certificados.
- Firmas.
- Perfiles.
- Procesos de publicación.
- Versionamiento.
- Actualizaciones.
- Ambientes de distribución.

---

# 53. Decisiones tecnológicas

Las decisiones tecnológicas importantes deberán documentarse mediante registros de decisión técnica (ADR) dentro de arquitectura.md.

Formato propuesto:

```text
ADR-001

Título:

Nombre de la decisión tecnológica.

Contexto:

Necesidad que origina la decisión.

Alternativas:

- Alternativa 1
- Alternativa 2
- Alternativa 3

Decisión:

Alternativa seleccionada.

Justificación:

Razones técnicas y económicas.

Consecuencias:

Impactos positivos y negativos.

Estado:

Propuesta / Aprobada / Rechazada / Obsoleta
```

---

# 54. Matriz tecnológica

Antes de comenzar el desarrollo de cada componente, deberán estar definidas las tecnologías necesarias para implementarlo.

Estas decisiones se registrarán en una matriz tecnológica que permita conocer qué tecnología se utilizará en cada componente, su estado de definición y la justificación de la decisión.

| Componente | Tecnología | Estado | Justificación |
|---|---|---|---|
| Aplicación móvil | Pendiente | Evaluación | — |
| Backend | Pendiente | Evaluación | — |
| Base de datos | Pendiente | Evaluación | — |
| Infraestructura | Pendiente | Evaluación | — |
| CI/CD | Pendiente | Evaluación | — |
| Monitoreo | Pendiente | Evaluación | — |
| Almacenamiento | Pendiente | Evaluación | — |
| Notificaciones | Pendiente | Evaluación | — |

No será necesario tener definidas todas las tecnologías del proyecto para comenzar el desarrollo. Sin embargo, cada componente deberá contar con las decisiones tecnológicas necesarias antes de iniciar su implementación.

La matriz deberá actualizarse a medida que se tomen o modifiquen decisiones tecnológicas.

---

# 55. Criterios de selección tecnológica

Las tecnologías deberán seleccionarse considerando:

| Criterio | Importancia |
|---|---|
| Seguridad | Alta |
| Escalabilidad | Alta |
| Mantenibilidad | Alta |
| Costos | Alta |
| Rendimiento | Alta |
| Disponibilidad de talento | Alta |
| Comunidad | Media/Alta |
| Documentación | Alta |
| Integraciones | Alta |
| Complejidad operacional | Alta |
| Soporte multiplataforma | Alta |
| Evolución futura | Alta |

---

# 56. Modelo de datos

El modelo de datos deberá diseñarse posteriormente a partir del modelo de negocio y los requerimientos funcionales.

Inicialmente se identifican los siguientes conceptos de información que deberán ser considerados durante el diseño del modelo de datos:

```text
PROPIETARIO

PRESTADOR DE SERVICIOS VEHICULARES


VEHÍCULO

   │

   ├── KILOMETRAJE

   ├── MANTENIMIENTO

   ├── REPARACIÓN

   ├── REPUESTO

   ├── DOCUMENTO

   ├── COSTO

   ├── HISTORIAL

   ├── ALERTA

   ├── RECOMENDACIÓN

   └── VIAJE

            │

            ├── DESTINO

            ├── DISTANCIA ESTIMADA

            ├── CHECKLIST

            └── RECOMENDACIONES


MANTENIMIENTO

   │

   └── REGLA DE MANTENIMIENTO


PROPIETARIO / PRESTADOR DE SERVICIOS VEHICULARES

   │

   └── SUSCRIPCIÓN

           │

           └── PLAN

                  │

                  └── FUNCIONALIDADES
```

Este esquema es conceptual y representa información relevante identificada hasta esta etapa del proyecto. No deberá interpretarse como la definición anticipada de entidades, tablas, atributos o relaciones del modelo de datos definitivo.

La estructura, relaciones, entidades, atributos, cardinalidades y demás elementos del modelo de datos deberán definirse posteriormente durante su diseño correspondiente.

Para la funcionalidad de viajes se deberá evaluar posteriormente la necesidad de estructuras de información relacionadas con:

- Viaje.
- Destino.
- Distancia.
- Checklist.
- Ítems de checklist.
- Recomendaciones.
- Estado de revisión.
- Resultado de revisión.
- Reglas de preparación para viajes.

---

# 57. UX/UI

La aplicación deberá diseñarse considerando las necesidades particulares de los diferentes actores que interactúen con ella, especialmente el Propietario y el Prestador de Servicios Vehiculares.

Se deberán definir posteriormente:

- Arquitectura de navegación.
- Pantallas.
- Flujos.
- Componentes.
- Formularios.
- Mensajes.
- Estados.
- Alertas.
- Notificaciones.
- Experiencia de propietario.
- Experiencia de Prestador de Servicios Vehiculares.
- Experiencia de preparación para viajes.

Para la funcionalidad de preparación para viajes se deberá considerar un flujo sencillo:

```text
Preparar mi viaje

        ↓

¿A dónde vas?

        ↓

Destino o distancia

        ↓

Analizar vehículo

        ↓

Revisión del estado

        ↓

Checklist

        ↓

Recomendaciones

        ↓

Mantenimientos pendientes

        ↓

Preparado / Revisar antes de viajar
```

La UX/UI deberá diseñarse a partir de los casos de uso y requerimientos funcionales, evitando diseñar pantallas antes de definir correctamente los procesos.

---

# 58. MVP

El proyecto deberá dividirse en un MVP y posteriores fases de evolución.

El MVP deberá contener únicamente las funcionalidades necesarias para validar la propuesta de valor principal.

La definición definitiva del MVP se realizará después de completar:

1. Modelo de negocio.
2. Casos de uso.
3. Requerimientos funcionales.
4. Reglas de negocio.
5. Modelo de datos preliminar.
6. Arquitectura inicial.

La funcionalidad de preparación para viajes deberá evaluarse durante la definición del MVP.

Como mínimo, deberá determinarse si el MVP incluirá:

- Registro de viaje.
- Registro de destino.
- Registro de distancia estimada.
- Checklist básico.
- Recomendaciones basadas en mantenimiento.
- Revisión de elementos de seguridad.

Las funcionalidades avanzadas de mapas, rutas y cálculo automático de distancias podrán ser consideradas para fases posteriores.

---

# 59. Roadmap

Se deberá establecer posteriormente un roadmap de evolución:

```text
MVP

 │

 ↓

FASE 2

 │

 ↓

FASE 3

 │

 ↓

ESCALAMIENTO
```

Cada fase deberá definir:

- Objetivo.
- Funcionalidades.
- Prioridad.
- Dependencias.
- Esfuerzo estimado.
- Riesgos.
- Criterios de salida.

Una posible evolución de la funcionalidad de viajes podrá contemplar:

```text
FASE INICIAL

Registro manual de viaje

        ↓

Checklist básico

        ↓

Recomendaciones basadas en historial


FASE POSTERIOR

Destino mediante ubicación

        ↓

Cálculo automático de distancia

        ↓

Integración con mapas

        ↓

Análisis avanzado de ruta


FASE FUTURA

Recomendaciones contextuales

        ↓

Paradas de mantenimiento

        ↓

Servicios cercanos

        ↓

Integración con Prestadores de Servicios Vehiculares
```

Esta evolución es conceptual y deberá validarse posteriormente.

---

# 60. Riesgos iniciales

Durante el levantamiento deberán analizarse como mínimo:

- Complejidad de las reglas de mantenimiento.
- Calidad de la información ingresada por los diferentes actores.
- Control de acceso entre Prestadores de Servicios Vehiculares y Propietarios.
- Protección de información personal.
- Costos de infraestructura.
- Costos de almacenamiento de documentos.
- Costos de notificaciones.
- Complejidad del modelo de suscripción.
- Escalabilidad.
- Transferencia de vehículos.
- Integridad del historial.
- Adopción por parte de Prestadores de Servicios Vehiculares.
- Adopción por parte de Propietarios.
- Complejidad de las reglas de preparación para viajes.
- Riesgo de generar recomendaciones incorrectas por información incompleta.
- Riesgo de que el usuario interprete una recomendación automática como un diagnóstico.
- Dependencia futura de servicios externos de mapas.

---

# 61. Decisiones pendientes

Los siguientes aspectos deberán completar su definición durante las etapas correspondientes del proyecto y antes de que sean necesarios para la implementación de las funcionalidades o componentes que dependan de ellos.

Algunos cuentan actualmente con principios, reglas o definiciones conceptuales generales, pero todavía requieren decisiones o detalles adicionales antes de su implementación definitiva.

## Negocio

- Modelo comercial.
- Modelo de suscripción.
- Planes.
- Funcionalidades por plan.
- Límites por plan.
- Estrategia de monetización.

## Funcional

- Información obligatoria del vehículo.
- Información opcional.
- Catálogo de mantenimientos.
- Catálogo de repuestos.
- Reglas específicas y configuraciones de mantenimiento.
- Reglas específicas de preparación para viajes.
- Elementos incluidos en el checklist de viaje.
- Umbrales específicos de alertas.
- Frecuencias específicas de notificaciones.
- Permisos.
- Autorizaciones.
- Transferencia de vehículos.
- Reglas específicas relacionadas con la conservación y acceso al historial.
- Eliminación de registros.
- Corrección de registros.
- Información mínima requerida para generar recomendaciones.
- Reglas específicas para el tratamiento de información faltante.
- Definición de cuándo una recomendación debe sugerir acudir a un Prestador de Servicios Vehiculares.
- Definición de si el viaje podrá registrarse únicamente por distancia o también mediante destino.
- Definición de si el cálculo de distancia será manual o automático.

## Técnico

- Framework móvil.
- Lenguaje backend.
- Framework backend.
- Base de datos.
- Modelo de infraestructura.
- Proveedor Cloud, si aplica.
- Arquitectura.
- Mecanismos de comunicación e integración.
- Autenticación.
- Almacenamiento.
- Mecanismos tecnológicos de notificaciones.
- CI/CD.
- Monitoreo.
- Logging.
- Backups.
- Estrategia de ambientes.
- Implementación técnica de la capacidad de evaluación de reglas.
- Servicio de mapas, si aplica.
- Servicio de geolocalización, si aplica.

---

# 62. Principios de diseño

## 62.1 El vehículo es el activo principal

La información deberá estructurarse alrededor del vehículo y su ciclo de vida.

## 62.2 El historial pertenece al vehículo

El historial no deberá depender exclusivamente de un Prestador de Servicios Vehiculares.

## 62.3 El Propietario mantiene el control

El Propietario deberá controlar el acceso de terceros a la información de su vehículo.

## 62.4 La información debe ser trazable

Los registros relevantes deberán permitir identificar quién realizó una acción y cuándo.

## 62.5 El sistema debe anticiparse

La aplicación no deberá limitarse a almacenar información.

Deberá utilizar la información disponible para evaluar las reglas aplicables y, cuando corresponda, generar alertas, recomendaciones u otros resultados funcionales.

## 62.6 Recomendación no es diagnóstico

El sistema puede recomendar una revisión basándose en reglas, pero no deberá presentar dicha recomendación como un diagnóstico mecánico.

## 62.7 Información centralizada

Los diferentes actores deberán consultar una fuente centralizada de información.

## 62.8 Actualización en línea

Los cambios relevantes deberán estar disponibles para los actores autorizados.

## 62.9 Arquitectura preparada para crecimiento

La solución deberá permitir incorporar posteriormente nuevas funcionalidades, actores, planes de suscripción y servicios.

## 62.10 Preparación contextual

La plataforma deberá utilizar la información del vehículo para generar recomendaciones contextualizadas según situaciones específicas, como la preparación para un viaje.

## 62.11 Información incompleta no debe generar falsas certezas

Cuando el sistema no disponga de información suficiente para determinar el estado de un componente, deberá indicarlo claramente y evitar asumir que dicho componente se encuentra en buenas condiciones.

## 62.12 La aplicación orienta, el profesional diagnostica

Las recomendaciones generadas automáticamente tienen carácter informativo y preventivo. Las inspecciones físicas, diagnósticos y certificaciones sobre el estado real del vehículo deberán corresponder a profesionales autorizados cuando aplique.

---

# 63. Definiciones funcionales del proyecto

Este bloque consolida las principales definiciones funcionales desarrolladas para Vehículos Services y establece los conceptos, responsabilidades, relaciones y reglas generales que servirán como base para el levantamiento detallado de requerimientos, reglas de negocio y casos de uso.


## 63.1 DEFINIR VEHÍCULO

### 63.1.1 Concepto de vehículo

Dentro de Vehículos Services, el vehículo será el activo principal sobre el cual se organizará la información y las funcionalidades de la plataforma.

Un vehículo representa cualquier medio de transporte automotor que pueda ser registrado y administrado dentro de la aplicación con el propósito de llevar control de su información, características, kilometraje, mantenimientos, reparaciones, repuestos, costos, documentos, Prestadores de Servicios Vehiculares relacionados, historial y demás eventos que se produzcan durante su ciclo de vida.

Cada vehículo deberá contar con una identidad propia dentro de Vehículos Services y deberá mantenerse como una unidad independiente de información.

Esto significa que la información generada durante su utilización deberá permanecer relacionada con el vehículo y no depender exclusivamente del propietario, Prestador de Servicios Vehiculares o usuario que haya realizado un determinado registro.

Conceptualmente:

```text
VEHÍCULO
   ↓
INFORMACIÓN GENERAL
   ↓
KILOMETRAJE
   ↓
MANTENIMIENTOS
   ↓
REPARACIONES
   ↓
REPUESTOS
   ↓
ABASTECIMIENTO Y CONSUMO
   ↓
DOCUMENTOS
   ↓
COSTOS
   ↓
HISTORIAL
   ↓
ALERTAS Y RECOMENDACIONES
```

El vehículo será, por lo tanto, el elemento central que permitirá conectar la información generada por los diferentes componentes de Vehículos Services.

---

### 63.1.2 Tipos de vehículos soportados

Vehículos Services deberá estar preparado para administrar diferentes tipos de vehículos y no deberá limitar su funcionamiento únicamente a automóviles particulares.

La plataforma deberá contemplar inicialmente, como mínimo, las siguientes categorías generales:

#### Automóviles

Vehículos destinados principalmente al transporte particular de personas.

Ejemplos:

- Sedán.
- Hatchback.
- Coupé.
- Convertible.
- Station Wagon.
- Otros tipos de automóviles que puedan incorporarse posteriormente.

#### Camionetas

Vehículos que pueden utilizarse para transporte particular, carga liviana, actividades comerciales, trabajo o uso mixto.

Ejemplos:

- Pickup.
- Doble cabina.
- Cabina sencilla.
- Van.
- Minivan.
- Otros tipos de camionetas.

#### SUV

Vehículos utilitarios deportivos que combinan características de automóviles y vehículos de mayor capacidad o altura.

Podrán existir diferentes configuraciones relacionadas con:

- Tamaño.
- Tipo de tracción.
- Capacidad.
- Motorización.
- Uso particular o comercial.

#### Motocicletas

Vehículos automotores de dos o más ruedas pertenecientes a la categoría de motocicletas.

La plataforma deberá permitir que las características y mantenimientos de una motocicleta puedan diferenciarse de los correspondientes a un automóvil.

Ejemplos:

- Urbana.
- Deportiva.
- Touring.
- Scooter.
- Enduro.
- Motocross.
- Cruiser.
- Adventure.
- Otras categorías de motocicletas.

#### Camiones

Vehículos destinados principalmente al transporte de carga.

La plataforma deberá permitir gestionar vehículos de diferentes tamaños y capacidades sin asumir que todos los vehículos utilizan las mismas características o reglas de mantenimiento.

Ejemplos:

- Camión liviano.
- Camión mediano.
- Camión pesado.
- Camión rígido.
- Tractocamión.
- Otros tipos de vehículos de carga.

#### Cuatrimotos

Vehículos motorizados de cuatro ruedas utilizados en actividades recreativas, rurales, deportivas, laborales u otras actividades específicas.

La plataforma deberá permitir registrar y administrar este tipo de vehículo aunque sus características técnicas, mantenimiento y forma de utilización puedan diferir de las de un automóvil o una motocicleta.

#### Otros vehículos

Vehículos Services deberá diseñarse de manera que en el futuro puedan incorporarse nuevas categorías de vehículos sin modificar el concepto general de la plataforma.

Esto permitirá evaluar posteriormente la incorporación de vehículos como:

- Buses.
- Microbuses.
- Vehículos comerciales.
- Vehículos especiales.
- Vehículos recreativos.
- Vehículos eléctricos especializados.
- Maquinaria o vehículos de trabajo, si posteriormente se determina que hacen parte del alcance.

La incorporación de una nueva categoría no deberá implicar que todos los vehículos compartan exactamente los mismos datos, componentes o reglas de mantenimiento.

---

### 63.1.3 Clasificación del vehículo

Cada vehículo deberá tener asociado un tipo o categoría que permita identificar su naturaleza dentro de la plataforma.

Ejemplos:

```text
Automóvil
    ↓
Hatchback

Motocicleta
    ↓
Scooter

Camioneta
    ↓
Pickup

Camión
    ↓
Camión pesado
```

La clasificación permitirá posteriormente definir características, mantenimientos, recomendaciones y reglas que puedan variar dependiendo del tipo de vehículo.

No deberá asumirse, por ejemplo, que una motocicleta necesita exactamente la misma información o los mismos mantenimientos que un camión.

---

### 63.1.4 Identidad del vehículo dentro de la plataforma

Cada vehículo registrado deberá contar con una identidad propia dentro de Vehículos Services.

La plataforma deberá generar un identificador interno único que permita reconocer al vehículo independientemente de otros datos visibles como la placa.

Conceptualmente:

```text
IDENTIFICADOR INTERNO
        +
DATOS DE IDENTIFICACIÓN DEL VEHÍCULO
        ↓
VEHÍCULO ÚNICO EN LA PLATAFORMA
```

Este identificador permitirá mantener relacionadas todas las actividades que se produzcan durante la vida del vehículo.

La definición técnica del formato de este identificador será realizada posteriormente durante el diseño del modelo de datos y de la arquitectura.

---

### 63.1.5 Información general del vehículo

Todo vehículo registrado en Vehículos Services deberá contar con una ficha de información general que permita identificarlo, clasificarlo y establecer la información inicial necesaria para comenzar su gestión dentro de la plataforma.

Debido a que Vehículos Services soportará diferentes tipos de vehículos, no todos los datos serán obligatorios para todas las categorías.

La información se clasificará en:

- Información obligatoria común.
- Información obligatoria según el tipo de vehículo.
- Información opcional.
- Información no aplicable según el tipo de vehículo.

#### Información obligatoria común

Para registrar un vehículo se deberá contar, como mínimo, con la siguiente información:

- Tipo de vehículo.
- Subtipo o categoría.
- Marca.
- Línea / referencia / modelo comercial.
- Año / modelo.
- Placa.
- Kilometraje o lectura actual de uso.
- Tipo de combustible o fuente de energía.
- Cilindraje, cuando aplique.
- Transmisión, cuando aplique.
- VIN.
- Organismo de tránsito.

Para la primera entrega del Propietario, el VIN será obligatorio. El propietario deberá ingresarlo y la plataforma deberá comprobar su correspondencia con el VIN informado en la tarjeta de propiedad.

Si el usuario no puede suministrar el VIN o no puede comprobarse su correspondencia con la tarjeta de propiedad, el registro definitivo permanecerá sin completar.

El número de chasis y el número de motor no sustituirán al VIN para cumplir este requisito. Los tres datos se conservarán en campos separados y no se copiarán automáticamente valores entre ellos.

Las condiciones detalladas de registro, comparación y búsqueda de identificadores se desarrollarán en RN-036 — Identificación, coincidencias y comparación documental del vehículo, de `reglas-negocio.md`, respetando la obligatoriedad del VIN y el carácter opcional del número de chasis y del número de motor.

Después de confirmar, aceptar y guardar el registro definitivo, el propietario no podrá editar ni eliminar directamente los datos obligatorios aplicables del vehículo, tanto los comunes como los específicos de su tipo. Las solicitudes de corrección de errores de captura se tramitarán mediante soporte conforme a RN-037 — Actualización de datos personales y correcciones mediante soporte, de `reglas-negocio.md`, y RF-052 de `requerimientos-funcionales-propietario.md`, respetando los límites de RN-036.

La actualización del kilometraje o lectura de uso continuará mediante nuevos registros conforme a RF-005. Esta operación no permitirá sobrescribir la lectura inicial ni las anteriores desde la ficha de información general.

#### Información obligatoria según el tipo de vehículo

Además de la información común, Vehículos Services podrá requerir información adicional dependiendo del tipo de vehículo registrado.

Por ejemplo, los datos requeridos para un automóvil podrán ser diferentes de los requeridos para una motocicleta, un camión o una cuatrimoto.

##### Automóvil

Además de la información obligatoria común, para los vehículos clasificados como Automóvil se deberá registrar:

- Tipo de carrocería.
- Número de puertas.
- Capacidad de pasajeros.
- Tracción.

##### Motocicleta

Además de la información obligatoria común, para los vehículos clasificados como Motocicleta se deberá registrar:

- Tipo de motocicleta.

##### Camioneta

Además de la información obligatoria común, para los vehículos clasificados como Camioneta se deberá registrar:

- Tipo de carrocería.
- Número de puertas.
- Capacidad de pasajeros.
- Capacidad de carga, cuando aplique.
- Tracción.

##### SUV

Además de la información obligatoria común, para los vehículos clasificados como SUV se deberá registrar:

- Tipo de carrocería.
- Número de puertas.
- Capacidad de pasajeros.
- Tracción.

##### Camión

Además de la información obligatoria común, para los vehículos clasificados como Camión se deberá registrar:

- Tipo de carrocería.
- Número de ejes.
- Capacidad de pasajeros.
- Capacidad de carga.
- Tracción.

##### Cuatrimoto

Además de la información obligatoria común, para los vehículos clasificados como Cuatrimoto se deberá registrar:

- Tipo de cuatrimoto.
- Capacidad de pasajeros.
- Tracción.

Ejemplo conceptual:

```text
VEHÍCULO
    │
    ├── AUTOMÓVIL
    │      └── Datos propios de automóvil
    │
    ├── MOTOCICLETA
    │      └── Datos propios de motocicleta
    │
    ├── CAMIONETA
    │      └── Datos propios de camioneta
    │
    ├── SUV
    │      └── Datos propios de SUV
    │
    ├── CAMIÓN
    │      └── Datos propios de vehículo de carga
    │
    └── CUATRIMOTO
           └── Datos propios de cuatrimoto
```

#### Información opcional

La plataforma podrá permitir el registro de información adicional que complemente la identificación y descripción del vehículo, sin impedir su registro cuando dicha información no esté disponible.

Entre los datos opcionales se contemplan:

- Número de chasis.
- Número de motor.
- Color.
- Fotografía principal del vehículo.
- Observaciones.
- Otras características técnicas aplicables que no hayan sido definidas como obligatorias para el tipo de vehículo registrado.

Para la primera entrega, el propietario podrá registrar el número de chasis y el número de motor como información complementaria. Su ausencia, falta de ingreso o imposibilidad de lectura en la tarjeta de propiedad no impedirán por sí solas completar el registro o la asociación del vehículo.

No se exigirá completar estos datos únicamente porque aparezcan en la tarjeta de propiedad. Tampoco se utilizará el VIN para rellenarlos automáticamente.

La información opcional podrá variar dependiendo del tipo, características y configuración del vehículo.

#### Información no aplicable

Vehículos Services no deberá exigir información que no corresponda al tipo o características del vehículo registrado.

Por ejemplo, determinados datos técnicos podrán aplicar a un camión pero no a una motocicleta, mientras que otros podrán aplicar únicamente a vehículos eléctricos, híbridos o a determinadas configuraciones mecánicas.

La plataforma deberá permitir diferenciar entre un dato que no fue suministrado y un dato que no aplica al vehículo.


---

### 63.1.6 Registro del vehículo

Vehículos Services deberá permitir registrar vehículos que posteriormente serán administrados y acompañados durante su ciclo de vida dentro de la plataforma.

El registro del vehículo deberá realizarse utilizando la información obligatoria definida en el apartado 63.1.5 Información general del vehículo.

Para completar el registro, toda la información definida como obligatoria deberá ser suministrada y validada. La plataforma no deberá permitir completar el registro definitivo de un vehículo cuando falte información obligatoria.

#### Placa del vehículo

La placa será un dato obligatorio para completar el registro del vehículo.

Vehículos Services no permitirá completar el registro definitivo de un vehículo que no cuente con placa.

#### Validación de existencia del vehículo

Antes de crear un nuevo vehículo, la plataforma deberá validar si este ya se encuentra registrado en Vehículos Services.

La búsqueda de coincidencias por placa y VIN, la normalización de esos identificadores y el tratamiento inicial de coincidencias contradictorias se realizarán conforme a RN-036 — Identificación, coincidencias y comparación documental del vehículo, de `reglas-negocio.md`. Una coincidencia impedirá crear automáticamente otro vehículo hasta comprobar la correspondencia, sin fusionar registros ni sobrescribir identificadores existentes. El número de chasis y el número de motor serán información complementaria opcional y no se exigirán para ejecutar esta búsqueda.

Un vehículo que ya exista dentro de la plataforma no deberá ser creado nuevamente como una unidad independiente.

Si el vehículo ya se encuentra registrado debido a que perteneció anteriormente a otro propietario, Vehículos Services deberá conservar la identidad única del vehículo y la continuidad de su historial.

El cambio de propietario no deberá provocar la creación de un nuevo vehículo ni de un nuevo historial independiente.

Cuando el vehículo ya exista, su incorporación para un nuevo propietario deberá continuar mediante las reglas correspondientes a la relación Propietario ↔ Vehículo, sin duplicar la identidad del vehículo existente.

#### Kilometraje inicial registrado

Durante el registro del vehículo deberá ingresarse su kilometraje o lectura actual de uso.

Este valor constituirá el punto inicial conocido para el seguimiento del vehículo dentro de Vehículos Services.

Por ejemplo:

Si un vehículo es registrado por primera vez en la plataforma con:

```text
Kilometraje registrado: 134 km
```

Vehículos Services deberá considerar los 134 km como el primer kilometraje conocido y registrado dentro de la plataforma.

A partir de este valor, los registros posteriores permitirán conocer la evolución del kilometraje y relacionarlo con mantenimientos, reparaciones, repuestos, abastecimientos, alertas y demás eventos asociados al vehículo.

El kilometraje registrado inicialmente no implica que el vehículo haya comenzado su vida útil en dicho valor.

En el caso de un vehículo usado, este podrá ser registrado, por ejemplo, por primera vez en Vehículos Services con 123.945 km. En este caso, los 123.945 km representan el primer kilometraje conocido por la plataforma y no el comienzo de la vida útil real del vehículo.

La actualización posterior del kilometraje se realizará mediante nuevos registros conforme a RF-005 de `requerimientos-funcionales-propietario.md`. La edición de la información general no permitirá sobrescribir la lectura inicial ni las anteriores.

#### Integridad de la información del registro

La información obligatoria solicitada durante el registro deberá estar disponible para poder crear definitivamente el vehículo dentro de la plataforma.

El objetivo será mantener un nivel adecuado de identificación, trazabilidad y confiabilidad de la información asociada a cada vehículo.

Por esta razón, cuando falte alguno de los datos definidos como obligatorios, el registro definitivo no deberá completarse hasta que dicha información sea suministrada.

Mientras diligencia el registro, antes de confirmar su envío, el usuario podrá corregir los datos digitados. Si las comprobaciones rechazan datos de la solicitud que todavía no hayan sido aceptados y guardados como información definitiva del vehículo, podrá corregirlos y repetir el proceso conforme a RN-036. Estas acciones no permitirán modificar datos ya confirmados y guardados.

Después de confirmar, aceptar y guardar el registro definitivo, el propietario no podrá editar ni eliminar directamente los datos obligatorios aplicables del vehículo. Los errores de captura se tramitarán mediante soporte conforme a RN-037 — Actualización de datos personales y correcciones mediante soporte, de `reglas-negocio.md`, y RF-052 de `requerimientos-funcionales-propietario.md`.

La solicitud de corrección no autorizará automáticamente un cambio. Las correcciones aprobadas deberán conservar el identificador interno, el historial y la trazabilidad del vehículo, respetando los límites de RN-036.

#### Flujo conceptual de registro

```text
USUARIO
    ↓
SELECCIONA REGISTRAR VEHÍCULO
    ↓
SELECCIONA TIPO DE VEHÍCULO
    ↓
INGRESA INFORMACIÓN OBLIGATORIA
    ↓
INGRESA KILOMETRAJE / LECTURA ACTUAL
    ↓
SISTEMA VALIDA INFORMACIÓN
    ↓
SISTEMA VALIDA SI EL VEHÍCULO YA EXISTE
    ↓
¿EL VEHÍCULO YA EXISTE?
    │
    ├── NO
    │    ↓
    │  CREACIÓN DEL VEHÍCULO
    │    ↓
    │  VEHÍCULO REGISTRADO
    │    ↓
    │  INICIO DEL SEGUIMIENTO
    │  EN VEHÍCULOS SERVICES
    │
    └── SÍ
         ↓
       NO CREAR UN NUEVO VEHÍCULO
         ↓
       CONTINUAR MEDIANTE LAS REGLAS
       DE RELACIÓN PROPIETARIO ↔ VEHÍCULO
```

Si el vehículo ya existe, la plataforma no deberá crear una nueva unidad vehicular ni un historial independiente.

El proceso deberá continuar mediante las reglas correspondientes de asociación o cambio de propietario, conservando la identidad y el historial existente del vehículo.

Las reglas específicas relacionadas con quién puede registrar un vehículo, la relación Propietario ↔ Vehículo, el cambio o transferencia de propiedad, los permisos de acceso, la privacidad de la información y la participación de los Prestadores de Servicios Vehiculares deberán permanecer definidas en sus apartados correspondientes.

---

### 63.1.7 Vehículos con diferentes tecnologías de propulsión

La plataforma deberá contemplar que los vehículos pueden utilizar diferentes tecnologías de propulsión y fuentes de energía.

Entre ellas podrán encontrarse:

- Gasolina.
- Diésel.
- Gas.
- Híbrido.
- Eléctrico.
- Otras tecnologías o fuentes de energía que puedan surgir o incorporarse posteriormente.

La tecnología de propulsión y la fuente de energía del vehículo podrán afectar posteriormente:

- Los mantenimientos aplicables.
- Los componentes del vehículo.
- Los repuestos.
- Las recomendaciones.
- Los intervalos de mantenimiento.
- Los abastecimientos o recargas.
- El seguimiento del consumo de combustible o energía.
- Las verificaciones previas a viajes.

Por ejemplo, un vehículo de combustión podrá registrar tanqueos de combustible, mientras que un vehículo eléctrico podrá requerir el registro de recargas de energía. Los vehículos híbridos podrán requerir el seguimiento de más de una fuente de energía.

Por lo tanto, Vehículos Services no deberá asumir que todos los vehículos utilizan motores de combustión tradicional ni que todos requieren los mismos mecanismos de abastecimiento, mantenimiento o seguimiento de consumo.

La definición detallada de los abastecimientos, recargas, consumos y sus métricas será desarrollada posteriormente en el apartado correspondiente.

---

### 63.1.8 Ciclo de vida digital del vehículo


Desde el momento en que un vehículo sea incorporado a Vehículos Services deberá comenzar o continuar su ciclo de vida digital dentro de la plataforma.

El ciclo de vida digital representará la evolución del vehículo dentro de Vehículos Services a partir de la información, eventos, relaciones e interacciones que se produzcan o sean incorporados durante su permanencia en la plataforma.

Conceptualmente:

```text
VEHÍCULO
        ↓
SE INCORPORA A
VEHÍCULOS SERVICES
        ↓
INICIA O CONTINÚA
SU CICLO DE VIDA DIGITAL
        ↓
SE PRODUCEN O INCORPORAN
INFORMACIÓN, EVENTOS
E INTERACCIONES
        ↓
EL VEHÍCULO EVOLUCIONA
DENTRO DE LA PLATAFORMA
```

Durante dicho ciclo podrán producirse, entre otros:

- Registros y actualizaciones de kilometraje.
- Mantenimientos.
- Reparaciones.
- Cambios de repuestos.
- Abastecimientos, tanqueos o recargas.
- Registros de consumo.
- Información y documentos relacionados con el vehículo.
- Alertas y recomendaciones.
- Servicios realizados por Prestadores de Servicios Vehiculares.
- Cambios de propietario.
- Preparaciones y verificaciones relacionadas con viajes.
- Otros eventos o interacciones que posteriormente sean definidos.

Estos elementos no deberán entenderse como una secuencia obligatoria ni como acontecimientos que deban presentarse necesariamente en todos los vehículos.

Cada vehículo podrá evolucionar de manera diferente dependiendo de sus características, uso, información disponible y acontecimientos que se produzcan durante su ciclo de vida.

Por ejemplo:

```text
VEHÍCULO
        ↓
INFORMACIÓN INICIAL
        ↓
ACTUALIZACIÓN DE KILOMETRAJE
        ↓
MANTENIMIENTO
        ↓
NUEVO KILOMETRAJE
        ↓
REPARACIÓN
        ↓
ABASTECIMIENTOS
        ↓
CAMBIO DE PROPIETARIO
        ↓
NUEVOS EVENTOS
        ↓
CONTINÚA EL CICLO
DE VIDA DIGITAL
```

Este ejemplo representa únicamente una posible evolución del vehículo dentro de la plataforma.

El vehículo deberá continuar siendo la misma unidad lógica dentro de Vehículos Services durante su ciclo de vida digital.

Por lo tanto:

```text
NUEVO EVENTO
        ≠
NUEVO VEHÍCULO

NUEVO MANTENIMIENTO
        ≠
NUEVO VEHÍCULO

NUEVO PRESTADOR
        ≠
NUEVO VEHÍCULO

CAMBIO DE PROPIETARIO
        ≠
NUEVO VEHÍCULO
```

Los cambios que se produzcan durante la vida del vehículo no deberán provocar por sí mismos la creación de una nueva identidad vehicular dentro de Vehículos Services.

Conceptualmente:

```text
MISMO VEHÍCULO
        ↓
DIFERENTES MOMENTOS
        ↓
DIFERENTES EVENTOS
        ↓
DIFERENTES INTERACCIONES
        ↓
DIFERENTES RELACIONES
        ↓
MISMO CICLO DE VIDA DIGITAL
```

El ciclo de vida digital y el historial vehicular deberán entenderse como conceptos relacionados, pero no idénticos.

Conceptualmente:

```text
CICLO DE VIDA DIGITAL
        ↓
Representa la evolución
del vehículo dentro
de Vehículos Services

HISTORIAL VEHICULAR
        ↓
Organiza y conserva
los registros históricos
correspondientes
a esa evolución
```

Por lo tanto:

```text
CICLO DE VIDA DIGITAL
        ≠
HISTORIAL VEHICULAR
```

El historial será uno de los componentes fundamentales para representar y conservar la evolución del vehículo, pero el ciclo de vida digital constituye un concepto más amplio que comprende la permanencia y evolución del vehículo dentro de la plataforma.

Las reglas específicas relacionadas con la estructura del historial, conservación de registros, temporalidad, procedencia, modificación, visibilidad, privacidad y acceso deberán mantenerse en el apartado correspondiente al Historial Vehicular.

De igual manera, las reglas específicas relacionadas con propietarios, Prestadores de Servicios Vehiculares, mantenimientos, kilometraje, repuestos, abastecimientos, alertas, recomendaciones y demás componentes deberán desarrollarse en sus respectivos apartados.

Como principio general:

```text
VEHÍCULO
        ↓
MANTIENE SU IDENTIDAD
        ↓
EVOLUCIONA DENTRO
DE VEHÍCULOS SERVICES
        ↓
INFORMACIÓN + EVENTOS
+ RELACIONES + INTERACCIONES
        ↓
CICLO DE VIDA DIGITAL
        ↓
CONTINÚA MIENTRAS
EL VEHÍCULO PERMANEZCA
EN LA PLATAFORMA
```

---

### 63.1.9 Vehículos nuevos y usados

Vehículos Services deberá permitir registrar y gestionar tanto vehículos nuevos como vehículos usados.

#### Vehículo nuevo

Un vehículo nuevo podrá incorporarse a Vehículos Services desde una etapa temprana de su ciclo de vida.

Su historial dentro de la plataforma comenzará a construirse a partir del momento de su registro y del kilometraje o lectura inicial informada.

La plataforma no deberá asumir que un vehículo nuevo tiene kilometraje cero, ya que el valor inicial corresponderá a la lectura real registrada al momento de incorporarlo a Vehículos Services.

Conceptualmente:

```text
VEHÍCULO NUEVO
        ↓
SE REGISTRA EN
VEHÍCULOS SERVICES
        ↓
SE REGISTRA SU
LECTURA ACTUAL
        ↓
COMIENZA SU HISTORIAL
CONOCIDO DENTRO
DE LA PLATAFORMA
```

#### Vehículo usado no registrado anteriormente en Vehículos Services

Un vehículo usado podrá incorporarse a Vehículos Services después de haber recorrido una parte de su vida útil sin haber tenido registros anteriores dentro de la plataforma.

En este caso, el kilometraje ingresado durante su registro representará el primer kilometraje conocido por Vehículos Services.

Por ejemplo:

```text
VEHÍCULO USADO

Kilometraje real al momento
de incorporarlo:
123.945 km
        ↓
PRIMER KILOMETRAJE
CONOCIDO POR
VEHÍCULOS SERVICES
```

Este valor no deberá interpretarse como el inicio de la vida útil real del vehículo.

Podrá existir información histórica anterior a su incorporación a Vehículos Services que:

- Sea conocida.
- Sea parcialmente conocida.
- No se encuentre disponible.

Cuando exista información histórica anterior del vehículo que pueda ser incorporada a Vehículos Services, la plataforma podrá permitir su registro de acuerdo con las reglas que posteriormente sean definidas para la incorporación y procedencia de información histórica.

La ausencia de información histórica anterior no deberá interpretarse como evidencia de que un mantenimiento, reparación, cambio de repuesto u otra intervención nunca ocurrió.

Por lo tanto:

```text
NO EXISTE INFORMACIÓN
REGISTRADA EN LA PLATAFORMA
        ≠
EL EVENTO NUNCA OCURRIÓ
```

#### Vehículo usado registrado anteriormente en Vehículos Services

Cuando un vehículo usado ya exista dentro de Vehículos Services, no deberá registrarse nuevamente como un vehículo diferente ni comenzar un nuevo ciclo de vida digital dentro de la plataforma.

Conceptualmente:

```text
VEHÍCULO USADO
        ↓
¿YA EXISTE EN
VEHÍCULOS SERVICES?
        │
    ┌───┴───┐
    ↓       ↓
   NO       SÍ
    │       │
    ↓       ↓
PUEDE      NO SE CREA
REGISTRARSE NUEVAMENTE
POR PRIMERA
VEZ
```

Si el vehículo existente se encuentra relacionado con un proceso de cambio de propietario, dicho proceso deberá realizarse mediante las reglas definidas para la relación Propietario ↔ Vehículo.

El hecho de que exista un nuevo propietario no deberá convertir al vehículo en una nueva unidad dentro de Vehículos Services.

Por lo tanto:

```text
VEHÍCULO EXISTENTE
        +
NUEVO PROPIETARIO
        ≠
NUEVO VEHÍCULO
EN LA PLATAFORMA
```

La continuidad del vehículo, su historial, las relaciones de propiedad y las reglas de privacidad correspondientes deberán regirse por los apartados específicos definidos para dichos componentes.

#### Diferenciación general

Vehículos Services deberá diferenciar conceptualmente entre:

```text
VEHÍCULO NUEVO
        ↓
Puede incorporarse desde
una etapa temprana
de su vida útil

VEHÍCULO USADO
NO EXISTENTE EN LA PLATAFORMA
        ↓
Se registra por primera vez
con la información actualmente
conocida

VEHÍCULO USADO
YA EXISTENTE EN LA PLATAFORMA
        ↓
No se crea nuevamente
        ↓
Continúa siendo
el mismo vehículo
```

Esta diferenciación deberá permitir incorporar vehículos en diferentes momentos de su vida útil sin asumir que el momento de registro en Vehículos Services corresponde necesariamente al inicio de la existencia real del vehículo.

Las reglas detalladas relacionadas con registro, identificación, incorporación de información histórica anterior, cambio de propietario, continuidad del historial, procedencia de registros, privacidad y permisos deberán mantenerse en los apartados funcionales correspondientes.

---

### 63.1.10 Información incompleta

Vehículos Services deberá diferenciar entre la información obligatoria necesaria para registrar e identificar un vehículo y la información histórica disponible sobre su ciclo de vida.

La información definida como obligatoria para completar el registro del vehículo deberá ser suministrada de acuerdo con lo establecido en los apartados anteriores.

Sin embargo, la plataforma deberá reconocer que el historial de vida de un vehículo puede encontrarse incompleto, especialmente cuando este se incorpora a Vehículos Services después de haber recorrido parte de su vida útil.

Esto puede ocurrir cuando:

- El vehículo fue adquirido usado.
- El propietario anterior no entregó toda la información.
- No existen facturas o soportes de determinadas intervenciones.
- Los mantenimientos anteriores no fueron documentados.
- El vehículo fue atendido en talleres que no registraron información en Vehículos Services.
- Parte del historial se perdió.
- Se desconoce si determinadas intervenciones fueron realizadas.

Cuando no exista información histórica suficiente, la plataforma deberá indicarlo expresamente.

La ausencia de información no deberá interpretarse como evidencia de que un mantenimiento, reparación, cambio de repuesto o intervención nunca ocurrió.

De igual manera, la plataforma no deberá asumir que un componente se encuentra en buen estado simplemente porque no existen registros de mantenimientos, reparaciones o fallas relacionadas con dicho componente.

Vehículos Services deberá diferenciar, cuando corresponda, entre:

- Información conocida.
- Información parcialmente conocida.
- Información no disponible.
- Información no aplicable.

Esta diferenciación permitirá mantener la trazabilidad del vehículo sin generar conclusiones basadas en información que la plataforma realmente no posee.

Las reglas detalladas para registrar, validar o incorporar información histórica anterior serán desarrolladas posteriormente durante la definición del historial del vehículo.

---

### 63.1.11 Diferencias de mantenimiento entre tipos de vehículos

Vehículos Services deberá contemplar que los requerimientos de mantenimiento pueden variar dependiendo del tipo, características y configuración del vehículo.

Por lo tanto, la plataforma no deberá asumir que todos los vehículos comparten los mismos:

- Mantenimientos.
- Componentes.
- Repuestos.
- Intervalos de mantenimiento.
- Recomendaciones.
- Criterios de seguimiento.

Por ejemplo:

```text
AUTOMÓVIL
    ↓
Mantenimientos y reglas correspondientes a automóvil

MOTOCICLETA
    ↓
Mantenimientos y reglas correspondientes a motocicleta

CAMIONETA / SUV
    ↓
Mantenimientos y reglas correspondientes a su configuración

CAMIÓN
    ↓
Mantenimientos y reglas correspondientes a vehículos de carga

CUATRIMOTO
    ↓
Mantenimientos y reglas correspondientes a cuatrimoto
```

Adicionalmente, vehículos pertenecientes a una misma categoría podrán requerir mantenimientos diferentes debido a sus características particulares, tecnología de propulsión, fuente de energía, componentes o especificaciones técnicas.

Por ejemplo, un automóvil de combustión y un automóvil eléctrico pertenecen a la categoría automóvil, pero no necesariamente requieren los mismos mantenimientos, componentes ni reglas de seguimiento.

La definición específica de estos mantenimientos y sus reglas no forma parte todavía de este punto.

Será desarrollada posteriormente durante la definición de:

- Mantenimiento.
- Repuestos.
- Kilometraje.
- Reglas de mantenimiento.
- Alertas.
- Recomendaciones.

---

### 63.1.12 Principio general de flexibilidad

La definición de vehículo deberá permitir que Vehículos Services evolucione sin quedar limitado a las características actuales de los automóviles particulares ni a las tecnologías vehiculares existentes en el momento de desarrollar la plataforma.

Por esta razón, el concepto de vehículo deberá permitir:

- Diferentes tipos y categorías de vehículos.
- Diferentes características y configuraciones técnicas.
- Diferentes motorizaciones.
- Diferentes tipos de transmisión.
- Diferentes tecnologías de propulsión.
- Diferentes fuentes de energía.
- Diferentes formas de utilización.
- Diferentes componentes.
- Diferentes mantenimientos.
- Diferentes repuestos.
- Diferentes reglas de mantenimiento.
- Diferentes intervalos y criterios de mantenimiento.
- Diferentes documentos.
- Diferentes unidades o criterios de seguimiento cuando técnicamente sea necesario.
- Nuevas características o tecnologías que puedan incorporarse posteriormente.

La incorporación de una nueva categoría, configuración, tecnología o característica vehicular no deberá requerir redefinir completamente el concepto central de vehículo dentro de Vehículos Services.

El objetivo será que la plataforma pueda evolucionar y adaptarse a diferentes tipos y configuraciones de vehículos, manteniendo una estructura suficientemente flexible para soportar nuevas necesidades en el futuro.

Las particularidades correspondientes a mantenimientos, repuestos, reglas, alertas, recomendaciones y demás funcionalidades serán definidas posteriormente en sus respectivos apartados.

---

### 63.1.13 Límites de esta definición

La presente sección establece qué representa un vehículo dentro de Vehículos Services, la información general necesaria para identificarlo y los principios generales que deberán considerarse para su gestión dentro de la plataforma.

Durante esta definición se han establecido conceptos relacionados con:

- La identificación del vehículo.
- Los diferentes tipos y categorías de vehículos.
- La información general del vehículo.
- El registro del vehículo.
- Las diferentes tecnologías de propulsión y fuentes de energía.
- El ciclo de vida digital del vehículo.
- Los vehículos nuevos y usados.
- El tratamiento conceptual de información histórica incompleta.
- Las diferencias generales de mantenimiento según el tipo, características y configuración del vehículo.
- La flexibilidad necesaria para soportar diferentes configuraciones y tecnologías vehiculares.

Sin embargo, esta sección no define todavía en detalle:

- El propietario.
- El Prestador de Servicios Vehiculares.
- La relación entre propietario y vehículo.
- La relación entre Prestador de Servicios Vehiculares y vehículo.
- El historial vehicular.
- Los mantenimientos y sus diferentes tipos.
- Los planes de mantenimiento aplicables a cada vehículo.
- Los repuestos.
- La gestión detallada del kilometraje.
- Las reglas de mantenimiento.
- Los intervalos de mantenimiento por kilometraje, tiempo u otras condiciones.
- Las fuentes utilizadas para determinar los planes e intervalos de mantenimiento correspondientes a cada vehículo.
- Las alertas.
- Las notificaciones.
- Las recomendaciones.
- Los reportes.
- Los permisos y niveles de acceso.
- La transferencia o cambio de propietario.
- Las suscripciones.
- La preparación para viajes.
- Los casos de uso.
- Los requerimientos funcionales.
- Los requerimientos no funcionales.
- El modelo de datos.
- La arquitectura tecnológica y demás aspectos técnicos de implementación.

Estos elementos serán desarrollados posteriormente siguiendo el orden establecido para el levantamiento del proyecto.

La definición realizada en este apartado deberá servir como base para las siguientes etapas, evitando redefinir posteriormente los principios del vehículo que ya hayan sido establecidos y aprobados.


---
## 63.2 DEFINIR PROPIETARIO

### 63.2.1 Concepto de propietario

Dentro de Vehículos Services, un propietario será la persona que es dueño del vehículo. la propiedad de uno o varios vehículos registrados en la plataforma.

El concepto de propietario deberá representar al dueño del vehículo y no simplemente a una persona que lo utiliza, conduce, administra o realiza mantenimientos sobre este.

Un propietario podrá estar relacionado con uno o varios vehículos, y un mismo vehículo podrá haber tenido diferentes propietarios a lo largo de su ciclo de vida.

Vehículos Services deberá conservar la trazabilidad histórica de los propietarios que haya tenido un vehículo.

Por lo tanto, la relación de propiedad deberá permitir conocer, posteriormente y de acuerdo con las reglas que sean definidas:

- Quién es el propietario actual del vehículo.
- Cuántos propietarios ha tenido el vehículo.
- Durante qué período estuvo asociado el vehículo a cada propietario.
- Cuánto tiempo permaneció el vehículo bajo la propiedad de cada uno.
- El kilometraje correspondiente al inicio y final de cada período de propiedad, cuando dicha información se encuentre disponible.
- El kilometraje recorrido durante cada período de propiedad.
- Los mantenimientos, reparaciones, repuestos, abastecimientos y demás eventos ocurridos durante cada período de propiedad.
- La evolución general del uso y cuidado del vehículo durante sus diferentes períodos de propiedad.

Conceptualmente:

VEHÍCULO
    ↓
PROPIETARIO A
    ↓
PERÍODO DE PROPIEDAD A
    ↓
Kilometraje inicial → Kilometraje final
    ↓
Eventos ocurridos durante el período
    ↓
CAMBIO DE PROPIETARIO
    ↓
PROPIETARIO B
    ↓
PERÍODO DE PROPIEDAD B
    ↓
Kilometraje inicial → Kilometraje actual
    ↓
Eventos ocurridos durante el período

Esta trazabilidad permitirá que el historial del vehículo pueda mostrar su evolución a través de los diferentes propietarios sin dividir ni reiniciar su ciclo de vida digital.

Por ejemplo, Vehículos Services podrá llegar a determinar conceptualmente:

Vehículo: X

Propietarios históricos: 3

Propietario 1
Período de propiedad: 2014 - 2018
Kilometraje durante el período: 0 km → 42.000 km
Kilómetros recorridos: 42.000 km

Propietario 2
Período de propiedad: 2018 - 2023
Kilometraje durante el período: 42.000 km → 96.000 km
Kilómetros recorridos: 54.000 km

Propietario 3
Período de propiedad: 2023 - Actualidad
Kilometraje durante el período: 96.000 km → 121.000 km
Kilómetros recorridos: 25.000 km

La información histórica asociada a los períodos de propiedad podrá contribuir posteriormente a comprender el tipo de uso, mantenimiento y cuidado que ha tenido el vehículo durante su ciclo de vida.

Sin embargo, Vehículos Services no deberá asumir automáticamente que un vehículo recibió un buen o mal uso únicamente a partir del kilometraje recorrido o de la cantidad de propietarios.

Cualquier indicador, clasificación o análisis relacionado con el uso, cuidado o estado histórico del vehículo deberá basarse en reglas e información suficiente y será definido posteriormente en los apartados correspondientes.

La conservación de esta trazabilidad tampoco implicará que un propietario actual pueda consultar información personal o privada de propietarios anteriores.

La información técnica e histórica permanecerá asociada al vehículo, mientras que la información personal de cada propietario deberá mantenerse protegida de acuerdo con las reglas de privacidad y permisos que sean definidas.

Las reglas específicas relacionadas con la validación de la propiedad, períodos de propiedad, cambio de propietario, transferencia del vehículo, kilometraje por propietario, acceso al historial y protección de información serán desarrolladas posteriormente en el apartado correspondiente a la relación Propietario ↔ Vehículo.

---
### 63.2.2 Información del propietario

Todo propietario registrado en Vehículos Services deberá contar con información que permita identificarlo dentro de la plataforma y gestionar su cuenta.

Vehículos Services deberá permitir que el propietario corresponda a:

- Persona natural.
- Persona jurídica / empresa.

La información requerida deberá adaptarse al tipo de propietario registrado.

La primera entrega del Propietario comprenderá únicamente personas naturales. La gestión de propietarios persona jurídica o empresa se habilitará posteriormente.

La información del propietario deberá mantenerse separada conceptualmente de la información propia del vehículo y de la relación de propiedad existente entre ambos.

#### Tipo de propietario

Durante el registro del propietario deberá indicarse si corresponde a:

PERSONA NATURAL
    ↓
Persona que posee uno o varios vehículos a título personal.

PERSONA JURÍDICA / EMPRESA
    ↓
Organización o entidad que posee uno o varios vehículos.

La selección y las condiciones de registro deberán respetar los tipos de propietario habilitados en cada entrega. Esta definición no exigirá registrar un propietario ni asociar vehículos para crear inicialmente una cuenta de usuario.

#### Información obligatoria para persona natural

Para una persona natural se deberá contar, como mínimo, con:

- Nombres.
- Apellidos.
- Tipo de documento de identidad.
- Número de documento de identidad.
- Correo electrónico.
- Número de celular de contacto.
- País.

El correo electrónico se obtendrá durante la creación de la cuenta conforme al mecanismo de registro utilizado.

Los nombres, apellidos, tipo y número de documento se solicitarán cuando el usuario vaya a asociar su primer vehículo, conforme a RN-025 — Cuenta de usuario e identidad del propietario, de `reglas-negocio.md`. No se exigirán desde la creación inicial de la cuenta.

El celular de contacto será obligatorio para completar la información del propietario antes de asociar su primer vehículo. No se exigirá para crear inicialmente la cuenta.

Para la primera entrega se admitirán únicamente vehículos y documentos de Colombia, conforme a las condiciones establecidas en RN-025.

El usuario podrá actualizar directamente su celular de contacto conforme a RN-037 — Actualización de datos personales y correcciones mediante soporte, de `reglas-negocio.md`. Su condición de obligatorio no impedirá actualizarlo, pero una actualización aceptada no podrá eliminarlo ni dejarlo vacío.

#### Información obligatoria para persona jurídica / empresa

Para una persona jurídica o empresa se deberá contar, como mínimo, con:

- Razón social.
- Tipo de identificación tributaria o empresarial.
- Número de identificación tributaria o empresarial.
- País.
- Correo electrónico de contacto.
- Número de teléfono de contacto.

La plataforma deberá permitir posteriormente asociar las personas autorizadas para administrar la cuenta de una persona jurídica o empresa.

Las reglas relacionadas con representantes legales, administradores, usuarios autorizados y permisos sobre cuentas empresariales serán definidas posteriormente en los apartados correspondientes.

#### Información opcional

La plataforma podrá permitir registrar información adicional que complemente el perfil del propietario.

Dependiendo del tipo de propietario y de la entrega habilitada, esta información podrá incluir:

- Fotografía de perfil o imagen de la empresa.
- Ciudad.
- Dirección.
- Segundo número de teléfono.
- Información adicional que posteriormente sea definida como necesaria.

Para la primera entrega del Propietario persona natural se habilitarán como datos opcionales la ciudad de residencia y la fotografía de perfil. El usuario podrá agregarlas, actualizarlas o retirarlas conforme a RN-037.

La dirección exacta de residencia no se solicitará inicialmente. Su inclusión en esta lista general no implicará que esté disponible o sea requerida en la primera entrega. Su incorporación posterior deberá responder a una finalidad funcional definida.

El celular tendrá inicialmente una finalidad de contacto y no se utilizará por sí solo para autenticación, recuperación de acceso o comprobación de identidad. La fotografía de perfil no constituirá prueba de identidad. Cambiar la ciudad de residencia no modificará automáticamente los datos ni el organismo de tránsito de un vehículo.

Una vez confirmados, aceptados y guardados los nombres, apellidos, tipo y número de documento, el usuario no podrá editarlos ni eliminarlos directamente, aunque todavía no tenga vehículos asociados. El correo de la cuenta quedará sujeto a esa restricción desde su creación, incluso mientras permanezca pendiente de verificación.

Las solicitudes de corrección de esos datos se tramitarán mediante soporte conforme a RN-037 y RF-052 de `requerimientos-funcionales-propietario.md`, sin autorizar automáticamente cambios ni eludir las condiciones de unicidad y revisión de conflictos correspondientes.

#### Protección de la información

La información personal, empresarial o de contacto del propietario deberá mantenerse protegida y no deberá formar parte automáticamente del historial visible del vehículo.

Cuando un vehículo cambie de propietario, la información privada del propietario anterior no deberá transferirse automáticamente al nuevo propietario.

Por lo tanto, Vehículos Services deberá diferenciar entre:

INFORMACIÓN DEL PROPIETARIO
        ↓
Información correspondiente a la persona natural
o persona jurídica propietaria.

RELACIÓN DE PROPIEDAD
        ↓
Información que establece la relación histórica
entre un propietario y un vehículo.

HISTORIAL DEL VEHÍCULO
        ↓
Información técnica e histórica que permanece
asociada al vehículo.

La existencia de una relación histórica de propiedad deberá poder conservarse sin que esto implique exponer información personal, privada o empresarial que no sea necesaria para comprender el historial del vehículo.

Las reglas detalladas relacionadas con privacidad, permisos, tratamiento de datos, validación de identidad y visibilidad de información serán definidas posteriormente en los apartados correspondientes.

---


### 63.2.3 Registro del propietario

Vehículos Services deberá permitir que una persona pueda crear una cuenta utilizando diferentes mecanismos de registro y autenticación.

Para la primera entrega, cada propietario persona natural únicamente podrá tener una cuenta. El correo electrónico de registro deberá ser único y un mismo tipo y número de documento no podrá identificar al propietario en cuentas diferentes. Las comprobaciones se realizarán en los momentos establecidos en RN-025 — Cuenta de usuario e identidad del propietario, de `reglas-negocio.md`. La cuenta podrá disponer de distintos métodos de acceso vinculados conforme a RN-031, sin que cada mecanismo represente una cuenta independiente.

Entre estos mecanismos podrán contemplarse:

- Registro tradicional mediante correo electrónico.
- Registro o inicio de sesión mediante Google.
- Registro o inicio de sesión mediante Apple.
- Registro o inicio de sesión mediante Microsoft.
- Otros proveedores de identidad que posteriormente sean incorporados a la plataforma.

Para la primera entrega del Propietario se habilitarán el registro propio mediante correo electrónico y contraseña y el registro o inicio de sesión mediante Google y Apple en Android e iOS. Microsoft y los demás proveedores se contemplarán para entregas posteriores; su inclusión en esta definición general no implicará que estén disponibles inicialmente.

Esta selección se establece en RN-026 — Mecanismos de registro y autenticación, de `reglas-negocio.md`. Las condiciones aprobadas de verificación del correo, datos y contraseña del registro propio, y recuperación de la contraseña propia se desarrollan en RN-027, RN-028 y RN-029, respectivamente. El registro y autenticación mediante Google se desarrollan en RN-030; la vinculación, incorporación y retiro de métodos de acceso, en RN-031; y el registro y autenticación mediante Apple, en RN-032. Los mecanismos técnicos se establecerán en los documentos de arquitectura y seguridad correspondientes.

En el registro propio mediante correo electrónico y contraseña, la verificación del correo será obligatoria antes de habilitar el uso de la cuenta. Mientras esté pendiente, el usuario únicamente podrá realizar las acciones permitidas para completar el registro, introducir el código de verificación, solicitar un nuevo envío de verificación o consultar las indicaciones para contactar a soporte. No podrá gestionar vehículos ni acceder a sus registros. Esta condición se desarrolla en RN-027 — Verificación del correo en el registro propio, de `reglas-negocio.md`.

Antes de confirmar el envío del formulario de registro propio, el usuario podrá corregir el correo digitado. Una vez creada la cuenta, incluso mientras permanezca pendiente de verificación, no podrá editar ni eliminar directamente ese correo. Si necesita corregirlo, deberá solicitar ayuda mediante soporte conforme a RN-037 — Actualización de datos personales y correcciones mediante soporte, de `reglas-negocio.md`, y RF-052 de `requerimientos-funcionales-propietario.md`.

La solicitud de ayuda por un correo incorrecto no dependerá de haber verificado ese correo ni de poder iniciar sesión. Contactar a soporte no autorizará automáticamente la corrección ni habilitará la cuenta. Las verificaciones correspondientes deberán cumplirse antes de ejecutar cualquier cambio.

La verificación del correo demostrará control sobre esa dirección, pero no acreditará por sí sola la identidad personal ni la propiedad de un vehículo. Esta condición no establecerá automáticamente el procedimiento de verificación aplicable al registro mediante Google o Apple, cuyas condiciones se desarrollan expresamente en RN-030 y RN-032, respectivamente. En todos los mecanismos, el acceso a las funcionalidades requerirá cumplir las condiciones de habilitación aplicables a la cuenta.

Cuando el registro se realice mediante un proveedor externo de identidad, Vehículos Services podrá utilizar la información básica proporcionada y autorizada por dicho proveedor para facilitar la creación de la cuenta.

La información obtenida dependerá de los datos que el proveedor permita compartir y de las autorizaciones otorgadas por el usuario.

La creación inicial de la cuenta no deberá exigir necesariamente toda la información requerida posteriormente para registrar o asociar un vehículo.

Conceptualmente:

CREACIÓN DE CUENTA
        ↓
SELECCIÓN DEL MECANISMO DE REGISTRO
        ↓
┌─────────────────────────────┐
│ Correo electrónico          │
│ Google                      │
│ Apple                       │
│ Microsoft                   │
│ Otros proveedores futuros   │
└─────────────────────────────┘
        ↓
AUTENTICACIÓN
        ↓
OBTENCIÓN DE INFORMACIÓN BÁSICA DISPONIBLE
        ↓
CUENTA CREADA
        ↓
CUMPLIMIENTO DE LAS CONDICIONES
DE VERIFICACIÓN Y HABILITACIÓN APLICABLES
        ↓
ACCESO A VEHÍCULOS SERVICES
        ↓
EL USUARIO PUEDE TENER
0, 1 O VARIOS VEHÍCULOS ASOCIADOS

#### Complementación de información al registrar un vehículo

La creación de una cuenta en Vehículos Services no implicará que el usuario tenga vehículos asociados.

Un usuario podrá utilizar inicialmente la plataforma sin tener ningún vehículo registrado.

Cuando posteriormente seleccione la opción de agregar un vehículo, Vehículos Services deberá verificar que se encuentre disponible la información necesaria para continuar con el proceso.

Si la información obtenida durante la creación de la cuenta no es suficiente, la plataforma deberá solicitar al usuario los datos faltantes.

Para la primera entrega, antes de asociar el primer vehículo deberán estar disponibles los datos de identidad establecidos en RN-025 y el celular de contacto obligatorio definido en 63.2.2 y RN-037. El celular no se exigirá para crear inicialmente la cuenta y podrá actualizarse directamente, sin eliminarlo ni dejarlo vacío mediante una actualización aceptada.

Los nombres, apellidos, tipo y número de documento podrán corregirse mientras se diligencian, antes de confirmar su envío. Una vez confirmados, aceptados y guardados, no podrán editarse ni eliminarse directamente por el usuario, aunque todavía no se haya completado la asociación del vehículo. Sus errores de captura se tramitarán mediante soporte conforme a RN-037, respetando las condiciones de unicidad y los procedimientos de revisión de conflictos aplicables.

Conceptualmente:

USUARIO REGISTRADO
        ↓
0 VEHÍCULOS ASOCIADOS
        ↓
AGREGAR VEHÍCULO
        ↓
SISTEMA VERIFICA INFORMACIÓN DISPONIBLE
        ↓
¿INFORMACIÓN COMPLETA?
        ↓
NO
        ↓
SOLICITA INFORMACIÓN FALTANTE
        ↓
VALIDA INFORMACIÓN
        ↓
CONTINÚA EL PROCESO DE REGISTRO
Y ASOCIACIÓN DEL VEHÍCULO

La utilización de Google, Apple, Microsoft u otro proveedor externo permitirá facilitar el registro y autenticación del usuario, pero no constituirá por sí misma una validación de que dicho usuario sea propietario de un determinado vehículo.

Las reglas mediante las cuales se validará y establecerá la propiedad de un vehículo serán definidas posteriormente en el apartado correspondiente a la relación Propietario ↔ Vehículo.

#### Registro para persona natural

Cuando el usuario corresponda a una persona natural y posteriormente registre un vehículo del cual sea propietario, la misma persona podrá actuar simultáneamente como usuario de Vehículos Services y como propietario del vehículo.

Conceptualmente:

PERSONA NATURAL
        ↓
CREA SU CUENTA
        ↓
USUARIO DE VEHÍCULOS SERVICES
        ↓
AGREGA UN VEHÍCULO DE SU PROPIEDAD
        ↓
SE ESTABLECE LA RELACIÓN DE PROPIEDAD
        ↓
USUARIO Y PROPIETARIO
CORRESPONDEN A LA MISMA PERSONA

Un usuario persona natural podrá tener cero, uno o varios vehículos asociados, siempre que se cumplan las reglas correspondientes para establecer la relación de propiedad.

#### Registro para persona jurídica / empresa

Vehículos Services deberá permitir que una persona jurídica o empresa sea propietaria de uno o varios vehículos.

En este escenario deberá diferenciarse entre la empresa propietaria de los vehículos y las personas que utilizan la plataforma para administrarlos.

Conceptualmente:

PERSONA JURÍDICA / EMPRESA
        ↓
PROPIETARIA DE LOS VEHÍCULOS
        ↓
VEHÍCULOS
        ↓
USUARIOS AUTORIZADOS POR LA EMPRESA

La empresa deberá conservar la propiedad y administración principal de los vehículos asociados a ella.

Una persona que acceda a Vehículos Services en representación de una empresa no deberá convertirse automáticamente en propietaria de los vehículos de dicha organización.

#### Acceso a vehículos pertenecientes a una persona jurídica / empresa

La empresa podrá autorizar a uno o varios usuarios para acceder o gestionar determinados vehículos de su propiedad.

Por ejemplo:

EMPRESA
        ↓
VEHÍCULO 1 → USUARIO A
VEHÍCULO 2 → USUARIO B
VEHÍCULO 3 → USUARIO C
VEHÍCULO 4 → USUARIO A

La asignación de un vehículo a un usuario no deberá modificar la propiedad del vehículo.

El vehículo continuará perteneciendo a la empresa, mientras que el usuario contará únicamente con una autorización de acceso o gestión.

Conceptualmente:

EMPRESA
        ↓
PROPIETARIA
        ↓
VEHÍCULO
        ↓
ASIGNA ACCESO
        ↓
USUARIO AUTORIZADO

Los usuarios autorizados únicamente podrán acceder a la información y funcionalidades que la empresa les haya permitido.

La empresa deberá poder retirar posteriormente el acceso otorgado a un usuario sin afectar:

- La propiedad del vehículo.
- La información del vehículo.
- El historial del vehículo.
- Los mantenimientos registrados.
- El kilometraje.
- Los documentos.
- Los demás eventos asociados al vehículo.

Por ejemplo, si un vehículo perteneciente a una empresa se encuentra asignado a un empleado y posteriormente dicho empleado deja de utilizarlo, la empresa podrá retirar su acceso y asignar el vehículo a otra persona sin que esto represente un cambio de propietario.

Conceptualmente:

EMPRESA
        ↓
VEHÍCULO
        ↓
USUARIO A
        ↓
SE RETIRA SU ACCESO
        ↓
VEHÍCULO CONTINÚA PERTENECIENDO A LA EMPRESA
        ↓
USUARIO B
        ↓
NUEVO ACCESO AUTORIZADO

El historial y ciclo de vida digital del vehículo deberán permanecer asociados al vehículo independientemente de los usuarios que hayan sido autorizados para utilizarlo o administrarlo.

#### Administración de vehículos empresariales

Una empresa podrá contar posteriormente con usuarios que tengan diferentes niveles de acceso sobre sus vehículos.

Por ejemplo, podrán existir usuarios con capacidad para administrar varios o todos los vehículos de la organización y otros usuarios que únicamente tengan acceso a los vehículos que les hayan sido asignados.

La definición específica de:

- Roles.
- Niveles de acceso.
- Funcionalidades permitidas.
- Asignación de vehículos.
- Revocación de accesos.
- Administradores de empresa.
- Usuarios autorizados.
- Restricciones de modificación.
- Gestión de permisos.

no forma parte todavía de este punto.

Estas reglas serán desarrolladas posteriormente en los apartados correspondientes a relaciones y permisos.

#### Separación conceptual

Vehículos Services deberá diferenciar conceptualmente entre el usuario que accede a la plataforma y quien es dueño propietario del vehículo.

En una persona natural ambos conceptos podrán corresponder a la misma persona:

PERSONA NATURAL
        ↓
USUARIO
        +
PROPIETARIO DEL VEHÍCULO

En una persona jurídica o empresa podrán corresponder a entidades diferentes:

EMPRESA
        ↓
PROPIETARIA DEL VEHÍCULO

USUARIO AUTORIZADO
        ↓
PERSONA QUE ACCEDE O GESTIONA
EL VEHÍCULO EN NOMBRE DE LA EMPRESA

Por lo tanto, la creación de una cuenta en Vehículos Services no implicará automáticamente la propiedad de ningún vehículo.

La propiedad surgirá de la relación que posteriormente sea establecida y validada entre un propietario y un vehículo.

Las reglas específicas relacionadas con validación de identidad, validación de propiedad, asociación de vehículos, transferencia de propiedad, asignación de vehículos empresariales y permisos serán desarrolladas posteriormente en los apartados correspondientes.




---

### 63.2.4 Permanencia del propietario dentro de Vehículos Services

La existencia de un propietario dentro de Vehículos Services no deberá depender de que este tenga actualmente uno o varios vehículos asociados.

Un propietario podrá tener:

- Cero vehículos asociados actualmente.
- Un vehículo asociado actualmente.
- Varios vehículos asociados actualmente.
- Vehículos asociados únicamente de manera histórica.

Por lo tanto, cuando un propietario deje de tener vehículos asociados actualmente, su existencia dentro de Vehículos Services no deberá eliminarse automáticamente.

Por ejemplo:

```text
PROPIETARIO
        ↓
VEHÍCULO A
        ↓
FINALIZA LA RELACIÓN
DE PROPIEDAD ACTUAL
        ↓
PROPIETARIO QUEDA CON
0 VEHÍCULOS ACTUALES
        ↓
CONTINÚA EXISTIENDO
EN VEHÍCULOS SERVICES
```

En este escenario, el propietario podrá continuar existiendo dentro de Vehículos Services y posteriormente podrá registrar o asociar nuevos vehículos de acuerdo con las reglas correspondientes.

La ausencia de vehículos actuales tampoco deberá eliminar las relaciones históricas de propiedad que hayan existido.

Conceptualmente:

```text
PROPIETARIO
        ↓
VEHÍCULOS ACTUALES: 0

PERO HISTÓRICAMENTE
        ↓
VEHÍCULO A
Propietario durante
un período determinado

VEHÍCULO B
Propietario durante
otro período determinado
```

Las relaciones históricas deberán conservarse para mantener la trazabilidad de los períodos de propiedad correspondientes.

Este principio deberá aplicar tanto para personas naturales como para personas jurídicas o empresas.

Por ejemplo, una empresa podrá haber tenido varios vehículos registrados en Vehículos Services y posteriormente transferirlos o venderlos todos.

```text
EMPRESA
        ↓
VEHÍCULOS ACTUALES: 0
        ↓
LA EMPRESA CONTINÚA EXISTIENDO
EN VEHÍCULOS SERVICES
```

La empresa podrá posteriormente incorporar nuevos vehículos sin que sea necesario crear nuevamente su identidad dentro de la plataforma.

De igual manera, que un propietario tenga cero vehículos asociados actualmente no deberá interpretarse automáticamente como que su cuenta se encuentra inactiva, eliminada o bloqueada.

Las reglas relacionadas con el acceso a vehículos que ya no son de su propiedad, los períodos históricos de propiedad, la transferencia de vehículos y la visibilidad de la información histórica se encuentran definidas o deberán desarrollarse dentro de los componentes correspondientes a la relación Propietario ↔ Vehículo, historial y permisos.

El estado de una cuenta y las reglas relacionadas con su activación, desactivación, eliminación, bloqueo, recuperación o conservación deberán desarrollarse posteriormente en los componentes correspondientes.


---
## 63.3 DEFINIR PRESTADOR DE SERVICIOS VEHICULARES
### 63.3.1 Concepto de Prestador de Servicios Vehiculares

Dentro de Vehículos Services, un Prestador de Servicios Vehiculares será una persona, establecimiento, empresa u organización que presta servicios relacionados con la revisión, mantenimiento, diagnóstico, reparación, inspección, peritaje o intervención de vehículos.

El concepto de Prestador de Servicios Vehiculares será el término general utilizado por la plataforma para representar a las diferentes entidades que pueden prestar servicios sobre un vehículo.

Por lo tanto, un taller no será considerado el único tipo de prestador dentro de Vehículos Services, sino una de las posibles clasificaciones de Prestador de Servicios Vehiculares.

Entre los tipos de prestadores que podrá contemplar la plataforma se encuentran:

- Taller mecánico.
- Taller de mantenimiento preventivo.
- Taller de mantenimiento correctivo.
- Taller especializado.
- Centro de diagnóstico.
- Centro o establecimiento de peritaje vehicular.
- Centro de inspección o revisión vehicular.
- Servicios especializados de electricidad automotriz.
- Servicios de latonería y pintura.
- Servicios relacionados con llantas, alineación y balanceo.
- Otros prestadores relacionados con la revisión, evaluación, diagnóstico, mantenimiento, reparación o intervención de vehículos que posteriormente sean contemplados por la plataforma.

Esta clasificación deberá permitir que Vehículos Services pueda incorporar diferentes tipos de prestadores sin asumir que todos corresponden a un taller mecánico.

Conceptualmente:

PRESTADOR DE SERVICIOS VEHICULARES
                ↓
        TIPO DE PRESTADOR
                ↓
    ┌───────────┼───────────────┐
    ↓           ↓               ↓
  TALLER     CENTRO DE       CENTRO DE
 MECÁNICO     PERITAJE       DIAGNÓSTICO
    ↓           ↓               ↓
SERVICIOS    EVALUACIÓN      DIAGNÓSTICO
    └───────────┼───────────────┘
                ↓
       EVENTOS DEL VEHÍCULO
                ↓
      HISTORIAL DEL VEHÍCULO

No todos los Prestadores de Servicios Vehiculares deberán necesariamente realizar las mismas actividades.

Por ejemplo, un taller mecánico podrá realizar mantenimientos y reparaciones, mientras que un centro de peritaje podrá realizar una evaluación del estado del vehículo y generar un resultado, informe, documento o evidencia correspondiente al peritaje realizado.

El Prestador de Servicios Vehiculares deberá existir dentro de la plataforma como una entidad independiente del propietario y del vehículo.

Un prestador podrá estar relacionado con uno o varios vehículos a lo largo del tiempo, pero la atención, revisión, evaluación, diagnóstico o intervención de un vehículo por parte de un prestador no implicará que dicho prestador sea propietario del vehículo.

De igual manera, un vehículo podrá haber sido atendido, revisado, evaluado, diagnosticado o intervenido por diferentes Prestadores de Servicios Vehiculares durante su ciclo de vida.

Por ejemplo:

VEHÍCULO
    ↓
TALLER MECÁNICO
    ↓
MANTENIMIENTO
    ↓
HISTORIAL DEL VEHÍCULO
    ↓
CENTRO DE PERITAJE
    ↓
PERITAJE
    ↓
HISTORIAL DEL VEHÍCULO
    ↓
TALLER ESPECIALIZADO
    ↓
REPARACIÓN
    ↓
HISTORIAL DEL VEHÍCULO

La participación de diferentes Prestadores de Servicios Vehiculares no deberá dividir, reiniciar ni reemplazar el historial del vehículo.

Cada servicio, intervención, revisión, diagnóstico, inspección, evaluación o peritaje deberá conservar la identificación del prestador que lo realizó o registró, cuando dicha información se encuentre disponible, permitiendo mantener la trazabilidad sobre el origen de la información incorporada al historial.

El Prestador de Servicios Vehiculares podrá participar en la construcción del historial del vehículo mediante el registro de los servicios, intervenciones, diagnósticos, inspecciones, evaluaciones o peritajes que realice, de acuerdo con las autorizaciones y reglas que posteriormente sean definidas.

En el caso particular de un peritaje, Vehículos Services deberá permitir conceptualmente conservar dentro del historial la existencia de dicha evaluación y la información que posteriormente sea definida como parte del registro del peritaje, pudiendo incluir resultados, documentos, evidencias u otra información relacionada.

La estructura detallada del peritaje, la información que deberá registrarse, sus resultados, documentos, evidencias y reglas específicas serán definidas posteriormente y no forman parte todavía de la definición conceptual del Prestador de Servicios Vehiculares.

La información registrada por un Prestador de Servicios Vehiculares como parte del historial deberá permanecer asociada al vehículo incluso si posteriormente:

- El propietario deja de utilizar los servicios de dicho prestador.
- El propietario revoca el acceso del prestador.
- El vehículo comienza a ser atendido por otro prestador.
- El vehículo cambia de propietario.
- El prestador deja de tener una relación activa con el vehículo.

Por lo tanto, finalizar la relación entre un Prestador de Servicios Vehiculares y un vehículo no deberá eliminar los registros históricos correspondientes a las intervenciones, servicios, diagnósticos, inspecciones, evaluaciones o peritajes realizados mientras existió dicha relación.

Vehículos Services deberá diferenciar conceptualmente entre:

PRESTADOR DE SERVICIOS VEHICULARES
        ↓
Entidad que presta el servicio

TIPO DE PRESTADOR
        ↓
Clasifica la naturaleza de los servicios
que presta la entidad

RELACIÓN PRESTADOR ↔ VEHÍCULO
        ↓
Determina la relación y autorización existente
entre el prestador y un vehículo

SERVICIO / INTERVENCIÓN / EVALUACIÓN
        ↓
Evento realizado sobre el vehículo

HISTORIAL DEL VEHÍCULO
        ↓
Conserva la trazabilidad
de los eventos registrados

El Prestador de Servicios Vehiculares no deberá considerarse propietario del historial del vehículo.

El historial permanecerá vinculado al vehículo y deberá conservarse independientemente del prestador que haya realizado cada intervención, servicio, diagnóstico, inspección, evaluación o peritaje.

Asimismo, deberá diferenciarse conceptualmente el Prestador de Servicios Vehiculares de las personas que posteriormente puedan acceder a Vehículos Services en representación de dicho prestador.

Por ejemplo:

PRESTADOR DE SERVICIOS VEHICULARES
        ↓
Entidad / establecimiento / empresa
        ↓
USUARIOS AUTORIZADOS
        ↓
Personas que acceden a la plataforma
en representación del prestador

La existencia de un usuario asociado a un Prestador de Servicios Vehiculares no deberá implicar que dicho usuario sea individualmente el prestador.

Una misma persona natural podrá ser propietaria de uno o varios vehículos y, al mismo tiempo, estar registrada como Prestador de Servicios Vehiculares. En este caso, podrá utilizar una sola cuenta de usuario para acceder a las funcionalidades que le correspondan como Propietario y como Prestador, cuando ambos módulos se encuentren disponibles.

La identidad de la persona, su relación de propiedad con cada vehículo y su condición de Prestador de Servicios Vehiculares deberán mantenerse diferenciadas. Los vehículos de su propiedad no deberán convertirse automáticamente en vehículos atendidos o autorizados para la operación del prestador. Si el prestador registra un servicio sobre uno de esos vehículos, deberán aplicarse las reglas correspondientes a la relación Prestador de Servicios Vehiculares ↔ Vehículo y conservarse la identificación del rol con el que se realizó cada acción.

El acceso como Propietario no deberá otorgar automáticamente permisos propios del Prestador, ni el acceso como Prestador deberá ampliar los permisos sobre los vehículos personales de la misma persona. Las funcionalidades disponibles en cada contexto deberán depender de las relaciones, autorizaciones y reglas aplicables.

La definición detallada de los usuarios asociados al prestador, sus funciones, niveles de acceso y permisos será desarrollada posteriormente en los apartados correspondientes.

Las reglas específicas relacionadas con el registro del prestador, autorización, acceso, revocación, información visible, relación Prestador de Servicios Vehiculares ↔ Vehículo y permisos serán desarrolladas posteriormente en los apartados correspondientes.

---

### 63.3.2 Información del Prestador de Servicios Vehiculares

Todo Prestador de Servicios Vehiculares registrado en Vehículos Services deberá contar con información que permita identificarlo dentro de la plataforma, diferenciar su naturaleza, conocer el tipo de servicios que ofrece y gestionar posteriormente su relación con los vehículos y propietarios.

La información requerida deberá adaptarse a la naturaleza del prestador y no deberá asumirse que todos los Prestadores de Servicios Vehiculares tienen la misma estructura, identificación, actividad o forma de operación.

Asimismo, deberá contemplarse que un Prestador de Servicios Vehiculares podrá operar mediante una o varias sedes. Por lo tanto, Vehículos Services deberá diferenciar la información general correspondiente al prestador de aquella información que corresponda específicamente a cada una de sus sedes.

Conceptualmente:

```text
PRESTADOR DE SERVICIOS VEHICULARES
        ↓
INFORMACIÓN GENERAL DEL PRESTADOR
        ↓
UNA O VARIAS SEDES
        ↓
INFORMACIÓN PARTICULAR DE CADA SEDE
```

La existencia, estructura, información, comportamiento y reglas específicas de las sedes serán desarrolladas posteriormente en el apartado correspondiente.

Vehículos Services deberá diferenciar conceptualmente entre:

```text
PRESTADOR DE SERVICIOS VEHICULARES
        ↓
NATURALEZA DEL PRESTADOR
        ↓
PERSONA NATURAL
        O
PERSONA JURÍDICA / EMPRESA
        ↓
IDENTIFICACIÓN
        ↓
TIPO DE PRESTADOR / ACTIVIDAD
        ↓
SERVICIOS OFRECIDOS
        ↓
ESTADO DE VERIFICACIÓN
```

Estos conceptos deberán mantenerse separados, ya que describen características diferentes del Prestador de Servicios Vehiculares.

#### Naturaleza del prestador

Vehículos Services deberá permitir que un Prestador de Servicios Vehiculares corresponda, como mínimo, a:

- Persona natural.
- Persona jurídica / empresa.

Una persona natural podrá prestar profesionalmente uno o varios servicios relacionados con vehículos sin que sea necesario que exista una persona jurídica independiente.

Una persona jurídica o empresa podrá corresponder a una organización constituida que preste uno o varios servicios relacionados con vehículos.

La naturaleza del prestador no deberá determinar automáticamente el tipo de servicio que puede ofrecer.

Por ejemplo:

```text
PERSONA NATURAL
        ↓
Puede prestar servicios de:
- Mecánica.
- Electricidad automotriz.
- Diagnóstico.
- Otros servicios que correspondan.

PERSONA JURÍDICA / EMPRESA
        ↓
Puede operar como:
- Taller.
- Centro de diagnóstico.
- Centro de peritaje.
- Centro de inspección.
- Establecimiento de latonería y pintura.
- Establecimiento de llantas, alineación o balanceo.
- Otros tipos de Prestadores de Servicios Vehiculares.
```

Por lo tanto:

```text
NATURALEZA DEL PRESTADOR
        ≠
TIPO DE PRESTADOR
        ≠
SERVICIOS OFRECIDOS
```

La clasificación detallada de los tipos de prestador, servicios y especialidades será desarrollada posteriormente dentro de este mismo apartado, evitando duplicidades entre estos conceptos.

#### Información básica obligatoria

Todo Prestador de Servicios Vehiculares deberá contar, como mínimo, con información básica que permita identificarlo y establecer un medio general de contacto.

Esta información deberá contemplar:

- Naturaleza del prestador.
- Nombre con el que se identifica dentro de la plataforma.
- Tipo de Prestador de Servicios Vehiculares.
- País de registro u operación general, cuando corresponda.
- Correo electrónico general de contacto.
- Número de teléfono general de contacto.

La información anterior corresponde al Prestador de Servicios Vehiculares como entidad general y no deberá utilizarse para asumir que todas sus sedes comparten una misma dirección, ubicación, teléfono, horario de atención u otra información operacional.

Cuando un prestador opere mediante una o varias sedes, la ubicación, dirección, información de contacto, horarios y demás datos particulares que posteriormente se definan deberán poder asociarse a la sede correspondiente.

Por ejemplo:

```text
PRESTADOR DE SERVICIOS VEHICULARES
Servicios Automotrices ABC S.A.S.
        ↓
INFORMACIÓN GENERAL DEL PRESTADOR
- Nombre.
- Identificación.
- Contacto general.
        ↓
SEDES
        ├── Sede Poblado
        │      └── Información propia de la sede
        │
        └── Sede Estadio
               └── Información propia de la sede
```

Esto deberá evitar que Vehículos Services represente diferentes ubicaciones de una misma organización como si necesariamente fueran Prestadores de Servicios Vehiculares independientes.

El nombre con el que el prestador se identifica dentro de Vehículos Services no necesariamente deberá corresponder exactamente con su nombre legal o razón social.

Por ejemplo:

```text
RAZÓN SOCIAL
Servicios Automotrices ABC S.A.S.

NOMBRE COMERCIAL
ABC Motor Center
```

Vehículos Services podrá utilizar el nombre comercial para identificar al prestador frente a los usuarios, conservando separadamente la información legal que corresponda.

#### Información para persona natural

Cuando el Prestador de Servicios Vehiculares corresponda a una persona natural, deberá contemplarse como mínimo:

- Nombres.
- Apellidos.
- Tipo de documento de identidad.
- Número de documento de identidad.
- Identificación tributaria, cuando aplique.

La existencia de una identificación tributaria no deberá utilizarse como criterio para determinar si el prestador corresponde a una persona natural o a una persona jurídica.

Una persona natural podrá contar también con identificación tributaria de acuerdo con las condiciones legales y tributarias que le correspondan.

#### Información para persona jurídica / empresa

Cuando el Prestador de Servicios Vehiculares corresponda a una persona jurídica o empresa, deberá contemplarse como mínimo:

- Razón social.
- Tipo de identificación tributaria o empresarial.
- Número de identificación tributaria o empresarial.

Una persona jurídica o empresa podrá operar mediante una o varias sedes sin que cada sede deba considerarse automáticamente una persona jurídica, empresa o Prestador de Servicios Vehiculares independiente.

Por ejemplo:

```text
PERSONA JURÍDICA / EMPRESA
Servicios Automotrices ABC S.A.S.
        ↓
PRESTADOR DE SERVICIOS VEHICULARES
ABC Motor Center
        ↓
SEDES
        ├── Sede Poblado
        ├── Sede Estadio
        └── Sede Rionegro
```

La relación exacta entre el prestador y sus sedes será definida posteriormente.

Posteriormente podrán asociarse las personas autorizadas para administrar o utilizar Vehículos Services en representación del prestador.

El Prestador de Servicios Vehiculares deberá mantenerse conceptualmente separado de las personas que acceden a la plataforma en su representación.

Por ejemplo:

```text
PRESTADOR DE SERVICIOS VEHICULARES
ABC Motor Center
        ↓
USUARIOS AUTORIZADOS
        ↓
Personas que utilizan Vehículos Services
en representación del prestador
```

Por lo tanto, una persona que utilice la plataforma en representación de un Prestador de Servicios Vehiculares no deberá convertirse por este hecho en el prestador mismo.

La existencia de sedes tampoco deberá utilizarse para asumir automáticamente que todos los usuarios asociados al prestador podrán acceder a todas ellas o consultar toda la información generada por estas.

La asociación de usuarios con el prestador o con determinadas sedes, así como sus roles, niveles de acceso, alcance de consulta y permisos, será definida posteriormente en los apartados correspondientes.

#### Identificación del prestador

Vehículos Services deberá permitir registrar la información de identificación correspondiente al prestador de acuerdo con:

- Su naturaleza.
- El país en el que se encuentre registrado o preste sus servicios.
- Los documentos de identificación que legal o administrativamente le correspondan.

No deberá establecerse una equivalencia rígida como:

```text
PERSONA NATURAL = CÉDULA

PERSONA JURÍDICA / EMPRESA = NIT
```

La plataforma deberá permitir manejar diferentes tipos de documentos de identidad, identificación tributaria o identificación empresarial según corresponda.

La identificación general del Prestador de Servicios Vehiculares deberá mantenerse diferenciada de la identificación o información particular que posteriormente pueda requerirse para cada una de sus sedes.

La definición específica de los documentos aceptados, sus reglas de validación y las particularidades correspondientes a cada país será desarrollada posteriormente.

#### Identificación y verificación

Vehículos Services deberá diferenciar entre la información registrada por un Prestador de Servicios Vehiculares y la verificación realizada sobre dicha información.

Conceptualmente:

```text
PRESTADOR SE REGISTRA
        ↓
INGRESA SU INFORMACIÓN
        ↓
REGISTRO DEL PRESTADOR
        ↓
APORTA INFORMACIÓN O DOCUMENTOS
REQUERIDOS PARA VERIFICACIÓN
        ↓
VEHÍCULOS SERVICES REALIZA
LAS VALIDACIONES CORRESPONDIENTES
        ↓
¿VALIDACIÓN SATISFACTORIA?
        ↓
     SÍ / NO
      ↓    ↓
VERIFICADO  NO VERIFICADO
```

El hecho de registrar correctamente un documento de identidad, identificación tributaria, razón social, nombre comercial u otra información no deberá convertir automáticamente al prestador en un Prestador de Servicios Vehiculares verificado.

Por lo tanto:

```text
PRESTADOR REGISTRADO
        ≠
PRESTADOR VERIFICADO
```

Un Prestador de Servicios Vehiculares registrado será aquel que haya creado su perfil y suministrado la información requerida por la plataforma.

Un Prestador de Servicios Vehiculares verificado será aquel cuya identidad o información correspondiente haya superado satisfactoriamente las validaciones que Vehículos Services defina para este propósito.

La verificación general del prestador no deberá utilizarse para asumir automáticamente que todas sus sedes se encuentran verificadas bajo los mismos criterios.

La necesidad de verificar sedes individualmente, los mecanismos aplicables y la relación entre el estado de verificación del prestador y el de sus sedes serán definidos posteriormente.

Los mecanismos específicos de verificación, documentos requeridos, fuentes de validación, responsables del proceso, estados intermedios, vigencias y reglas aplicables según el país o tipo de prestador serán definidos posteriormente.

#### Información complementaria

Vehículos Services podrá permitir que el Prestador de Servicios Vehiculares registre información adicional para complementar su perfil general.

Esta información podrá incluir posteriormente, entre otros elementos:

- Logo o imagen del prestador.
- Página web.
- Descripción del prestador.
- Información general adicional de contacto.
- Otra información que posteriormente sea definida como necesaria a nivel del prestador.

Los datos que correspondan específicamente a una ubicación física u operacional no deberán confundirse con la información general del prestador.

Por ejemplo, elementos como:

- Dirección de una sede.
- Ciudad o ubicación de una sede.
- Teléfono particular de una sede.
- Horarios de atención de una sede.
- Información de contacto particular de una sede.
- Otros datos operacionales propios de una ubicación.

deberán poder registrarse posteriormente como información correspondiente a la sede respectiva.

Conceptualmente:

```text
INFORMACIÓN DEL PRESTADOR
        ≠
INFORMACIÓN DE LA SEDE
```

La obligatoriedad de estos datos será determinada posteriormente de acuerdo con las necesidades funcionales de la plataforma.

#### Protección y visibilidad de la información

La información registrada sobre un Prestador de Servicios Vehiculares no deberá considerarse automáticamente pública.

Vehículos Services deberá diferenciar entre:

```text
INFORMACIÓN DE IDENTIFICACIÓN
        ↓
Datos utilizados para identificar
legal o administrativamente al prestador.

INFORMACIÓN DE CONTACTO
        ↓
Datos utilizados para establecer
comunicación con el prestador.

INFORMACIÓN PÚBLICA DEL PERFIL
        ↓
Información que podrá ser consultada
por otros usuarios de la plataforma.

INFORMACIÓN DE VERIFICACIÓN
        ↓
Información y documentos utilizados
para validar al prestador.
```

Los documentos personales de una persona natural, documentos tributarios, documentos utilizados durante procesos de verificación y demás información sensible no deberán hacerse visibles automáticamente para otros usuarios.

La existencia de diferentes sedes tampoco deberá implicar que toda la información general del prestador o toda la información particular de sus sedes sea automáticamente visible entre usuarios, propietarios, otras sedes o terceros.

Las reglas específicas relacionadas con privacidad, visibilidad de información, protección de datos, consulta de perfiles, acceso a documentación y visibilidad entre sedes serán definidas posteriormente en los apartados correspondientes.

#### Límites de esta definición

Este punto establece la información general necesaria para representar e identificar conceptualmente a un Prestador de Servicios Vehiculares dentro de Vehículos Services.

También establece que la información general del prestador deberá mantenerse diferenciada de la información particular correspondiente a sus sedes.

Todavía no se definen en detalle:

- La clasificación definitiva de tipos de Prestadores de Servicios Vehiculares.
- El catálogo de servicios que podrán ofrecer.
- Las especialidades.
- La estructura y comportamiento de las sedes.
- La información obligatoria y opcional de cada sede.
- La identificación de cada sede dentro de Vehículos Services.
- La existencia o definición de una sede principal.
- Los estados aplicables a las sedes.
- La verificación de las sedes.
- La relación entre tipos, especialidades, servicios y sedes.
- La asociación de usuarios a una o varias sedes.
- La visibilidad y acceso de información entre sedes de un mismo prestador.
- Los mecanismos específicos de verificación.
- Los documentos exigidos para cada proceso de verificación.
- Las reglas particulares por país.
- Los roles de los usuarios asociados al prestador.
- Los niveles de acceso.
- Los permisos.
- La relación entre Prestador de Servicios Vehiculares y vehículo.
- La relación entre Prestador de Servicios Vehiculares y propietario.
- Las reglas para registrar eventos en el historial del vehículo.
- La identificación de la sede en la que fue realizado o registrado un evento.
- Las reglas específicas para mantenimientos, diagnósticos, inspecciones, evaluaciones o peritajes.

Estos elementos deberán desarrollarse en los puntos correspondientes siguiendo el orden establecido para el levantamiento del proyecto.
---
### 63.3.3 Tipos y especialidades del Prestador de Servicios Vehiculares

Vehículos Services deberá permitir clasificar a los Prestadores de Servicios Vehiculares de acuerdo con la naturaleza de las actividades que realizan, manteniendo separados los conceptos de tipo de prestador, especialidad y servicio ofrecido.

Esta clasificación deberá permitir representar diferentes modelos de operación sin asumir que todos los Prestadores de Servicios Vehiculares corresponden a talleres mecánicos ni que todos realizan las mismas actividades.

Conceptualmente:

```text
PRESTADOR DE SERVICIOS VEHICULARES
        ↓
TIPOS DE PRESTADOR
        ↓
ESPECIALIDADES
        ↓
SERVICIOS OFRECIDOS
```

Por lo tanto:

```text
TIPO DE PRESTADOR
        ≠
ESPECIALIDAD
        ≠
SERVICIO OFRECIDO
```

Cada uno de estos conceptos deberá mantenerse separado dentro de Vehículos Services.

#### Tipos de Prestador de Servicios Vehiculares

El tipo de prestador permitirá identificar la naturaleza general de las actividades que desarrolla un Prestador de Servicios Vehiculares.

Un mismo Prestador de Servicios Vehiculares podrá estar clasificado simultáneamente en uno o varios tipos cuando su operación corresponda realmente a diferentes actividades.

No deberá asumirse que cada prestador puede pertenecer únicamente a un tipo.

Por ejemplo:

```text
PRESTADOR DE SERVICIOS VEHICULARES
ABC Motor Center
        ↓
TIPOS DE PRESTADOR
        ├── Taller mecánico
        ├── Centro de diagnóstico
        └── Centro de peritaje
```

En este caso, ABC Motor Center continúa siendo un único Prestador de Servicios Vehiculares, aunque pueda desarrollar actividades correspondientes a diferentes tipos de prestador.

Como referencia inicial, Vehículos Services podrá contemplar tipos como:

- Taller mecánico.
- Taller o establecimiento de mantenimiento preventivo.
- Taller o establecimiento de mantenimiento correctivo.
- Taller especializado.
- Centro de diagnóstico.
- Centro o establecimiento de peritaje vehicular.
- Centro de inspección o revisión vehicular.
- Prestador de servicios de electricidad automotriz.
- Establecimiento de latonería y pintura.
- Establecimiento de llantas, alineación y balanceo.
- Otros tipos de Prestadores de Servicios Vehiculares que posteriormente sean definidos.

Esta lista no deberá considerarse definitiva ni cerrada.

La clasificación deberá poder evolucionar a medida que Vehículos Services incorpore nuevos tipos de Prestadores de Servicios Vehiculares.

#### Catálogo controlado de tipos de prestador

Los tipos de Prestador de Servicios Vehiculares deberán administrarse mediante un catálogo controlado por Vehículos Services.

Un prestador podrá seleccionar uno o varios tipos existentes dentro del catálogo, de acuerdo con las actividades que realmente desarrolla.

El prestador no deberá poder crear libremente nuevos tipos mediante texto abierto.

Esta restricción busca evitar que una misma clasificación sea registrada de múltiples maneras.

Por ejemplo, sin un catálogo controlado podrían generarse clasificaciones como:

```text
Taller mecánico
Taller de mecánica
Mecánica automotriz
Servicio mecánico
Taller automotriz mecánico
```

Aunque conceptualmente podrían hacer referencia a una misma clasificación.

La utilización de un catálogo controlado deberá permitir mantener consistencia, evitar duplicidades y facilitar posteriormente búsquedas, filtros, reglas, permisos, reportes y demás funcionalidades relacionadas con los Prestadores de Servicios Vehiculares.

#### Solicitud de nuevos tipos de prestador

Cuando un Prestador de Servicios Vehiculares considere que ninguno de los tipos disponibles representa adecuadamente su actividad, podrá existir un mecanismo para solicitar la incorporación de un nuevo tipo.

Conceptualmente:

```text
PRESTADOR
        ↓
CONSULTA CATÁLOGO DE TIPOS
        ↓
¿EXISTE EL TIPO REQUERIDO?
        ↓
     SÍ / NO
      ↓    ↓
SELECCIONA  SOLICITA NUEVO TIPO
                ↓
        REVISIÓN / NORMALIZACIÓN
                ↓
             APROBACIÓN
                ↓
       INCORPORACIÓN AL CATÁLOGO
```

La solicitud realizada por un prestador no deberá crear automáticamente una nueva clasificación.

Antes de incorporar un nuevo tipo deberá existir un proceso de revisión que permita determinar, entre otros aspectos, si:

- El tipo solicitado ya existe con otra denominación.
- Corresponde realmente a un tipo de prestador.
- Corresponde en realidad a una especialidad.
- Corresponde en realidad a un servicio.
- Es necesario crear una nueva clasificación.

Los criterios de aprobación, responsables, estados y flujo definitivo serán definidos posteriormente.

#### Especialidades del Prestador de Servicios Vehiculares

Vehículos Services deberá permitir que un Prestador de Servicios Vehiculares registre una o varias especialidades.

La especialidad representa un área específica en la cual el prestador desarrolla conocimientos, experiencia o una orientación particular de sus actividades.

Un prestador podrá tener múltiples especialidades.

Por ejemplo:

```text
PRESTADOR
Taller Automotriz ABC
        │
        ├── TIPOS DE PRESTADOR
        │      ├── Taller mecánico
        │      └── Centro de diagnóstico
        │
        └── ESPECIALIDADES
               ├── Frenos
               ├── Suspensión
               └── Diagnóstico electrónico
```

Como referencia inicial, podrán existir especialidades relacionadas con:

- Frenos.
- Suspensión.
- Dirección.
- Motor.
- Transmisión.
- Electricidad automotriz.
- Electrónica automotriz.
- Diagnóstico.
- Aire acondicionado.
- Otras especialidades que posteriormente sean definidas.

Esta lista será únicamente una referencia inicial y no deberá considerarse definitiva.

#### Diferencia entre tipo de prestador y especialidad

El tipo de prestador describe qué clase de Prestador de Servicios Vehiculares es o qué naturaleza general tienen sus actividades.

La especialidad describe un área particular en la cual desarrolla dichas actividades.

Por ejemplo:

```text
PRESTADOR
Frenos Medellín
        ↓
TIPO DE PRESTADOR
Taller mecánico
        ↓
ESPECIALIDAD
Sistema de frenos
```

Otro ejemplo:

```text
PRESTADOR
AutoTech Integral
        ↓
TIPOS DE PRESTADOR
- Taller mecánico.
- Centro de diagnóstico.
- Prestador de electricidad automotriz.
        ↓
ESPECIALIDADES
- Electricidad automotriz.
- Sistemas electrónicos.
- Diagnóstico electrónico.
```

Una especialidad no deberá crear automáticamente un nuevo tipo de prestador.

De igual manera, pertenecer a determinado tipo de prestador no deberá significar automáticamente que el prestador sea especialista en todas las áreas relacionadas con dicho tipo.

#### Diferencia entre especialidad y servicio ofrecido

La especialidad tampoco deberá confundirse con los servicios concretos que realiza el prestador.

Por ejemplo:

```text
TIPO DE PRESTADOR
Taller mecánico
        ↓
ESPECIALIDAD
Sistema de frenos
        ↓
SERVICIOS OFRECIDOS
- Revisión del sistema de frenos.
- Cambio de pastillas de freno.
- Cambio de discos de freno.
- Cambio de líquido de frenos.
- Otros servicios relacionados.
```

En este ejemplo:

- Taller mecánico corresponde al tipo de prestador.
- Sistema de frenos corresponde a la especialidad.
- Cambio de pastillas de freno corresponde a un servicio específico.

Esta separación deberá mantenerse para evitar que tipos, especialidades y servicios terminen siendo utilizados como conceptos equivalentes dentro de la plataforma.

#### Catálogo controlado de especialidades

Las especialidades deberán administrarse mediante un catálogo controlado por Vehículos Services.

Un Prestador de Servicios Vehiculares podrá seleccionar una o varias especialidades existentes dentro del catálogo.

El prestador no deberá poder crear libremente especialidades mediante texto abierto.

Por ejemplo, sin un catálogo controlado podrían generarse registros como:

```text
Frenos
Especialista en frenos
Sistemas de frenos
Frenos automotrices
Servicio especializado de frenos
```

Aunque varios de estos registros podrían representar conceptualmente la misma especialidad.

El catálogo controlado deberá permitir mantener una clasificación consistente y reutilizable entre diferentes Prestadores de Servicios Vehiculares.

#### Solicitud de nuevas especialidades

Cuando la especialidad requerida no exista dentro del catálogo, el Prestador de Servicios Vehiculares podrá solicitar su incorporación.

Conceptualmente:

```text
PRESTADOR
        ↓
SELECCIONA ESPECIALIDADES
        ↓
CATÁLOGO CONTROLADO
        ↓
¿EXISTE LA ESPECIALIDAD?
        ↓
     SÍ / NO
      ↓    ↓
SELECCIONA  SOLICITA NUEVA ESPECIALIDAD
                ↓
        REVISIÓN / NORMALIZACIÓN
                ↓
             APROBACIÓN
                ↓
       INCORPORACIÓN AL CATÁLOGO
```

La solicitud no deberá crear automáticamente una nueva especialidad.

La nueva especialidad deberá pasar por un proceso de revisión que permita evitar duplicidades, denominaciones equivalentes, clasificaciones incorrectas o conceptos que correspondan realmente a servicios o tipos de prestador.

Los responsables, criterios, estados y flujo definitivo de aprobación serán definidos posteriormente.

#### Relación entre tipos y especialidades

Un Prestador de Servicios Vehiculares podrá tener múltiples tipos y múltiples especialidades.

No deberá establecerse inicialmente una relación rígida de uno a uno entre tipo de prestador y especialidad.

Conceptualmente:

```text
PRESTADOR
        ↓
MÚLTIPLES TIPOS
        ↓
MÚLTIPLES ESPECIALIDADES
```

Una misma especialidad podrá estar relacionada con diferentes tipos de prestador cuando funcionalmente corresponda.

Las reglas definitivas de relación entre tipos, especialidades y servicios serán desarrolladas posteriormente.

#### Tipos, especialidades y sedes

La clasificación general de un Prestador de Servicios Vehiculares deberá mantenerse diferenciada de las capacidades disponibles en cada una de sus sedes.

Cuando un prestador opere mediante varias sedes, no deberá asumirse automáticamente que todas ellas corresponden a los mismos tipos de operación, poseen las mismas especialidades o posteriormente ofrecen los mismos servicios.

Por ejemplo:

```text
PRESTADOR DE SERVICIOS VEHICULARES
ABC Motor Center
        │
        ├── CLASIFICACIÓN GENERAL DEL PRESTADOR
        │      ├── Taller mecánico
        │      ├── Centro de diagnóstico
        │      └── Centro de peritaje
        │
        ├── SEDE POBLADO
        │      ├── Taller mecánico
        │      ├── Centro de peritaje
        │      └── Especialidad: Frenos
        │
        └── SEDE ESTADIO
               ├── Centro de diagnóstico
               └── Especialidad: Diagnóstico electrónico
```

En este ejemplo, ABC Motor Center continúa siendo un único Prestador de Servicios Vehiculares, pero las capacidades disponibles en cada sede pueden ser diferentes.

Por lo tanto:

```text
TIPOS / ESPECIALIDADES DEL PRESTADOR
        ≠
TIPOS / ESPECIALIDADES DISPONIBLES
EN TODAS SUS SEDES
```

La existencia de una clasificación a nivel general del prestador no deberá utilizarse para asumir automáticamente que dicha capacidad se encuentra disponible en todas sus sedes.

De igual manera, cuando posteriormente se defina el catálogo de servicios, deberá contemplarse que los servicios efectivamente ofrecidos podrán variar entre las diferentes sedes de un mismo prestador.

La estructura de las sedes, su información, clasificación, relación con tipos, especialidades y servicios, así como las reglas para determinar qué capacidades se encuentran disponibles en cada sede, serán desarrolladas en el apartado correspondiente a las sedes del Prestador de Servicios Vehiculares.

#### Evolución de la clasificación del prestador

Los tipos y especialidades asociados a un Prestador de Servicios Vehiculares podrán cambiar a lo largo del tiempo.

Un prestador podrá incorporar nuevas actividades, dejar de ofrecer determinadas capacidades o modificar sus especialidades.

De igual manera, las capacidades disponibles en una sede podrán cambiar a lo largo del tiempo.

Estos cambios no deberán modificar, eliminar ni reinterpretar automáticamente los eventos históricos que ya hayan sido registrados sobre los vehículos.

Por ejemplo, si un prestador realizó un peritaje cuando una de sus sedes se encontraba habilitada para dicha actividad y posteriormente esa sede deja de realizar peritajes, el evento histórico deberá conservar el contexto correspondiente al momento en que fue realizado.

Las reglas específicas para conservar la clasificación histórica del prestador, la sede relacionada, los cambios realizados y su trazabilidad serán definidas posteriormente junto con las reglas del historial y auditoría.

#### Límites de esta definición

Este punto establece conceptualmente que:

- Un Prestador de Servicios Vehiculares podrá pertenecer a uno o varios tipos.
- Un Prestador de Servicios Vehiculares podrá tener una o varias especialidades.
- Los tipos de prestador deberán administrarse mediante un catálogo controlado.
- Las especialidades deberán administrarse mediante un catálogo controlado.
- Los prestadores no podrán crear libremente tipos o especialidades.
- Podrá existir un mecanismo para solicitar la incorporación de nuevos tipos.
- Podrá existir un mecanismo para solicitar la incorporación de nuevas especialidades.
- Una solicitud no deberá generar automáticamente una nueva clasificación.
- Tipo de prestador, especialidad y servicio ofrecido deberán mantenerse como conceptos separados.
- Un Prestador de Servicios Vehiculares podrá operar mediante una o varias sedes.
- No deberá asumirse que todas las sedes de un prestador tienen los mismos tipos, especialidades o servicios disponibles.
- La clasificación general del prestador deberá mantenerse diferenciada de las capacidades disponibles en cada sede.
- Los tipos y especialidades podrán evolucionar sin modificar automáticamente los eventos históricos ya registrados.

Todavía no se definen en detalle:

- El catálogo definitivo de tipos de Prestadores de Servicios Vehiculares.
- El catálogo definitivo de especialidades.
- El catálogo de servicios.
- Las relaciones definitivas entre tipos, especialidades y servicios.
- La estructura y comportamiento de las sedes.
- Las reglas para asociar tipos de prestador a cada sede.
- Las reglas para asociar especialidades a cada sede.
- Las reglas para asociar servicios a cada sede.
- Los criterios de aprobación de nuevos tipos.
- Los criterios de aprobación de nuevas especialidades.
- Los responsables de dichas aprobaciones.
- Los estados de las solicitudes.
- Los mecanismos para acreditar o verificar una especialidad.
- La visibilidad pública de tipos y especialidades.
- Los permisos derivados del tipo de prestador.
- Las capacidades funcionales habilitadas según el tipo de prestador.
- La relación entre Prestador de Servicios Vehiculares y vehículo.
- La relación entre Prestador de Servicios Vehiculares y propietario.
- Las reglas específicas para registrar eventos en el historial.
- La trazabilidad detallada de la sede que realizó cada evento.

Estos elementos serán desarrollados posteriormente en los puntos correspondientes.
---
### 63.3.4 Sedes del Prestador de Servicios Vehiculares

Vehículos Services deberá permitir que un Prestador de Servicios Vehiculares opere mediante una o múltiples sedes.

Una sede representa una ubicación física u operacional específica desde la cual un Prestador de Servicios Vehiculares desarrolla determinadas actividades o presta servicios relacionados con vehículos.

La existencia de varias sedes no deberá generar automáticamente diferentes Prestadores de Servicios Vehiculares.

Conceptualmente:

```text
PRESTADOR DE SERVICIOS VEHICULARES
        ↓
UNA O MÚLTIPLES SEDES
        ↓
ACTIVIDADES Y SERVICIOS
REALIZADOS DESDE CADA SEDE
```

Por ejemplo:

```text
PRESTADOR DE SERVICIOS VEHICULARES
SURA
        │
        ├── Sede Poblado
        ├── Sede Estadio
        └── Sede Rionegro
```

En este ejemplo:

```text
SURA
= 1 Prestador de Servicios Vehiculares

Sede Poblado
= 1 sede de SURA

Sede Estadio
= 1 sede de SURA

Sede Rionegro
= 1 sede de SURA
```

Por lo tanto, las sedes deberán mantenerse conceptualmente diferenciadas del Prestador de Servicios Vehiculares al cual pertenecen.

#### Prestadores con una única sede

El concepto de sede no deberá limitarse a organizaciones que posean múltiples establecimientos.

Un Prestador de Servicios Vehiculares podrá operar mediante una única sede.

Por ejemplo:

```text
PRESTADOR
Taller Mecánico Santiago
        ↓
ÚNICA SEDE
Sede Medellín
```

Esto permitirá mantener una estructura consistente independientemente del tamaño o modelo de operación del prestador.

Por lo tanto:

```text
PRESTADOR
        ↓
1..N SEDES
```

Un prestador deberá contar con al menos una sede para representar el lugar o unidad operacional desde la cual presta sus servicios dentro de Vehículos Services.

---

#### Identificación única de la sede

Cada sede deberá contar con un identificador único propio dentro de Vehículos Services.

Este identificador deberá permitir distinguir inequívocamente una sede de cualquier otra, incluso cuando existan sedes con:

- Nombres similares.
- La misma ciudad.
- Direcciones similares.
- Nombres comerciales equivalentes.
- Información de contacto compartida.
- Otros datos coincidentes.

Conceptualmente:

```text
PRESTADOR
SURA
ID Prestador: PRESTADOR-001
        │
        ├── Sede Poblado
        │   ID Sede: SEDE-001
        │
        └── Sede Estadio
            ID Sede: SEDE-002
```

Los identificadores utilizados en el ejemplo son únicamente ilustrativos. Su estructura técnica definitiva será establecida posteriormente.

El identificador de la sede no deberá depender de su nombre, teléfono, correo, horario u otros datos que puedan cambiar durante su operación.

El identificador único tampoco deberá poder ser modificado libremente por el Prestador de Servicios Vehiculares.

Su finalidad será preservar de forma inequívoca la identidad y trazabilidad de la sede dentro de Vehículos Services.

Por lo tanto:

```text
IDENTIFICADOR DE SEDE
        ≠
NOMBRE DE SEDE
        ≠
DIRECCIÓN
        ≠
DATOS DE CONTACTO
```

---

#### Relación entre Prestador de Servicios Vehiculares y sede

Toda sede deberá encontrarse asociada a un Prestador de Servicios Vehiculares.

Una sede no deberá existir de manera independiente dentro del modelo funcional de Vehículos Services sin conocer a qué prestador pertenece.

Conceptualmente:

```text
PRESTADOR
        ↓
SEDE
```

La relación será:

```text
UN PRESTADOR
        ↓
PUEDE TENER
UNA O MÚLTIPLES SEDES

UNA SEDE
        ↓
PERTENECE A
UN PRESTADOR
```

Una misma sede no deberá pertenecer simultáneamente a diferentes Prestadores de Servicios Vehiculares.

La relación de pertenencia entre una sede y su prestador deberá considerarse información estructural de la sede y no deberá poder ser modificada libremente como si se tratara de información operativa.

Por ejemplo, no deberá permitirse que una sede que históricamente pertenece al Prestador A sea modificada directamente para aparecer posteriormente como perteneciente al Prestador B conservando el mismo identificador y sus relaciones históricas.

Conceptualmente:

```text
SEDE-001
        ↓
PERTENECE A
PRESTADOR A

NO DEBERÁ PODER CONVERTIRSE LIBREMENTE EN:

SEDE-001
        ↓
PERTENECE A
PRESTADOR B
```

Esto evitará que eventos históricos asociados a una sede puedan aparentar haber sido realizados por un prestador diferente.

El hecho de que dos prestadores operen físicamente en una misma dirección tampoco deberá convertirlos en una misma sede.

Por ejemplo:

```text
MISMA DIRECCIÓN FÍSICA
Calle XX # YY-ZZ
        │
        ├── PRESTADOR A
        │      └── Sede Poblado
        │
        └── PRESTADOR B
               └── Sede Poblado
```

Aunque ambos se encuentren físicamente en la misma ubicación, corresponden a sedes diferentes porque pertenecen a Prestadores de Servicios Vehiculares diferentes.

---

#### Información de la sede

Cada sede deberá contar con información propia que permita identificarla, localizarla y diferenciarla de las demás sedes pertenecientes al mismo prestador.

Deberá contemplarse información como:

- Identificador único de la sede dentro de Vehículos Services.
- Nombre o denominación de la sede.
- País.
- Ciudad, municipio o localidad que corresponda.
- Dirección física.
- Información de contacto propia, cuando aplique.
- Teléfono de contacto, cuando aplique.
- Correo electrónico de contacto, cuando aplique.
- Horarios de atención, cuando aplique.
- Estado de la sede.

Podrá contemplarse posteriormente información complementaria como referencias de ubicación u otros datos necesarios para identificar, localizar o contactar correctamente la sede.

La información particular de una sede deberá mantenerse separada de la información general del Prestador de Servicios Vehiculares.

Por lo tanto:

```text
INFORMACIÓN GENERAL DEL PRESTADOR
        ≠
INFORMACIÓN PARTICULAR DE LA SEDE
```

Por ejemplo:

```text
PRESTADOR
SURA
        │
        ├── Información general del prestador
        │
        ├── SEDE POBLADO
        │      ├── Dirección propia
        │      ├── Teléfono propio
        │      └── Horario propio
        │
        └── SEDE ESTADIO
               ├── Dirección propia
               ├── Teléfono propio
               └── Horario propio
```

No deberá asumirse que todas las sedes comparten automáticamente la misma dirección, teléfono, correo, horario u otra información operacional.

---

#### Diferenciación entre información operativa e información estructural o sensible

No toda la información de una sede deberá tener el mismo nivel de modificación.

Vehículos Services deberá diferenciar conceptualmente entre:

```text
INFORMACIÓN OPERATIVA
        ≠
INFORMACIÓN ESTRUCTURAL O SENSIBLE
```

##### Información operativa

Corresponde a información que puede cambiar como parte de la operación normal de una sede sin que dicho cambio implique necesariamente una modificación de su identidad.

Como referencia inicial, podrá incluir:

- Teléfono de contacto.
- Correo electrónico de contacto.
- Horarios de atención.
- Otros datos operativos que posteriormente sean autorizados.

Los usuarios autorizados del Prestador de Servicios Vehiculares podrán administrar este tipo de información de acuerdo con los roles y permisos que posteriormente sean definidos.

Por ejemplo:

```text
SEDE POBLADO

Teléfono anterior:
604 XXX XXXX

        ↓

Teléfono nuevo:
604 YYY YYYY
```

Este cambio no deberá implicar la creación de una nueva sede ni modificar su identidad.

De igual manera:

```text
Horario anterior:
08:00 - 17:00

        ↓

Horario nuevo:
07:00 - 18:00
```

corresponde a un cambio operacional y no a una nueva sede.

##### Información estructural o sensible

Corresponde a información cuya modificación puede afectar la identidad, autenticidad, pertenencia o trazabilidad de la sede.

Como referencia conceptual inicial, deberá considerarse dentro de esta categoría:

- Identificador único de la sede.
- Prestador de Servicios Vehiculares al cual pertenece.
- Dirección física de la sede.
- Información utilizada para identificar o verificar formalmente la sede.
- Otros datos que posteriormente sean clasificados como sensibles para su identidad o trazabilidad.

Esta información no deberá poder ser modificada libremente mediante la administración ordinaria de una sede.

Conceptualmente:

```text
DATOS OPERATIVOS
        ↓
MODIFICACIÓN AUTORIZADA
SEGÚN ROL Y PERMISOS

DATOS ESTRUCTURALES / SENSIBLES
        ↓
NO MODIFICACIÓN LIBRE
        ↓
PROCESO CONTROLADO
```

El mecanismo mediante el cual podrán solicitarse, validar, aprobar, rechazar o registrar cambios sobre información estructural o sensible será definido posteriormente.

---

#### Nombre del prestador y nombre de la sede

Deberá mantenerse una separación clara entre el nombre del Prestador de Servicios Vehiculares y el nombre o denominación utilizada para identificar una sede.

Por ejemplo:

```text
PRESTADOR
SURA

        ↓

SEDES
├── Sede Poblado
├── Sede Estadio
└── Sede Rionegro
```

El nombre del Prestador de Servicios Vehiculares no deberá considerarse un dato editable desde la administración normal de una sede.

Por lo tanto:

```text
NOMBRE DEL PRESTADOR
        ≠
NOMBRE DE LA SEDE
```

Un usuario que tenga permisos para administrar determinada sede no deberá, por ese solo hecho, tener autorización para modificar la identidad general del Prestador de Servicios Vehiculares.

El tratamiento definitivo de cambios relacionados con el nombre, razón social, nombre comercial u otros elementos de identificación del prestador deberá regirse por las reglas correspondientes a la información general y verificación del Prestador de Servicios Vehiculares.

---

#### Nombre o denominación de la sede

Cada sede deberá contar con una denominación que permita reconocerla y diferenciarla dentro del prestador.

Por ejemplo:

```text
PRESTADOR
SURA
        │
        ├── Sede Poblado
        ├── Sede Estadio
        └── Sede Rionegro
```

El nombre o denominación de la sede tendrá una función descriptiva y de identificación para los usuarios, pero no constituirá su identificador único dentro de Vehículos Services.

Por lo tanto:

```text
NOMBRE DE LA SEDE
        ≠
IDENTIFICADOR ÚNICO DE LA SEDE
```

La posibilidad de modificar el nombre o denominación de una sede, las condiciones para hacerlo y la trazabilidad que deberá conservarse sobre dicho cambio serán definidas posteriormente.

Hasta que dichas reglas sean establecidas, no deberá asumirse que el Prestador de Servicios Vehiculares puede modificar libremente el nombre de una sede.

---

#### Dirección física de la sede

La dirección física deberá considerarse un elemento relevante para la identificación y trazabilidad de una sede.

Por esta razón, no deberá tratarse como un dato operativo ordinario equivalente a un teléfono, correo electrónico u horario.

Conceptualmente:

```text
TELÉFONO / CORREO / HORARIO
        ↓
DATOS OPERATIVOS

DIRECCIÓN FÍSICA
        ↓
DATO ESTRUCTURAL O SENSIBLE
```

El Prestador de Servicios Vehiculares no deberá poder sustituir libremente la dirección física de una sede cuando esta ya se encuentre identificada dentro de Vehículos Services.

Esto permitirá evitar situaciones en las cuales una sede con eventos históricos registrados pueda ser transformada artificialmente en otra ubicación manteniendo el mismo identificador y aparentando que los eventos anteriores ocurrieron en la nueva dirección.

Por ejemplo:

```text
SEDE-001
Sede Poblado

Dirección:
Calle 10 # 30-20

Historial:
500 eventos realizados
```

No deberá permitirse una modificación libre que produzca simplemente:

```text
SEDE-001
Sede Poblado

Nueva dirección:
Carrera 80 # 40-10

Historial:
Los mismos 500 eventos
```

sin determinar previamente qué ocurrió realmente con la sede.

Un cambio legítimo de ubicación puede corresponder, por ejemplo, a:

- Un traslado de la misma sede.
- El cierre de una sede y apertura de otra.
- Una reorganización operacional.
- Otra situación que posteriormente sea definida.

Vehículos Services deberá diferenciar estas situaciones mediante reglas específicas antes de permitir que un cambio de dirección afecte la información estructural de una sede.

Por lo tanto:

```text
CAMBIO DE DIRECCIÓN
        ≠
ACTUALIZACIÓN OPERATIVA SIMPLE
```

Las reglas para determinar cuándo existe un traslado de la misma sede y cuándo debe considerarse una nueva sede serán definidas posteriormente.

---

#### Protección de la identidad y trazabilidad de la sede

Las restricciones sobre información estructural o sensible deberán evitar que la modificación de datos actuales altere indirectamente el significado de registros históricos.

Por ejemplo, si:

```text
SEDE-001
Prestador: SURA
Sede: Poblado
Dirección: XXX
```

realizó históricamente diferentes mantenimientos y peritajes, no deberá ser posible transformar libremente esa misma identidad en:

```text
SEDE-001
Prestador: Empresa XYZ
Sede: Laureles
Dirección: YYY
```

conservando todos los eventos anteriores como si hubieran sido realizados por la nueva identidad.

Conceptualmente:

```text
IDENTIDAD ACTUAL DE LA SEDE
        ↓
NO DEBE PODER REINTERPRETAR
        ↓
LOS EVENTOS HISTÓRICOS
```

La plataforma deberá proteger la relación histórica existente entre:

```text
EVENTO
   ↓
PRESTADOR QUE PARTICIPÓ
   ↓
SEDE QUE PARTICIPÓ
```

Las reglas técnicas y funcionales específicas de auditoría, versionamiento, corrección o conservación de valores históricos serán desarrolladas posteriormente.

---

#### Tipos, especialidades y servicios disponibles por sede

Las sedes de un mismo Prestador de Servicios Vehiculares podrán tener diferentes capacidades operacionales.

No deberá asumirse que todas las sedes pertenecientes al mismo prestador realizan los mismos tipos de actividades, poseen las mismas especialidades o ofrecen los mismos servicios.

Por ejemplo:

```text
PRESTADOR
SURA
        │
        ├── SEDE POBLADO
        │      ├── Taller mecánico
        │      ├── Centro de peritaje
        │      ├── Especialidad: Frenos
        │      └── Servicios relacionados
        │
        └── SEDE ESTADIO
               ├── Centro de diagnóstico
               ├── Centro de peritaje
               ├── Especialidad: Diagnóstico
               └── Servicios relacionados
```

Por lo tanto:

```text
CAPACIDADES GENERALES DEL PRESTADOR
        ≠
CAPACIDADES DISPONIBLES
EN CADA SEDE
```

Una clasificación existente a nivel general del prestador no deberá significar automáticamente que dicha capacidad se encuentra disponible en todas sus sedes.

Las relaciones definitivas entre tipos de prestador, especialidades, servicios y sedes serán desarrolladas posteriormente junto con los catálogos y reglas funcionales correspondientes.

---

#### Sede asociada a un evento del vehículo

Cuando un servicio, procedimiento, diagnóstico, mantenimiento, inspección, evaluación, peritaje u otro evento sea realizado desde una sede determinada, Vehículos Services deberá conservar tanto la identificación del Prestador de Servicios Vehiculares como la identificación de la sede relacionada con dicho evento.

Conceptualmente:

```text
EVENTO DEL VEHÍCULO
        ↓
PRESTADOR
        ↓
SEDE
```

Por ejemplo:

```text
VEHÍCULO
        ↓
MANTENIMIENTO
Cambio de frenos
        ↓
PRESTADOR
SURA
        ↓
SEDE
Sede Poblado
```

Esto permitirá diferenciar:

```text
¿QUIÉN REALIZÓ EL EVENTO?
        ↓
PRESTADOR

¿DÓNDE / DESDE QUÉ SEDE?
        ↓
SEDE
```

La sede deberá formar parte del contexto histórico del evento cuando corresponda.

Los cambios posteriores sobre la información actual de una sede no deberán modificar automáticamente el contexto histórico de los eventos previamente registrados.

Esto deberá aplicar incluso cuando posteriormente:

- La sede cambie información operativa.
- La sede deje de prestar determinado servicio.
- La sede cambie sus especialidades.
- La sede deje de operar.
- Se produzca un cambio estructural autorizado sobre la sede.

Las reglas específicas sobre qué información deberá conservarse exactamente como contexto histórico del evento serán desarrolladas posteriormente dentro de la definición del historial y auditoría.

---

#### Consulta de antecedentes realizados en otras sedes del mismo prestador

La existencia de múltiples sedes deberá permitir que Vehículos Services identifique que diferentes eventos fueron realizados por el mismo Prestador de Servicios Vehiculares, aunque hayan ocurrido en sedes diferentes.

Por ejemplo:

```text
PRIMER EVENTO

VEHÍCULO
        ↓
SURA
        ↓
SEDE POBLADO
        ↓
Cambio de frenos
        ↓
HISTORIAL DEL VEHÍCULO
```

Posteriormente:

```text
SEGUNDO EVENTO

VEHÍCULO
        ↓
SURA
        ↓
SEDE ESTADIO
        ↓
Consulta de antecedentes autorizados
```

Cuando las reglas de acceso correspondientes lo permitan, podrá identificarse que el evento anterior fue realizado por:

```text
Prestador: SURA
Sede: Poblado
```

De esta manera, el historial no deberá fragmentarse como si cada sede correspondiera necesariamente a un prestador diferente.

Sin embargo, pertenecer al mismo Prestador de Servicios Vehiculares no deberá otorgar automáticamente a todos los usuarios de todas sus sedes acceso irrestricto a toda la información.

El acceso a información entre sedes dependerá posteriormente de:

- Los usuarios asociados al prestador.
- La sede o sedes a las que se encuentre asociado cada usuario.
- Los roles.
- Los permisos.
- Las autorizaciones existentes sobre el vehículo.
- Las reglas de privacidad y visibilidad.
- Las demás condiciones funcionales que posteriormente sean definidas.

Por lo tanto:

```text
MISMO PRESTADOR
        ≠
ACCESO AUTOMÁTICO E IRRESTRICTO
ENTRE TODAS SUS SEDES
```

Las reglas específicas de consulta entre sedes serán definidas posteriormente en los apartados de relaciones, historial, usuarios, permisos y seguridad.

---

#### Escenario de mantenimiento entre diferentes sedes

Como ejemplo funcional, podrá presentarse el siguiente escenario:

Santiago lleva su vehículo a SURA, sede Poblado, para realizar un mantenimiento relacionado con el sistema de frenos.

Durante el servicio podrán registrarse posteriormente datos como:

- Fecha del mantenimiento.
- Kilometraje del vehículo.
- Servicio realizado.
- Repuestos instalados.
- Características de las pastillas de freno instaladas.
- Otros componentes intervenidos.
- Observaciones.
- Documentos o evidencias que correspondan.
- Prestador que realizó el servicio.
- Sede donde fue realizado.

Conceptualmente:

```text
VEHÍCULO
        ↓
SURA
        ↓
SEDE POBLADO
        ↓
CAMBIO DE FRENOS
        ↓
REGISTRO DEL EVENTO
        ↓
HISTORIAL DEL VEHÍCULO
```

Un año después, Santiago podrá llevar el mismo vehículo a SURA, sede Estadio.

Si los permisos y autorizaciones correspondientes permiten consultar el antecedente, un usuario autorizado podrá identificar que el mantenimiento anterior fue realizado por el mismo prestador en otra sede y consultar la información histórica disponible para dicho evento.

Conceptualmente:

```text
SURA
SEDE ESTADIO
        ↓
VEHÍCULO AUTORIZADO
        ↓
CONSULTA HISTORIAL
        ↓
MANTENIMIENTO ANTERIOR
        ↓
Prestador: SURA
Sede: Poblado
Kilometraje: ...
Servicio: Cambio de frenos
Repuestos: ...
Fecha: ...
Información relacionada: ...
```

La información del mantenimiento deberá permanecer asociada al historial del vehículo y no deberá considerarse propiedad exclusiva de la sede que realizó el servicio.

---

#### Escenario de peritaje entre diferentes sedes

El mismo principio deberá aplicar a otros tipos de eventos, como los peritajes.

Por ejemplo:

```text
PRIMER PERITAJE

VEHÍCULO
        ↓
SURA
        ↓
SEDE POBLADO
        ↓
PERITAJE
        ↓
Resultado
Observaciones
Documentos
Evidencias
Kilometraje
Fecha
        ↓
HISTORIAL DEL VEHÍCULO
```

Posteriormente podrá realizarse un nuevo peritaje:

```text
SEGUNDO PERITAJE

VEHÍCULO
        ↓
SURA
        ↓
SEDE ESTADIO
        ↓
NUEVO PERITAJE
```

Cuando las reglas de acceso y autorización lo permitan, la sede Estadio podrá consultar la información histórica disponible correspondiente al peritaje realizado previamente en la sede Poblado.

El nuevo peritaje deberá constituir un nuevo evento y no deberá sobrescribir ni reemplazar el peritaje anterior.

Conceptualmente:

```text
HISTORIAL DEL VEHÍCULO
        │
        ├── PERITAJE 1
        │      ├── Prestador: SURA
        │      └── Sede: Poblado
        │
        └── PERITAJE 2
               ├── Prestador: SURA
               └── Sede: Estadio
```

Esto permitirá conservar la evolución histórica del vehículo y conocer qué prestador y qué sede participaron en cada procedimiento.

---

#### Estado de una sede

Una sede podrá cambiar su condición operacional a lo largo del tiempo.

Como referencia conceptual inicial, deberá poder distinguirse como mínimo entre una sede que se encuentra operativa y una sede que ya no se encuentra operativa.

La nomenclatura y catálogo definitivo de estados será definido posteriormente.

Una sede que deje de operar no deberá eliminarse cuando posea relaciones históricas con vehículos.

Por ejemplo:

```text
SURA
        │
        ├── Sede Poblado
        │   Estado actual: No operativa
        │
        └── Sede Estadio
            Estado actual: Operativa
```

Si la sede Poblado realizó anteriormente mantenimientos, diagnósticos, peritajes u otros eventos, dichos registros deberán continuar indicando que fueron realizados en esa sede.

Por lo tanto:

```text
SEDE DEJA DE OPERAR
        ≠
ELIMINACIÓN DE SU HISTORIAL
```

La sede podrá dejar de estar disponible para nuevas operaciones sin que esto implique eliminar o modificar los eventos históricos relacionados con ella.

Las reglas definitivas de estados, cierre, reactivación, suspensión u otras condiciones operacionales serán desarrolladas posteriormente.

---

#### Modificación de información de una sede

La información actual de una sede podrá requerir cambios a lo largo del tiempo, pero estos cambios deberán tratarse de acuerdo con la naturaleza del dato afectado.

Por ejemplo:

```text
CAMBIO DE TELÉFONO
        ↓
CAMBIO OPERATIVO

CAMBIO DE HORARIO
        ↓
CAMBIO OPERATIVO

CAMBIO DE DIRECCIÓN
        ↓
CAMBIO ESTRUCTURAL / SENSIBLE

CAMBIO DE PRESTADOR ASOCIADO
        ↓
CAMBIO ESTRUCTURAL / SENSIBLE

CAMBIO DE IDENTIFICADOR
        ↓
NO DEBERÁ SER UNA MODIFICACIÓN
ORDINARIA DEL PRESTADOR
```

Los cambios operativos podrán ser realizados por usuarios autorizados según los roles y permisos que posteriormente sean definidos.

Los cambios estructurales o sensibles deberán requerir un tratamiento controlado y no podrán realizarse como una edición ordinaria de información.

Vehículos Services deberá posteriormente definir:

- Qué información puede modificarse directamente.
- Qué información requiere validación.
- Qué información no puede modificarse.
- Quién puede solicitar un cambio estructural.
- Quién puede aprobarlo.
- Qué evidencias pueden requerirse.
- Cómo se conserva la trazabilidad del cambio.
- Cómo se protege el historial relacionado con la sede.

---

#### Usuarios asociados a sedes

Vehículos Services deberá contemplar posteriormente que los usuarios que representan a un Prestador de Servicios Vehiculares puedan estar relacionados con una o varias de sus sedes.

Conceptualmente:

```text
PRESTADOR
SURA
        │
        ├── SEDE POBLADO
        │      └── Usuarios autorizados
        │
        └── SEDE ESTADIO
               └── Usuarios autorizados
```

No deberá asumirse que todo usuario perteneciente al prestador pertenece automáticamente a todas sus sedes.

Tampoco deberá asumirse que todos los usuarios de una sede poseen los mismos permisos.

Las reglas relacionadas con:

- Usuarios del prestador.
- Asociación usuario ↔ sede.
- Usuarios asociados a múltiples sedes.
- Roles.
- Permisos.
- Acceso a vehículos.
- Consulta de información entre sedes.
- Registro de eventos.
- Administración de información operativa de la sede.
- Solicitud de cambios sobre información estructural o sensible.
- Administración de sedes.

serán definidas posteriormente en los apartados correspondientes.

---

#### Permanencia histórica de la sede

La sede deberá conservarse como referencia histórica cuando haya participado en eventos relacionados con vehículos.

Una sede no deberá desaparecer del historial simplemente porque:

- Dejó de operar.
- Fue desactivada.
- Cambió información operativa.
- Dejó de prestar determinado servicio.
- El prestador abrió nuevas sedes.
- Los usuarios que trabajaban en ella dejaron de tener acceso.
- El vehículo cambió de propietario.
- El prestador dejó posteriormente de tener relación con el vehículo.

Conceptualmente:

```text
EVENTO HISTÓRICO
        ↓
PRESTADOR
        ↓
SEDE QUE PARTICIPÓ
        ↓
REFERENCIA HISTÓRICA PERMANENTE
```

Los cambios actuales realizados sobre una sede no deberán utilizarse para reinterpretar automáticamente las condiciones bajo las cuales ocurrió un evento histórico.

Las reglas específicas de inmutabilidad, corrección, anulación, auditoría, versionamiento y conservación de información histórica serán definidas posteriormente dentro del apartado correspondiente al historial.

---

#### Límites de esta definición

Este punto establece conceptualmente que:

- Un Prestador de Servicios Vehiculares podrá tener una o múltiples sedes.
- Un prestador con una única ubicación también será representado mediante una sede.
- Cada sede deberá contar con un identificador único dentro de Vehículos Services.
- El identificador de una sede no dependerá de su nombre, dirección o información de contacto.
- Cada sede pertenecerá a un Prestador de Servicios Vehiculares.
- Una misma sede no pertenecerá simultáneamente a varios prestadores.
- La pertenencia de una sede a un prestador no será un dato de modificación libre.
- Dos prestadores podrán operar físicamente en una misma dirección sin convertirse en una misma sede.
- Cada sede contará con información propia.
- La información de la sede deberá mantenerse separada de la información general del prestador.
- El nombre del prestador y la denominación de la sede corresponden a conceptos diferentes.
- No deberá asumirse que un usuario autorizado para administrar una sede puede modificar la identidad general del prestador.
- La información de una sede deberá diferenciarse entre información operativa e información estructural o sensible.
- Datos operativos como teléfono, correo u horarios podrán ser administrados posteriormente por usuarios autorizados de acuerdo con sus permisos.
- Datos estructurales o sensibles no deberán poder modificarse libremente.
- La dirección física deberá tratarse como información estructural o sensible y no como una actualización operativa ordinaria.
- Un cambio de dirección deberá pasar por reglas controladas que permitan determinar si corresponde a un traslado de la misma sede o a la creación de una nueva sede.
- Las sedes de un mismo prestador podrán tener diferentes capacidades, tipos, especialidades y servicios disponibles.
- Los eventos realizados desde una sede deberán conservar la identificación del prestador y de la sede correspondiente.
- Diferentes sedes de un mismo prestador no deberán fragmentar artificialmente la identidad del prestador.
- Pertenecer al mismo prestador no otorgará automáticamente acceso irrestricto entre todas sus sedes.
- Una sede que deje de operar no deberá perder sus relaciones históricas.
- Las modificaciones actuales de una sede no deberán reinterpretar automáticamente los eventos históricos previamente registrados.
- La sede deberá permanecer identificable dentro del historial cuando haya participado en eventos relacionados con vehículos.

Todavía no se definen en detalle:

- El formato técnico del identificador de sede.
- El catálogo definitivo de estados de una sede.
- Las reglas de creación de sedes.
- Las reglas definitivas para modificar información operativa.
- El listado definitivo de datos estructurales o sensibles.
- El proceso para solicitar cambios estructurales.
- Los responsables de validar o aprobar dichos cambios.
- Las evidencias requeridas para cambios estructurales.
- Las reglas de cierre, suspensión o reactivación de sedes.
- Las reglas para traslado físico de una sede.
- Los criterios para determinar cuándo un traslado conserva la misma sede.
- Los criterios para determinar cuándo debe crearse una nueva sede.
- Las reglas definitivas para modificar el nombre o denominación de una sede.
- La existencia y comportamiento de una sede principal.
- Los mecanismos de verificación de una sede.
- Los documentos requeridos para verificar una sede.
- Las reglas particulares según país.
- Las relaciones definitivas entre tipos, especialidades, servicios y sedes.
- El catálogo definitivo de servicios.
- La asociación definitiva entre usuarios y sedes.
- Los roles y permisos dentro de cada sede.
- El acceso a información entre diferentes sedes.
- Las autorizaciones requeridas para consultar el historial de un vehículo.
- Las reglas específicas para registrar mantenimientos, diagnósticos, inspecciones, evaluaciones o peritajes.
- La estructura definitiva de los eventos del historial.
- Las reglas de auditoría, versionamiento y conservación histórica.

Estos elementos deberán desarrollarse posteriormente en los puntos correspondientes siguiendo el orden establecido para el levantamiento del proyecto.
---
### 63.3.5 Ciclo de vida, operación y estado del Prestador de Servicios Vehiculares

Vehículos Services deberá permitir representar el ciclo de vida de un Prestador de Servicios Vehiculares desde su incorporación a la plataforma, diferenciando conceptualmente su registro, verificación, capacidad de operación y estado dentro de la plataforma.

La existencia de un Prestador de Servicios Vehiculares dentro de Vehículos Services no deberá depender exclusivamente de que haya completado previamente un proceso de verificación.

Conceptualmente:

```text
PRESTADOR DE SERVICIOS VEHICULARES
        ↓
REGISTRO EN LA PLATAFORMA
        ↓
EXISTENCIA DEL PRESTADOR
DENTRO DE VEHÍCULOS SERVICES
        ↓
POSIBILIDAD DE OPERAR
BAJO LAS REGLAS DEFINIDAS
        ↓
VERIFICACIÓN
        ↓
MAYOR NIVEL DE VALIDACIÓN
SOBRE DETERMINADA INFORMACIÓN
```

Por lo tanto:

```text
PRESTADOR REGISTRADO
        ≠
PRESTADOR VERIFICADO
        ≠
PRESTADOR BLOQUEADO
```

Un Prestador de Servicios Vehiculares podrá comenzar a operar dentro de Vehículos Services sin que necesariamente haya completado previamente todos los procesos de verificación que posteriormente sean establecidos.

Esta definición busca permitir la participación de diferentes modelos de Prestadores de Servicios Vehiculares, incluyendo personas naturales, talleres independientes, pequeños establecimientos, empresas, organizaciones y demás prestadores que puedan ofrecer servicios relacionados con vehículos.

La ausencia de una verificación completa no deberá interpretarse automáticamente como la imposibilidad de utilizar la plataforma.

Sin embargo, la posibilidad de operar sin estar verificado tampoco deberá interpretarse como autorización irrestricta para ejecutar cualquier acción dentro de Vehículos Services.

---

#### Registro del Prestador de Servicios Vehiculares

El registro permitirá incorporar un Prestador de Servicios Vehiculares dentro de Vehículos Services.

Como resultado del registro, el prestador deberá adquirir una identidad propia dentro de la plataforma que permita diferenciarlo de otros prestadores y conservar posteriormente sus relaciones, sedes, usuarios, actividades y referencias históricas.

Conceptualmente:

```text
PRESTADOR
        ↓
REGISTRO
        ↓
IDENTIDAD DENTRO DE
VEHÍCULOS SERVICES
```

El registro no deberá significar automáticamente que Vehículos Services haya comprobado, certificado o validado toda la información declarada por el prestador.

Por lo tanto:

```text
REGISTRADO
        ≠
VERIFICADO
```

La información necesaria para registrar un prestador deberá mantenerse alineada con la naturaleza del prestador definida anteriormente, permitiendo representar tanto personas naturales como personas jurídicas.

Los datos obligatorios, mecanismos de registro, validaciones iniciales, documentos requeridos y demás condiciones específicas serán definidos posteriormente.

---

#### Operación de un Prestador no verificado

Un Prestador de Servicios Vehiculares registrado podrá comenzar a utilizar Vehículos Services aunque todavía no haya completado un proceso de verificación.

Conceptualmente:

```text
PRESTADOR REGISTRADO
        ↓
NO VERIFICADO
        ↓
PUEDE COMENZAR A OPERAR
        ↓
SUJETO A REGLAS,
AUTORIZACIONES,
PERMISOS Y CONTROLES
```

Dependiendo del tipo de prestador, de los servicios que realice y de las reglas que posteriormente sean definidas, un prestador no verificado podrá llegar a realizar actividades dentro de la plataforma tales como:

- Registrar información correspondiente a su operación.
- Administrar la información que posteriormente sea definida como modificable.
- Registrar y administrar sus sedes, de acuerdo con las reglas correspondientes.
- Registrar los tipos, especialidades y servicios que declara ofrecer, sujeto a las reglas que posteriormente sean establecidas.
- Relacionarse con vehículos cuando exista la autorización o condición necesaria para hacerlo.
- Registrar mantenimientos cuando corresponda.
- Registrar reparaciones cuando corresponda.
- Registrar repuestos utilizados cuando corresponda.
- Registrar diagnósticos cuando corresponda.
- Registrar inspecciones o evaluaciones cuando corresponda.
- Registrar peritajes cuando corresponda.
- Registrar kilometrajes asociados a los servicios o eventos realizados cuando corresponda.
- Registrar costos asociados a los servicios realizados cuando aplique.
- Adjuntar documentos, facturas, fotografías u otras evidencias relacionadas con los servicios o eventos realizados cuando corresponda.

Esta enumeración es conceptual y no establece todavía que todas estas funcionalidades estarán disponibles de manera irrestricta para cualquier prestador no verificado.

La disponibilidad definitiva de cada funcionalidad dependerá de las reglas de negocio, relaciones, autorizaciones, roles, permisos, nivel de verificación, tipo de prestador, tipo de servicio y controles de seguridad que posteriormente sean definidos.

---

#### Verificación y capacidad de operación

La verificación no deberá considerarse equivalente a la capacidad general de operar dentro de Vehículos Services.

Conceptualmente:

```text
REGISTRO
        ↓
PERMITE EXISTIR EN LA PLATAFORMA

OPERACIÓN
        ↓
PERMITE REALIZAR ACCIONES
SEGÚN REGLAS Y AUTORIZACIONES

VERIFICACIÓN
        ↓
PERMITE CONFIRMAR
DETERMINADA INFORMACIÓN
DEL PRESTADOR
```

Por lo tanto:

```text
REGISTRO
        ≠
VERIFICACIÓN
        ≠
PERMISOS
        ≠
AUTORIZACIÓN SOBRE UN VEHÍCULO
```

Un prestador podrá encontrarse registrado y no verificado y, aun así, disponer de determinadas capacidades operativas.

De igual manera, que un prestador se encuentre verificado no deberá significar automáticamente que pueda ejecutar cualquier acción sobre cualquier vehículo.

La verificación del prestador no reemplazará las reglas relacionadas con:

- La relación Prestador de Servicios Vehiculares ↔ Vehículo.
- La autorización para consultar información de un vehículo.
- La autorización para registrar información sobre un vehículo.
- Los roles y permisos de los usuarios del prestador.
- La asociación de usuarios a determinadas sedes.
- La visibilidad de información.
- La protección de datos.
- Las reglas de seguridad.
- Las reglas específicas aplicables a determinados servicios o eventos.

Por ejemplo:

```text
PRESTADOR VERIFICADO
        ↓
NO IMPLICA
        ↓
ACCESO AUTOMÁTICO
A CUALQUIER VEHÍCULO
```

De igual manera:

```text
PRESTADOR NO VERIFICADO
        ↓
NO IMPLICA
        ↓
PRESTADOR BLOQUEADO
```

---

#### Autorización sobre el vehículo

La capacidad de un Prestador de Servicios Vehiculares para registrar información relacionada con un vehículo deberá mantenerse separada de su estado de verificación.

Un prestador, independientemente de que se encuentre verificado o no verificado, no deberá obtener automáticamente la capacidad de consultar, modificar o incorporar información sobre cualquier vehículo registrado en Vehículos Services.

Conceptualmente:

```text
PRESTADOR
        ↓
RELACIÓN / AUTORIZACIÓN
SOBRE EL VEHÍCULO
        ↓
ACCESO SEGÚN
REGLAS Y PERMISOS
        ↓
REGISTRO O CONSULTA
DE INFORMACIÓN
```

Por ejemplo, un taller registrado pero todavía no verificado podrá realizar un mantenimiento sobre un vehículo y registrar dicho evento cuando exista la relación, autorización o condición que posteriormente sea definida para permitirlo.

Por el contrario, el simple hecho de que un prestador exista dentro de Vehículos Services no deberá permitirle buscar arbitrariamente un vehículo y registrar información sobre su historial sin que exista la relación o autorización correspondiente.

Las reglas definitivas de creación, aceptación, vigencia, revocación y finalización de dicha relación serán desarrolladas posteriormente en el apartado correspondiente a la relación Prestador de Servicios Vehiculares ↔ Vehículo.

---

#### Acciones sujetas a mayor nivel de control

Vehículos Services deberá permitir que determinadas funcionalidades puedan requerir condiciones adicionales cuando su ejecución represente un mayor impacto sobre la seguridad, identidad, confianza, privacidad o integridad de la información.

Por lo tanto, el hecho de permitir que un Prestador no verificado opere desde su registro no deberá impedir que posteriormente determinadas acciones puedan requerir:

- Verificación del prestador.
- Verificación de determinada información.
- Verificación de una sede.
- Un nivel específico de autorización.
- Un rol o permiso determinado.
- Una relación válida con el vehículo.
- Autorización del propietario o actor correspondiente.
- Evidencias adicionales.
- Otros controles que posteriormente sean definidos.

Conceptualmente:

```text
OPERACIÓN GENERAL
        ↓
PUEDE ESTAR DISPONIBLE
SIN VERIFICACIÓN COMPLETA

ACCIONES DE MAYOR RIESGO
        ↓
PUEDEN REQUERIR
CONTROLES ADICIONALES
```

La clasificación definitiva de cuáles funcionalidades podrán ejecutarse sin verificación y cuáles requerirán verificaciones o controles adicionales será definida posteriormente.

---

#### Verificación del Prestador de Servicios Vehiculares

La verificación deberá entenderse como un mecanismo mediante el cual Vehículos Services podrá comprobar determinada información relacionada con un Prestador de Servicios Vehiculares.

La existencia de una verificación no deberá interpretarse automáticamente como una certificación absoluta sobre el prestador, sus trabajadores, todos sus servicios, todas sus sedes o la veracidad de todos los eventos que posteriormente registre.

Conceptualmente:

```text
PRESTADOR VERIFICADO
        ↓
VEHÍCULOS SERVICES
HA VALIDADO DETERMINADA
INFORMACIÓN
        ≠
GARANTÍA ABSOLUTA
SOBRE TODA SU OPERACIÓN
```

La plataforma deberá evitar que el concepto de verificación genere una interpretación diferente al alcance real de las validaciones efectuadas.

Por esta razón, posteriormente deberá determinarse exactamente qué elementos pueden ser objeto de verificación.

Como referencia conceptual, podrán existir verificaciones relacionadas con:

- Identidad del prestador.
- Información general del prestador.
- Existencia o formalización del prestador cuando corresponda.
- Información de sus sedes.
- Información utilizada para acreditar determinada actividad.
- Información relacionada con determinados tipos, especialidades o servicios.
- Otros elementos que posteriormente sean considerados necesarios.

No se establece todavía que todos estos elementos deban convertirse obligatoriamente en verificaciones independientes.

La estructura definitiva de verificación será determinada posteriormente.

---

#### Verificación según la naturaleza del prestador

Los requisitos de verificación no deberán diseñarse suponiendo que todos los Prestadores de Servicios Vehiculares corresponden a personas jurídicas o empresas de gran tamaño.

Vehículos Services deberá contemplar las diferentes naturalezas de prestador definidas anteriormente.

Por ejemplo:

```text
PRESTADOR
        ↓
┌─────────────────────────┐
│                         │
↓                         ↓
PERSONA NATURAL     PERSONA JURÍDICA
│                         │
↓                         ↓
REQUISITOS             REQUISITOS
APLICABLES             APLICABLES
SEGÚN SU               SEGÚN SU
NATURALEZA             NATURALEZA
```

Los requisitos podrán variar posteriormente dependiendo de factores como:

- Naturaleza del prestador.
- País.
- Tipo de prestador.
- Actividad realizada.
- Especialidades.
- Servicios ofrecidos.
- Sede.
- Requisitos legales o regulatorios aplicables.
- Nivel de verificación requerido.
- Otros criterios que posteriormente sean definidos.

Por lo tanto, no deberá asumirse que existe necesariamente una única lista universal de documentos o requisitos aplicable a todos los Prestadores de Servicios Vehiculares.

---

#### Verificación del prestador y verificación de sus sedes

La verificación general del Prestador de Servicios Vehiculares deberá mantenerse conceptualmente diferenciada de la verificación de sus sedes.

Por lo tanto:

```text
VERIFICACIÓN DEL PRESTADOR
        ≠
VERIFICACIÓN AUTOMÁTICA
DE TODAS SUS SEDES
```

Un Prestador de Servicios Vehiculares podrá contar con una o múltiples sedes y las condiciones de cada una podrán ser diferentes.

La existencia de una verificación general sobre el prestador no deberá utilizarse automáticamente para afirmar que todas sus sedes fueron verificadas bajo los mismos criterios.

De igual manera, la verificación de una sede determinada no deberá modificar la identidad de las demás sedes pertenecientes al prestador.

Los mecanismos, requisitos, documentos, responsables y resultados correspondientes a la verificación de sedes serán definidos posteriormente.

---

#### Verificación y registro de eventos

La posibilidad de registrar un mantenimiento, reparación, diagnóstico, inspección, evaluación, peritaje u otro evento deberá mantener trazabilidad sobre el Prestador de Servicios Vehiculares que lo registró o realizó, cuando corresponda.

Cuando posteriormente se determine que el estado o nivel de verificación del prestador debe ser visible dentro de determinadas consultas, Vehículos Services deberá presentar dicha información sin convertirla en una garantía sobre el contenido del evento registrado.

Por ejemplo:

```text
EVENTO
Cambio de pastillas de freno

        ↓

PRESTADOR
Taller Santiago

        ↓

SEDE
Sede Medellín

        ↓

ORIGEN DEL REGISTRO
Prestador de Servicios Vehiculares
```

El hecho de que el prestador se encuentre verificado podrá constituir información adicional de confianza sobre determinados datos previamente comprobados por Vehículos Services, pero no deberá significar automáticamente que la plataforma certifica como verdadero todo el contenido registrado por dicho prestador.

La definición de si el historial deberá conservar el estado de verificación existente en el momento del evento, mostrar el estado actual del prestador o conservar ambos valores será desarrollada posteriormente dentro de las reglas correspondientes al historial y trazabilidad.

---

#### Cambio posterior del estado de verificación

Un Prestador de Servicios Vehiculares podrá modificar su condición de verificación a lo largo del tiempo de acuerdo con los procesos que posteriormente sean definidos.

Por ejemplo:

```text
PRESTADOR REGISTRADO
        ↓
NO VERIFICADO
        ↓
OPERA BAJO LAS
CONDICIONES PERMITIDAS
        ↓
COMPLETA PROCESO
DE VERIFICACIÓN
        ↓
PRESTADOR VERIFICADO
```

El cambio posterior de su condición de verificación no deberá eliminar, reemplazar ni reasignar los eventos registrados previamente.

De igual manera, los cambios futuros en la condición de verificación deberán conservar la trazabilidad necesaria para evitar que se altere incorrectamente el significado histórico de los eventos previamente registrados.

Las reglas específicas relacionadas con pérdida, vencimiento, renovación, rechazo o recuperación de una verificación serán definidas posteriormente.

---

#### Estado operativo del Prestador de Servicios Vehiculares

El estado operativo del Prestador deberá mantenerse diferenciado de su estado de verificación.

Conceptualmente:

```text
ESTADO OPERATIVO
        ≠
ESTADO DE VERIFICACIÓN
```

Por ejemplo, conceptualmente podría existir un prestador:

```text
OPERATIVO
+
NO VERIFICADO
```

o:

```text
OPERATIVO
+
VERIFICADO
```

De igual manera, un Prestador previamente verificado podría posteriormente dejar de encontrarse operativo sin que ello implique eliminar su identidad o su participación histórica.

El catálogo definitivo de estados operativos no se establece todavía.

Posteriormente podrán analizarse condiciones relacionadas con:

- Operación.
- Inactividad.
- Suspensión.
- Cese de actividades.
- Reactivación.
- Bloqueo por razones de seguridad.
- Otros estados que funcionalmente sean necesarios.

La inclusión de estos conceptos como referencia no significa que todos deban convertirse obligatoriamente en estados definitivos de la plataforma.

---

#### Prestador que deja de operar

Cuando un Prestador de Servicios Vehiculares deje de operar dentro de Vehículos Services, su identidad no deberá eliminarse cuando existan relaciones o eventos históricos asociados a vehículos.

Conceptualmente:

```text
PRESTADOR DEJA DE OPERAR
        ≠
ELIMINACIÓN DEL PRESTADOR
        ≠
ELIMINACIÓN DEL HISTORIAL
```

Los mantenimientos, reparaciones, diagnósticos, inspecciones, evaluaciones, peritajes, documentos, evidencias y demás eventos previamente asociados al prestador deberán conservar la referencia correspondiente.

Por ejemplo:

```text
VEHÍCULO
        ↓
MANTENIMIENTO
14/09/2026
        ↓
TALLER SANTIAGO
        ↓
AÑOS DESPUÉS
TALLER SANTIAGO
DEJA DE OPERAR
        ↓
EL MANTENIMIENTO
PERMANECE EN EL HISTORIAL
```

El prestador podrá dejar de estar disponible para nuevas operaciones sin que ello elimine o modifique automáticamente los registros históricos previamente generados.

Las reglas definitivas para suspensión, cierre, desactivación, reactivación o cese de operación serán definidas posteriormente.

---

#### Diferencia entre Prestador, cuenta y usuarios

La existencia del Prestador de Servicios Vehiculares deberá mantenerse separada de las cuentas o usuarios que posteriormente puedan actuar en su representación.

Conceptualmente:

```text
PRESTADOR
        ≠
CUENTA / USUARIO
QUE ACTÚA EN SU REPRESENTACIÓN
```

Por lo tanto, la desactivación, bloqueo, eliminación o pérdida de acceso de un usuario no deberá interpretarse automáticamente como eliminación del Prestador de Servicios Vehiculares.

De igual manera, la salida de una persona que trabajaba para un prestador no deberá eliminar la identidad del prestador, sus sedes ni los eventos históricos registrados mientras dicha persona se encontraba autorizada.

Las reglas específicas relacionadas con usuarios, cuentas, roles, permisos, recuperación de acceso, bloqueo y administración de usuarios serán desarrolladas posteriormente en los apartados correspondientes.

---

#### Permanencia histórica del Prestador de Servicios Vehiculares

El Prestador de Servicios Vehiculares deberá conservarse como referencia histórica cuando haya participado en eventos relacionados con vehículos.

Un prestador no deberá desaparecer del historial simplemente porque:

- Dejó de operar.
- Fue desactivado.
- Fue suspendido.
- Cambió su estado de verificación.
- Perdió una verificación.
- Modificó información permitida.
- Cerró alguna o todas sus sedes.
- Los usuarios que lo representaban dejaron de tener acceso.
- El propietario revocó posteriormente una relación con el prestador.
- El vehículo cambió de propietario.
- El prestador dejó de tener relación activa con determinados vehículos.

Conceptualmente:

```text
EVENTO HISTÓRICO
        ↓
PRESTADOR QUE PARTICIPÓ
        ↓
SEDE QUE PARTICIPÓ
CUANDO CORRESPONDA
        ↓
REFERENCIA HISTÓRICA
PERMANENTE
```

Los cambios posteriores del prestador no deberán utilizarse para reinterpretar automáticamente las condiciones bajo las cuales ocurrió un evento histórico.

Las reglas específicas de inmutabilidad, corrección, anulación, auditoría, versionamiento y conservación de información histórica serán definidas posteriormente dentro del apartado correspondiente al historial.

---

#### Límites de esta definición

Este punto establece conceptualmente que:

- Un Prestador de Servicios Vehiculares podrá registrarse dentro de Vehículos Services sin encontrarse previamente verificado.
- Estar registrado y estar verificado corresponden a conceptos diferentes.
- Un Prestador no verificado podrá comenzar a operar dentro de la plataforma bajo las reglas y condiciones definidas.
- No estar verificado no significará automáticamente estar bloqueado.
- Permitir operar a un prestador no verificado no significará otorgarle acceso irrestricto a todas las funcionalidades.
- Registro, verificación, permisos y autorización sobre vehículos corresponden a conceptos diferentes.
- Un Prestador verificado tampoco obtendrá automáticamente acceso a cualquier vehículo.
- La relación o autorización correspondiente seguirá siendo necesaria para consultar o registrar información sobre vehículos cuando aplique.
- Determinadas funcionalidades de mayor riesgo podrán requerir verificaciones o controles adicionales.
- La verificación deberá indicar que determinada información fue comprobada y no una certificación absoluta sobre toda la operación del prestador.
- Los requisitos de verificación podrán variar dependiendo de la naturaleza, país, tipo, actividad, sede, servicio u otros criterios aplicables al prestador.
- No deberá asumirse una única lista universal de requisitos para todos los prestadores.
- La verificación general del prestador deberá mantenerse diferenciada de la verificación de sus sedes.
- El estado operativo deberá mantenerse diferenciado del estado de verificación.
- Un prestador podrá evolucionar de no verificado a verificado sin perder los eventos registrados previamente.
- Un cambio posterior de verificación no deberá eliminar ni reasignar eventos históricos.
- Un prestador que deje de operar no deberá desaparecer de los historiales en los que haya participado.
- El Prestador deberá mantenerse conceptualmente separado de las cuentas y usuarios que actúen en su representación.
- La pérdida de acceso de un usuario no deberá eliminar al Prestador ni su historial.
- La información histórica deberá conservar la identificación del Prestador y de la sede que participó cuando corresponda.

Todavía no se definen en detalle:

- El mecanismo definitivo de registro de un Prestador de Servicios Vehiculares.
- Quién podrá crear, registrar o solicitar la incorporación de un prestador.
- La información mínima obligatoria para completar el registro.
- Los mecanismos definitivos de verificación.
- Los niveles o tipos de verificación que existirán.
- Si existirán verificaciones independientes para identidad, prestador, sede, actividad, especialidad o servicio.
- Los documentos requeridos para cada proceso de verificación.
- Los requisitos específicos para personas naturales.
- Los requisitos específicos para personas jurídicas.
- Las reglas particulares de verificación según país.
- Los requisitos particulares según tipo de prestador o actividad realizada.
- Las funcionalidades exactas disponibles para un prestador no verificado.
- Las funcionalidades que requerirán obligatoriamente algún nivel de verificación.
- La clasificación definitiva de acciones de mayor riesgo.
- Los controles adicionales aplicables a dichas acciones.
- El catálogo definitivo de estados operativos del prestador.
- Las reglas de suspensión.
- Las reglas de cese de operación.
- Las reglas de reactivación.
- Las reglas de bloqueo por seguridad.
- Las reglas de pérdida, vencimiento, renovación o recuperación de una verificación.
- El comportamiento de las sedes cuando el prestador general cambia de estado.
- Las reglas definitivas de verificación de sedes.
- La forma en que se mostrará públicamente el estado o nivel de verificación.
- La información exacta que podrá visualizar un propietario sobre la verificación de un prestador.
- La conservación del estado de verificación existente al momento de registrar un evento.
- La relación Prestador de Servicios Vehiculares ↔ Vehículo.
- Las autorizaciones necesarias para consultar o registrar información sobre vehículos.
- Los roles y permisos de los usuarios del prestador.
- Las reglas de seguridad, auditoría y trazabilidad aplicables a las operaciones del prestador.

Estos elementos deberán desarrollarse posteriormente en los apartados correspondientes, evitando que su definición futura contradiga la separación establecida entre registro, operación, verificación, autorización y permanencia histórica.

---
## 63.4 DEFINIR RELACIÓN PROPIETARIO ↔ VEHÍCULO

### 63.4.1 Concepto de la relación Propietario ↔ Vehículo

Dentro de Vehículos Services, la relación Propietario ↔ Vehículo representará el vínculo de propiedad existente entre un propietario registrado en la plataforma y uno o varios vehículos que legalmente le pertenecen.

Esta relación deberá permitir identificar quién es el propietario de un vehículo durante un período determinado de su ciclo de vida.

Conceptualmente:

```text
PROPIETARIO
        ↓
OSTENTA LA PROPIEDAD
        ↓
VEHÍCULO
```

La relación de propiedad no deberá establecerse únicamente porque una persona:

- Utilice el vehículo.
- Conduzca el vehículo.
- Administre el vehículo.
- Realice mantenimientos sobre el vehículo.
- Pague gastos relacionados con el vehículo.
- Conozca la placa del vehículo.
- Tenga físicamente el vehículo.
- Tenga acceso a información del vehículo.
- Sea un usuario autorizado para gestionarlo.

Por lo tanto:

```text
USAR UN VEHÍCULO
        ≠
SER PROPIETARIO DEL VEHÍCULO
```

y:

```text
ADMINISTRAR UN VEHÍCULO
        ≠
SER PROPIETARIO DEL VEHÍCULO
```

La propiedad deberá establecerse mediante el mecanismo de validación definido por Vehículos Services.

Para esta etapa del proyecto, la tarjeta de propiedad del vehículo será el documento utilizado para validar la relación de propiedad.

---

### 63.4.2 Cardinalidad de la relación de propiedad

Un propietario podrá estar relacionado con uno o varios vehículos.

Conceptualmente:

```text
PROPIETARIO
        ↓
┌─────────────────────┐
│                     │
↓                     ↓
VEHÍCULO A        VEHÍCULO B
│
↓
VEHÍCULO C
```

Por ejemplo:

```text
PROPIETARIO
Santiago

Vehículos actuales:
- Vehículo A
- Vehículo B
- Vehículo C
```

Cada vehículo deberá conservar su propia identidad, información e historial independientemente de que varios vehículos pertenezcan al mismo propietario.

La existencia de varios vehículos asociados a un propietario no deberá mezclar:

- Sus historiales.
- Sus kilometrajes.
- Sus mantenimientos.
- Sus reparaciones.
- Sus repuestos.
- Sus abastecimientos o recargas.
- Sus documentos.
- Sus alertas.
- Sus demás eventos.

De igual manera, un propietario podrá llegar a tener cero vehículos actuales sin que esto implique eliminar su identidad dentro de Vehículos Services.

Un mismo vehículo podrá haber pertenecido a diferentes propietarios a lo largo del tiempo.

Por lo tanto, deberá diferenciarse entre:

```text
PROPIETARIO ACTUAL
        ≠
PROPIETARIOS HISTÓRICOS
```

Los diferentes propietarios históricos no deberán generar vehículos diferentes ni historiales independientes.

El vehículo deberá conservar una única identidad y un único ciclo de vida digital a través de sus diferentes períodos de propiedad.

---

### 63.4.3 Validación de la propiedad mediante la tarjeta de propiedad

Para establecer una relación Propietario ↔ Vehículo, Vehículos Services deberá comprobar la correspondencia entre los datos declarados por el usuario que solicita su asociación y la información del propietario indicada en la tarjeta de propiedad.

La tarjeta de propiedad del vehículo será el documento utilizado para realizar esta validación.

Para la primera entrega del Propietario, únicamente se admitirán vehículos y documentos de Colombia. Los nombres, apellidos, tipo y número de documento del usuario se solicitarán cuando vaya a asociar su primer vehículo, sin exigirlos para crear la cuenta, conforme a RN-025 — Cuenta de usuario e identidad del propietario, de `reglas-negocio.md`.

La validación inicial consistirá en comparar esos datos declarados con la información disponible en la tarjeta de propiedad. No constituirá una comprobación independiente de que la persona que utiliza la cuenta sea quien aparece en el documento, ni acreditará por sí sola la autenticidad o vigencia de la tarjeta de propiedad.

Conceptualmente:

```text
PROPIETARIO REGISTRADO
        ↓
SOLICITA AGREGAR / ASOCIAR VEHÍCULO
        ↓
ESCANEA O CAPTURA
LA TARJETA DE PROPIEDAD
        ↓
VEHÍCULOS SERVICES
OBTIENE LA INFORMACIÓN
DEL DOCUMENTO
        ↓
IDENTIFICA
PROPIETARIO + VEHÍCULO
        ↓
COMPARA LA INFORMACIÓN
        ↓
¿CORRESPONDE EL PROPIETARIO?
```

La información obtenida de la tarjeta de propiedad deberá permitir comprobar, como mínimo conceptualmente:

1. La identidad del propietario indicado en el documento.
2. La identidad del vehículo al cual corresponde el documento.
3. La correspondencia entre el propietario registrado en Vehículos Services y el propietario indicado en la tarjeta de propiedad.
4. La correspondencia entre el vehículo que se pretende asociar y el vehículo identificado en la tarjeta de propiedad.

Para esta primera entrega, la identidad del propietario registrado en Vehículos Services corresponderá a los datos declarados por el usuario. Una coincidencia documental no deberá presentarse como una comprobación independiente de su identidad real.

Los datos, documentos de identificación admitidos y criterios de comparación del propietario se regirán por RN-025. La identificación, detección de coincidencias y comparación documental del vehículo se regirán por RN-036. Las precisiones pendientes de cada regla deberán completarse antes de implementar las operaciones que dependan de ellas. Los mecanismos técnicos de captura, lectura y procesamiento se detallarán en los documentos técnicos, respetando las condiciones funcionales aprobadas.

---

### 63.4.4 Coincidencia del propietario

La relación de propiedad solamente deberá establecerse cuando la información del propietario registrada en Vehículos Services corresponda con la información del propietario identificada en la tarjeta de propiedad.

Para la primera entrega, la información registrada corresponderá a los datos declarados por el usuario conforme a RN-025. La comparación deberá respetar el alcance y las limitaciones establecidos en `63.4.3`.

Conceptualmente:

```text
PROPIETARIO EN
VEHÍCULOS SERVICES
        ↓
COMPARACIÓN
        ↑
PROPIETARIO EN
TARJETA DE PROPIEDAD
        ↓
¿COINCIDEN?
```

Si existe coincidencia:

```text
SÍ
        ↓
PROPIEDAD VALIDADA
        ↓
SE ESTABLECE
PROPIETARIO ↔ VEHÍCULO
```

La expresión “PROPIEDAD VALIDADA” representará el resultado satisfactorio del procedimiento de comparación documental y de las demás condiciones aplicables para establecer la relación en la plataforma. No representará una comprobación independiente de la identidad real del usuario ni de la autenticidad o vigencia del documento.

Si no existe coincidencia:

```text
NO
        ↓
PROPIEDAD NO VALIDADA
        ↓
NO SE ESTABLECE AUTOMÁTICAMENTE
LA RELACIÓN DE PROPIEDAD
```

Por ejemplo:

```text
Usuario / propietario registrado:
Santiago Oquendo

Tarjeta de propiedad:
Santiago Oquendo

        ↓
INFORMACIÓN COINCIDENTE
        ↓
RELACIÓN DE PROPIEDAD
PUEDE SER ESTABLECIDA
```

Este ejemplo ilustrará únicamente la coincidencia del nombre. La relación no deberá establecerse por esa coincidencia aislada: deberán cumplirse los criterios de comparación de los datos de identificación y las demás validaciones aplicables al vehículo.

En cambio:

```text
Usuario / propietario registrado:
Santiago Oquendo

Tarjeta de propiedad:
Juan Pérez

        ↓
INFORMACIÓN NO COINCIDENTE
        ↓
NO SE ESTABLECE
LA RELACIÓN DE PROPIEDAD
```

El tratamiento de diferencias de escritura, información incompleta o ilegible y resultados de comparación del propietario se realizará conforme a los criterios aprobados en RN-025. No deberá asumirse una coincidencia satisfactoria cuando falte información necesaria para comprobarla o no se cumplan dichos criterios.

Cuando la identificación esté bloqueada porque el tipo y número de documento ya aparecen asociados a otra cuenta, el usuario autenticado podrá solicitar revisión manual desde la primera entrega del Propietario, conforme a RN-035 de `reglas-negocio.md` y RF-051 de `requerimientos-funcionales-propietario.md`. La revisión incluirá una comprobación adicional de identidad y respetará los límites de corrección establecidos en RN-035. No fusionará cuentas ni asociará o transferirá vehículos automáticamente. Si se autoriza y ejecuta una corrección, deberán completarse nuevamente las comprobaciones normales antes de establecer la relación de propiedad.

El conocimiento de la placa, VIN, número de motor u otra información identificadora del vehículo no deberá reemplazar la validación de propiedad.

Por lo tanto:

```text
CONOCER DATOS DEL VEHÍCULO
        ≠
DEMOSTRAR PROPIEDAD
```

---

### 63.4.5 Validación del vehículo contenido en la tarjeta de propiedad

La validación no deberá limitarse únicamente a comprobar el nombre o identificación del propietario.

Vehículos Services también deberá comprobar que la tarjeta de propiedad presentada corresponda al vehículo que se pretende registrar o asociar.

Conceptualmente:

```text
TARJETA DE PROPIEDAD
        ↓
IDENTIFICA
        ↓
PROPIETARIO
        +
VEHÍCULO
```

Por lo tanto, deberán existir dos correspondencias:

```text
PROPIETARIO REGISTRADO
        =
PROPIETARIO DEL DOCUMENTO

Y

VEHÍCULO SOLICITADO
        =
VEHÍCULO DEL DOCUMENTO
```

Solo cuando las validaciones requeridas sean satisfactorias podrá establecerse la relación correspondiente.

Esto deberá evitar escenarios en los cuales una persona utilice una tarjeta de propiedad válida que realmente corresponda a otro vehículo.

Para la primera entrega, la comparación obligatoria del vehículo se realizará mediante la placa y el VIN conforme a RN-036 — Identificación, coincidencias y comparación documental del vehículo, de `reglas-negocio.md`. El propietario deberá ingresar el VIN y deberá comprobarse su correspondencia con el documento. El número de chasis y el número de motor serán información complementaria opcional; su ausencia, falta de ingreso o imposibilidad de lectura no impedirán por sí solas completar el registro o la asociación. Se aplicarán las condiciones de validación básica de captura, mensajes y corrección de datos aprobadas en RN-036. El tratamiento de inconsistencias de la primera entrega se regirá por esa regla: si el conflicto requiere la revisión especial de conflictos vehiculares, la asociación permanecerá sin completar; esa revisión especial, la transferencia de propiedad y la validación avanzada de patrones por categoría se desarrollarán posteriormente.

Las correcciones de errores de captura en datos obligatorios de un vehículo ya registrado se tramitarán mediante soporte desde la primera entrega, conforme a RN-037 — Actualización de datos personales y correcciones mediante soporte, de `reglas-negocio.md`, y RF-052 de `requerimientos-funcionales-propietario.md`. Esta vía no permitirá resolver conflictos entre identidades vehiculares ni transferir propiedad. Cuando una corrección autorizada afecte la placa o el VIN, deberán repetirse las búsquedas y comparaciones aplicables conforme a RN-036 antes de aceptar el cambio.



---

### 63.4.6 Captura y procesamiento de la tarjeta de propiedad

Vehículos Services deberá permitir obtener la información necesaria de la tarjeta de propiedad mediante un mecanismo de captura o digitalización.

Conceptualmente:

```text
TARJETA DE PROPIEDAD
        ↓
CAPTURA / ESCANEO
        ↓
LECTURA DE INFORMACIÓN
        ↓
EXTRACCIÓN DE DATOS
        ↓
VALIDACIÓN
        ↓
RESULTADO
```

El objetivo será evitar que la relación de propiedad dependa exclusivamente de información digitada manualmente por el usuario.

La captura del documento deberá permitir posteriormente utilizar la información disponible para:

- Identificar al propietario.
- Identificar el vehículo.
- Comparar la información registrada en Vehículos Services.
- Detectar inconsistencias.
- Apoyar la creación o asociación del vehículo.
- Conservar la trazabilidad necesaria del proceso de validación.

No se define todavía la tecnología mediante la cual se realizará la lectura del documento.

Por lo tanto, esta definición no establece todavía si se utilizará:

- OCR.
- Reconocimiento documental.
- Inteligencia artificial.
- Lectura de códigos.
- Integraciones externas.
- Validaciones contra fuentes oficiales.
- Una combinación de diferentes mecanismos.

Estas decisiones corresponden a etapas posteriores del diseño técnico y de integración.

---

### 63.4.7 Propietario persona natural

Cuando el propietario corresponda a una persona natural, Vehículos Services deberá comparar la identidad registrada para dicha persona con la identidad del propietario indicada en la tarjeta de propiedad.

Para la primera entrega, la identidad registrada corresponderá a los nombres, apellidos, tipo y número de documento declarados por el usuario conforme a RN-025 — Cuenta de usuario e identidad del propietario, de `reglas-negocio.md`. La comparación deberá cumplir las condiciones y limitaciones establecidas en `63.4.3` y `63.4.4`.

Conceptualmente:

```text
PERSONA NATURAL
        ↓
IDENTIDAD REGISTRADA
EN VEHÍCULOS SERVICES
        ↓
COMPARACIÓN
        ↑
IDENTIDAD INDICADA
EN TARJETA DE PROPIEDAD
```

Cuando la información corresponda y las demás validaciones requeridas sean satisfactorias, podrá establecerse la relación de propiedad.

Una misma persona natural podrá establecer relaciones de propiedad con varios vehículos, siempre que la propiedad de cada uno sea validada individualmente.

Por ejemplo:

```text
SANTIAGO
        ↓
TARJETA VEHÍCULO A
Propietario: Santiago
        ↓
VEHÍCULO A ASOCIADO

SANTIAGO
        ↓
TARJETA VEHÍCULO B
Propietario: Santiago
        ↓
VEHÍCULO B ASOCIADO
```

La validación realizada sobre un vehículo no deberá utilizarse automáticamente para validar la propiedad de otro.

---

### 63.4.8 Propietario persona jurídica o empresa

Cuando el propietario corresponda a una persona jurídica o empresa, la propiedad deberá establecerse a favor de dicha organización y no automáticamente a favor de la persona que realiza el proceso dentro de Vehículos Services.

Conceptualmente:

```text
EMPRESA
        ↓
PROPIETARIA DEL VEHÍCULO
        ↓
TARJETA DE PROPIEDAD
        ↓
VALIDACIÓN DE PROPIEDAD
```

La información identificadora de la empresa deberá corresponder con la información del propietario contenida en la tarjeta de propiedad, de acuerdo con los datos y mecanismos que posteriormente sean definidos.

El usuario que realice el proceso podrá actuar en representación de la empresa cuando se encuentre autorizado para hacerlo, pero no deberá convertirse por este motivo en propietario del vehículo.

Por lo tanto:

```text
EMPRESA
        ↓
PROPIETARIA

USUARIO AUTORIZADO
        ↓
ADMINISTRA / GESTIONA
```

y:

```text
USUARIO AUTORIZADO
        ≠
PROPIETARIO DEL VEHÍCULO
```

Una empresa podrá ser propietaria de uno o varios vehículos y cada relación de propiedad deberá conservarse individualmente.

Las reglas específicas relacionadas con representación de empresas, usuarios autorizados, administradores y permisos serán desarrolladas posteriormente.

---

### 63.4.9 Vehículo nuevo dentro de Vehículos Services

Cuando el propietario intente asociar un vehículo que todavía no exista dentro de Vehículos Services, el proceso deberá permitir validar la propiedad y posteriormente crear el vehículo siguiendo las reglas definidas para su registro.

Conceptualmente:

```text
PROPIETARIO
        ↓
AGREGAR VEHÍCULO
        ↓
VALIDACIÓN DE PROPIEDAD
        ↓
TARJETA DE PROPIEDAD
        ↓
PROPIEDAD VALIDADA
        ↓
¿VEHÍCULO EXISTE
EN VEHÍCULOS SERVICES?
        ↓
NO
        ↓
REGISTRO DEL VEHÍCULO
        ↓
CREACIÓN DE SU IDENTIDAD
        ↓
RELACIÓN
PROPIETARIO ↔ VEHÍCULO
```

El vehículo deberá crearse una sola vez dentro de Vehículos Services.

A partir de ese momento deberá comenzar su ciclo de vida digital dentro de la plataforma desde el primer registro conocido, sin que esto implique que dicho momento corresponda necesariamente al inicio real de la vida útil del vehículo.

---

### 63.4.10 Vehículo que ya existe dentro de Vehículos Services

Cuando el vehículo que se intenta asociar ya exista dentro de Vehículos Services, la plataforma no deberá crear un nuevo vehículo ni un nuevo historial independiente.

Conceptualmente:

```text
PROPIETARIO
        ↓
SOLICITA ASOCIAR VEHÍCULO
        ↓
VALIDACIÓN DE PROPIEDAD
        ↓
VEHÍCULO YA EXISTE
        ↓
NO CREAR NUEVO VEHÍCULO
        ↓
CONSERVAR IDENTIDAD
E HISTORIAL EXISTENTE
        ↓
ESTABLECER LA NUEVA RELACIÓN
DE PROPIEDAD CUANDO CORRESPONDA
```

Por lo tanto:

```text
MISMO VEHÍCULO
        =
MISMA IDENTIDAD
        +
MISMO CICLO DE VIDA DIGITAL
```

Un cambio de propietario no deberá generar:

```text
VEHÍCULO A - PROPIETARIO 1
VEHÍCULO A - PROPIETARIO 2
```

como si correspondieran a dos vehículos diferentes.

Deberá mantenerse:

```text
VEHÍCULO A
        ↓
PROPIETARIO 1
        ↓
PERÍODO DE PROPIEDAD 1
        ↓
CAMBIO DE PROPIETARIO
        ↓
PROPIETARIO 2
        ↓
PERÍODO DE PROPIEDAD 2
```

La información histórica del vehículo deberá continuar acumulándose sobre la misma identidad vehicular.

---

### 63.4.11 Períodos de propiedad

La relación Propietario ↔ Vehículo deberá tener una dimensión temporal que permita identificar durante qué período un propietario fue dueño del vehículo.

Conceptualmente:

```text
PROPIETARIO
        ↓
INICIO DE PROPIEDAD
        ↓
PERÍODO DE PROPIEDAD
        ↓
FINALIZACIÓN DE PROPIEDAD
        ↓
RELACIÓN HISTÓRICA
```

Esta información permitirá posteriormente relacionar los diferentes eventos del vehículo con el período de propiedad durante el cual ocurrieron.

Por ejemplo:

```text
VEHÍCULO
        ↓
PROPIETARIO A
2020 → 2024
        ↓
Eventos del período A
        ↓
FINALIZA SU PERÍODO
        ↓
RELACIÓN HISTÓRICA
SE CONSERVA

        ↓

PROPIETARIO B
2024 → Actualidad
        ↓
Eventos del período B
        ↓
RELACIÓN ACTUAL
```

Cada período de propiedad deberá conservarse históricamente aunque posteriormente exista un nuevo propietario.

La finalización de un período de propiedad no deberá eliminar la relación histórica entre el propietario anterior y el vehículo.

Esta relación histórica deberá permanecer aunque posteriormente:

- El vehículo cambie de propietario.
- El propietario deje de tener vehículos actuales.
- El propietario deje de utilizar Vehículos Services.
- Cambien o finalicen las autorizaciones otorgadas a otros usuarios.
- El vehículo sea administrado posteriormente por otras personas.
- Se relacionen nuevos Prestadores de Servicios Vehiculares con el vehículo.
- Se generen nuevos eventos durante períodos de propiedad posteriores.

La existencia de un nuevo período de propiedad no deberá reemplazar, eliminar ni fragmentar los períodos anteriores.

De esta manera, un mismo vehículo podrá conservar de forma continua la secuencia de propietarios que haya tenido a lo largo del tiempo, manteniendo cada relación Propietario ↔ Vehículo asociada al período durante el cual estuvo vigente.

La permanencia de estas relaciones permitirá preservar la trazabilidad de la propiedad como parte del ciclo de vida histórico del vehículo.

---

### 63.4.12 Información asociada al período de propiedad

Vehículos Services deberá permitir que posteriormente pueda determinarse qué información y eventos del vehículo ocurrieron durante cada período de propiedad.

Entre ellos podrán encontrarse:

- Kilometraje inicial conocido del período.
- Kilometraje final conocido del período.
- Kilómetros recorridos durante el período.
- Mantenimientos.
- Reparaciones.
- Repuestos.
- Diagnósticos.
- Inspecciones.
- Peritajes.
- Abastecimientos, tanqueos o recargas.
- Registros de consumo.
- Documentos.
- Costos.
- Alertas.
- Otros eventos asociados al vehículo.

Conceptualmente:

```text
PERÍODO DE PROPIEDAD
        ↓
INICIO
        ↓
EVENTOS DEL VEHÍCULO
        ↓
FINALIZACIÓN
```

La existencia de esta relación temporal permitirá comprender posteriormente qué ocurrió con el vehículo mientras estuvo bajo la propiedad de cada propietario.

Sin embargo, la asociación temporal de un evento con determinado propietario no deberá interpretarse automáticamente como que dicho propietario fue personalmente quien realizó, autorizó o registró el evento.

El evento podrá haber sido generado por diferentes actores autorizados, incluyendo Prestadores de Servicios Vehiculares.

---

### 63.4.13 Cambio o transferencia de propietario

Cuando un vehículo cambie de propietario, Vehículos Services deberá conservar la identidad y el historial del vehículo y finalizar la relación de propiedad correspondiente al propietario anterior.

Conceptualmente:

```text
PROPIETARIO A
        ↓
VEHÍCULO
        ↓
FINALIZA SU
PERÍODO DE PROPIEDAD
        ↓
CAMBIO / TRANSFERENCIA
        ↓
PROPIETARIO B
        ↓
VALIDACIÓN DE PROPIEDAD
        ↓
INICIA NUEVO
PERÍODO DE PROPIEDAD
```

El nuevo propietario deberá demostrar la propiedad mediante la tarjeta de propiedad correspondiente antes de establecerse la nueva relación de propiedad.

El cambio de propietario no deberá:

- Eliminar el vehículo.
- Crear un vehículo duplicado.
- Reiniciar el kilometraje.
- Reiniciar el historial.
- Eliminar mantenimientos anteriores.
- Eliminar reparaciones anteriores.
- Eliminar repuestos registrados.
- Eliminar abastecimientos o recargas anteriores.
- Eliminar documentos históricos que deban permanecer asociados al vehículo.
- Modificar los eventos ocurridos durante períodos anteriores.
- Convertir al nuevo propietario en autor de información generada previamente.

Conceptualmente:

```text
CAMBIA EL PROPIETARIO
        ↓
NO CAMBIA LA IDENTIDAD
DEL VEHÍCULO
        ↓
NO SE REINICIA
SU HISTORIAL
```

Las reglas operativas específicas mediante las cuales se determinará la fecha exacta de finalización del período anterior y el inicio del nuevo período serán definidas posteriormente.

---

### 63.4.14 Acceso del propietario actual

Mientras una relación de propiedad se encuentre vigente, el propietario actual podrá acceder a la información y funcionalidades correspondientes a su vehículo de acuerdo con las reglas de permisos, privacidad y visibilidad que posteriormente sean establecidas.

Conceptualmente:

```text
PROPIETARIO ACTUAL
        ↓
RELACIÓN DE PROPIEDAD VIGENTE
        ↓
ACCESO AL VEHÍCULO
        ↓
FUNCIONALIDADES PERMITIDAS
```

La condición de propietario deberá constituir la base de su relación con el vehículo, pero no significa que toda la información existente dentro de Vehículos Services deba ser visible sin restricciones.

Podrán existir posteriormente:

- Información privada de terceros.
- Información protegida de Prestadores de Servicios Vehiculares.
- Información interna.
- Datos sujetos a restricciones.
- Documentos con niveles específicos de acceso.
- Otros elementos cuya visibilidad deba controlarse.

Las reglas definitivas serán desarrolladas posteriormente en los apartados correspondientes a historial, permisos, privacidad y seguridad.

---

### 63.4.15 Acceso del propietario anterior e integridad del historial ante cambios de propietario

Cuando finalice una relación de propiedad, el propietario anterior podrá conservar acceso a la información histórica correspondiente únicamente al período durante el cual el vehículo estuvo bajo su propiedad, de acuerdo con las reglas de visibilidad y permisos que posteriormente sean definidas.

Este acceso tendrá carácter exclusivamente de consulta.

Por lo tanto, una vez finalizado su período de propiedad, el propietario anterior podrá visualizar la información correspondiente a dicho período, pero no podrá editar, modificar, sobrescribir, eliminar o borrar los registros históricos asociados al vehículo.

Conceptualmente:

```text
PROPIETARIO A
        ↓
PERÍODO DE PROPIEDAD
        ↓
EVENTOS DEL PERÍODO
        ↓
VENDE / TRANSFIERE
        ↓
FINALIZA RELACIÓN ACTUAL
        ↓
CONSERVA ACCESO
A SU PERÍODO HISTÓRICO
        ↓
ACCESO SOLO DE CONSULTA
        ↓
PUEDE VISUALIZAR
        ↓
NO PUEDE EDITAR
NO PUEDE MODIFICAR
NO PUEDE SOBRESCRIBIR
NO PUEDE ELIMINAR
NO PUEDE BORRAR
```

Esta restricción deberá aplicar a la información histórica correspondiente al período en el cual fue propietario, incluyendo, cuando existan:

- Mantenimientos.
- Reparaciones.
- Repuestos.
- Kilometrajes.
- Diagnósticos.
- Inspecciones.
- Peritajes.
- Abastecimientos, tanqueos o recargas.
- Registros de consumo.
- Documentos.
- Costos.
- Demás eventos asociados al vehículo durante dicho período.

La conservación del acceso histórico no deberá interpretarse como la conservación de permisos de administración sobre el vehículo.

Por lo tanto:

```text
PROPIETARIO ANTERIOR
        ↓
CONSERVA CONSULTA HISTÓRICA
DE SU PERÍODO
        ≠
CONSERVA CONTROL SOBRE EL VEHÍCULO
```

El propietario anterior tampoco deberá obtener acceso automático a los nuevos eventos generados después de finalizar su relación de propiedad.

Por ejemplo:

```text
PROPIETARIO A
2023 → 2026
        ↓
VENDE EL VEHÍCULO
        ↓
CONSERVA CONSULTA
DE INFORMACIÓN 2023 → 2026

PROPIETARIO B
2026 → ACTUALIDAD
        ↓
NUEVO MANTENIMIENTO
        ↓
PROPIETARIO A
NO OBTIENE ACCESO AUTOMÁTICO
A ESTE NUEVO EVENTO
```

De esta manera, Vehículos Services permitirá que el propietario anterior conserve como referencia la información correspondiente al período durante el cual el vehículo fue suyo, sin permitirle alterar posteriormente dicha información ni acceder automáticamente a la evolución del vehículo bajo propietarios posteriores.

La protección del historial también deberá aplicar al propietario actual.

Cuando un nuevo propietario adquiera el vehículo, el hecho de convertirse en propietario actual no deberá permitirle editar, modificar, sobrescribir, eliminar o borrar arbitrariamente los eventos históricos correspondientes a períodos de propiedad anteriores.

Conceptualmente:

```text
PROPIETARIO A
        ↓
PERÍODO DE PROPIEDAD A
        ↓
EVENTOS HISTÓRICOS A
        ↓
CAMBIO DE PROPIETARIO
        ↓
PROPIETARIO B
        ↓
NUEVO PERÍODO DE PROPIEDAD
        ↓
NO PUEDE ALTERAR
LOS EVENTOS HISTÓRICOS
DEL PERÍODO A
```

Por ejemplo:

```text
2025
PROPIETARIO A
        ↓
CAMBIO DE CORREA
        ↓
EVENTO REGISTRADO

2026
VEHÍCULO VENDIDO
        ↓
PROPIETARIO B
        ↓
EL EVENTO DE 2025
PERMANECE EN EL HISTORIAL
        ↓
PROPIETARIO B
NO PUEDE MODIFICARLO
O ELIMINARLO ARBITRARIAMENTE
```

Por lo tanto, ante un cambio de propietario deberán protegerse ambos lados de la relación histórica:

```text
PROPIETARIO ANTERIOR
        ↓
PUEDE CONSULTAR
SU PERÍODO HISTÓRICO
        ↓
NO PUEDE ALTERARLO

NUEVO PROPIETARIO
        ↓
INICIA SU PROPIO
PERÍODO DE PROPIEDAD
        ↓
NO PUEDE ALTERAR
LOS PERÍODOS ANTERIORES

        ↓

EL HISTORIAL DEL VEHÍCULO
PERMANECE ÍNTEGRO
```

Los eventos históricos deberán permanecer asociados al vehículo y al período en el cual ocurrieron, independientemente de los cambios posteriores de propietario.

Esta protección no significa que un registro histórico nunca pueda requerir una corrección legítima. Sin embargo, cualquier mecanismo que posteriormente permita corregir, anular o ajustar información histórica deberá conservar la trazabilidad necesaria y no deberá funcionar como una modificación o eliminación arbitraria del historial.

Las reglas definitivas relacionadas con:

- Correcciones de información histórica.
- Anulaciones.
- Reclamaciones sobre información registrada.
- Versionamiento.
- Auditoría.
- Trazabilidad de modificaciones.
- Autorizaciones para realizar correcciones.
- Tratamiento de información registrada incorrectamente.
- Demás mecanismos excepcionales sobre registros históricos.

serán desarrolladas posteriormente dentro del apartado correspondiente al historial vehicular.

Por lo tanto, este punto establece únicamente el principio de que el cambio de propietario no deberá permitir que el propietario anterior ni el nuevo propietario alteren arbitrariamente la información histórica del vehículo, manteniendo al mismo tiempo para el propietario anterior el acceso de consulta que corresponda a su propio período de propiedad.

---

### 63.4.16 Protección de información entre propietarios

La conservación de diferentes propietarios históricos no deberá implicar que estos puedan acceder automáticamente a la información personal, privada o empresarial de los demás propietarios.

Vehículos Services deberá mantener separados conceptualmente:

```text
IDENTIDAD DEL PROPIETARIO
        ↓
INFORMACIÓN PRIVADA

RELACIÓN DE PROPIEDAD
        ↓
PERÍODO HISTÓRICO

HISTORIAL DEL VEHÍCULO
        ↓
INFORMACIÓN TÉCNICA
Y EVENTOS DEL VEHÍCULO
```

Por lo tanto, un nuevo propietario no deberá recibir automáticamente información personal o privada del propietario anterior únicamente porque ahora posee el mismo vehículo.

De igual manera, un propietario anterior no deberá recibir información privada del nuevo propietario.

La plataforma deberá conservar la trazabilidad de propiedad necesaria sin exponer información que no sea requerida para comprender el historial del vehículo.

---

### 63.4.17 Usuarios autorizados para vehículos de una persona jurídica o empresa

Vehículos Services deberá diferenciar la gestión de los vehículos dependiendo de si el propietario corresponde a una persona natural o a una persona jurídica o empresa.

Cuando el propietario sea una persona natural, dentro del alcance definido actualmente, no se contempla la existencia de otros usuarios autorizados para administrar los vehículos de su propiedad.

La persona natural propietaria será quien gestione directamente los vehículos asociados a su cuenta.

Conceptualmente:

```text
PERSONA NATURAL
        ↓
PROPIETARIO
        ↓
UNO O VARIOS VEHÍCULOS
        ↓
GESTIONA DIRECTAMENTE
SUS VEHÍCULOS
```

Por lo tanto:

```text
PERSONA NATURAL
        ↓
PROPIETARIO
        ↓
NO ASIGNA OTROS USUARIOS
PARA ADMINISTRAR SUS VEHÍCULOS
```

Cuando el propietario corresponda a una persona jurídica o empresa, el comportamiento será diferente.

Una persona jurídica o empresa podrá ser propietaria de uno o varios vehículos y podrá contar con usuarios autorizados para acceder o gestionar determinados vehículos en representación de la organización.

Conceptualmente:

```text
PERSONA JURÍDICA / EMPRESA
        ↓
PROPIETARIA
        ↓
UNO O VARIOS VEHÍCULOS
        ↓
PUEDE AUTORIZAR USUARIOS
        ↓
USUARIOS AUTORIZADOS
        ↓
ACCEDEN O GESTIONAN
LOS VEHÍCULOS ASIGNADOS
```

La existencia de un usuario autorizado no deberá modificar la propiedad del vehículo.

El vehículo continuará perteneciendo a la persona jurídica o empresa registrada como propietaria, mientras que el usuario autorizado tendrá únicamente las capacidades de acceso o gestión que posteriormente le sean asignadas.

Por lo tanto:

```text
EMPRESA
        ↓
PROPIETARIA DEL VEHÍCULO

USUARIO AUTORIZADO
        ↓
ACCEDE / GESTIONA
EL VEHÍCULO

USUARIO AUTORIZADO
        ≠
PROPIETARIO DEL VEHÍCULO
```

La asignación de un vehículo a un usuario autorizado deberá representar únicamente una autorización de acceso o gestión y no una transferencia de propiedad.

Conceptualmente:

```text
RELACIÓN DE PROPIEDAD
EMPRESA ↔ VEHÍCULO

        ≠

RELACIÓN DE AUTORIZACIÓN
USUARIO ↔ VEHÍCULO
```

Una empresa podrá autorizar a un mismo usuario para gestionar uno o varios de sus vehículos y podrá contar con diferentes usuarios autorizados para diferentes vehículos.

Por ejemplo:

```text
EMPRESA ABC
        ↓
PROPIETARIA
        ↓
┌─────────────────────────────┐
│                             │
↓                             ↓
VEHÍCULO A                VEHÍCULO B
    ↓                         ↓
USUARIO 1                 USUARIO 2
AUTORIZADO                AUTORIZADO
```

En este escenario:

- La Empresa ABC continúa siendo propietaria de los vehículos A y B.
- El Usuario 1 podrá gestionar el Vehículo A de acuerdo con los permisos que posteriormente tenga asignados.
- El Usuario 2 podrá gestionar el Vehículo B de acuerdo con los permisos que posteriormente tenga asignados.
- Ninguno de los usuarios autorizados se convertirá en propietario de los vehículos por el hecho de administrarlos.

Un usuario autorizado tampoco deberá adquirir automáticamente acceso a todos los vehículos pertenecientes a la empresa.

La autorización deberá poder establecerse sobre determinados vehículos, de manera que la existencia de una relación entre un usuario y una empresa no implique por sí sola acceso general a todos los vehículos propiedad de dicha organización.

Conceptualmente:

```text
USUARIO AUTORIZADO
        ↓
VEHÍCULO O VEHÍCULOS
QUE LE SEAN ASIGNADOS

        ≠

ACCESO AUTOMÁTICO
A TODOS LOS VEHÍCULOS
DE LA EMPRESA
```

La empresa podrá posteriormente retirar, cambiar o reasignar las autorizaciones otorgadas a sus usuarios sin que esto modifique la relación de propiedad existente entre la empresa y sus vehículos.

Por lo tanto:

```text
EMPRESA
        ↓
PROPIETARIA DEL VEHÍCULO
        ↓
AUTORIZA USUARIO
        ↓
USUARIO GESTIONA VEHÍCULO
        ↓
SE RETIRA AUTORIZACIÓN
        ↓
EMPRESA CONTINÚA SIENDO
PROPIETARIA DEL VEHÍCULO
```

La creación, modificación o finalización de una autorización de usuario no deberá:

- Cambiar el propietario del vehículo.
- Crear un nuevo período de propiedad.
- Finalizar la relación de propiedad entre la empresa y el vehículo.
- Crear un nuevo vehículo.
- Reiniciar el ciclo de vida digital del vehículo.
- Reiniciar o eliminar su historial.

De esta manera, la propiedad del vehículo deberá permanecer independiente de las personas que una empresa autorice temporalmente para gestionarlo.

Las reglas específicas relacionadas con:

- Creación de usuarios autorizados.
- Vinculación de usuarios con una empresa.
- Validación de que un usuario puede representar a la empresa.
- Asignación de vehículos a usuarios.
- Retiro o reasignación de vehículos.
- Revocación de accesos.
- Roles.
- Permisos.
- Niveles de acceso.
- Funcionalidades disponibles para cada usuario.
- Acceso al historial.
- Registro de eventos.
- Trazabilidad de las acciones realizadas por cada usuario.
- Seguridad y auditoría.

serán definidas posteriormente en los apartados correspondientes a usuarios, relaciones, permisos, historial y seguridad.

Por lo tanto, este punto establece únicamente que:

```text
PERSONA NATURAL
        ↓
GESTIONA DIRECTAMENTE
SUS PROPIOS VEHÍCULOS

PERSONA JURÍDICA / EMPRESA
        ↓
ES PROPIETARIA
DE SUS VEHÍCULOS
        ↓
PUEDE AUTORIZAR USUARIOS
PARA GESTIONARLOS
        ↓
LOS USUARIOS AUTORIZADOS
NO SE CONVIERTEN
EN PROPIETARIOS
```

---

### 63.4.18 Casos especiales de propiedad

Vehículos Services deberá contemplar que podrán existir situaciones de propiedad que no puedan resolverse aplicando directamente las reglas generales definidas para la relación Propietario ↔ Vehículo.

La regla general continuará siendo:

```text
PROPIETARIO REGISTRADO
        ↓
TARJETA DE PROPIEDAD
        ↓
VALIDACIÓN DEL PROPIETARIO
        +
VALIDACIÓN DEL VEHÍCULO
        ↓
RELACIÓN
PROPIETARIO ↔ VEHÍCULO
```

Sin embargo, podrán presentarse casos especiales que requieran validaciones o reglas particulares antes de establecer la relación de propiedad.

Entre estos casos podrán encontrarse:

- Vehículos cuya tarjeta de propiedad registre más de un propietario.
- Diferencias en la identificación, nombre o denominación del propietario que requieran una validación adicional.
- Vehículos pertenecientes a personas jurídicas o empresas que presenten situaciones particulares de representación.
- Cambios o transferencias de propietario que todavía se encuentren en proceso.
- Documentos de propiedad cuya estructura, información o características varíen según el país.
- Vehículos o documentos sometidos a situaciones administrativas particulares.
- Otros casos excepcionales de propiedad que sean identificados posteriormente durante el levantamiento funcional.

La existencia de uno de estos casos no deberá provocar que Vehículos Services asuma automáticamente quién es el propietario ni que establezca una relación de propiedad sin contar con las validaciones correspondientes.

Conceptualmente:

```text
CASO ESPECIAL DE PROPIEDAD
        ↓
NO APLICAR SUPUESTOS
        ↓
REQUIERE TRATAMIENTO
O VALIDACIÓN PARTICULAR
        ↓
DETERMINAR SI PUEDE
ESTABLECERSE LA RELACIÓN
PROPIETARIO ↔ VEHÍCULO
```

La existencia de casos especiales no modifica la regla general de validación de propiedad definida por Vehículos Services.

Las reglas específicas para resolver cada uno de estos escenarios serán definidas posteriormente cuando se realice el levantamiento funcional correspondiente y se determine la información, validaciones y condiciones necesarias para cada caso.

Por lo tanto, este punto únicamente establece que los casos especiales de propiedad deberán ser identificados y tratados de manera particular, evitando establecer relaciones de propiedad mediante supuestos o reglas que todavía no hayan sido definidas.

---

### 63.4.19 Límites de esta definición

La presente definición establece los principios conceptuales de la relación Propietario ↔ Vehículo necesarios para continuar con el levantamiento de Vehículos Services.

En esta etapa se define cómo deberá entenderse la relación de propiedad dentro de la plataforma, pero no se establecen todavía todos los procedimientos, validaciones, excepciones, permisos ni mecanismos técnicos necesarios para su implementación.

Por lo tanto, todavía no se definen en detalle:

- Los campos exactos que deberán extraerse de la tarjeta de propiedad.
- Las reglas exactas de comparación entre la información registrada en Vehículos Services y la información contenida en la tarjeta de propiedad.
- Las tolerancias aplicables a nombres, identificaciones, razones sociales u otros datos utilizados durante la validación.
- La tecnología que será utilizada para capturar, leer o procesar la tarjeta de propiedad.
- Los mecanismos de OCR, reconocimiento documental, inteligencia artificial u otras tecnologías que puedan utilizarse para procesar el documento.
- Las posibles integraciones con fuentes oficiales o externas para complementar o verificar la información.
- Los mecanismos para validar la autenticidad, vigencia o validez de la tarjeta de propiedad.
- Los mecanismos para detectar documentos alterados, falsificados, inválidos o que presenten inconsistencias.
- El tratamiento definitivo de documentos ilegibles, incompletos o cuya información no pueda ser procesada satisfactoriamente.
- Los mecanismos de reintento, revisión o escalamiento cuando una validación no pueda completarse automáticamente.
- Los procesos de revisión manual que puedan ser requeridos.
- El tratamiento definitivo de vehículos cuya tarjeta de propiedad registre más de un propietario.
- Las reglas específicas para cambios o transferencias de propietario que todavía se encuentren en proceso.
- Las particularidades que deberán contemplarse para documentos de propiedad de diferentes países.
- La fecha o condición exacta que determinará el inicio de un período de propiedad dentro de Vehículos Services.
- La fecha o condición exacta que determinará la finalización de un período de propiedad.
- La forma definitiva de establecer el kilometraje inicial y final correspondiente a cada período de propiedad.
- Las reglas operativas y funcionales definitivas para ejecutar un cambio o transferencia de propietario dentro de la plataforma.
- Las reglas para resolver situaciones en las que dos o más actores reclamen simultáneamente la propiedad del mismo vehículo.
- Los mecanismos para corregir una relación Propietario ↔ Vehículo que haya sido establecida incorrectamente.
- Las condiciones y reglas mediante las cuales una relación de propiedad pueda ser anulada, corregida o regularizada sin afectar indebidamente el historial del vehículo.
- Las reglas funcionales específicas para la creación, modificación, asignación, reasignación y finalización de usuarios autorizados asociados a una persona jurídica o empresa.
- Los roles, permisos y niveles de acceso de los usuarios autorizados asociados a una persona jurídica o empresa.
- Las excepciones que puedan existir sobre la visibilidad de información correspondiente a períodos históricos de propiedad.
- Las reglas definitivas de privacidad y protección de información entre propietarios actuales y anteriores.
- Las reglas de modificación, corrección, anulación, versionamiento, auditoría y trazabilidad aplicables a las relaciones históricas de propiedad.
- Los requerimientos técnicos para el almacenamiento, protección, conservación y acceso a las tarjetas de propiedad y demás evidencias utilizadas durante la validación.

Estos elementos deberán desarrollarse posteriormente en los apartados funcionales, reglas de negocio, requerimientos, seguridad, permisos, historial y diseño técnico que correspondan.

Las decisiones posteriores deberán respetar los principios establecidos en esta definición y no deberán provocar:

- La creación de propietarios mediante supuestos no validados.
- La duplicación de un vehículo debido a un cambio de propietario.
- La pérdida o fragmentación de la identidad digital del vehículo.
- La eliminación arbitraria de períodos históricos de propiedad.
- La alteración indebida del historial del vehículo.
- La exposición automática de información personal o privada entre propietarios.
- La conversión de un usuario autorizado en propietario por el solo hecho de gestionar un vehículo.

De esta manera, la relación Propietario ↔ Vehículo queda definida conceptualmente para esta etapa del proyecto, mientras que sus procedimientos detallados, excepciones, controles y mecanismos técnicos serán desarrollados posteriormente en los apartados correspondientes.

---

## 63.5 DEFINIR RELACIÓN PRESTADOR DE SERVICIOS VEHICULARES ↔ VEHÍCULO

### 63.5.1 Concepto de la relación Prestador de Servicios Vehiculares ↔ Vehículo

Dentro de Vehículos Services, la relación Prestador de Servicios Vehiculares ↔ Vehículo representará el vínculo que permite identificar que un Prestador de Servicios Vehiculares se encuentra o se encontró relacionado con un vehículo para la prestación de uno o varios servicios vehiculares.

Esta relación deberá mantenerse conceptualmente separada de la relación de propiedad.

Por lo tanto:

```text
PRESTADOR DE SERVICIOS VEHICULARES
        ↓
SE RELACIONA CON
        ↓
VEHÍCULO

        ≠

PROPIETARIO
        ↓
ES DUEÑO DE
        ↓
VEHÍCULO
```

Que un Prestador de Servicios Vehiculares atienda, revise, diagnostique, inspeccione, evalúe, repare, realice mantenimiento, efectúe un peritaje o preste cualquier otro servicio sobre un vehículo no deberá convertirlo en propietario del vehículo.

La relación deberá permitir representar que diferentes Prestadores de Servicios Vehiculares pueden participar en distintos momentos del ciclo de vida de un mismo vehículo.

Por ejemplo:

```text
VEHÍCULO
        ↓
TALLER MECÁNICO
        ↓
MANTENIMIENTO

        ↓

CENTRO DE DIAGNÓSTICO
        ↓
DIAGNÓSTICO

        ↓

CENTRO DE PERITAJE
        ↓
PERITAJE
```

Todos estos Prestadores de Servicios Vehiculares podrán relacionarse con el mismo vehículo sin modificar su identidad, su propietario ni fragmentar su ciclo de vida digital.

De igual manera, un mismo Prestador de Servicios Vehiculares podrá relacionarse con uno o varios vehículos a lo largo del tiempo.

Conceptualmente:

```text
PRESTADOR DE SERVICIOS VEHICULARES
        ↓
┌───────────────────────────────┐
│               │               │
↓               ↓               ↓
VEHÍCULO A      VEHÍCULO B      VEHÍCULO C
```

La existencia de una relación Prestador de Servicios Vehiculares ↔ Vehículo deberá mantenerse diferenciada de los servicios o eventos específicos realizados sobre el vehículo.

Por lo tanto:

```text
RELACIÓN PRESTADOR ↔ VEHÍCULO
        ≠
SERVICIO O EVENTO REALIZADO
```

La relación identifica el vínculo existente entre el Prestador de Servicios Vehiculares y el vehículo.

El servicio o evento representa una actuación concreta realizada sobre dicho vehículo, como por ejemplo:

- Un mantenimiento.
- Una reparación.
- Un diagnóstico.
- Una inspección.
- Una revisión.
- Una evaluación.
- Un peritaje.
- La instalación o sustitución de un repuesto.
- Otro servicio vehicular que posteriormente sea definido.

Un mismo Prestador de Servicios Vehiculares podrá realizar diferentes servicios o generar diferentes eventos sobre un mismo vehículo sin que sea necesario interpretar cada evento como un vehículo diferente o como una nueva relación de propiedad.

Conceptualmente:

```text
PRESTADOR
        ↓
RELACIÓN CON EL VEHÍCULO
        ↓
VEHÍCULO
        ↓
┌───────────────────────────────┐
│               │               │
↓               ↓               ↓
SERVICIO 1      SERVICIO 2      SERVICIO 3
        ↓
EVENTOS DEL VEHÍCULO
        ↓
HISTORIAL
```

Cuando corresponda, los servicios o eventos realizados por un Prestador de Servicios Vehiculares deberán conservar la identificación del prestador que participó en ellos, con el propósito de mantener la trazabilidad sobre el origen de la información incorporada al historial del vehículo.

Cuando el servicio haya sido realizado desde una sede específica, también deberá poder conservarse la identificación de la sede correspondiente, de acuerdo con las reglas que posteriormente sean definidas.

La participación de diferentes prestadores o sedes no deberá dividir, reiniciar, reemplazar ni crear historiales independientes para el mismo vehículo.

El historial deberá continuar asociado a la identidad del vehículo.

Por lo tanto:

```text
UN VEHÍCULO
        ↓
DIFERENTES PRESTADORES
        ↓
DIFERENTES SERVICIOS Y EVENTOS
        ↓
UN MISMO CICLO DE VIDA DIGITAL
        ↓
UN HISTORIAL CONTINUO
```

La existencia de la relación Prestador de Servicios Vehiculares ↔ Vehículo tampoco deberá significar automáticamente que el prestador tenga acceso irrestricto a toda la información del vehículo.

La relación, la autorización y los permisos deberán entenderse como conceptos diferentes.

Conceptualmente:

```text
EXISTE RELACIÓN
PRESTADOR ↔ VEHÍCULO
        ≠
ACCESO IRRESTRICTO
A LA INFORMACIÓN
```

El acceso para consultar, registrar o gestionar información del vehículo dependerá de las autorizaciones, permisos, roles, condiciones de seguridad y reglas funcionales que posteriormente sean definidas.

De igual manera, la finalización de una autorización o de una relación activa entre el Prestador de Servicios Vehiculares y el vehículo no deberá eliminar los eventos históricos que hayan sido registrados legítimamente durante dicha relación.

Por ejemplo:

```text
PRESTADOR A
        ↓
REALIZA SERVICIO
        ↓
SE GENERA EVENTO
        ↓
EVENTO SE INCORPORA
AL HISTORIAL
        ↓
FINALIZA POSTERIORMENTE
LA RELACIÓN O AUTORIZACIÓN
        ↓
EL EVENTO HISTÓRICO
SE CONSERVA
```

Esto permitirá diferenciar claramente cuatro conceptos:

```text
PRESTADOR DE SERVICIOS VEHICULARES
        ↓
Entidad que presta el servicio

RELACIÓN PRESTADOR ↔ VEHÍCULO
        ↓
Vínculo existente entre el prestador
y un vehículo

AUTORIZACIÓN / PERMISOS
        ↓
Determinan qué puede consultar,
registrar o gestionar el prestador

SERVICIO / EVENTO
        ↓
Actuación concreta realizada
sobre el vehículo
        ↓
HISTORIAL DEL VEHÍCULO
```

La relación Prestador de Servicios Vehiculares ↔ Vehículo deberá, por lo tanto, permitir representar la participación de los diferentes prestadores durante el ciclo de vida del vehículo sin confundir dicha participación con propiedad, sin otorgar acceso automático a toda la información y sin fragmentar la identidad ni el historial del vehículo.

Las reglas específicas para establecer, autorizar, modificar, finalizar o revocar esta relación, así como sus permisos, niveles de acceso, temporalidad y demás condiciones funcionales, serán desarrolladas en los siguientes puntos de esta definición.

---
### 63.5.2 Establecimiento, autorización y alcance de la relación Prestador de Servicios Vehiculares ↔ Vehículo

La relación entre un Prestador de Servicios Vehiculares y un vehículo no deberá establecerse automáticamente por el simple hecho de que el prestador se encuentre registrado, verificado, disponible u operativo dentro de Vehículos Services.

Para que un Prestador de Servicios Vehiculares pueda relacionarse con un vehículo deberá existir una acción o condición válida que permita establecer dicha relación.

Inicialmente se contemplan dos mecanismos conceptuales para iniciar esta relación:

```text
OPCIÓN 1

PROPIETARIO
        ↓
SELECCIONA UN VEHÍCULO
        ↓
AUTORIZA A UN PRESTADOR
        ↓
SE ESTABLECE LA RELACIÓN
PRESTADOR ↔ VEHÍCULO
```

o:

```text
OPCIÓN 2

PRESTADOR
        ↓
SOLICITA RELACIONARSE
CON UN VEHÍCULO
        ↓
PROPIETARIO
REVISA LA SOLICITUD
        ↓
¿ACEPTA?
   │
   ├── SÍ
   │    ↓
   │  SE ESTABLECE
   │  LA RELACIÓN
   │
   └── NO
        ↓
      NO SE ESTABLECE
      LA RELACIÓN
```

En ambos escenarios, el propietario deberá conservar el control sobre la autorización de la relación entre su vehículo y un Prestador de Servicios Vehiculares.

Una solicitud realizada por un prestador no deberá otorgarle acceso al vehículo mientras no haya sido aceptada mediante el mecanismo correspondiente.

Por lo tanto:

```text
SOLICITUD DE RELACIÓN
        ≠
RELACIÓN ACTIVA
```

y:

```text
SOLICITUD PENDIENTE
        ↓
NO OTORGA ACCESO
AL VEHÍCULO
```

Cuando la autorización correspondiente haya sido otorgada, la relación podrá considerarse activa dentro de Vehículos Services.

Conceptualmente:

```text
PROPIETARIO
        ↓
AUTORIZACIÓN VÁLIDA
        ↓
PRESTADOR ↔ VEHÍCULO
        ↓
RELACIÓN ACTIVA
```

La existencia de una relación activa permitirá que el Prestador de Servicios Vehiculares participe sobre el vehículo dentro de las funcionalidades que posteriormente le sean habilitadas de acuerdo con las autorizaciones, permisos y reglas aplicables.

Sin embargo:

```text
RELACIÓN ACTIVA
        ≠
ACCESO IRRESTRICTO
AL VEHÍCULO
```

La relación deberá representar el vínculo autorizado entre el prestador y el vehículo, pero no deberá interpretarse como autorización automática para consultar o gestionar toda la información existente sobre este.

El acceso efectivo a información y funcionalidades deberá depender adicionalmente de los permisos, roles, reglas de visibilidad y demás condiciones que correspondan.

Conceptualmente:

```text
RELACIÓN ACTIVA
        ↓
HABILITA LA POSIBILIDAD
DE INTERACTUAR CON EL VEHÍCULO
        ↓
SEGÚN
AUTORIZACIONES + PERMISOS
+ REGLAS DE VISIBILIDAD
```

Por lo tanto, deberán mantenerse diferenciados los siguientes conceptos:

```text
RELACIÓN
        ↓
Determina la existencia
del vínculo autorizado
Prestador ↔ Vehículo

PERMISOS
        ↓
Determinan qué acciones
puede realizar

VISIBILIDAD
        ↓
Determina qué información
puede consultar
```

Estos conceptos deberán trabajar conjuntamente, pero no deberán considerarse equivalentes.

La relación deberá establecerse individualmente para cada vehículo.

Por ejemplo:

```text
PROPIETARIO
        │
        ├── VEHÍCULO A
        │       ↕
        │   PRESTADOR X
        │   RELACIÓN ACTIVA
        │
        └── VEHÍCULO B
                ↓
            SIN RELACIÓN
            CON PRESTADOR X
```

La existencia de una relación entre el Prestador X y el Vehículo A no deberá crear automáticamente una relación con el Vehículo B aunque ambos pertenezcan al mismo propietario.

De igual manera, un mismo vehículo podrá mantener relaciones con diferentes Prestadores de Servicios Vehiculares cuando corresponda.

Por ejemplo:

```text
VEHÍCULO
    │
    ├── PRESTADOR A
    │
    ├── PRESTADOR B
    │
    └── PRESTADOR C
```

Cada relación deberá mantenerse identificada de manera independiente.

La existencia simultánea de varias relaciones no deberá implicar que los diferentes prestadores adquieran acceso entre sí a la información que cada uno genere.

Las reglas específicas de visibilidad sobre el historial vehicular deberán regirse por el apartado correspondiente a visibilidad y acceso a la información del historial, evitando redefinirlas dentro de este punto.

La relación tampoco deberá otorgar derechos de propiedad sobre el vehículo ni convertir al Prestador de Servicios Vehiculares en propietario, administrador general o representante del propietario.

Por lo tanto:

```text
RELACIÓN
PRESTADOR ↔ VEHÍCULO
        ≠
PROPIEDAD DEL VEHÍCULO
```

La finalidad de esta relación será permitir que Vehículos Services identifique qué Prestadores de Servicios Vehiculares se encuentran autorizados para interactuar con determinado vehículo dentro de los límites funcionales correspondientes.

La vigencia, finalización, reactivación y demás cambios de estado de esta relación deberán regirse por el apartado correspondiente al ciclo de vida de la relación Prestador ↔ Vehículo.

Como principio general:

```text
PRESTADOR
        ↓
SOLICITUD / AUTORIZACIÓN
        ↓
RELACIÓN CON
UN VEHÍCULO ESPECÍFICO
        ↓
RELACIÓN ACTIVA
        ↓
INTERACCIÓN PERMITIDA
SEGÚN AUTORIZACIONES,
PERMISOS Y VISIBILIDAD
```

La definición detallada de permisos, información visible, acceso al historial, roles, seguridad y demás controles deberá desarrollarse o mantenerse en los componentes funcionales correspondientes.

---
### 63.5.3 Vigencia, finalización y reactivación de la relación Prestador de Servicios Vehiculares ↔ Vehículo

La relación entre un Prestador de Servicios Vehiculares y un vehículo deberá permitir determinar si actualmente existe una autorización que habilite al prestador para interactuar con dicho vehículo dentro de Vehículos Services.

Conceptualmente, deberán diferenciarse como mínimo las siguientes situaciones:

```text
RELACIÓN PRESTADOR ↔ VEHÍCULO
        ↓
┌───────────────────────┐
│                       │
ACTIVA               INACTIVA
│                       │
↓                       ↓
EXISTE                NO EXISTE
AUTORIZACIÓN          AUTORIZACIÓN
VIGENTE               ACTIVA
```

Una relación activa permitirá al Prestador de Servicios Vehiculares interactuar con el vehículo dentro de las funcionalidades que le correspondan de acuerdo con las autorizaciones, permisos y reglas aplicables.

La existencia de una relación activa no deberá significar acceso irrestricto al vehículo ni a su historial.

Las reglas específicas relacionadas con la información que podrá consultar el prestador deberán mantenerse en los componentes correspondientes a visibilidad, acceso y permisos.

La relación deberá poder cambiar de estado a lo largo del tiempo sin perder la trazabilidad de los diferentes períodos durante los cuales estuvo activa o inactiva.

Conceptualmente:

```text
RELACIÓN CREADA
        ↓
ACTIVA
        ↓
FINALIZADA
        ↓
INACTIVA
        ↓
POSIBLE NUEVA AUTORIZACIÓN
        ↓
ACTIVA NUEVAMENTE
```

La reactivación posterior no deberá eliminar ni reemplazar los períodos anteriores de la relación.

#### Finalización de la relación

La relación entre un Prestador de Servicios Vehiculares y un vehículo podrá finalizar por decisión del propietario o del propio prestador.

Conceptualmente:

```text
RELACIÓN ACTIVA
        ↓
PUEDE SER FINALIZADA POR
        ↓
┌──────────────────────────┐
│                          │
PROPIETARIO            PRESTADOR
│                          │
└────────────┬─────────────┘
             ↓
      RELACIÓN INACTIVA
```

La finalización realizada por cualquiera de las partes deberá afectar la relación existente dentro de Vehículos Services.

Cuando la relación deje de estar activa, el Prestador de Servicios Vehiculares deberá dejar de estar autorizado para interactuar con el vehículo mediante las funcionalidades que dependan de dicha relación.

Conceptualmente:

```text
RELACIÓN ACTIVA
        ↓
INTERACCIÓN AUTORIZADA
SEGÚN REGLAS Y PERMISOS
        ↓
FINALIZA LA RELACIÓN
        ↓
RELACIÓN INACTIVA
        ↓
FINALIZA LA AUTORIZACIÓN
DEPENDIENTE DE ESA RELACIÓN
```

La finalización de la relación dentro de Vehículos Services no deberá interpretarse automáticamente como:

- Cancelación de obligaciones comerciales existentes entre las partes.
- Terminación de garantías asociadas a servicios previamente realizados.
- Cancelación de compromisos contractuales externos a la plataforma.
- Eliminación de servicios previamente realizados.
- Eliminación de registros históricos.
- Eliminación de la identificación del prestador que participó en eventos anteriores.

Vehículos Services deberá diferenciar la relación funcional existente dentro de la plataforma de las obligaciones comerciales, contractuales, legales o de garantía que puedan existir externamente entre el propietario y el prestador.

Por lo tanto:

```text
FINALIZAR RELACIÓN
EN VEHÍCULOS SERVICES
        ≠
ELIMINAR O CANCELAR
OBLIGACIONES EXTERNAS
ENTRE LAS PARTES
```

La finalización de una relación tampoco deberá eliminar los eventos, intervenciones o registros que hayan sido incorporados legítimamente al historial del vehículo durante el período en que dicha relación estuvo activa.

Conceptualmente:

```text
PRESTADOR
        ↓
RELACIÓN ACTIVA
        ↓
REALIZA INTERVENCIONES
        ↓
SE GENERAN REGISTROS
        ↓
FINALIZA LA RELACIÓN
        ↓
LOS REGISTROS
PERMANECEN ASOCIADOS
AL VEHÍCULO
```

Por lo tanto:

```text
FINALIZAR RELACIÓN
        ≠
ELIMINAR HISTORIAL
```

La conservación de dichos registros no deberá interpretarse como conservación permanente de acceso por parte del prestador.

Las reglas específicas sobre qué información podrá consultar un prestador mientras exista una relación activa, qué accesos perderá cuando finalice y bajo qué condiciones podrá recuperar acceso posteriormente deberán regirse por los apartados correspondientes a visibilidad, acceso y permisos.

#### Reactivación de la relación

Una relación previamente finalizada podrá establecerse nuevamente cuando exista una nueva autorización válida.

La reactivación no deberá producirse automáticamente por el simple hecho de que el prestador haya tenido anteriormente una relación con el vehículo.

Por lo tanto:

```text
RELACIÓN ANTERIOR
        ↓
FINALIZADA
        ↓
NO SE REACTIVA
AUTOMÁTICAMENTE
```

Para que exista nuevamente una relación activa deberá cumplirse el mecanismo de autorización correspondiente.

Conceptualmente:

```text
RELACIÓN INACTIVA
        ↓
NUEVA AUTORIZACIÓN VÁLIDA
        ↓
RELACIÓN ACTIVA
NUEVAMENTE
```

La nueva relación deberá conservar la trazabilidad de los períodos anteriores.

Por ejemplo:

```text
PRESTADOR A ↔ VEHÍCULO

Período 1:
ACTIVA
01/02/2026
        ↓
FINALIZA
30/04/2026

Período 2:
NUEVA AUTORIZACIÓN
15/08/2026
        ↓
ACTIVA NUEVAMENTE
```

Vehículos Services no deberá representar este escenario como si la relación hubiera permanecido activa de manera continua entre ambos períodos.

Conceptualmente:

```text
PERÍODO ACTIVO 1
        ↓
PERÍODO INACTIVO
        ↓
PERÍODO ACTIVO 2
```

Esto permitirá conservar la evolución real de la relación Prestador de Servicios Vehiculares ↔ Vehículo.

La reactivación tampoco deberá crear una nueva identidad para el prestador, para el vehículo ni para los registros históricos existentes.

Por lo tanto:

```text
REACTIVAR RELACIÓN
        ≠
CREAR NUEVO PRESTADOR

REACTIVAR RELACIÓN
        ≠
CREAR NUEVO VEHÍCULO

REACTIVAR RELACIÓN
        ≠
CREAR NUEVO HISTORIAL
```

Los registros históricos generados durante los diferentes períodos deberán continuar asociados al mismo vehículo y conservar la identificación del prestador que participó en ellos.

La posibilidad de consultar nuevamente información histórica después de una reactivación deberá depender de las reglas de visibilidad, acceso y permisos correspondientes y no deberá redefinirse dentro de este punto.

#### Trazabilidad de los períodos de relación

Vehículos Services deberá conservar la trazabilidad de los diferentes períodos durante los cuales haya existido una relación entre un prestador y un vehículo.

Conceptualmente:

```text
PRESTADOR A
        ↕
VEHÍCULO
        │
        ├── Período activo 1
        ├── Período inactivo
        └── Período activo 2
```

La existencia de varios períodos no deberá generar relaciones históricas desconectadas ni eliminar la información correspondiente a períodos anteriores.

La plataforma deberá poder determinar que el mismo prestador estuvo relacionado con el mismo vehículo en diferentes momentos.

Como principio general:

```text
RELACIÓN
PRESTADOR ↔ VEHÍCULO
        ↓
PUEDE ESTAR
ACTIVA O INACTIVA
        ↓
PUEDE FINALIZAR
        ↓
PUEDE ESTABLECERSE
NUEVAMENTE
        ↓
SE CONSERVAN LOS
PERÍODOS DE RELACIÓN
        ↓
LOS EVENTOS HISTÓRICOS
NO SE ELIMINAN
```

Los estados técnicos definitivos de la relación, motivos de finalización, notificaciones, procedimientos de autorización y reactivación, controles adicionales y demás comportamientos específicos deberán desarrollarse posteriormente en los componentes funcionales correspondientes.

---

### 63.5.4 Comportamiento de la relación Prestador de Servicios Vehiculares ↔ Vehículo ante un cambio de propietario

Cuando un vehículo cambie de propietario, las relaciones activas existentes entre dicho vehículo y los Prestadores de Servicios Vehiculares deberán finalizar.

Esto se debe a que las autorizaciones existentes fueron otorgadas dentro del contexto de la relación con el propietario anterior y no deberán transferirse automáticamente al nuevo propietario.

Conceptualmente:

```text
PROPIETARIO A
        ↓
VEHÍCULO
        ↕
PRESTADOR A
RELACIÓN ACTIVA
        ↓
CAMBIO DE PROPIETARIO
        ↓
PROPIETARIO B
        ↓
MISMO VEHÍCULO
        ↓
RELACIÓN CON PRESTADOR A
DEJA DE ESTAR ACTIVA
```

Por lo tanto:

```text
CAMBIO DE PROPIETARIO
        ↓
FINALIZAN LAS RELACIONES
ACTIVAS CON PRESTADORES
        ↓
LAS AUTORIZACIONES
ANTERIORES NO SE TRANSFIEREN
AL NUEVO PROPIETARIO
```

Esta regla deberá aplicar a todas las relaciones activas que existan entre el vehículo y Prestadores de Servicios Vehiculares al momento del cambio de propietario.

Por ejemplo:

```text
PROPIETARIO A
        ↓
VEHÍCULO
        │
        ├── PRESTADOR A
        │   Relación activa
        │
        ├── PRESTADOR B
        │   Relación activa
        │
        └── PRESTADOR C
            Relación activa

        ↓
CAMBIO DE PROPIETARIO
        ↓

PROPIETARIO B
        ↓
MISMO VEHÍCULO
        │
        ├── PRESTADOR A
        │   Relación inactiva
        │
        ├── PRESTADOR B
        │   Relación inactiva
        │
        └── PRESTADOR C
            Relación inactiva
```

El cambio de propietario no deberá requerir que el nuevo propietario conserve, acepte o herede las relaciones que habían sido autorizadas por el propietario anterior.

Por lo tanto:

```text
RELACIONES AUTORIZADAS
POR PROPIETARIO A
        ≠
RELACIONES AUTOMÁTICAMENTE
AUTORIZADAS POR PROPIETARIO B
```

El nuevo propietario deberá tener la capacidad de decidir con qué Prestadores de Servicios Vehiculares desea establecer relaciones sobre el vehículo.

Podrá:

- Establecer relaciones con nuevos prestadores.
- Establecer nuevamente una relación con uno o varios prestadores que estuvieron relacionados anteriormente con el vehículo.
- No establecer relación con ninguno de los prestadores anteriores.

Por ejemplo:

```text
PROPIETARIO A
        ↓
VEHÍCULO
        │
        ├── PRESTADOR A
        └── PRESTADOR B
        ↓
CAMBIO DE PROPIETARIO
        ↓
FINALIZAN RELACIONES
CON A Y B
        ↓
PROPIETARIO B
        │
        ├── Autoriza nuevamente
        │   PRESTADOR A
        │
        └── No autoriza
            PRESTADOR B
```

En este escenario, únicamente deberá establecerse nuevamente la relación correspondiente al Prestador A.

La existencia de una relación anterior entre un prestador y el vehículo no deberá constituir por sí misma una autorización válida otorgada por el nuevo propietario.

Conceptualmente:

```text
PRESTADOR
TUVO RELACIÓN ANTERIOR
CON EL VEHÍCULO
        ≠
TIENE RELACIÓN ACTIVA
CON EL NUEVO PROPIETARIO
```

Si el nuevo propietario desea continuar utilizando un Prestador de Servicios Vehiculares que anteriormente estuvo relacionado con el vehículo, deberá establecerse una nueva autorización siguiendo las reglas correspondientes a la relación Prestador de Servicios Vehiculares ↔ Vehículo.

Conceptualmente:

```text
CAMBIO DE PROPIETARIO
        ↓
RELACIÓN ANTERIOR
FINALIZA
        ↓
NUEVO PROPIETARIO
DECIDE AUTORIZAR
AL MISMO PRESTADOR
        ↓
NUEVA AUTORIZACIÓN
        ↓
RELACIÓN ACTIVA
NUEVAMENTE
```

Esta nueva autorización deberá considerarse un nuevo período de relación y no la continuación ininterrumpida de la autorización otorgada por el propietario anterior.

Por ejemplo:

```text
PRESTADOR A ↔ VEHÍCULO

PROPIETARIO A
        ↓
RELACIÓN ACTIVA
        ↓
CAMBIO DE PROPIETARIO
        ↓
RELACIÓN FINALIZA

PROPIETARIO B
        ↓
NUEVA AUTORIZACIÓN
        ↓
RELACIÓN ACTIVA
NUEVAMENTE
```

La plataforma deberá conservar la trazabilidad de estos diferentes períodos de relación.

El cambio de propietario y la finalización de las relaciones activas no deberán eliminar, modificar ni desvincular los eventos históricos que hayan sido legítimamente registrados sobre el vehículo.

Por lo tanto:

```text
CAMBIO DE PROPIETARIO
        ↓
FINALIZAN RELACIONES
ACTIVAS CON PRESTADORES
        ↓
PERO
        ↓
LOS EVENTOS HISTÓRICOS
DEL VEHÍCULO
SE CONSERVAN
```

Los servicios e intervenciones realizados anteriormente deberán continuar asociados al mismo vehículo y conservar la identificación del Prestador de Servicios Vehiculares que participó en ellos cuando corresponda.

Conceptualmente:

```text
RELACIÓN ACTIVA
        ↓
PUEDE FINALIZAR

EVENTO HISTÓRICO
LEGÍTIMAMENTE REGISTRADO
        ↓
PERMANECE ASOCIADO
AL VEHÍCULO
```

La aparición de un Prestador de Servicios Vehiculares dentro de un registro histórico no deberá interpretarse como evidencia de que actualmente mantiene una relación activa con el vehículo.

Por ejemplo:

```text
HISTORIAL
        ↓
2025
Mantenimiento realizado
por PRESTADOR A

ESTADO ACTUAL
        ↓
PRESTADOR A
SIN RELACIÓN ACTIVA
```

Por lo tanto:

```text
APARECER EN EL HISTORIAL
        ≠
TENER RELACIÓN ACTIVA
ACTUALMENTE
```

La conservación de estos registros deberá mantener la continuidad del historial del vehículo, pero las reglas relacionadas con quién puede consultarlos deberán regirse por los apartados correspondientes a historial, visibilidad, acceso, privacidad y permisos.

De igual manera, si un prestador es autorizado nuevamente por el nuevo propietario, las reglas sobre qué información histórica podrá consultar deberán regirse por dichos componentes y no por el simple hecho de haber tenido una relación anterior.

Como principio general:

```text
CAMBIO DE PROPIETARIO
        ↓
FINALIZAN RELACIONES
PRESTADOR ↔ VEHÍCULO
EXISTENTES
        ↓
NO SE TRANSFIEREN
AUTORIZACIONES
        ↓
NUEVO PROPIETARIO
DECIDE SUS RELACIONES
        ↓
PUEDEN ESTABLECERSE
NUEVAS AUTORIZACIONES
        ↓
LOS PERÍODOS DE RELACIÓN
SE CONSERVAN
        ↓
EL HISTORIAL DEL VEHÍCULO
NO SE ELIMINA
```

Las reglas específicas relacionadas con el acceso al historial por parte del propietario actual, propietarios anteriores o Prestadores de Servicios Vehiculares deberán mantenerse en los componentes correspondientes y no redefinirse dentro de este punto.

---
## 63.6 HISTORIAL VEHICULAR
### 63.6.1 Concepto y propósito del historial vehicular

Dentro de Vehículos Services, el historial vehicular representará el conjunto estructurado y trazable de información, registros, eventos, documentos e interacciones asociados a un vehículo durante su ciclo de vida dentro de la plataforma.

El historial deberá mantenerse asociado a la identidad del vehículo y no deberá limitarse únicamente a los mantenimientos, reparaciones o servicios realizados por Prestadores de Servicios Vehiculares.

Conceptualmente:

```text
VEHÍCULO
        ↓
DURANTE SU CICLO DE VIDA
SE GENERA Y REGISTRA INFORMACIÓN
        ↓
MANTENIMIENTOS
REPARACIONES
REPUESTOS
KILOMETRAJE
PÓLIZAS DE SEGUROS
SOAT
IMPUESTOS
REVISIONES
DIAGNÓSTICOS
PERITAJES
DOCUMENTOS
FACTURAS
EVIDENCIAS
OTROS REGISTROS E INTERACCIONES
        ↓
HISTORIAL VEHICULAR
```

El historial deberá permitir representar de manera integral la vida registrada del vehículo dentro de Vehículos Services, conservando la información relevante que se vaya generando o incorporando sobre este a lo largo del tiempo.

Por lo tanto:

```text
HISTORIAL VEHICULAR
        ≠
HISTORIAL DE MANTENIMIENTO
```

Los mantenimientos serán solamente uno de los diferentes tipos de información que podrán formar parte del historial.

El historial podrá contener información relacionada con el cuidado, mantenimiento, operación, documentación, seguros, obligaciones y demás aspectos asociados al vehículo que sean contemplados por Vehículos Services.

Cuando una misma clase de información tenga diferentes registros a lo largo del tiempo, el historial deberá permitir conservar su evolución histórica y no únicamente su estado o registro más reciente.

Por ejemplo, las diferentes pólizas de seguro de un vehículo deberán poder conservarse históricamente:

```text
PÓLIZA DE SEGURO 2025
        ↓
PÓLIZA DE SEGURO 2026
        ↓
PÓLIZA DE SEGURO 2027
        ↓
TODAS PERMANECEN COMO PARTE
DEL HISTORIAL DEL VEHÍCULO
```

La misma lógica podrá aplicarse a otros registros cuya información evolucione o se renueve con el tiempo.

Por ejemplo:

```text
SOAT 2025
        ↓
SOAT 2026
        ↓
SOAT 2027
        ↓
SE CONSERVA LA TRAZABILIDAD
DE CADA PERIODO
```

```text
IMPUESTO VEHICULAR 2025
        ↓
IMPUESTO VEHICULAR 2026
        ↓
IMPUESTO VEHICULAR 2027
        ↓
SE CONSERVAN LOS REGISTROS
DE CADA AÑO
```

También deberán conservarse los eventos que ocurran durante la vida del vehículo y que no correspondan necesariamente a documentos con vigencia.

Por ejemplo:

```text
MANTENIMIENTO
10/01/2026
        ↓
CAMBIO DE REPUESTO
15/03/2026
        ↓
ACTUALIZACIÓN DE KILOMETRAJE
20/04/2026
        ↓
REPARACIÓN
05/06/2026
        ↓
NUEVO MANTENIMIENTO
10/09/2026
```

Estos registros deberán permanecer asociados al vehículo y formar parte de la construcción progresiva de su historial.

De esta manera, la incorporación de un nuevo registro no deberá provocar automáticamente la eliminación o sustitución histórica de los registros anteriores.

Este principio podrá aplicarse, según corresponda a la naturaleza de cada información, a pólizas de seguros, SOAT o documentos equivalentes, impuestos, revisiones técnico-mecánicas, kilometraje, mantenimientos, reparaciones, repuestos y demás registros que formen parte del historial.

El historial deberá conservar su continuidad alrededor de la identidad del vehículo.

Por ejemplo:

```text
PROPIETARIO A
        ↓
VEHÍCULO
        ↓
HISTORIAL ACUMULADO
        ↓
CAMBIO DE PROPIETARIO
        ↓
PROPIETARIO B
        ↓
MISMO VEHÍCULO
        ↓
EL HISTORIAL CONTINÚA
```

De igual manera:

```text
PRESTADOR A
        ↓
REALIZA INTERVENCIÓN
        ↓
PRESTADOR B
        ↓
REALIZA OTRA INTERVENCIÓN
        ↓
AMBAS PERMANECEN ASOCIADAS
AL HISTORIAL DEL MISMO VEHÍCULO
```

Los cambios de propietario, Prestadores de Servicios Vehiculares, sedes u otros actores relacionados con el vehículo no deberán fragmentar, reiniciar ni crear automáticamente un nuevo historial para el mismo vehículo.

Cuando un registro haya sido generado o se encuentre relacionado con un actor determinado, deberá conservarse la referencia histórica correspondiente cuando aplique, con el propósito de mantener la trazabilidad sobre el origen de la información.

La permanencia de un registro dentro del historial no deberá significar que todos los actores relacionados con el vehículo puedan consultarlo. La existencia de la información, su conservación histórica y los permisos para acceder a ella deberán entenderse como conceptos diferentes.

Las reglas específicas relacionadas con los tipos de información que conformarán el historial, su organización, temporalidad, visualización, permisos, privacidad, corrección, anulación, versionamiento, auditoría y demás tratamientos serán desarrolladas en los siguientes puntos de esta definición.

---
### 63.6.2 Tipos de información y registros que conforman el historial vehicular

El historial vehicular deberá consolidar de manera estructurada la información, eventos, registros e interacciones asociados al vehículo durante su ciclo de vida dentro de Vehículos Services.

El historial no deberá limitarse exclusivamente a mantenimientos, reparaciones o servicios realizados por Prestadores de Servicios Vehiculares. Su propósito será representar de manera integral la vida registrada del vehículo, incluyendo información relacionada con su situación legal, documental y administrativa, cuidado, mantenimiento, operación, uso y demás acontecimientos relevantes.

Conceptualmente:

```text
VEHÍCULO
   │
   ├── Información legal, documental y administrativa
   ├── Mantenimientos
   ├── Reparaciones
   ├── Repuestos
   ├── Diagnósticos
   ├── Inspecciones
   ├── Kilometraje
   ├── Abastecimientos / Recargas
   ├── Preparaciones y verificaciones
   ├── Documentos y evidencias
   └── Otros registros e interacciones
                ↓
        HISTORIAL VEHICULAR
```

Estas agrupaciones deberán entenderse como categorías o familias de información dentro de un mismo historial y no como historiales independientes.

Por lo tanto:

```text
MANTENIMIENTOS
      +
PÓLIZAS
      +
KILOMETRAJE
      +
IMPUESTOS
      +
REPARACIONES
      +
ABASTECIMIENTOS
      +
OTROS REGISTROS
      ↓
UN ÚNICO HISTORIAL
DEL VEHÍCULO
```

La información legal, documental y administrativa del vehículo podrá formar parte del historial cuando corresponda.

Esta información podrá contemplar, entre otros:

- SOAT o su equivalente según el país.
- Revisión técnico-mecánica o su equivalente.
- Impuestos asociados al vehículo.
- Pólizas de seguros.
- Vigencias y renovaciones.
- Otros registros legales, documentales o administrativos que posteriormente sean definidos.

El registro de esta información deberá permitir conservar su evolución histórica.

Por ejemplo:

```text
PÓLIZA 2025
    ↓
PÓLIZA 2026
    ↓
PÓLIZA 2027
```

Los diferentes registros deberán poder permanecer asociados al mismo vehículo como parte de su evolución histórica, de acuerdo con la naturaleza de la información correspondiente.

La información relacionada con el cuidado, mantenimiento e intervención del vehículo también podrá formar parte del historial.

Esta información podrá contemplar, entre otros:

- Mantenimientos.
- Reparaciones.
- Repuestos instalados o sustituidos.
- Diagnósticos.
- Inspecciones.
- Revisiones.
- Evaluaciones.
- Peritajes.
- Servicios realizados sobre el vehículo.
- Observaciones relacionadas con las intervenciones.
- Recomendaciones cuando corresponda.
- Costos asociados cuando aplique.
- Otros eventos de cuidado o intervención que posteriormente sean definidos.

Conceptualmente:

```text
VEHÍCULO
   │
   ├── Mantenimiento
   ├── Reparación
   ├── Diagnóstico
   ├── Inspección
   ├── Evaluación
   ├── Peritaje
   └── Otros servicios
           ↓
    HISTORIAL VEHICULAR
```

La incorporación de un nuevo evento no deberá eliminar automáticamente los eventos anteriores.

Los campos específicos, obligatoriedad, reglas y demás características propias de cada tipo de intervención deberán definirse posteriormente en sus componentes funcionales correspondientes.

La información relacionada con el uso y operación del vehículo también podrá formar parte del historial.

Esta información podrá contemplar:

- Registros de kilometraje.
- Evolución del kilometraje.
- Abastecimientos o tanqueos para vehículos que utilicen combustible.
- Recargas para vehículos eléctricos.
- Información relacionada con consumo de combustible o energía.
- Fechas asociadas.
- Otros registros operativos que posteriormente sean definidos.

Conceptualmente:

```text
VEHÍCULO
   │
   ├── KILOMETRAJE
   ├── ABASTECIMIENTOS / TANQUEOS
   ├── RECARGAS ELÉCTRICAS
   └── CONSUMO
           ↓
   INFORMACIÓN DE USO
      Y OPERACIÓN
           ↓
   HISTORIAL VEHICULAR
```

Esta información podrá posteriormente alimentar funcionalidades relacionadas con cálculos, alertas, mantenimiento, análisis de consumo, preparación de viajes, reportes u otras capacidades que sean definidas.

La definición detallada del funcionamiento de kilometraje, abastecimientos, recargas, consumo y demás registros operativos deberá realizarse en los puntos funcionales correspondientes.

El historial también podrá incorporar preparaciones, verificaciones y otras interacciones relacionadas con el vehículo.

Entre ellas podrán encontrarse:

- Revisiones previas a viajes.
- Preparaciones para viajes.
- Listas de verificación.
- Resultados de verificaciones realizadas por el propietario cuando sean definidas.
- Observaciones.
- Evidencias fotográficas.
- Otros eventos o interacciones relevantes relacionados con el vehículo.

Estas categorías no deberán considerarse cerradas o exhaustivas.

Vehículos Services podrá incorporar posteriormente nuevos tipos de información al historial siempre que correspondan a acontecimientos, condiciones, documentos, actividades o interacciones relevantes para la vida registrada del vehículo.

El registro de información dentro del historial deberá diferenciarse del almacenamiento de documentos de soporte.

Como principio general:

```text
REGISTRAR LA INFORMACIÓN
        ≠
ADJUNTAR EL DOCUMENTO
```

Vehículos Services deberá permitir que un registro histórico pueda existir mediante información estructurada sin exigir obligatoriamente que el propietario cargue el documento, factura, fotografía, archivo o evidencia correspondiente.

Por ejemplo, para una póliza el propietario podrá registrar información como:

```text
PÓLIZA

Aseguradora:
[Información registrada]

Número de póliza:
[Información registrada]

Fecha de inicio:
[Información registrada]

Fecha de vencimiento:
[Información registrada]

Cobertura:
[Información registrada]

Documento adjunto:
Opcional
```

La ausencia del documento adjunto no deberá impedir que la información registrada forme parte del historial cuando se hayan proporcionado los datos requeridos para dicho tipo de registro.

Este principio podrá aplicarse, según corresponda, a los diferentes tipos de información que formen parte del historial vehicular.

Los documentos, archivos y evidencias cargados directamente por el propietario deberán mantenerse diferenciados de la información estructurada que representan o soportan.

Por lo tanto:

```text
REGISTRO HISTÓRICO
        │
        ├── INFORMACIÓN ESTRUCTURADA
        │
        └── DOCUMENTO / EVIDENCIA
            CUANDO EXISTA
```

La existencia de información estructurada no deberá exigir automáticamente la existencia de un archivo adjunto.

De igual manera, la visibilidad de la información estructurada y la visibilidad de los documentos o archivos asociados no deberán asumirse como equivalentes.

Conceptualmente:

```text
VISIBILIDAD DE
INFORMACIÓN ESTRUCTURADA
        ≠
VISIBILIDAD AUTOMÁTICA
DEL DOCUMENTO ADJUNTO
```

Los documentos, archivos y evidencias cargados directamente por el propietario deberán considerarse información privada del propietario y su consulta deberá regirse por las reglas de visibilidad, privacidad y permisos correspondientes.

La existencia de una relación activa con un Prestador de Servicios Vehiculares no deberá otorgar automáticamente acceso a dichos documentos.

El tratamiento de documentos, facturas, diagnósticos, evidencias, fotografías u otros archivos generados o cargados directamente por un Prestador de Servicios Vehiculares deberá definirse posteriormente de acuerdo con su naturaleza, origen y permisos aplicables.

La existencia de diferentes tipos de información no deberá fragmentar el historial.

Conceptualmente:

```text
INFORMACIÓN LEGAL,
DOCUMENTAL Y ADMINISTRATIVA
            +
MANTENIMIENTOS
            +
REPARACIONES
            +
KILOMETRAJE
            +
ABASTECIMIENTOS
            +
VERIFICACIONES
            +
OTROS REGISTROS
            ↓
      MISMO VEHÍCULO
            ↓
  HISTORIAL VEHICULAR
   ÚNICO Y CONTINUO
```

Los mecanismos mediante los cuales los diferentes actores podrán crear, incorporar, completar o actualizar los registros, así como la identificación de su procedencia, deberán regirse por el apartado correspondiente a creación, incorporación y procedencia de los registros históricos.

Los detalles específicos de cada tipo de información deberán desarrollarse posteriormente en sus componentes funcionales correspondientes, manteniendo los principios de continuidad, privacidad, integridad y trazabilidad definidos para el historial vehicular.

---
### 63.6.3 Estructura temporal, continuidad y consulta del historial vehicular

El historial vehicular deberá conservar de manera continua la evolución de la información, los eventos, registros e interacciones asociados al vehículo durante su ciclo de vida dentro de Vehículos Services.

Cada registro deberá conservar su referencia temporal de acuerdo con su naturaleza, permitiendo identificar cuándo ocurrió, fue realizado, inició, finalizó, venció, fue registrado o adquirió vigencia, según corresponda al tipo de información.

El historial deberá estar asociado a la identidad del vehículo y no deberá reiniciarse como consecuencia del paso del tiempo, del registro de nueva información, de un cambio de propietario, de la participación de diferentes Prestadores de Servicios Vehiculares o de cualquier otra situación que no implique la creación de un vehículo diferente dentro de la plataforma.

Conceptualmente:

```text
VEHÍCULO
   │
   ├── 2024
   │    ├── Póliza
   │    ├── Mantenimiento
   │    └── Kilometraje
   │
   ├── 2025
   │    ├── SOAT
   │    ├── Impuesto
   │    ├── Reparación
   │    └── Mantenimiento
   │
   └── 2026
        ├── Póliza
        ├── Kilometraje
        ├── Cambio de repuesto
        └── Abastecimientos
                ↓
        UN MISMO HISTORIAL
             CONTINUO
```

La incorporación de nueva información no deberá eliminar automáticamente los registros históricos anteriores.

Cuando un mismo tipo de información se genere nuevamente con el paso del tiempo, los registros anteriores deberán conservarse cuando su naturaleza corresponda a eventos, períodos, vigencias o estados históricos diferentes.

Por ejemplo:

```text
PÓLIZAS

2025
Póliza A
    ↓
2026
Póliza B
    ↓
2027
Póliza C

RESULTADO:

Las tres pólizas forman parte
del historial del vehículo.
```

El mismo principio podrá aplicarse, según corresponda, a:

- SOAT o equivalente.
- Pólizas de seguros.
- Impuestos.
- Revisión técnico-mecánica o equivalente.
- Mantenimientos.
- Reparaciones.
- Repuestos.
- Kilometraje.
- Abastecimientos.
- Recargas.
- Diagnósticos.
- Inspecciones.
- Evaluaciones.
- Peritajes.
- Revisiones y preparaciones para viajes.
- Otros registros que posteriormente formen parte del historial vehicular.

Esto permitirá reconstruir la evolución del vehículo y no solamente conocer su información más reciente.

Los registros deberán conservar la información temporal necesaria para poder establecer la secuencia en la que los diferentes acontecimientos relacionados con el vehículo ocurrieron.

Por ejemplo:

```text
10/01/2026
Kilometraje: 60.000 km
        ↓
25/01/2026
Cambio de aceite
        ↓
15/03/2026
Cambio de pastillas de freno
        ↓
20/05/2026
Diagnóstico
        ↓
05/06/2026
Reparación
        ↓
01/08/2026
Kilometraje: 64.500 km
        ↓
18/09/2026
Nuevo mantenimiento
```

Todos estos registros deberán permanecer asociados al mismo vehículo y permitir conocer progresivamente lo ocurrido durante su ciclo de vida.

Cuando los registros históricos dispongan de información de kilometraje suficiente, Vehículos Services deberá permitir determinar y presentar la distancia recorrida entre eventos comparables o sucesivos.

Esto permitirá que el historial no solamente indique en qué kilometraje ocurrió cada intervención, sino también cuánto recorrió el vehículo entre una intervención y otra.

Por ejemplo:

```text
MANTENIMIENTO ANTERIOR
40.000 km
        ↓
8.500 km recorridos
        ↓
SIGUIENTE MANTENIMIENTO
48.500 km
```

Conceptualmente:

```text
KM TRANSCURRIDOS
ENTRE INTERVENCIONES
=
KM DE LA INTERVENCIÓN POSTERIOR
-
KM DE LA INTERVENCIÓN ANTERIOR
```

Esta lógica deberá poder aplicarse cuando exista información suficiente para realizar el cálculo y no deberá limitarse exclusivamente a un tipo específico de mantenimiento.

Por ejemplo, podrá utilizarse para conocer la distancia recorrida entre cambios, mantenimientos, intervenciones o eventos comparables que cuenten con una referencia válida de kilometraje.

Adicionalmente, cuando un mantenimiento, intervención o elemento de seguimiento tenga asociado un kilometraje de realización y exista un próximo kilometraje objetivo, Vehículos Services deberá permitir relacionar dicha información con el kilometraje actual del vehículo para presentar el avance correspondiente.

Conceptualmente:

```text
ÚLTIMA INTERVENCIÓN
40.000 km
        ↓
KM TRANSCURRIDOS
6.500 km
        ↓
KILOMETRAJE ACTUAL
46.500 km
        ↓
KM RESTANTES
3.500 km
        ↓
PRÓXIMA INTERVENCIÓN
50.000 km
```

De esta manera, cuando se consulte un elemento cuyo seguimiento se encuentre controlado por kilometraje y exista la información necesaria, deberá poder conocerse la relación entre:

```text
KM DE LA ÚLTIMA INTERVENCIÓN
            ↓
KM TRANSCURRIDOS
            ↓
KM ACTUAL DEL VEHÍCULO
            ↓
KM RESTANTES
            ↓
KM OBJETIVO DE LA
PRÓXIMA INTERVENCIÓN
```

Por ejemplo:

```text
CAMBIO DE ACEITE

Realizado:
1.000 km

Próximo cambio:
11.000 km

Kilometraje actual:
3.300 km

Kilómetros transcurridos:
2.300 km

Kilómetros restantes:
7.700 km
```

El cambio de aceite corresponde únicamente a un ejemplo.

Este comportamiento no deberá limitarse al cambio de aceite y deberá poder aplicarse a cualquier mantenimiento, intervención, componente o elemento cuyo seguimiento haya sido definido por kilometraje.

Conceptualmente:

```text
ELEMENTO CONTROLADO
POR KILOMETRAJE
        ↓
ÚLTIMA INTERVENCIÓN
        ↓
KM TRANSCURRIDOS
        ↓
KM ACTUAL
        ↓
KM RESTANTES
        ↓
PRÓXIMO KM OBJETIVO
```

Los kilómetros transcurridos deberán representar la distancia recorrida desde el kilometraje correspondiente a la última intervención hasta el kilometraje actual del vehículo.

Conceptualmente:

```text
KM TRANSCURRIDOS
=
KM ACTUAL
-
KM DE LA ÚLTIMA INTERVENCIÓN
```

Los kilómetros restantes deberán representar la distancia que falta para alcanzar el kilometraje objetivo de la próxima intervención.

Conceptualmente:

```text
KM RESTANTES
=
KM OBJETIVO DE LA PRÓXIMA INTERVENCIÓN
-
KM ACTUAL
```

Estos valores deberán actualizarse conforme evolucione el kilometraje actual registrado para el vehículo.

Por ejemplo:

```text
INTERVENCIÓN REALIZADA:
1.000 km

PRÓXIMA INTERVENCIÓN:
11.000 km
```

Si el vehículo se encuentra en:

```text
3.300 km

Transcurridos:
2.300 km

Restantes:
7.700 km
```

Y posteriormente el kilometraje actual cambia a:

```text
6.000 km

Transcurridos:
5.000 km

Restantes:
5.000 km
```

El seguimiento deberá reflejar la nueva situación utilizando el kilometraje actual disponible.

La presentación de kilómetros transcurridos y kilómetros restantes deberá realizarse cuando exista información suficiente para efectuar dichos cálculos.

La definición detallada de las fuentes del kilometraje actual, validaciones, actualización, intervalos, kilometraje objetivo, tolerancias, estados y comportamiento cuando el kilometraje objetivo sea alcanzado o superado deberá desarrollarse posteriormente dentro de los componentes específicos de Kilometraje y Reglas de Mantenimiento.

La fecha relevante de un registro dependerá de su naturaleza.

Por ejemplo:

```text
MANTENIMIENTO
→ Fecha de realización

REPARACIÓN
→ Fecha de realización

PÓLIZA
→ Fecha de inicio y fecha de finalización o vencimiento

SOAT
→ Fecha de inicio y fecha de vencimiento

IMPUESTO
→ Período o año correspondiente y fecha de pago cuando aplique

KILOMETRAJE
→ Fecha correspondiente a la lectura o registro

ABASTECIMIENTO
→ Fecha del abastecimiento
```

Los campos específicos requeridos para cada tipo de información serán definidos posteriormente en los puntos funcionales correspondientes.

El cambio de propietario no deberá generar un nuevo historial ni reiniciar el historial existente.

Conceptualmente:

```text
PROPIETARIO A
      ↓
   VEHÍCULO
      ↓
HISTORIAL ACUMULADO
      ↓
CAMBIO DE PROPIETARIO
      ↓
PROPIETARIO B
      ↓
MISMO VEHÍCULO
      ↓
EL HISTORIAL CONTINÚA
```

Los registros generados durante diferentes períodos de propiedad deberán continuar formando parte del historial del mismo vehículo.

La continuidad del historial no deberá interpretarse como acceso irrestricto a información privada de propietarios anteriores. Las reglas de privacidad, visibilidad y acceso deberán aplicarse independientemente de la conservación histórica de los registros.

La participación de diferentes Prestadores de Servicios Vehiculares tampoco deberá dividir, reiniciar o reemplazar el historial.

Por ejemplo:

```text
Vehículo
   │
   ├── Prestador A
   │      └── Mantenimiento
   │
   ├── Prestador B
   │      └── Reparación
   │
   ├── Propietario
   │      └── Registro de kilometraje
   │
   └── Prestador C
          └── Diagnóstico

TODOS LOS REGISTROS
        ↓
MISMO HISTORIAL DEL VEHÍCULO
```

Cada registro deberá conservar la identificación de su origen y de los actores relacionados cuando corresponda, sin que la participación de diferentes actores genere historiales independientes.

La existencia de todos estos registros dentro del mismo historial no deberá otorgar a los diferentes Prestadores de Servicios Vehiculares acceso a registros pertenecientes a otros prestadores. La continuidad histórica y las reglas de acceso deberán mantenerse como conceptos independientes.

Vehículos Services deberá manejar conceptualmente un único historial por vehículo.

Sin embargo, esto no significa que toda la información deba ser presentada al usuario permanentemente como una única lista de eventos.

El mismo historial podrá ser consultado y organizado de diferentes maneras sin duplicar los registros ni crear historiales independientes.

Conceptualmente:

```text
                 HISTORIAL VEHICULAR
                         │
          ┌──────────────┼──────────────┐
          ↓              ↓              ↓
   CRONOLÓGICO      POR CATEGORÍA    POR PERÍODO
          │              │              │
   Todos los         Mantenimiento     Año
   eventos según     Reparaciones      Mes
   sus fechas        Seguros           Rango
                     Impuestos         de fechas
                     Kilometraje
                     Abastecimientos
                     Otros
```

Por ejemplo, un propietario podrá consultar el historial completo del vehículo y posteriormente aplicar una selección o filtro para visualizar únicamente:

```text
TODO EL HISTORIAL
        ↓
Filtro: Mantenimientos
        ↓
SOLO MANTENIMIENTOS

TODO EL HISTORIAL
        ↓
Filtro: Pólizas
        ↓
SOLO PÓLIZAS

TODO EL HISTORIAL
        ↓
Período: 2026
        ↓
REGISTROS CORRESPONDIENTES
AL PERÍODO CONSULTADO
```

Estas consultas deberán representar diferentes vistas sobre la misma información histórica.

Por lo tanto:

```text
FILTRAR EL HISTORIAL
        ≠
CREAR OTRO HISTORIAL

ORGANIZAR EL HISTORIAL
        ≠
DUPLICAR LOS REGISTROS
```

La forma en que la información sea conservada como parte del historial deberá diferenciarse conceptualmente de la manera en que posteriormente sea presentada al usuario.

El historial deberá conservar la información necesaria para representar la evolución del vehículo, mientras que la interfaz podrá ofrecer diferentes mecanismos de consulta y visualización.

Conceptualmente:

```text
HISTORIAL DEL VEHÍCULO
        ↓
INFORMACIÓN CONSERVADA
        ↓
DIFERENTES FORMAS DE CONSULTARLA
        │
        ├── Cronológicamente
        ├── Por categoría
        ├── Por período
        ├── Por tipo de registro
        └── Otras formas que
            posteriormente se definan
```

La definición detallada de filtros, búsquedas, ordenamiento, agrupaciones, vistas, indicadores, diseño visual y demás mecanismos de consulta deberá desarrollarse posteriormente durante la definición funcional y de UX/UI correspondiente.

Como principio general, Vehículos Services deberá permitir que la información asociada al vehículo se acumule progresivamente durante su ciclo de vida, preservando los registros históricos que correspondan y permitiendo reconstruir su evolución.

Cuando exista información de kilometraje suficiente, esta evolución también deberá permitir conocer cuánto ha recorrido el vehículo entre determinados eventos históricos y cuál es el avance respecto de próximos eventos controlados por kilometraje.

Conceptualmente:

```text
NUEVO REGISTRO
      ↓
SE INCORPORA
      ↓
HISTORIAL EXISTENTE
      ↓
SE CONSERVA
      ↓
EL HISTORIAL CRECE
CON EL VEHÍCULO
      ↓
EL KILOMETRAJE PERMITE
MEDIR SU EVOLUCIÓN
CUANDO CORRESPONDA
```

La incorporación de nueva información no deberá interpretarse como el reemplazo automático de la información histórica anterior.

Las reglas específicas para correcciones, actualizaciones, anulaciones, versionamiento, eliminación lógica, auditoría y demás situaciones que puedan afectar un registro histórico deberán definirse posteriormente, preservando en todo caso los principios de continuidad, integridad y trazabilidad establecidos para el historial vehicular.

---
### 63.6.4 Creación, incorporación y procedencia de los registros históricos

Los registros que conforman el historial vehicular podrán ser incorporados desde diferentes actores y en diferentes momentos durante el ciclo de vida del vehículo, de acuerdo con las funcionalidades, permisos y reglas de negocio que correspondan.

La incorporación de un registro al historial deberá permitir identificar su procedencia y diferenciar, cuando aplique, el evento ocurrido sobre el vehículo de la acción mediante la cual dicho evento fue registrado en Vehículos Services.

Conceptualmente:

```text
EVENTO / INFORMACIÓN DEL VEHÍCULO
                ↓
        REGISTRO HISTÓRICO
                │
                ├── ¿Qué ocurrió?
                ├── ¿Cuándo ocurrió?
                ├── ¿Quién realizó la intervención?
                ├── ¿Quién creó el registro?
                ├── ¿Cuándo fue creado?
                └── ¿Fue completado o actualizado
                    posteriormente?
```

No todos estos elementos deberán existir obligatoriamente en todos los tipos de registros. Su aplicación dependerá de la naturaleza de la información registrada.

Por ejemplo, una póliza, un registro de kilometraje y un mantenimiento representan situaciones diferentes y, por lo tanto, podrán requerir información de procedencia y temporalidad diferente.

El propietario deberá poder incorporar directamente al historial la información correspondiente a su vehículo cuando la funcionalidad respectiva lo permita.

Esta capacidad no deberá depender de:

- La existencia de un Prestador de Servicios Vehiculares registrado en Vehículos Services.
- La existencia de una relación activa con un prestador.
- La disponibilidad del módulo correspondiente al Prestador de Servicios Vehiculares.
- Que el prestador que realizó una intervención utilice Vehículos Services.

Esto permitirá que el módulo del Propietario funcione de manera independiente durante la primera etapa de desarrollo de la aplicación y que el propietario pueda comenzar a construir el historial de su vehículo desde dicho módulo.

Por ejemplo:

```text
PROPIETARIO
     ↓
Lleva su vehículo a
ABC Aceites
     ↓
ABC Aceites realiza
cambio de aceite
     ↓
ABC Aceites no utiliza
Vehículos Services
     ↓
PROPIETARIO REGISTRA
EL MANTENIMIENTO
     ↓
EL EVENTO FORMA PARTE
DEL HISTORIAL
```

El hecho de que el propietario cree el registro no deberá significar que él realizó personalmente el servicio o intervención.

Cuando corresponda, podrá indicarse separadamente quién realizó el servicio.

El propietario podrá registrar información correspondiente a servicios realizados por talleres, establecimientos, técnicos u otros prestadores que no se encuentren registrados dentro de Vehículos Services.

Por ejemplo:

```text
MANTENIMIENTO

Servicio:
Cambio de aceite

Realizado por:
ABC Aceites

ABC Aceites registrado
en Vehículos Services:
No

Registro creado por:
Propietario
```

La inexistencia del prestador dentro de la plataforma no deberá impedir que el evento sea incorporado al historial.

La información que posteriormente se permita registrar sobre un prestador no registrado deberá definirse en el punto funcional correspondiente, evitando establecer en esta etapa campos específicos que todavía no hayan sido levantados.

La referencia ingresada por el propietario sobre quién realizó el servicio no deberá interpretarse automáticamente como una cuenta, perfil, relación o validación formal de dicho prestador dentro de Vehículos Services.

Conceptualmente:

```text
PRESTADOR INDICADO
POR EL PROPIETARIO
        ≠
PRESTADOR REGISTRADO
Y VALIDADO EN LA PLATAFORMA
```

Cuando el módulo del Prestador de Servicios Vehiculares sea incorporado e integrado a la solución, los prestadores podrán generar registros correspondientes a los servicios, intervenciones, diagnósticos, inspecciones, evaluaciones, peritajes u otras actuaciones que realicen sobre un vehículo, de acuerdo con las relaciones, autorizaciones, permisos y reglas de negocio establecidas.

Por ejemplo:

```text
VEHÍCULO
    ↓
ABC Aceites
realiza mantenimiento
    ↓
ABC Aceites
crea el registro
    ↓
REGISTRO INCORPORADO
AL HISTORIAL DEL VEHÍCULO
```

La incorporación de registros desde el módulo del Prestador no deberá crear un historial diferente.

Los registros generados desde ambos frentes deberán alimentar el mismo historial asociado al vehículo:

```text
MÓDULO PROPIETARIO
        │
        ├─────────────┐
        │             ↓
        │      HISTORIAL VEHICULAR
        │             ↑
        └─────────────┤
                      │
              MÓDULO PRESTADOR
```

La procedencia de cada registro deberá conservarse para permitir identificar desde qué actor fue generado.

Vehículos Services deberá diferenciar conceptualmente al actor que realizó un servicio o intervención del actor que incorporó la información a la plataforma.

Por ejemplo:

```text
CAMBIO DE ACEITE

Realizado por:
ABC Aceites

Registrado en Vehículos Services por:
Propietario
```

En este escenario:

```text
QUIÉN REALIZÓ EL SERVICIO
ABC Aceites

            ≠

QUIÉN CREÓ EL REGISTRO
Propietario
```

También podrá existir un escenario en el que ambos correspondan al mismo prestador:

```text
CAMBIO DE ACEITE

Realizado por:
ABC Aceites

Registro creado por:
ABC Aceites
```

Esta diferenciación deberá conservarse cuando sea aplicable para evitar atribuir incorrectamente la creación de un registro al actor que realizó físicamente el servicio o viceversa.

Vehículos Services deberá diferenciar igualmente la fecha correspondiente al evento histórico de la fecha en que la información fue incorporada a la plataforma.

Por ejemplo:

```text
MANTENIMIENTO REALIZADO
05/09/2026
        ↓
PROPIETARIO LO REGISTRA
18/09/2026
```

En este escenario deberán conservarse conceptualmente ambas referencias:

```text
Fecha del mantenimiento:
05/09/2026

Fecha de creación del registro
en Vehículos Services:
18/09/2026
```

Por lo tanto:

```text
FECHA DEL EVENTO
        ≠
FECHA DE CREACIÓN DEL REGISTRO
```

Cuando el tipo de información represente un evento ocurrido sobre el vehículo, su ubicación temporal dentro del historial deberá corresponder principalmente a la fecha asociada al evento y no necesariamente a la fecha en que fue ingresado en Vehículos Services.

Esto permitirá que un propietario pueda incorporar información histórica que no haya sido registrada en la aplicación exactamente el día en que ocurrió.

Por ejemplo:

```text
HOY
18/09/2026

El propietario registra:

Mantenimiento
realizado el
05/09/2026
        ↓
HISTORIAL
        ↓
05/09/2026
Cambio de aceite
```

Vehículos Services deberá conservar adicionalmente la fecha en que el registro fue incorporado a la plataforma para efectos de trazabilidad.

La naturaleza de determinados registros podrá requerir otras referencias temporales, como fecha de inicio, fecha de vencimiento, período, fecha de lectura u otras que serán definidas en los puntos funcionales correspondientes.

El propietario podrá incorporar información correspondiente a eventos ocurridos antes de la fecha en que fueron registrados en Vehículos Services.

Esto permitirá construir progresivamente el historial del vehículo incluso cuando parte de su información exista previamente fuera de la aplicación.

Por ejemplo:

```text
PROPIETARIO COMIENZA A UTILIZAR
VEHÍCULOS SERVICES
18/09/2026
        ↓
REGISTRA INFORMACIÓN PREVIA
        │
        ├── Mantenimiento 10/02/2026
        ├── Póliza 15/03/2026
        ├── Reparación 20/05/2026
        └── Mantenimiento 05/09/2026
        ↓
LA INFORMACIÓN SE ORGANIZA
SEGÚN SU REFERENCIA TEMPORAL
DENTRO DEL HISTORIAL
```

El hecho de que estos registros sean incorporados posteriormente no deberá modificar la fecha real o declarada del evento correspondiente.

Deberá conservarse la diferencia entre:

```text
CUÁNDO OCURRIÓ
        ↓
Fecha del evento

CUÁNDO SE INFORMÓ A LA PLATAFORMA
        ↓
Fecha de creación del registro
```

La incorporación posterior de información histórica deberá conservar su procedencia y no deberá presentarse como si hubiera sido registrada en Vehículos Services en la misma fecha en que ocurrió el evento.

Un registro podrá ser creado inicialmente con determinada información y posteriormente ser completado por otro actor cuando las reglas del tipo de registro lo permitan.

Por ejemplo:

```text
ABC ACEITES
crea registro
        ↓
Cambio de aceite
Fecha: 10/09/2026
        ↓
Información pendiente:
- Marca del aceite
- Tipo de aceite
- Kilometraje
        ↓
PROPIETARIO
completa posteriormente
        ↓
Marca: Mobil
Tipo: 5W-30
Kilometraje: 65.200 km
```

La incorporación posterior de información no deberá eliminar la identificación del actor que creó originalmente el registro.

Conceptualmente:

```text
REGISTRO ORIGINAL
Creado por: ABC Aceites
        ↓
INFORMACIÓN COMPLETADA
Por: Propietario
        ↓
MISMO REGISTRO
        ↓
TRAZABILIDAD DE AMBAS ACCIONES
```

De esta manera podrán coexistir dentro del mismo registro diferentes responsabilidades de participación:

```text
Servicio realizado por:
ABC Aceites

Registro creado por:
ABC Aceites

Información completada posteriormente por:
Propietario
```

La definición exacta de qué información podrá ser completada por cada actor deberá establecerse posteriormente según el tipo de registro y las reglas de permisos correspondientes.

Cada registro histórico deberá conservar la información suficiente para identificar su procedencia cuando corresponda.

Dependiendo de la naturaleza del registro, deberá ser posible diferenciar conceptualmente:

- El actor que creó el registro.
- El actor que realizó el servicio o intervención, cuando aplique.
- La fecha correspondiente al evento.
- La fecha de creación del registro dentro de Vehículos Services.
- Los actores que posteriormente completaron o actualizaron información, cuando aplique.
- Las fechas correspondientes a dichas acciones relevantes.

La procedencia deberá conservarse incluso cuando posteriormente el registro sea completado o actualizado.

Por ejemplo:

```text
REGISTRO DE MANTENIMIENTO
        │
        ├── Servicio realizado por:
        │   ABC Aceites
        │
        ├── Fecha del servicio:
        │   10/09/2026
        │
        ├── Registro creado por:
        │   ABC Aceites
        │
        ├── Fecha de creación:
        │   10/09/2026
        │
        └── Completado posteriormente por:
            Propietario
            12/09/2026
```

La trazabilidad no deberá depender únicamente del valor actual de la información registrada. Deberá permitir conservar la referencia de los actores que participaron en las acciones relevantes sobre el registro.

La identificación de quién creó un registro deberá indicar su procedencia, pero no deberá interpretarse automáticamente como una validación independiente de que toda la información registrada sea correcta, completa o auténtica.

Por ejemplo:

```text
Registro creado por:
Propietario

Significa:
El propietario incorporó la información.

NO significa automáticamente:
Vehículos Services verificó
externamente la información.
```

De igual manera:

```text
Registro creado por:
Prestador

Significa:
El prestador incorporó el registro
correspondiente a su actuación.

NO significa automáticamente:
Vehículos Services realizó una
validación externa del contenido.
```

Las posibles validaciones, verificaciones, evidencias, confirmaciones o mecanismos de confianza que posteriormente se definan deberán manejarse separadamente de la procedencia del registro.

Como principio general, Vehículos Services deberá permitir construir el historial progresivamente a partir de información incorporada por los actores autorizados, sin exigir que todos los eventos hayan sido registrados en la plataforma exactamente en el momento en que ocurrieron.

Conceptualmente:

```text
EVENTO DEL VEHÍCULO
        ↓
PUEDE SER REGISTRADO
EN EL MOMENTO
        │
        └───────────────┐
                        ↓
                O POSTERIORMENTE
                        ↓
                 MISMO HISTORIAL
                        ↓
              SE CONSERVA CUÁNDO
              OCURRIÓ EL EVENTO
                        +
              CUÁNDO FUE REGISTRADO
                        +
              QUIÉN LO REGISTRÓ
```

La creación o incorporación de un registro deberá conservar su procedencia y temporalidad sin afectar los principios de continuidad, integridad y trazabilidad del historial vehicular.

Las reglas específicas relacionadas con modificación de información existente, correcciones, anulaciones, versionamiento, eliminación lógica, conflictos entre actores y demás situaciones posteriores a la creación del registro deberán definirse separadamente, evitando interpretar la capacidad de crear o completar información como autorización para modificar arbitrariamente registros históricos.

---
### 63.6.5 Modificación, corrección y conservación de registros históricos

Los registros que forman parte del historial vehicular podrán requerir acciones posteriores a su creación para completar información faltante, modificar determinada información, corregir errores o anular registros que hayan sido incorporados incorrectamente.

Vehículos Services deberá permitir estas acciones cuando las reglas de negocio, el tipo de registro y los permisos del actor correspondiente lo autoricen, sin comprometer la integridad ni la trazabilidad del historial.

Como principio general:

```text
PERMITIR CORREGIR INFORMACIÓN
            ≠
PERMITIR SOBRESCRIBIRLA
SIN TRAZABILIDAD
```

Vehículos Services deberá conservar internamente la trazabilidad de los cambios relevantes realizados sobre los registros históricos.

Por lo tanto, una modificación o corrección podrá cambiar la información vigente que se presenta normalmente al usuario, pero no deberá provocar que la información anterior desaparezca internamente como si nunca hubiera existido.

Conceptualmente:

```text
REGISTRO ORIGINAL
        ↓
CAMBIO AUTORIZADO
        ↓
INFORMACIÓN ACTUALIZADA
        ↓
EL USUARIO CONSULTA
EL VALOR VIGENTE

MIENTRAS VEHÍCULOS SERVICES
CONSERVA INTERNAMENTE
        ↓
QUÉ CAMBIÓ
        +
VALOR ANTERIOR
        +
VALOR NUEVO
        +
QUIÉN REALIZÓ EL CAMBIO
        +
CUÁNDO SE REALIZÓ
```

Completar un registro significa incorporar información que no había sido registrada inicialmente y cuyo campo o elemento correspondiente se encontraba pendiente, vacío o sin información.

Por ejemplo:

```text
REGISTRO CREADO POR:
ABC Aceites

Servicio:
Cambio de aceite

Marca del aceite:
Sin información

Tipo de aceite:
Sin información

Kilometraje:
Sin información
        ↓
POSTERIORMENTE
EL PROPIETARIO COMPLETA
        ↓
Marca:
Mobil

Tipo:
5W-30

Kilometraje:
65.200 km
```

Cuando las reglas del registro lo permitan, el propietario podrá completar información faltante incluso cuando el registro haya sido creado inicialmente por un Prestador de Servicios Vehiculares.

Esta acción no deberá modificar la identificación del creador original.

Por ejemplo:

```text
Registro creado por:
ABC Aceites

Información completada posteriormente por:
Propietario
```

Ambas participaciones deberán conservarse de acuerdo con las reglas de trazabilidad correspondientes.

Por lo tanto:

```text
COMPLETAR UN REGISTRO
        ≠
CONVERTIRSE EN SU
CREADOR ORIGINAL
```

La definición específica de qué campos pueden ser completados posteriormente dependerá del tipo de registro y deberá establecerse en los puntos funcionales correspondientes.

Modificar un registro implica cambiar información que ya contiene un valor previamente registrado.

Por ejemplo:

```text
VALOR EXISTENTE

Marca del aceite:
Castrol
        ↓
MODIFICACIÓN
        ↓
NUEVO VALOR

Marca del aceite:
Mobil
```

Este escenario deberá diferenciarse de completar un campo que anteriormente se encontraba vacío.

Conceptualmente:

```text
CAMPO VACÍO
    ↓
SE AGREGA INFORMACIÓN
    ↓
COMPLETAR

CAMPO CON INFORMACIÓN
    ↓
SE CAMBIA SU VALOR
    ↓
MODIFICAR
```

La posibilidad de modificar información existente deberá depender de:

- El tipo de registro.
- El origen del registro.
- El actor que intenta realizar la modificación.
- Los permisos aplicables.
- El estado del registro cuando corresponda.
- Las reglas de negocio específicas que posteriormente sean definidas.

La existencia de un registro dentro del historial no deberá implicar que cualquier actor relacionado con el vehículo pueda modificarlo.

Vehículos Services deberá contemplar la posibilidad de corregir errores legítimos presentes en un registro histórico.

Por ejemplo:

```text
KILOMETRAJE REGISTRADO
652.000 km

        ↓

SE DETECTA ERROR

        ↓

KILOMETRAJE CORRECTO
65.200 km
```

Impedir cualquier corrección produciría información histórica incorrecta y afectaría la utilidad del historial.

Por esta razón, cuando el actor correspondiente tenga autorización para realizar la corrección, Vehículos Services deberá permitir que el valor vigente sea rectificado.

Sin embargo, la corrección no deberá eliminar internamente la existencia del valor anterior.

Conceptualmente:

```text
VALOR ORIGINAL
652.000 km
        ↓
CORRECCIÓN AUTORIZADA
        ↓
VALOR VIGENTE
65.200 km
```

Mientras que internamente deberá conservarse, como mínimo, la trazabilidad necesaria para determinar:

```text
Valor anterior
        ↓
652.000 km

Valor nuevo
        ↓
65.200 km

Quién realizó la corrección
        ↓
Actor correspondiente

Cuándo se realizó
        ↓
Fecha y hora del cambio
```

La información vigente podrá ser la utilizada normalmente para la consulta y operación de la aplicación, sin necesidad de presentar permanentemente al usuario todos los detalles internos de auditoría.

Vehículos Services deberá diferenciar conceptualmente las acciones de completar, modificar y corregir debido a que representan situaciones distintas sobre un registro histórico.

```text
COMPLETAR
    ↓
Agregar información
que estaba faltante

MODIFICAR
    ↓
Cambiar información
que ya tenía un valor

CORREGIR
    ↓
Rectificar información
que fue registrada
incorrectamente
```

Por ejemplo:

```text
Kilometraje: [Sin información]
        ↓
Kilometraje: 65.200 km

= COMPLETAR
```

```text
Marca: Castrol
        ↓
Marca: Mobil

= MODIFICAR
```

```text
Kilometraje: 652.000 km
        ↓
Kilometraje: 65.200 km

= CORREGIR
```

Aunque técnicamente una corrección pueda implicar modificar un valor existente, funcionalmente deberá poder reconocerse que el cambio corresponde a la rectificación de información previamente registrada.

Las reglas detalladas para determinar cuándo una modificación requiere justificación, confirmación u otros controles serán definidas posteriormente.

Vehículos Services no deberá borrar internamente la información histórica relevante como consecuencia de una modificación o corrección autorizada.

Cuando un cambio requiera trazabilidad, la plataforma deberá conservar la información necesaria para reconstruir la evolución del registro.

Conceptualmente:

```text
REGISTRO
   │
   ├── Información inicial
   │
   ├── Cambio realizado
   │
   ├── Actor responsable
   │
   ├── Fecha y hora
   │
   └── Información vigente
```

Por ejemplo:

```text
REGISTRO ORIGINAL

Kilometraje:
652.000 km

        ↓

CORRECCIÓN

Kilometraje:
65.200 km

        ↓

VISTA NORMAL

65.200 km

        ↓

TRAZABILIDAD INTERNA

Anterior:
652.000 km

Nuevo:
65.200 km

Modificado por:
Propietario

Fecha y hora:
Momento correspondiente
a la modificación
```

De esta manera, la información incorrecta no tendrá que continuar presentándose como el valor vigente, pero tampoco desaparecerá de la trazabilidad interna de Vehículos Services.

Vehículos Services deberá contemplar situaciones en las que un registro completo haya sido incorporado incorrectamente y no deba continuar considerándose como un evento válido del historial operativo del vehículo.

Por ejemplo:

```text
PROPIETARIO REGISTRA

Cambio de batería
        ↓
POSTERIORMENTE IDENTIFICA

El mantenimiento pertenecía
a otro vehículo
```

En este escenario, modificar únicamente uno de los campos podría no solucionar el problema, debido a que el registro completo fue asociado incorrectamente.

Cuando las reglas correspondientes lo permitan, el registro podrá ser anulado.

Conceptualmente:

```text
REGISTRO CREADO
        ↓
SE IDENTIFICA QUE
NO DEBE CONSIDERARSE VÁLIDO
        ↓
ANULACIÓN
        ↓
DEJA DE OPERAR COMO
REGISTRO VIGENTE
```

Sin embargo:

```text
ANULAR
    ≠
BORRAR INTERNAMENTE
LA EXISTENCIA DEL REGISTRO
```

Vehículos Services deberá conservar internamente la trazabilidad suficiente para identificar que:

- El registro existió.
- Fue posteriormente anulado.
- Quién realizó o solicitó la acción correspondiente, según se defina.
- Cuándo se realizó la anulación.
- La información necesaria para mantener la trazabilidad de la acción.

La necesidad de registrar motivos de anulación, mecanismos de aprobación o controles adicionales será definida posteriormente según el tipo de registro y actor involucrado.

Como principio general, los registros que hayan adquirido relevancia histórica dentro de Vehículos Services no deberán desaparecer físicamente de la información interna de la plataforma mediante una eliminación ordinaria realizada por el usuario.

Cuando funcionalmente sea necesario dejar de considerar un registro como válido, deberán utilizarse mecanismos controlados como la corrección o anulación, según corresponda.

Conceptualmente:

```text
REGISTRO HISTÓRICO
        ↓
ERROR DETECTADO
        ↓
NO SE HACE DESAPARECER
SIN TRAZABILIDAD
        ↓
SE CORRIGE
O
SE ANULA
SEGÚN CORRESPONDA
```

Esto permitirá preservar la integridad del historial y evitar que acontecimientos previamente registrados desaparezcan sin dejar evidencia.

Los escenarios excepcionales en los que determinada información deba ser eliminada físicamente por razones legales, regulatorias, de privacidad, seguridad u otras obligaciones aplicables deberán tratarse posteriormente mediante reglas específicas y no deberán confundirse con la eliminación ordinaria de un registro por parte de un usuario.

La posibilidad de que diferentes actores participen sobre un mismo registro no deberá eliminar la identidad de quienes realizaron acciones anteriores.

Por ejemplo:

```text
ABC ACEITES
        ↓
Crea registro de mantenimiento
        ↓
PROPIETARIO
        ↓
Completa kilometraje
        ↓
POSTERIORMENTE
        ↓
Se realiza una corrección autorizada
```

La trazabilidad deberá permitir diferenciar las acciones relevantes realizadas durante la evolución del registro.

Por lo tanto:

```text
QUIÉN CREÓ EL REGISTRO
        ≠
QUIÉN COMPLETÓ INFORMACIÓN
        ≠
QUIÉN REALIZÓ UNA CORRECCIÓN
```

Estos actores podrán coincidir o ser diferentes dependiendo del escenario.

La participación posterior de otro actor no deberá reemplazar la identificación del creador original.

Un Prestador de Servicios Vehiculares no deberá poder modificar, corregir, anular o eliminar registros históricos correspondientes a intervenciones realizadas o registradas por otro prestador, salvo que posteriormente se defina algún escenario excepcional expresamente autorizado y controlado por Vehículos Services.

Por ejemplo:

```text
PRESTADOR A
        ↓
Registra mantenimiento

PRESTADOR B
        ↓
NO PUEDE MODIFICAR
EL REGISTRO DEL PRESTADOR A
```

La existencia de una relación activa entre el Prestador B y el mismo vehículo no deberá otorgarle derechos de modificación sobre los registros pertenecientes al Prestador A.

Esto deberá mantenerse alineado con las reglas previamente establecidas para separación de información entre prestadores.

Un cambio de propietario tampoco deberá otorgar al nuevo propietario autorización automática para modificar arbitrariamente los registros históricos correspondientes a períodos anteriores de propiedad.

Conceptualmente:

```text
PROPIETARIO A
        ↓
PERÍODO DE PROPIEDAD
        ↓
REGISTROS HISTÓRICOS
        ↓
CAMBIO DE PROPIETARIO
        ↓
PROPIETARIO B
        ↓
CONSULTA EL HISTORIAL
SEGÚN SUS PERMISOS

PERO

NO ADQUIERE AUTOMÁTICAMENTE
DERECHO A REESCRIBIR
LOS EVENTOS ANTERIORES
```

La continuidad del historial deberá permitir que el nuevo propietario conozca la evolución acumulada del vehículo según las reglas de visibilidad establecidas, pero no deberá convertirlo automáticamente en autor o modificador de información histórica generada durante períodos anteriores.

Los mecanismos para reportar errores, solicitar correcciones o gestionar inconsistencias sobre información correspondiente a períodos de propiedad anteriores deberán definirse posteriormente.

Vehículos Services deberá diferenciar entre la información vigente de un registro y la trazabilidad interna conservada sobre sus cambios.

Conceptualmente:

```text
INFORMACIÓN VIGENTE
        ↓
La información que debe utilizar
normalmente la aplicación

        ≠

TRAZABILIDAD INTERNA
        ↓
La información necesaria para
reconstruir cambios relevantes
realizados sobre el registro
```

Por ejemplo:

```text
VALOR ORIGINAL
652.000 km
        ↓
CORRECCIÓN
65.200 km
        ↓

INFORMACIÓN VIGENTE
65.200 km

TRAZABILIDAD INTERNA
652.000 km → 65.200 km
```

Esta separación permitirá mantener una experiencia de consulta clara para el usuario sin sacrificar la integridad histórica de la información.

La existencia de trazabilidad interna no deberá significar que todos los actores puedan consultar todos los valores anteriores, cambios, motivos, usuarios o detalles de auditoría.

La visibilidad de dicha información deberá depender de los roles, permisos, reglas de privacidad, seguridad y auditoría que posteriormente sean definidos.

Como principio general, Vehículos Services deberá permitir que la información histórica pueda evolucionar y ser corregida cuando exista una razón válida y el actor correspondiente tenga autorización para hacerlo, sin convertir el historial en información rígida que no pueda corregirse y sin permitir que los cambios destruyan la trazabilidad de lo ocurrido.

Conceptualmente:

```text
REGISTRO ORIGINAL
        ↓
PUEDE SER
        │
        ├── Completado
        ├── Modificado
        ├── Corregido
        └── Anulado
                ↓
        SEGÚN REGLAS
        Y PERMISOS
                ↓
INFORMACIÓN VIGENTE
        +
TRAZABILIDAD INTERNA
```

Por lo tanto:

```text
CORREGIR
    ≠
BORRAR EL PASADO

ACTUALIZAR
    ≠
PERDER EL ORIGEN

ANULAR
    ≠
HACER DESAPARECER
EL REGISTRO

CONSERVAR TRAZABILIDAD
    ≠
MOSTRAR TODA LA AUDITORÍA
A TODOS LOS USUARIOS
```

Las reglas detalladas sobre campos modificables, responsables autorizados, motivos de cambio, confirmaciones, versionamiento, mecanismos de recuperación, auditoría, visualización de cambios y situaciones excepcionales deberán definirse posteriormente en los componentes funcionales, de permisos, seguridad y auditoría correspondientes.

---
### 63.6.6 Visibilidad y acceso a la información del historial vehicular

El historial vehicular deberá mantenerse como un historial único, continuo y asociado a la identidad del vehículo; sin embargo, la existencia de información dentro de dicho historial no deberá implicar que todos los actores relacionados con el vehículo puedan consultarla.

Vehículos Services deberá separar conceptualmente:

```text
CONSERVACIÓN DE LA INFORMACIÓN
            ≠
DERECHO DE ACCESO A LA INFORMACIÓN
```

Un registro podrá permanecer legítimamente dentro del historial durante todo el ciclo de vida del vehículo y, al mismo tiempo, estar sujeto a diferentes condiciones de visibilidad dependiendo del actor que intenta consultarlo, su relación con el vehículo, el origen de la información, su naturaleza y los permisos aplicables.

Conceptualmente:

```text
             HISTORIAL VEHICULAR
                     │
          INFORMACIÓN CONSERVADA
                     │
          ┌──────────┼──────────┐
          ↓          ↓          ↓
     PROPIETARIO  PRESTADOR   OTROS ACTORES
          │          │          │
          └──────────┼──────────┘
                     ↓
              ACCESO SEGÚN
          REGLAS Y PERMISOS
```

Todos los registros correspondientes al vehículo podrán formar parte del mismo historial sin que esto genere un derecho de consulta común para todos los actores que hayan participado en él.

Por ejemplo:

```text
VEHÍCULO
   │
   ├── Prestador A
   │      └── Mantenimiento
   │
   ├── Prestador B
   │      └── Reparación
   │
   └── Prestador C
          └── Diagnóstico
```

Los tres eventos podrán formar parte del mismo historial del vehículo.

Sin embargo:

```text
MISMO HISTORIAL
      ≠
VISIBILIDAD COMPARTIDA
ENTRE PRESTADORES
```

La centralización del historial deberá permitir preservar la vida registrada del vehículo sin convertir dicha centralización en un mecanismo de intercambio irrestricto de información entre los diferentes actores.

El propietario actual deberá poder consultar el historial acumulado del vehículo de acuerdo con las reglas de visibilidad, privacidad y protección de información aplicables.

El cambio de propietario no deberá reiniciar el historial ni provocar la pérdida de los registros correspondientes a períodos anteriores.

Conceptualmente:

```text
PROPIETARIO A
      ↓
PERÍODO DE PROPIEDAD
      ↓
HISTORIAL ACUMULADO
      ↓
CAMBIO DE PROPIETARIO
      ↓
PROPIETARIO B
      ↓
MISMO VEHÍCULO
      ↓
EL HISTORIAL CONTINÚA
```

El propietario actual podrá conocer la evolución histórica acumulada del vehículo, incluyendo los eventos correspondientes a períodos anteriores, cuando dichos registros formen parte de la información histórica transferible del vehículo.

Sin embargo, la continuidad del historial no deberá implicar la transferencia automática de información personal, privada o restringida perteneciente a propietarios anteriores.

Por lo tanto:

```text
HISTORIAL DEL VEHÍCULO
SE CONSERVA
        ↓
PERO
        ↓
INFORMACIÓN PRIVADA DE
PROPIETARIOS ANTERIORES
DEBERÁ RESPETAR SUS
REGLAS DE PRIVACIDAD
```

La definición específica de qué información deberá permanecer visible, ocultarse, anonimizarse, restringirse o recibir otro tratamiento después de un cambio de propietario deberá establecerse posteriormente dentro de las reglas de privacidad y permisos correspondientes.

Un Prestador de Servicios Vehiculares no deberá obtener acceso completo al historial del vehículo únicamente por encontrarse relacionado con este.

La relación activa entre un vehículo y un prestador deberá permitir únicamente el acceso expresamente habilitado para dicho prestador.

Como principio general, un prestador podrá consultar sus propias intervenciones y registros cuando exista una relación activa que habilite dicho acceso, además de la información general del vehículo y del propietario que haya sido expresamente autorizada para su operación.

Conceptualmente:

```text
PRESTADOR A
     ↓
RELACIÓN ACTIVA
CON EL VEHÍCULO
     ↓
PUEDE CONSULTAR
     │
     ├── Sus propias intervenciones
     ├── Sus propios registros
     └── Información expresamente
         habilitada
```

Esto no deberá extenderse automáticamente a los registros generados por otros prestadores.

Los Prestadores de Servicios Vehiculares deberán mantener separación respecto de la información correspondiente a las intervenciones realizadas por otros prestadores.

Por ejemplo:

```text
HISTORIAL DEL VEHÍCULO
        │
        ├── Prestador A
        │     └── Mantenimiento
        │
        ├── Prestador B
        │     └── Reparación
        │
        └── Prestador C
              └── Diagnóstico
```

Desde la perspectiva de acceso:

```text
PRESTADOR A
    ↓
Puede acceder a:
Sus propios registros

No puede acceder a:
Registros propios de B y C
```

La misma regla deberá aplicarse para los demás prestadores.

La restricción deberá contemplar, según corresponda, información propia de las intervenciones de otro prestador como:

- Servicios realizados.
- Mantenimientos.
- Reparaciones.
- Diagnósticos.
- Inspecciones.
- Evaluaciones.
- Peritajes.
- Repuestos registrados.
- Costos y precios.
- Facturas.
- Documentos.
- Evidencias.
- Fotografías.
- Observaciones.
- Recomendaciones.
- Otros elementos asociados directamente con sus actuaciones.

Por lo tanto:

```text
PRESTADOR A
        ≠
ACCESO A INFORMACIÓN
PROPIA DEL PRESTADOR B
```

La existencia de múltiples prestadores dentro del historial deberá servir para mantener la trazabilidad del vehículo, no para compartir automáticamente información comercial, operativa o documental entre ellos.

Además de sus propias intervenciones, un Prestador de Servicios Vehiculares con una relación activa podrá acceder a determinada información general necesaria para prestar sus servicios, siempre que dicha información haya sido expresamente habilitada por las reglas de Vehículos Services.

De acuerdo con lo definido inicialmente, esta información podrá contemplar:

```text
INFORMACIÓN DEL VEHÍCULO
        ↓
Kilometraje actual
```

Y respecto del propietario:

```text
INFORMACIÓN BÁSICA
DEL PROPIETARIO
        │
        ├── Nombre
        ├── Correo electrónico
        └── Número de celular
```

Esta definición corresponde al alcance inicialmente establecido y podrá evolucionar posteriormente conforme se definan las necesidades funcionales, permisos y reglas de privacidad.

El hecho de que determinada información general sea visible para el prestador no deberá otorgarle acceso al resto del historial.

Los documentos, archivos y evidencias que sean cargados directamente por el propietario deberán considerarse información privada del propietario.

Por ejemplo:

```text
PROPIETARIO
     ↓
REGISTRA INFORMACIÓN
DE UNA PÓLIZA
     ↓
OPCIONALMENTE
ADJUNTA EL DOCUMENTO
     ↓
DOCUMENTO PRIVADO
DEL PROPIETARIO
```

El documento adjunto directamente por el propietario solamente deberá ser visible para el propietario correspondiente, de acuerdo con las reglas aplicables.

La existencia de una relación activa con un Prestador de Servicios Vehiculares no deberá conceder al prestador acceso a dichos archivos.

Conceptualmente:

```text
PROPIETARIO
      ↓
ADJUNTA DOCUMENTO
      ↓
DOCUMENTO PRIVADO
      ↓
PRESTADOR
NO OBTIENE ACCESO
POR TENER UNA
RELACIÓN ACTIVA
```

Por lo tanto:

```text
RELACIÓN ACTIVA
PROPIETARIO ↔ PRESTADOR
        ≠
AUTORIZACIÓN PARA CONSULTAR
DOCUMENTOS PRIVADOS
DEL PROPIETARIO
```

Esta regla deberá mantenerse incluso cuando el documento esté relacionado con información del vehículo que sí pueda ser visible parcialmente para el prestador.

Vehículos Services deberá tratar separadamente la información estructurada de un registro y los documentos o archivos privados adjuntados directamente por el propietario.

Por ejemplo:

```text
PÓLIZA
   │
   ├── Información estructurada
   │      ├── Aseguradora
   │      ├── Número de póliza
   │      ├── Fecha de inicio
   │      ├── Fecha de vencimiento
   │      └── Cobertura
   │
   └── Documento adjunto
          └── Archivo almacenado
              por el propietario
```

La eventual autorización para consultar determinada información estructurada no deberá implicar automáticamente autorización para consultar el archivo adjunto.

Conceptualmente:

```text
PERMISO PARA CONSULTAR
INFORMACIÓN ESTRUCTURADA
        ≠
PERMISO PARA CONSULTAR
EL DOCUMENTO ADJUNTO
```

Por ejemplo, si posteriormente se establece que un prestador puede consultar determinada información relacionada con la vigencia de una póliza, esto no deberá significar que pueda visualizar el documento privado que el propietario haya adjuntado.

Los documentos, facturas, diagnósticos, evidencias, fotografías u otros archivos generados o cargados directamente por un Prestador de Servicios Vehiculares no deberán asumir automáticamente el mismo tratamiento de privacidad establecido para los documentos cargados directamente por el propietario.

Conceptualmente:

```text
DOCUMENTO CARGADO
POR EL PROPIETARIO
        ↓
REGLA DE PRIVACIDAD
DEL PROPIETARIO

        ≠

DOCUMENTO GENERADO O CARGADO
POR UN PRESTADOR
        ↓
TRATAMIENTO POR DEFINIR
SEGÚN SU NATURALEZA,
ORIGEN Y PERMISOS
```

Posteriormente deberá definirse qué actores podrán consultar estos documentos considerando, entre otros aspectos:

- Quién generó el documento.
- Quién lo cargó.
- A qué intervención corresponde.
- Su naturaleza.
- La relación existente con el vehículo.
- Los permisos aplicables.
- Las reglas de privacidad y seguridad.

Hasta que dichas reglas sean definidas, no deberá asumirse que un documento generado por un prestador es automáticamente privado para el propietario ni automáticamente visible para otros prestadores.

Cuando finalice la relación entre un vehículo y un Prestador de Servicios Vehiculares, el prestador deberá perder los accesos que dependan de la existencia de dicha relación activa.

Conceptualmente:

```text
RELACIÓN ACTIVA
      ↓
ACCESO SEGÚN
PERMISOS
      ↓
FINALIZA LA RELACIÓN
      ↓
SE PIERDE EL ACCESO
DEPENDIENTE DE LA RELACIÓN
```

Esto incluye inicialmente el acceso ordinario del prestador a sus propias intervenciones históricas asociadas al vehículo cuando dicho acceso dependa de mantener una relación activa.

Sin embargo:

```text
PERDER ACCESO
      ≠
ELIMINAR REGISTROS
DEL HISTORIAL
```

Las intervenciones, servicios y demás registros legítimamente generados por el prestador deberán permanecer dentro del historial del vehículo.

Por ejemplo:

```text
PRESTADOR A
      ↓
Realiza mantenimiento
      ↓
Registro entra al historial
      ↓
Posteriormente finaliza
la relación
      ↓
Prestador A pierde
el acceso correspondiente
      ↓
PERO
      ↓
El mantenimiento continúa
formando parte del historial
del vehículo
```

Si posteriormente se establece nuevamente una relación válida entre el mismo prestador y el vehículo, el acceso a sus propias intervenciones históricas podrá restablecerse conforme a las reglas y permisos aplicables.

Una solicitud de relación enviada por un Prestador de Servicios Vehiculares no deberá otorgarle acceso al historial ni a la información del vehículo mientras no exista una autorización válida.

Conceptualmente:

```text
PRESTADOR
     ↓
SOLICITA RELACIÓN
     ↓
ESTADO PENDIENTE
     ↓
NO OBTIENE ACCESO
A LA INFORMACIÓN
DEL VEHÍCULO
```

Solamente después de establecerse una relación válida podrán habilitarse los accesos correspondientes según las reglas definidas.

Por lo tanto:

```text
SOLICITAR RELACIÓN
        ≠
OBTENER ACCESO
```

La trazabilidad interna conservada por Vehículos Services respecto de modificaciones, correcciones, anulaciones y otras acciones realizadas sobre los registros no deberá considerarse automáticamente información visible para todos los usuarios.

Por ejemplo:

```text
VALOR ORIGINAL
652.000 km
        ↓
CORRECCIÓN
65.200 km
        ↓
VEHÍCULOS SERVICES
CONSERVA INTERNAMENTE
LA TRAZABILIDAD
```

La aplicación podrá presentar normalmente al usuario autorizado el valor vigente:

```text
Kilometraje:
65.200 km
```

Mientras internamente conserva:

```text
Valor anterior
Valor nuevo
Actor que realizó el cambio
Fecha y hora
Acción realizada
```

El acceso a esta información de auditoría deberá definirse posteriormente según roles, permisos y necesidades operativas, administrativas, de soporte, seguridad o auditoría.

Por lo tanto:

```text
CONSERVAR TRAZABILIDAD
        ≠
MOSTRAR TODA LA TRAZABILIDAD
A TODOS LOS ACTORES
```

Podrán existir situaciones excepcionales en las que personal autorizado de Vehículos Services requiera acceder a determinada información para actividades como soporte, seguridad, investigación de incidentes, atención de reclamaciones u otras necesidades legítimas que posteriormente sean definidas.

Dicho acceso no deberá considerarse acceso ordinario al historial.

Deberá estar sujeto a mecanismos específicos de autorización, control y trazabilidad que serán definidos posteriormente dentro de los componentes correspondientes de seguridad, permisos y auditoría.

Como principio general, Vehículos Services deberá conservar un historial integral y continuo del vehículo mientras controla independientemente quién puede consultar cada parte de la información.

Conceptualmente:

```text
              VEHÍCULO
                  ↓
        HISTORIAL ÚNICO
          Y CONTINUO
                  ↓
        INFORMACIÓN DE
       DIFERENTES ORÍGENES
                  ↓
         REGLAS DE ACCESO
                  │
       ┌──────────┼──────────┐
       ↓          ↓          ↓
 PROPIETARIO   PRESTADOR   OTROS
       │          │          │
       └──────────┼──────────┘
                  ↓
        SOLO INFORMACIÓN
           AUTORIZADA
```

Por lo tanto:

```text
PERTENECER AL HISTORIAL
        ≠
SER VISIBLE PARA TODOS

RELACIÓN CON EL VEHÍCULO
        ≠
ACCESO TOTAL AL HISTORIAL

INFORMACIÓN ESTRUCTURADA
        ≠
DOCUMENTO PRIVADO ADJUNTO

CONSERVACIÓN HISTÓRICA
        ≠
VISIBILIDAD PERMANENTE

FINALIZAR UN ACCESO
        ≠
ELIMINAR EL REGISTRO
```

Las reglas detalladas de autorización, roles, permisos, privacidad, seguridad, tratamiento de información de propietarios anteriores, documentos generados por prestadores y accesos excepcionales deberán desarrollarse posteriormente en los componentes específicos correspondientes, manteniendo los principios establecidos en este punto.

---
## 63.7 MANTENIMIENTO
### 63.7.1 Concepto y propósito del mantenimiento

El mantenimiento dentro de Vehículos Services deberá representar las intervenciones realizadas sobre un vehículo con el propósito de conservar, revisar, ajustar, prevenir, corregir o restablecer condiciones relacionadas con su funcionamiento, seguridad, confiabilidad, desempeño o conservación.

El mantenimiento deberá entenderse como uno de los componentes que forman parte de la vida registrada del vehículo y, por lo tanto, los mantenimientos realizados deberán poder incorporarse a su historial vehicular de acuerdo con las reglas definidas para los registros históricos.

Conceptualmente:

```text
VEHÍCULO
    ↓
MANTENIMIENTO
    ↓
INTERVENCIÓN REALIZADA
SOBRE EL VEHÍCULO
    ↓
REGISTRO DEL MANTENIMIENTO
    ↓
HISTORIAL VEHICULAR
```

El mantenimiento no deberá entenderse únicamente como una reparación originada por una falla.

Dentro del ciclo de vida del vehículo podrán existir intervenciones realizadas para prevenir fallas o deterioros, intervenciones derivadas del uso o de necesidades periódicas y actuaciones destinadas a corregir condiciones detectadas.

Por ejemplo:

```text
VEHÍCULO
   │
   ├── Cambio de aceite
   ├── Cambio de filtros
   ├── Revisión de frenos
   ├── Alineación
   ├── Balanceo
   ├── Cambio de líquido de frenos
   ├── Revisión del sistema de refrigeración
   ├── Cambio de correa cuando corresponda
   ├── Revisión de suspensión
   └── Otras intervenciones
            ↓
       MANTENIMIENTOS
```

Estos ejemplos son únicamente conceptuales y no deberán interpretarse como un catálogo definitivo de mantenimientos aplicable a todos los vehículos.

Las intervenciones necesarias podrán variar según las características del vehículo, sus componentes, tecnología, fabricante, condiciones de uso y demás criterios que posteriormente sean definidos.

La clasificación o naturaleza de los mantenimientos deberá mantenerse separada de su definición general y será desarrollada específicamente en el apartado correspondiente.

Vehículos Services deberá diferenciar conceptualmente el mantenimiento realizado sobre el vehículo del registro mediante el cual dicho mantenimiento queda documentado dentro de la aplicación.

Por lo tanto:

```text
MANTENIMIENTO REALIZADO
          ≠
REGISTRO DEL MANTENIMIENTO
EN VEHÍCULOS SERVICES
```

El mantenimiento corresponde al evento o intervención realizada sobre el vehículo.

El registro corresponde a la información mediante la cual dicho evento queda representado dentro de Vehículos Services.

Por ejemplo:

```text
05/09/2026

ABC Aceites realiza
un mantenimiento
        ↓
EVENTO REAL
DEL VEHÍCULO
        ↓
Posteriormente se registra
en Vehículos Services
        ↓
REGISTRO DE MANTENIMIENTO
        ↓
HISTORIAL VEHICULAR
```

Esta separación permitirá que un mantenimiento pueda formar parte del historial incluso cuando haya sido registrado posteriormente a la fecha en que realmente se realizó, de acuerdo con los principios establecidos para los registros históricos.

El propietario deberá poder registrar directamente un mantenimiento realizado sobre su vehículo cuando la funcionalidad correspondiente lo permita, independientemente de que exista o no un Prestador de Servicios Vehiculares registrado o relacionado activamente con el vehículo.

Esto permitirá que la gestión de mantenimientos pueda funcionar desde la primera etapa correspondiente al módulo del Propietario, sin depender de la implementación del módulo del Prestador de Servicios Vehiculares.

Posteriormente, cuando el módulo del Prestador sea incorporado, los prestadores también podrán generar registros correspondientes a los mantenimientos que realicen, de acuerdo con las relaciones, autorizaciones, permisos y reglas aplicables.

Cuando el propietario registre un mantenimiento realizado por un taller, técnico u otro prestador, podrá asociar la información correspondiente al actor que realizó la intervención cuando dicha información se encuentre disponible.

La identificación del prestador que realizó el mantenimiento no deberá significar automáticamente que dicho prestador haya creado, confirmado o validado el registro dentro de Vehículos Services.

Las reglas generales relacionadas con la procedencia, creación, incorporación, modificación, corrección, conservación y trazabilidad de estos registros deberán regirse por los principios establecidos para el historial vehicular, evitando redefinirlos específicamente para cada tipo de evento.

Un mantenimiento podrá estar compuesto por una o varias actividades realizadas durante una misma intervención.

La definición de dichas actividades, su comportamiento y sus posibles seguimientos se desarrollará específicamente en el apartado correspondiente.

De igual manera, los mantenimientos podrán relacionarse, cuando corresponda, con elementos como:

- Kilometraje.
- Repuestos.
- Componentes.
- Insumos.
- Prestadores de Servicios Vehiculares.
- Costos.
- Observaciones.
- Recomendaciones.
- Documentos o evidencias.
- Reglas de seguimiento.
- Alertas.

La existencia de estas relaciones no deberá implicar que su funcionamiento detallado deba definirse dentro del concepto general de mantenimiento.

Cada componente deberá conservar sus propias reglas dentro del apartado funcional correspondiente.

Por ejemplo:

```text
MANTENIMIENTO
      │
      ├── ACTIVIDADES
      ├── KILOMETRAJE
      ├── REPUESTOS
      ├── INSUMOS
      ├── PRESTADOR
      ├── COSTOS
      ├── RECOMENDACIONES
      └── OTROS ELEMENTOS
             ↓
      RELACIONES SEGÚN
      CORRESPONDA
```

Los mantenimientos realizados deberán acumularse históricamente y permanecer asociados al vehículo.

La realización de un nuevo mantenimiento no deberá reemplazar automáticamente los mantenimientos anteriores.

Conceptualmente:

```text
MANTENIMIENTO A
      ↓
HISTORIAL

MANTENIMIENTO B
      ↓
HISTORIAL

MANTENIMIENTO C
      ↓
HISTORIAL
```

Los diferentes registros deberán permitir conocer progresivamente las intervenciones realizadas sobre el vehículo durante su ciclo de vida.

La conservación, continuidad, temporalidad, modificación y visibilidad de dichos registros deberán seguir las reglas generales establecidas para el historial vehicular, sin crear un historial independiente exclusivo para mantenimiento.

Como principio general:

```text
VEHÍCULO
    ↓
INTERVENCIONES DE MANTENIMIENTO
    ↓
REGISTROS DE MANTENIMIENTO
    ↓
HISTORIAL VEHICULAR
ÚNICO Y CONTINUO
```

La definición detallada de la clasificación de los mantenimientos, las actividades que los conforman, los criterios de seguimiento, kilometraje, periodicidades, reglas, estados, próximos objetivos, repuestos, alertas, recomendaciones y demás comportamientos deberá desarrollarse en los componentes funcionales correspondientes.


---
### 63.7.2 Clasificación de los mantenimientos

Vehículos Services deberá permitir clasificar los mantenimientos de acuerdo con la naturaleza o contexto de la intervención realizada sobre el vehículo.

Esta clasificación deberá permitir identificar conceptualmente por qué o bajo qué contexto general se realizó una intervención, sin reemplazar la descripción específica de las actividades ejecutadas ni las reglas utilizadas para determinar cuándo corresponde realizar un mantenimiento.

Conceptualmente:

```text
MANTENIMIENTO
      ↓
NATURALEZA O CONTEXTO
DE LA INTERVENCIÓN
      │
      ├── Preventivo
      ├── Periódico
      ├── Correctivo
      └── Otras clasificaciones
          que posteriormente
          puedan definirse
```

Inicialmente podrán contemplarse las siguientes clasificaciones conceptuales:

```text
MANTENIMIENTO PREVENTIVO
        ↓
Intervención realizada con el propósito
de prevenir fallas, deterioros o problemas
y contribuir a conservar adecuadamente
el vehículo o alguno de sus componentes.
```

Por ejemplo:

```text
Revisión preventiva
del sistema de frenos
        ↓
No necesariamente existe
una falla previamente detectada
        ↓
Se revisa el sistema para
conocer su condición y prevenir
posibles problemas
```

El mantenimiento preventivo no deberá implicar necesariamente que exista una falla, daño o anomalía previa.

También podrán existir intervenciones cuya realización responda a una recurrencia o periodicidad.

Conceptualmente:

```text
MANTENIMIENTO PERIÓDICO
        ↓
Intervención cuya realización
se repite de acuerdo con
una condición o recurrencia
definida
```

La clasificación de una intervención como periódica deberá indicar que existe una necesidad de repetición o seguimiento, pero no deberá determinar por sí sola el criterio específico, intervalo o condición mediante el cual se realizará dicho seguimiento.

Por lo tanto:

```text
MANTENIMIENTO PERIÓDICO
        ≠
INTERVALO ESPECÍFICO
DE MANTENIMIENTO
```

Una intervención periódica podrá estar asociada posteriormente a criterios como kilometraje, tiempo, una combinación de ambos u otros que sean definidos.

La definición de dichos criterios, intervalos, objetivos y reglas deberá realizarse en los componentes funcionales correspondientes.

Por otra parte, podrán existir mantenimientos realizados como consecuencia de una condición, desgaste, daño, anomalía o falla identificada.

Conceptualmente:

```text
MANTENIMIENTO CORRECTIVO
        ↓
SE IDENTIFICA
UNA CONDICIÓN
        ↓
SE REQUIERE
UNA INTERVENCIÓN
        ↓
SE REALIZA
EL MANTENIMIENTO
```

Por ejemplo:

```text
Se detecta desgaste
en un componente
        ↓
Se determina que
requiere intervención
        ↓
Se realiza el trabajo
correspondiente
        ↓
Se registra dentro
del historial vehicular
```

La clasificación de los mantenimientos no deberá interpretarse necesariamente como un conjunto de categorías rígidas o excluyentes entre sí.

Una misma intervención podrá presentar características correspondientes a más de una clasificación cuando conceptualmente resulte válido.

Por ejemplo:

```text
CAMBIO DE UN COMPONENTE
        │
        ├── Puede realizarse
        │   periódicamente
        │
        └── También puede realizarse
            antes del intervalo previsto
            debido a una condición
            o falla detectada
```

Por esta razón, Vehículos Services no deberá asumir que el nombre de una actividad determina automáticamente y de manera permanente la clasificación del mantenimiento.

La clasificación deberá corresponder al contexto de la intervención registrada.

Por ejemplo:

```text
REVISIÓN DE FRENOS
        │
        ├── Puede realizarse
        │   preventivamente
        │
        ├── Puede formar parte
        │   de una revisión periódica
        │
        └── Puede originarse por
            una condición detectada
```

La actividad puede ser similar, pero la razón o contexto por el cual fue realizada puede ser diferente.

Vehículos Services deberá diferenciar expresamente la clasificación o naturaleza del mantenimiento del criterio utilizado para realizar su seguimiento.

Por lo tanto:

```text
CLASIFICACIÓN O NATURALEZA
DEL MANTENIMIENTO
        ≠
CRITERIO DE SEGUIMIENTO
```

La clasificación deberá responder principalmente a:

```text
¿QUÉ NATURALEZA O CONTEXTO
TIENE LA INTERVENCIÓN?
        ↓
PREVENTIVO
PERIÓDICO
CORRECTIVO
OTROS
```

Mientras que el criterio de seguimiento deberá responder a:

```text
¿MEDIANTE QUÉ CONDICIÓN
SE CONTROLA CUÁNDO
CORRESPONDE REALIZARLA?
        ↓
KILOMETRAJE
TIEMPO
KILOMETRAJE + TIEMPO
OTROS CRITERIOS
```

Por ejemplo:

```text
Mantenimiento:
Cambio de determinado componente

Clasificación:
Preventivo / Periódico

Criterio de seguimiento:
Kilometraje
```

o:

```text
Mantenimiento:
Revisión de determinado sistema

Clasificación:
Preventivo

Criterio de seguimiento:
Tiempo
```

o:

```text
Mantenimiento:
Intervención sobre un componente

Clasificación:
Correctivo

Origen:
Condición o falla detectada
```

De esta manera:

```text
PREVENTIVO
PERIÓDICO
CORRECTIVO
        ↓
CLASIFICACIÓN O NATURALEZA

        ≠

KILOMETRAJE
TIEMPO
KILOMETRAJE + TIEMPO
        ↓
CRITERIOS DE SEGUIMIENTO
```

Esta separación deberá mantenerse en todo Vehículos Services para evitar utilizar ambos conceptos como si representaran la misma característica del mantenimiento.

Las reglas específicas para determinar cuándo corresponde realizar una intervención no deberán quedar definidas únicamente por su clasificación.

Por ejemplo, clasificar un mantenimiento como preventivo no deberá indicar automáticamente:

- Cada cuántos kilómetros debe realizarse.
- Cada cuánto tiempo debe realizarse.
- Cuál será su próximo kilometraje objetivo.
- Cuál será su próxima fecha objetivo.
- Cuándo deberá considerarse próximo.
- Cuándo deberá considerarse vencido.
- Qué alerta deberá generarse.

De igual manera, clasificar una intervención como periódica deberá indicar su carácter recurrente, pero no deberá definir automáticamente el intervalo que le corresponde.

Estas condiciones deberán depender de las reglas de mantenimiento que posteriormente sean establecidas.

No todos los mantenimientos deberán requerir obligatoriamente un criterio de seguimiento.

Podrán existir intervenciones que correspondan únicamente a un evento realizado y registrado dentro del historial sin que necesariamente generen una próxima intervención.

Conceptualmente:

```text
INTERVENCIÓN REALIZADA
        ↓
SE REGISTRA
        ↓
FORMA PARTE DEL HISTORIAL
        ↓
PUEDE REQUERIR
SEGUIMIENTO
        O
NO REQUERIRLO
```

La clasificación del mantenimiento tampoco deberá confundirse con las actividades específicas que lo conforman.

Por lo tanto:

```text
CLASIFICACIÓN
        ↓
Describe la naturaleza
o contexto general
del mantenimiento

ACTIVIDAD
        ↓
Describe específicamente
qué se realizó
```

Por ejemplo:

```text
MANTENIMIENTO

Clasificación:
Preventivo

Actividades:
- Cambio de aceite
- Cambio de filtro
- Revisión de frenos
```

La clasificación no deberá reemplazar el detalle de las actividades realizadas.

De igual manera, las actividades no deberán utilizarse por sí solas para inferir automáticamente una clasificación sin considerar el contexto de la intervención.

Conceptualmente:

```text
MANTENIMIENTO
        │
        ├── CLASIFICACIÓN
        │       ↓
        │   Naturaleza o contexto
        │
        ├── ACTIVIDADES
        │       ↓
        │   Qué se realizó
        │
        └── CRITERIO DE SEGUIMIENTO
                ↓
            Cómo se controla
            cuándo corresponde
            una próxima intervención
```

Estos elementos podrán relacionarse, pero deberán mantenerse conceptualmente diferenciados.

Como principio general:

```text
MANTENIMIENTO
        ↓
CLASIFICACIÓN
        ↓
DEFINE SU NATURALEZA
O CONTEXTO

MANTENIMIENTO / ACTIVIDAD
        ↓
CRITERIO DE SEGUIMIENTO
        ↓
DEFINE CÓMO SE CONTROLA
SU RECURRENCIA
CUANDO CORRESPONDA
```

La definición detallada de los criterios de seguimiento, intervalos, reglas por kilometraje, reglas por tiempo, combinación de condiciones, próximos objetivos, estados, tolerancias, alertas y recomendaciones deberá desarrollarse posteriormente dentro de Kilometraje, Reglas de Mantenimiento y los demás componentes funcionales correspondientes.

---

### 63.7.3 Actividades que conforman un mantenimiento

Un mantenimiento podrá estar conformado por una o varias actividades realizadas durante una misma intervención sobre el vehículo.

La actividad deberá representar específicamente la acción o trabajo realizado, mientras que el mantenimiento permitirá agrupar las diferentes actividades que fueron ejecutadas como parte de una misma intervención.

Por lo tanto:

```text
MANTENIMIENTO
      ≠
ACTIVIDAD INDIVIDUAL
```

Conceptualmente:

```text
MANTENIMIENTO
05/09/2026
65.200 km
      │
      ├── Cambio de aceite
      ├── Cambio de filtro de aceite
      ├── Revisión de frenos
      └── Revisión de niveles
```

En este ejemplo existe un único mantenimiento realizado en una fecha y kilometraje determinados, pero dentro de él se realizaron diferentes actividades.

Esta separación permitirá conservar conjuntamente las acciones que hicieron parte de una misma intervención sin tener que registrar artificialmente cada una como un mantenimiento independiente.

Las diferentes actividades realizadas dentro de un mismo mantenimiento no deberán asumir automáticamente el mismo comportamiento posterior.

Una actividad podrá requerir seguimiento y otra podrá representar únicamente una acción realizada que queda incorporada al historial sin necesidad de generar un próximo seguimiento.

Cuando una actividad requiera seguimiento, este podrá depender, según corresponda, de criterios como:

- Kilometraje.
- Tiempo.
- Kilometraje y tiempo.
- Otros criterios que posteriormente sean definidos.

Por lo tanto, Vehículos Services no deberá asumir que todas las actividades incluidas dentro de un mismo mantenimiento comparten automáticamente:

- El mismo criterio de seguimiento.
- El mismo intervalo.
- El mismo próximo objetivo.
- La misma regla de mantenimiento.
- El mismo estado de seguimiento.
- La misma necesidad de generar alertas o recomendaciones.

Conceptualmente:

```text
MANTENIMIENTO
      │
      ├── ACTIVIDAD A
      │       ↓
      │   SEGUIMIENTO PROPIO
      │   CUANDO CORRESPONDA
      │
      ├── ACTIVIDAD B
      │       ↓
      │   SEGUIMIENTO PROPIO
      │   CUANDO CORRESPONDA
      │
      └── ACTIVIDAD C
              ↓
         SIN SEGUIMIENTO
         POSTERIOR
```

Esto permitirá que las actividades realizadas durante una misma intervención puedan evolucionar de manera independiente cuando sus características o reglas así lo requieran.

Por ejemplo:

```text
MANTENIMIENTO
65.200 km
      │
      ├── Cambio de aceite
      │       ↓
      │   Requiere seguimiento
      │
      ├── Cambio de filtro de aire
      │       ↓
      │   Puede tener su propio
      │   seguimiento
      │
      └── Revisión de frenos
              ↓
          Puede quedar únicamente
          como actividad realizada
```

Los ejemplos anteriores son conceptuales y no deberán interpretarse como reglas técnicas predeterminadas para todos los vehículos.

La definición de los criterios, intervalos, cálculos, objetivos, estados y demás comportamientos utilizados para realizar el seguimiento de una actividad deberá establecerse posteriormente dentro de los componentes correspondientes de Kilometraje y Reglas de Mantenimiento.

Una actividad incluida dentro de un mantenimiento histórico deberá representar una acción efectivamente realizada.

Por esta razón, deberá diferenciarse de una actividad que solamente haya sido recomendada, identificada como pendiente o prevista para realizarse posteriormente.

Conceptualmente:

```text
ACTIVIDAD REALIZADA
        ↓
FORMA PARTE DEL
MANTENIMIENTO REALIZADO
        ↓
FORMA PARTE DEL
HISTORIAL
```

mientras que:

```text
ACTIVIDAD RECOMENDADA
O PENDIENTE
        ↓
NO DEBERÁ PRESENTARSE
COMO SI YA HUBIERA
SIDO REALIZADA
```

Por ejemplo, si durante un mantenimiento se realiza un cambio de aceite y adicionalmente se recomienda revisar las pastillas de freno posteriormente:

```text
REALIZADO:
Cambio de aceite

RECOMENDADO:
Revisar pastillas de freno
en próxima visita
```

Vehículos Services deberá conservar la diferencia entre ambas situaciones.

Una recomendación, actividad pendiente, actividad programada o trabajo sugerido no deberá incorporarse al historial como una intervención efectivamente realizada hasta que exista un evento que confirme su ejecución.

Por lo tanto:

```text
REALIZADO
    ≠
RECOMENDADO
    ≠
PENDIENTE
    ≠
PROGRAMADO
```

La definición detallada de recomendaciones, programación, estados, alertas y demás comportamientos relacionados deberá desarrollarse posteriormente en sus componentes funcionales correspondientes.

Las actividades también podrán relacionarse con componentes, repuestos, insumos u otros elementos involucrados durante la intervención cuando corresponda.

Por ejemplo:

```text
ACTIVIDAD
Cambio de aceite
      │
      ├── Aceite utilizado
      └── Filtro utilizado
```

o:

```text
ACTIVIDAD
Cambio de pastillas de freno
      │
      └── Repuesto instalado
```

No toda actividad deberá requerir necesariamente un repuesto o insumo.

Por ejemplo:

```text
Inspección visual
        ↓
Puede realizarse
sin reemplazar componentes
```

mientras que:

```text
Cambio de batería
        ↓
Implica la instalación
de un componente
```

La relación de una actividad con repuestos, componentes o insumos no deberá sustituir la definición y gestión propia de dichos elementos dentro de sus componentes funcionales correspondientes.

Conceptualmente:

```text
MANTENIMIENTO
      ↓
ACTIVIDAD
      ↓
REPUESTO / INSUMO
      ↓
RELACIÓN ENTRE
LOS ELEMENTOS
```

La actividad tampoco deberá confundirse con la clasificación general del mantenimiento.

Por ejemplo:

```text
MANTENIMIENTO

Clasificación:
Preventivo

Actividades:
- Cambio de aceite
- Cambio de filtro
- Revisión de frenos
```

Conceptualmente:

```text
CLASIFICACIÓN
      ↓
Describe la naturaleza
general del mantenimiento

ACTIVIDAD
      ↓
Describe específicamente
qué se realizó
```

De esta manera, Vehículos Services podrá identificar tanto la naturaleza general de una intervención como las acciones específicas que fueron realizadas durante ella.

Las actividades realizadas deberán permanecer asociadas al mantenimiento correspondiente y formar parte de la información histórica del vehículo.

Si posteriormente una misma actividad vuelve a realizarse, la nueva ejecución deberá corresponder a un nuevo evento y no deberá reemplazar la ejecución anterior.

Por ejemplo:

```text
10/01/2026
Cambio de aceite
60.000 km
        ↓
05/09/2026
Cambio de aceite
65.200 km
        ↓
AMBAS EJECUCIONES
SE CONSERVAN
```

Esto permitirá reconstruir la evolución de una actividad específica a través del tiempo sin perder las intervenciones anteriores.

Cuando exista información suficiente, los diferentes eventos podrán relacionarse posteriormente con los mecanismos de seguimiento correspondientes, sin que dicha lógica de cálculo deba redefinirse dentro del concepto de actividad.

Como principio general:

```text
MANTENIMIENTO
      ↓
AGRUPA LA INTERVENCIÓN
      ↓
ACTIVIDADES
      ↓
DETALLAN QUÉ SE HIZO
      ↓
CADA ACTIVIDAD PUEDE
TENER SU PROPIO
SEGUIMIENTO
CUANDO CORRESPONDA
      ↓
TODO PERMANECE
RELACIONADO CON
EL HISTORIAL VEHICULAR
```

La definición detallada de catálogos de actividades, creación de actividades personalizadas, criterios y reglas de seguimiento, relación con componentes, repuestos, insumos, costos, estados, recomendaciones y demás comportamientos deberá desarrollarse posteriormente en los componentes funcionales correspondientes.

Un mantenimiento podrá estar conformado por una o varias actividades realizadas sobre el vehículo durante una misma intervención.

La actividad deberá representar específicamente qué se hizo sobre el vehículo, permitiendo que el registro del mantenimiento conserve un nivel de detalle suficiente para conocer las acciones realizadas y no únicamente una descripción general del servicio.

Conceptualmente:

```text
MANTENIMIENTO
      ↓
UNA O VARIAS
ACTIVIDADES
      │
      ├── Actividad A
      ├── Actividad B
      ├── Actividad C
      └── ...
```

Por ejemplo:

```text
MANTENIMIENTO

Fecha:
05/09/2026

Kilometraje:
65.200 km

Actividades:
- Cambio de aceite
- Cambio de filtro de aceite
- Revisión de frenos
- Revisión de niveles
```

En este escenario deberá existir una diferencia conceptual entre el mantenimiento como intervención general y cada una de las actividades que fueron realizadas dentro de dicha intervención.

Por lo tanto:

```text
MANTENIMIENTO
      ≠
ACTIVIDAD INDIVIDUAL
```

El mantenimiento podrá funcionar como el registro que agrupa una intervención realizada en determinado momento, mientras que las actividades permitirán identificar específicamente los trabajos que hicieron parte de dicha intervención.

Conceptualmente:

```text
MANTENIMIENTO
05/09/2026
65.200 km
      │
      ├── Cambio de aceite
      ├── Cambio de filtro de aceite
      ├── Revisión de frenos
      └── Revisión de niveles
```

Esta separación será importante porque las diferentes actividades realizadas dentro de un mismo mantenimiento no necesariamente deberán tener el mismo comportamiento posterior.

Una actividad podrá requerir seguimiento por kilometraje, otra podrá depender del tiempo, otra podrá depender de ambos criterios y otra podrá representar únicamente una acción realizada sin generar un próximo seguimiento.

Por ejemplo:

```text
MISMO MANTENIMIENTO
        │
        ├── Cambio de aceite
        │       ↓
        │   Seguimiento propio
        │
        ├── Cambio de filtro
        │       ↓
        │   Seguimiento propio
        │
        ├── Revisión de frenos
        │       ↓
        │   Puede generar o no
        │   seguimiento posterior
        │
        └── Revisión general
                ↓
            Puede quedar únicamente
            como evento histórico
```

Por lo tanto, Vehículos Services no deberá asumir que todas las actividades incluidas dentro de un mismo mantenimiento comparten automáticamente:

- El mismo intervalo de kilometraje.
- La misma periodicidad temporal.
- El mismo próximo kilometraje objetivo.
- La misma próxima fecha objetivo.
- La misma regla de mantenimiento.
- El mismo estado de seguimiento.
- La misma necesidad de generar alertas o recomendaciones.

Cada actividad deberá poder conservar el comportamiento que corresponda según su naturaleza y las reglas que posteriormente sean definidas.

Conceptualmente:

```text
MANTENIMIENTO
      │
      ├── ACTIVIDAD A
      │       ↓
      │    REGLA A
      │       ↓
      │   SEGUIMIENTO A
      │
      ├── ACTIVIDAD B
      │       ↓
      │    REGLA B
      │       ↓
      │   SEGUIMIENTO B
      │
      └── ACTIVIDAD C
              ↓
         SIN SEGUIMIENTO
         POSTERIOR
```

Esto permitirá que un mantenimiento realizado en una misma fecha pueda generar diferentes seguimientos posteriores sin necesidad de dividir artificialmente la intervención original en varios mantenimientos independientes.

Por ejemplo:

```text
MANTENIMIENTO
65.200 km
      │
      ├── Cambio de aceite
      │       ↓
      │   Próximo objetivo:
      │   75.200 km
      │
      ├── Cambio de filtro de aire
      │       ↓
      │   Seguimiento según
      │   su propia regla
      │
      └── Revisión de frenos
              ↓
          Sin próximo kilometraje
          definido en ese momento
```

Los valores anteriores corresponden únicamente a un ejemplo conceptual y no deberán interpretarse como intervalos técnicos predeterminados para todos los vehículos.

Cuando una actividad tenga seguimiento por kilometraje y exista la información necesaria, deberá aplicarse el principio definido previamente para mostrar su evolución respecto al kilometraje actual del vehículo.

Por ejemplo:

```text
ACTIVIDAD:
Cambio de aceite

Realizada:
65.200 km

Próximo objetivo:
75.200 km

Kilometraje actual:
69.500 km

Kilómetros transcurridos:
4.300 km

Kilómetros restantes:
5.700 km
```

Conceptualmente:

```text
ACTIVIDAD
CONTROLADA POR KM
        ↓
KM DE REALIZACIÓN
        ↓
KM TRANSCURRIDOS
        ↓
KM ACTUAL
        ↓
KM RESTANTES
        ↓
PRÓXIMO KM OBJETIVO
```

Este cálculo deberá actualizarse conforme evolucione el kilometraje actual registrado para el vehículo, de acuerdo con las reglas que posteriormente se definan para la gestión del kilometraje.

De igual manera, cuando una actividad tenga seguimiento temporal, deberá poder relacionarse posteriormente con la fecha en que fue realizada y con la siguiente referencia temporal que corresponda.

Conceptualmente:

```text
ACTIVIDAD
CONTROLADA POR TIEMPO
        ↓
FECHA DE REALIZACIÓN
        ↓
TIEMPO TRANSCURRIDO
        ↓
FECHA ACTUAL
        ↓
TIEMPO RESTANTE
        ↓
PRÓXIMA FECHA OBJETIVO
```

Cuando una actividad se encuentre controlada tanto por kilometraje como por tiempo, ambos seguimientos deberán poder coexistir sin que sea necesario duplicar la actividad.

Conceptualmente:

```text
                 ACTIVIDAD
                     ↓
             SEGUIMIENTO
                     │
          ┌──────────┴──────────┐
          ↓                     ↓
     KILOMETRAJE              TIEMPO
          │                     │
          ↓                     ↓
     KM OBJETIVO          FECHA OBJETIVO
```

La manera exacta en que ambas condiciones deberán evaluarse conjuntamente será definida posteriormente dentro de Reglas de Mantenimiento.

Una actividad deberá representar una acción efectivamente realizada cuando forme parte de un mantenimiento histórico.

Por esta razón, deberá diferenciarse entre una actividad realizada y una actividad recomendada, pendiente o prevista para el futuro.

Conceptualmente:

```text
ACTIVIDAD REALIZADA
        ↓
FORMA PARTE DEL
MANTENIMIENTO
        ↓
FORMA PARTE DEL
HISTORIAL
```

mientras que:

```text
ACTIVIDAD RECOMENDADA
O PENDIENTE
        ↓
NO DEBERÁ PRESENTARSE
COMO SI YA HUBIERA
SIDO REALIZADA
```

Por ejemplo, si durante un mantenimiento se realiza un cambio de aceite y adicionalmente se recomienda revisar las pastillas de freno posteriormente:

```text
REALIZADO:
Cambio de aceite

RECOMENDADO:
Revisar pastillas de freno
en próxima visita
```

Vehículos Services deberá conservar conceptualmente la diferencia entre ambas situaciones.

La recomendación no deberá incorporarse al historial como una intervención efectivamente realizada hasta que exista un evento que confirme su ejecución.

Esto permitirá preservar la integridad del historial y evitar que una recomendación, cotización, actividad pendiente o trabajo sugerido sea interpretado posteriormente como un mantenimiento realmente efectuado.

Por lo tanto:

```text
REALIZADO
    ≠
RECOMENDADO
    ≠
PENDIENTE
    ≠
PROGRAMADO
```

La relación entre estos conceptos y los estados que posteriormente puedan definirse deberá desarrollarse en los componentes correspondientes.

Las actividades también podrán relacionarse con componentes, repuestos, insumos u otros elementos involucrados durante la intervención cuando corresponda.

Por ejemplo:

```text
ACTIVIDAD
Cambio de aceite
      │
      ├── Aceite utilizado
      └── Filtro utilizado
```

o:

```text
ACTIVIDAD
Cambio de pastillas de freno
      │
      └── Repuesto instalado
```

Sin embargo, registrar un repuesto o insumo dentro de una actividad no deberá eliminar la necesidad de conservar su información dentro de la estructura correspondiente cuando posteriormente se defina el componente de Repuestos.

Conceptualmente:

```text
MANTENIMIENTO
      ↓
ACTIVIDAD
      ↓
REPUESTO / INSUMO
      ↓
RELACIÓN ENTRE
LOS ELEMENTOS
```

No deberá asumirse que toda actividad requiere necesariamente un repuesto o insumo.

Por ejemplo:

```text
Inspección visual
        ↓
Puede realizarse
sin reemplazar componentes
```

mientras que:

```text
Cambio de batería
        ↓
Implica la instalación
de un componente
```

Cuando una actividad sea registrada, deberá conservarse la información suficiente para identificarla dentro del mantenimiento al que pertenece y mantener su relación con el evento histórico correspondiente.

La definición exacta de los datos asociados a cada actividad, sus campos obligatorios y opcionales, catálogos, descripciones, relación con componentes, repuestos, insumos, costos, recomendaciones y demás información específica deberá realizarse posteriormente en los componentes funcionales correspondientes.

La actividad tampoco deberá confundirse con la clasificación general del mantenimiento.

Por ejemplo:

```text
MANTENIMIENTO

Clasificación:
Preventivo

Actividades:
- Cambio de aceite
- Cambio de filtro
- Revisión de frenos
```

Conceptualmente:

```text
CLASIFICACIÓN
      ↓
Describe la naturaleza
general del mantenimiento

ACTIVIDAD
      ↓
Describe específicamente
qué se realizó
```

Esta separación permitirá que Vehículos Services pueda organizar los mantenimientos por su naturaleza y, al mismo tiempo, conservar el detalle de las acciones realmente ejecutadas.

Las actividades realizadas deberán permanecer asociadas al mantenimiento correspondiente y formar parte de la información histórica del vehículo.

Conceptualmente:

```text
VEHÍCULO
    ↓
HISTORIAL
    ↓
MANTENIMIENTO
    ↓
ACTIVIDADES REALIZADAS
```

Si posteriormente una misma actividad vuelve a realizarse, deberá generarse un nuevo evento asociado a la nueva intervención y conservarse el registro anterior.

Por ejemplo:

```text
10/01/2026
Cambio de aceite
60.000 km
        ↓
05/09/2026
Cambio de aceite
65.200 km
        ↓
AMBOS REGISTROS
SE CONSERVAN
```

Esto permitirá reconstruir la evolución de una actividad específica a través del tiempo y, cuando exista información suficiente, determinar la distancia recorrida o el tiempo transcurrido entre sus diferentes intervenciones.

Conceptualmente:

```text
ACTIVIDAD ANTERIOR
        ↓
EVOLUCIÓN DEL VEHÍCULO
        ↓
NUEVA EJECUCIÓN
DE LA ACTIVIDAD
        ↓
AMBOS EVENTOS
PERMANECEN EN
EL HISTORIAL
```

Como principio general, Vehículos Services deberá permitir que un mantenimiento represente una intervención completa y que las actividades representen específicamente las acciones realizadas dentro de ella, manteniendo la posibilidad de que cada actividad tenga relaciones y seguimientos propios cuando corresponda.

Conceptualmente:

```text
MANTENIMIENTO
      ↓
AGRUPA LA INTERVENCIÓN
      ↓
ACTIVIDADES
      ↓
DETALLAN QUÉ SE HIZO
      ↓
CADA ACTIVIDAD PUEDE
TENER SU PROPIO
SEGUIMIENTO
      ↓
TODO PERMANECE
RELACIONADO CON
EL HISTORIAL VEHICULAR
```

La definición detallada de catálogos de actividades, creación de actividades personalizadas, reglas de seguimiento, relación con componentes, repuestos, insumos, costos, estados, recomendaciones y demás comportamientos deberá desarrollarse posteriormente en los puntos funcionales correspondientes.

---
### 63.7.4 Información asociada a un mantenimiento

Cada mantenimiento registrado en Vehículos Services deberá poder conservar la información necesaria para identificar y describir la intervención realizada sobre el vehículo.

La información asociada al mantenimiento deberá permitir comprender el contexto básico de la intervención sin que sea necesario interpretar el mantenimiento únicamente a partir de una descripción libre.

Conceptualmente:

```text
MANTENIMIENTO
        ↓
INTERVENCIÓN REALIZADA
        ↓
INFORMACIÓN ASOCIADA
        │
        ├── Fecha
        ├── Kilometraje
        ├── Clasificación
        ├── Actividades realizadas
        ├── Responsable de la intervención,
        │   cuando corresponda
        ├── Costos,
        │   cuando corresponda
        ├── Observaciones
        ├── Repuestos / insumos,
        │   cuando corresponda
        └── Documentos / evidencias,
            cuando corresponda
```

La información que pueda estar asociada a un mantenimiento podrá incluir, entre otros elementos:

- Fecha de realización de la intervención.
- Kilometraje del vehículo al momento de la intervención, cuando se encuentre disponible o corresponda registrarlo.
- Clasificación o naturaleza del mantenimiento.
- Actividad o actividades realizadas.
- Responsable de la intervención, cuando corresponda.
- Prestador de Servicios Vehiculares que realizó la intervención, cuando corresponda.
- Información que permita identificar a quien realizó el servicio cuando este no corresponda a un Prestador de Servicios Vehiculares registrado en la plataforma.
- Identificación de que la intervención fue realizada directamente por el propietario, cuando corresponda.
- Costos asociados, cuando corresponda.
- Observaciones relacionadas con la intervención.
- Repuestos, componentes o insumos utilizados, instalados, reemplazados o relacionados con las actividades realizadas, cuando corresponda.
- Documentos, facturas, fotografías u otras evidencias asociadas, cuando correspondan.
- Otra información que posteriormente sea determinada como necesaria para representar adecuadamente la intervención.

La existencia de estos elementos dentro de la definición conceptual no deberá significar que todos sean obligatorios para todos los mantenimientos.

Por ejemplo:

```text
MANTENIMIENTO A
        ↓
Fecha
Kilometraje
Clasificación
Actividades
Prestador
Costo
Repuestos
Factura
Observaciones

MANTENIMIENTO B
        ↓
Fecha
Kilometraje
Clasificación
Actividades
Observaciones
```

Ambos podrán representar intervenciones válidas, siempre que cumplan con la información requerida de acuerdo con las reglas que posteriormente sean definidas.

Vehículos Services deberá diferenciar entre la información propia del mantenimiento como intervención y la información específica perteneciente a las actividades que lo conforman.

Conceptualmente:

```text
MANTENIMIENTO
        │
        ├── INFORMACIÓN GENERAL
        │   DE LA INTERVENCIÓN
        │
        │   Fecha
        │   Kilometraje
        │   Clasificación
        │   Responsable
        │   Costo general,
        │   cuando corresponda
        │   Observaciones generales
        │
        └── ACTIVIDADES
                │
                ├── Actividad A
                ├── Actividad B
                └── Actividad C
```

Por ejemplo:

```text
MANTENIMIENTO

Fecha:
05/09/2026

Kilometraje:
65.200 km

Clasificación:
Preventivo / Periódico

Prestador:
ABC Aceites

Actividades:
- Cambio de aceite
- Cambio de filtro de aceite
- Revisión de niveles

Costo:
$250.000

Observación:
Se realizó revisión general
durante la intervención
```

En este ejemplo, la fecha y el kilometraje permiten contextualizar cuándo se realizó la intervención, mientras que las actividades permiten conocer específicamente qué trabajos fueron ejecutados.

La clasificación deberá conservar el significado definido para la naturaleza o contexto del mantenimiento y no deberá utilizarse para sustituir el detalle de las actividades realizadas.

Por lo tanto:

```text
CLASIFICACIÓN:
Preventivo
        ≠
ACTIVIDAD:
Cambio de aceite
```

De igual manera, la existencia de un kilometraje asociado al mantenimiento deberá representar la lectura correspondiente a la intervención cuando dicha información se encuentre disponible.

Por ejemplo:

```text
MANTENIMIENTO
05/09/2026

Kilometraje asociado:
65.200 km
```

El registro de este kilometraje podrá posteriormente relacionarse con los mecanismos de seguimiento y cálculo correspondientes, pero este punto no deberá definir cómo se calculan kilómetros transcurridos, kilómetros restantes, próximos kilometrajes objetivo ni demás reglas relacionadas con el seguimiento por kilometraje.

Dichos comportamientos deberán permanecer definidos dentro de Kilometraje y Reglas de Mantenimiento.

La persona, establecimiento o Prestador de Servicios Vehiculares que haya realizado una intervención deberá poder diferenciarse del actor que posteriormente registre la información en Vehículos Services.

Cuando la intervención haya sido realizada por un Prestador de Servicios Vehiculares, el mantenimiento podrá conservar la relación con dicho prestador.

Conceptualmente:

```text
MANTENIMIENTO
        ↓
REALIZADO POR
        ↓
PRESTADOR DE SERVICIOS
VEHICULARES
```

Sin embargo, la información relacionada con quién realizó la intervención no deberá confundirse con quién creó, incorporó, completó o modificó posteriormente el registro dentro de Vehículos Services.

Por lo tanto:

```text
QUIÉN REALIZÓ
LA INTERVENCIÓN
        ≠
QUIÉN REGISTRÓ
LA INFORMACIÓN
```

Las reglas relacionadas con la creación del registro, su procedencia y la trazabilidad de los actores que intervienen sobre la información deberán mantenerse en el apartado correspondiente al Historial Vehicular.

También podrán registrarse mantenimientos realizados por talleres, personas o prestadores que no se encuentren registrados como Prestadores de Servicios Vehiculares dentro de Vehículos Services.

En estos casos, cuando corresponda, podrá conservarse información suficiente para identificar quién realizó la intervención sin que esto implique la creación automática de una relación formal Prestador ↔ Vehículo dentro de la plataforma.

Conceptualmente:

```text
SERVICIO REALIZADO POR
TALLER NO REGISTRADO
        ↓
SE REGISTRA EL MANTENIMIENTO
        ↓
SE PUEDE CONSERVAR
INFORMACIÓN DEL TALLER
        ↓
NO SE CREA AUTOMÁTICAMENTE
UNA RELACIÓN
PRESTADOR ↔ VEHÍCULO
```

Un mantenimiento o alguna de sus actividades también podrá haber sido realizado directamente por el propietario del vehículo cuando corresponda.

Vehículos Services no deberá asumir que toda intervención, mantenimiento, sustitución de un repuesto o actividad registrada sobre un vehículo fue realizada necesariamente por un Prestador de Servicios Vehiculares.

Por ejemplo:

```text
PROPIETARIO
        ↓
REALIZA DIRECTAMENTE
UNA INTERVENCIÓN
        │
        ├── Cambio de plumillas
        ├── Cambio de batería
        └── Otra actividad
            que pueda realizar
            directamente
        ↓
REGISTRA EL MANTENIMIENTO
O LA INTERVENCIÓN
        ↓
HISTORIAL VEHICULAR
```

En estos casos, el propietario podrá corresponder tanto al actor que realizó la intervención como al actor que registró la información en Vehículos Services.

Conceptualmente:

```text
REALIZADO POR:
Propietario

REGISTRADO POR:
Propietario
```

Por lo tanto, Vehículos Services deberá contemplar, entre otros, los siguientes escenarios:

```text
ESCENARIO 1

PRESTADOR
realiza la intervención
        ↓
PRESTADOR
registra la información
```

```text
ESCENARIO 2

PRESTADOR O TERCERO
realiza la intervención
        ↓
PROPIETARIO
registra la información
```

```text
ESCENARIO 3

PROPIETARIO
realiza directamente
la intervención
        ↓
PROPIETARIO
registra la información
```

La realización directa de una intervención por parte del propietario no deberá requerir la existencia ni la asociación artificial de un Prestador de Servicios Vehiculares para poder incorporar el evento al historial.

Por lo tanto:

```text
MANTENIMIENTO O INTERVENCIÓN
        ≠
PRESTADOR OBLIGATORIO
```

Cuando una intervención realizada por el propietario involucre repuestos, componentes o insumos, estos podrán relacionarse con la actividad correspondiente de la misma manera que en otras intervenciones, de acuerdo con las reglas que posteriormente sean definidas para dichos elementos.

Por ejemplo:

```text
PROPIETARIO
        ↓
CAMBIA BATERÍA
        ↓
ACTIVIDAD:
Cambio de batería
        ↓
REPUESTO / COMPONENTE:
Batería instalada
        ↓
REGISTRO EN
HISTORIAL VEHICULAR
```

El hecho de que una intervención haya sido realizada directamente por el propietario deberá conservarse como parte de la información asociada al evento y no deberá atribuirse dicha intervención a un Prestador de Servicios Vehiculares inexistente.

La posibilidad de registrar una intervención realizada directamente por el propietario tampoco deberá implicar que Vehículos Services determine que cualquier actividad puede ser realizada técnicamente por el propietario.

La plataforma deberá limitarse a conservar correctamente la información registrada sobre quién realizó la intervención. Las recomendaciones, restricciones, advertencias o criterios que posteriormente puedan aplicar a determinadas actividades deberán definirse en los componentes correspondientes.

Los costos podrán asociarse al mantenimiento cuando dicha información se encuentre disponible.

Conceptualmente:

```text
MANTENIMIENTO
        ↓
ACTIVIDADES REALIZADAS
        +
REPUESTOS / INSUMOS
        +
OTROS CONCEPTOS
        ↓
INFORMACIÓN DE COSTOS
CUANDO CORRESPONDA
```

La existencia de costos asociados permitirá posteriormente utilizar esta información para consultas, análisis, reportes u otras funcionalidades que sean definidas.

Este punto no deberá establecer todavía cómo se distribuirán los costos entre mano de obra, actividades, repuestos, insumos, impuestos, descuentos u otros conceptos.

La estructura detallada de costos deberá definirse posteriormente cuando se determine el nivel de detalle requerido para esta funcionalidad.

Un mantenimiento también podrá relacionarse con repuestos, componentes o insumos cuando alguna de sus actividades los utilice, instale, reemplace, retire o involucre.

Por ejemplo:

```text
MANTENIMIENTO
        ↓
ACTIVIDAD:
Cambio de filtro de aceite
        ↓
REPUESTO / INSUMO:
Filtro de aceite
```

o:

```text
MANTENIMIENTO
        ↓
ACTIVIDAD:
Cambio de batería
        ↓
COMPONENTE:
Batería instalada
```

Esta relación no deberá significar que todos los mantenimientos requieren obligatoriamente repuestos, componentes o insumos.

Por ejemplo:

```text
REVISIÓN VISUAL
        ↓
PUEDE FORMAR PARTE
DE UN MANTENIMIENTO
        ↓
SIN REQUERIR
REEMPLAZO DE REPUESTOS
```

La información específica relacionada con identificación, características, instalación, reemplazo, retiro, vida útil o seguimiento de repuestos y componentes deberá desarrollarse posteriormente dentro del componente correspondiente a Repuestos.

El mantenimiento también podrá contener observaciones que permitan complementar el contexto de la intervención.

Por ejemplo:

```text
OBSERVACIÓN

“Durante la revisión se identificó
desgaste en las pastillas de freno.”
```

Una observación deberá entenderse como información complementaria del mantenimiento y no deberá convertirse automáticamente en una actividad realizada, una falla confirmada, una recomendación, un mantenimiento pendiente o una próxima intervención.

Por lo tanto:

```text
OBSERVACIÓN
        ≠
ACTIVIDAD REALIZADA

OBSERVACIÓN
        ≠
MANTENIMIENTO FUTURO
AUTOMÁTICAMENTE PROGRAMADO
```

Cuando una observación deba posteriormente originar una recomendación, seguimiento, alerta u otra acción dentro de Vehículos Services, dicho comportamiento deberá depender de las reglas funcionales correspondientes.

También podrán asociarse documentos o evidencias al mantenimiento cuando se encuentren disponibles o cuando posteriormente sean requeridos por una funcionalidad específica.

Por ejemplo:

```text
MANTENIMIENTO
        │
        ├── Factura
        ├── Fotografía
        ├── Orden de servicio
        └── Otro soporte
```

Sin embargo:

```text
REGISTRAR UN MANTENIMIENTO
        ≠
ADJUNTAR OBLIGATORIAMENTE
UN DOCUMENTO
```

La existencia del registro estructurado del mantenimiento deberá diferenciarse de la existencia de documentos o evidencias adjuntas.

Las reglas relacionadas con privacidad, visibilidad, acceso y conservación de dichos documentos deberán regirse por los principios establecidos para el Historial Vehicular y por las reglas específicas que posteriormente sean definidas para documentos y permisos.

La información asociada al mantenimiento deberá conservar su relación con el vehículo y con el evento histórico correspondiente.

Conceptualmente:

```text
VEHÍCULO
        ↓
HISTORIAL VEHICULAR
        ↓
MANTENIMIENTO
        │
        ├── Información general
        ├── Clasificación
        ├── Actividades
        ├── Responsable de la intervención
        ├── Costos
        ├── Repuestos / insumos
        ├── Observaciones
        └── Documentos / evidencias
```

Este punto define únicamente la información conceptual que podrá estar asociada a una intervención de mantenimiento.

No se definen todavía:

- Los campos técnicos del registro.
- Los nombres definitivos de los campos.
- Los tipos de datos.
- Los campos obligatorios y opcionales definitivos.
- Los catálogos que deberán utilizarse.
- La estructura de almacenamiento.
- El modelo de datos.
- La interfaz o formulario de registro.
- Las validaciones técnicas.
- Las reglas detalladas de costos.
- Las reglas detalladas de repuestos e insumos.
- Los cálculos de kilometraje.
- Los intervalos de mantenimiento.
- Los próximos objetivos por kilometraje o tiempo.
- Los estados del mantenimiento.
- Las tolerancias.
- Las alertas.
- Las recomendaciones.
- Los permisos de consulta o modificación.
- Las reglas de auditoría.
- Los mecanismos de integración con Prestadores de Servicios Vehiculares.

Estos elementos deberán desarrollarse posteriormente dentro de sus respectivos componentes funcionales y técnicos.

Como principio general:

```text
MANTENIMIENTO
        ↓
IDENTIFICA UNA
INTERVENCIÓN REALIZADA
        ↓
CONSERVA INFORMACIÓN
QUE PERMITE
CONTEXTUALIZARLA
        ↓
DETALLA LAS ACTIVIDADES
REALIZADAS
        ↓
IDENTIFICA QUIÉN REALIZÓ
LA INTERVENCIÓN
        ↓
PUEDE HABER SIDO REALIZADA POR
PRESTADOR / TERCERO / PROPIETARIO
        ↓
PUEDE RELACIONARSE CON
COSTOS
REPUESTOS / INSUMOS
OBSERVACIONES
DOCUMENTOS / EVIDENCIAS
        ↓
SE INCORPORA AL
HISTORIAL VEHICULAR
```

La existencia de información asociada al mantenimiento no deberá provocar que este componente asuma responsabilidades correspondientes a otros componentes de Vehículos Services.

Cada concepto relacionado deberá conservar las reglas y comportamientos definidos en su apartado correspondiente.

---

## 63.8 REPUESTOS

### 63.8.1 Concepto y propósito del repuesto

Dentro de Vehículos Services, un repuesto deberá entenderse como un elemento que puede ser instalado, sustituido o retirado de un vehículo como consecuencia de una intervención realizada sobre este.

Los repuestos deberán poder formar parte de la información registrada durante el ciclo de vida del vehículo cuando su identificación resulte relevante para conocer qué elementos han sido instalados, reemplazados o retirados.

Conceptualmente:

```text
VEHÍCULO
        ↓
INTERVENCIÓN
        ↓
REPUESTO
        ↓
INSTALACIÓN / REEMPLAZO / RETIRO
        ↓
REGISTRO
        ↓
HISTORIAL VEHICULAR
```

El propósito de gestionar repuestos dentro de Vehículos Services no deberá limitarse a registrar que se realizó determinada actividad.

Cuando exista información suficiente, la plataforma deberá permitir conocer qué repuesto estuvo relacionado con dicha intervención.

Por ejemplo:

```text
MANTENIMIENTO
        ↓
ACTIVIDAD:
Cambio de batería
        ↓
REPUESTO:
Batería
```

De esta manera, deberá poder diferenciarse entre la actividad realizada y el elemento involucrado en ella.

Por lo tanto:

```text
ACTIVIDAD
        ≠
REPUESTO
```

Por ejemplo:

```text
ACTIVIDAD:
Cambio de pastillas de freno

REPUESTO:
Pastillas de freno instaladas
```

La actividad representa lo que se realizó sobre el vehículo, mientras que el repuesto representa el elemento relacionado con dicha actividad.

Un repuesto podrá estar relacionado con diferentes tipos de intervenciones.

Por ejemplo:

```text
REPUESTO
        ↓
PUEDE ESTAR RELACIONADO CON
        │
        ├── Mantenimiento
        ├── Reparación
        ├── Sustitución
        ├── Instalación
        └── Otra intervención
            que posteriormente
            sea definida
```

Por lo tanto, la gestión de repuestos no deberá quedar limitada exclusivamente a los mantenimientos.

Una reparación también podrá involucrar la instalación o sustitución de uno o varios repuestos y deberá poder conservar dicha información dentro del historial del vehículo.

Por ejemplo:

```text
VEHÍCULO
        ↓
REPARACIÓN
        ↓
REEMPLAZO DE ALTERNADOR
        ↓
REPUESTO INSTALADO:
Alternador
        ↓
HISTORIAL VEHICULAR
```

La incorporación de un repuesto deberá permitir posteriormente conocer, cuando exista la información correspondiente, qué elemento fue instalado o reemplazado en el vehículo y en qué intervención ocurrió.

Conceptualmente:

```text
VEHÍCULO
        ↓
INTERVENCIÓN
        ↓
ACTIVIDAD
        ↓
REPUESTO RELACIONADO
        ↓
INFORMACIÓN CONSERVADA
COMO PARTE DE LA VIDA
REGISTRADA DEL VEHÍCULO
```

Un mismo vehículo podrá tener diferentes repuestos registrados durante su ciclo de vida.

Además, un mismo tipo de repuesto podrá ser reemplazado varias veces a lo largo del tiempo.

Por ejemplo:

```text
BATERÍA
Instalada: 2024
        ↓
REEMPLAZADA
        ↓
BATERÍA
Instalada: 2026
        ↓
REEMPLAZADA
        ↓
BATERÍA
Instalada: 2029
```

Estos registros deberán representar eventos diferentes y no deberán interpretarse como un único repuesto que simplemente modifica sus datos.

Por lo tanto:

```text
NUEVO REPUESTO INSTALADO
        ≠
SOBRESCRIBIR EL REPUESTO
ANTERIORMENTE REGISTRADO
```

Cuando un repuesto sea reemplazado, la información histórica del elemento anterior deberá conservarse de acuerdo con las reglas correspondientes del Historial Vehicular.

Esto permitirá posteriormente responder preguntas como:

```text
¿Qué repuesto tiene instalado actualmente el vehículo?

¿Cuándo fue instalado?

¿En qué kilometraje fue instalado?

¿Qué repuesto tenía anteriormente?

¿Cuándo fue reemplazado?

¿En qué intervención se realizó el cambio?

¿Quién realizó la intervención?

¿Cuánto tiempo permaneció instalado?

¿Cuántos kilómetros recorrió mientras estuvo instalado?
```

La posibilidad de responder cada una de estas preguntas dependerá de que exista la información necesaria y de las reglas que posteriormente sean definidas para cada caso.

No deberá asumirse que todos los repuestos requieren el mismo nivel de seguimiento.

Por ejemplo, determinados elementos podrán requerir conocer su instalación y posterior reemplazo, mientras que para otros podrá ser suficiente conservar que fueron utilizados o reemplazados durante determinada intervención.

Conceptualmente:

```text
REPUESTO
        ↓
SU COMPORTAMIENTO Y SEGUIMIENTO
PUEDE DEPENDER DE
        ↓
TIPO DE ELEMENTO
        +
INFORMACIÓN DISPONIBLE
        +
REGLAS APLICABLES
```

La definición de un repuesto tampoco deberá implicar que todo elemento utilizado durante una intervención deba tratarse de la misma manera.

Vehículos Services deberá poder diferenciar posteriormente conceptos como:

```text
REPUESTO

COMPONENTE

INSUMO
```

Por ejemplo, una batería, un sistema de frenos y un aceite utilizado durante un mantenimiento representan elementos conceptualmente diferentes y no deberán tratarse automáticamente como equivalentes.

La diferenciación formal entre repuesto, componente e insumo será desarrollada en el punto correspondiente.

Los repuestos podrán estar relacionados con intervenciones realizadas por diferentes actores.

Por lo tanto, la existencia de un repuesto instalado, reemplazado o retirado no deberá implicar que necesariamente haya participado un Prestador de Servicios Vehiculares.

Conceptualmente:

```text
INTERVENCIÓN
        ↓
PUEDE SER REALIZADA POR
        │
        ├── Prestador de Servicios Vehiculares
        ├── Tercero
        └── Propietario
        ↓
PUEDE INVOLUCRAR
UN REPUESTO
```

Por ejemplo:

```text
PROPIETARIO
        ↓
CAMBIA LAS PLUMILLAS
        ↓
REGISTRA LA INTERVENCIÓN
        ↓
REPUESTO INSTALADO:
Nuevas plumillas
        ↓
HISTORIAL VEHICULAR
```

o:

```text
PROPIETARIO
        ↓
CAMBIA LA BATERÍA
        ↓
REGISTRA LA INTERVENCIÓN
        ↓
REPUESTO INSTALADO:
Nueva batería
        ↓
HISTORIAL VEHICULAR
```

Esto deberá mantenerse alineado con las reglas definidas para Mantenimiento, donde una intervención puede ser realizada directamente por el propietario y posteriormente incorporada al historial sin requerir la asociación artificial de un Prestador de Servicios Vehiculares.

La gestión de repuestos deberá permitir conservar tanto la relación del elemento con el vehículo como su relación con la intervención en la cual fue instalado, reemplazado, retirado o utilizado, cuando corresponda.

Conceptualmente:

```text
VEHÍCULO
        ↓
INTERVENCIÓN
        ↓
ACTIVIDAD
        ↓
REPUESTO
        ↓
RELACIÓN CON EL VEHÍCULO
        ↓
HISTORIAL
```

Sin embargo, este punto no deberá definir todavía:

- La diferenciación detallada entre repuesto, componente e insumo.
- La forma exacta en que un repuesto se relaciona con una actividad.
- Las reglas de instalación.
- Las reglas de reemplazo.
- Las reglas de retiro.
- La permanencia de un repuesto en el vehículo.
- La información específica que deberá registrarse para cada repuesto.
- Los campos obligatorios u opcionales.
- La identificación de marca, referencia, fabricante u otras características específicas.
- El tratamiento de repuestos nuevos, usados, originales, alternativos u otras clasificaciones que posteriormente puedan definirse.
- Las reglas de vida útil.
- Los criterios de seguimiento por kilometraje o tiempo.
- Los cálculos relacionados con duración o uso.
- Los estados de un repuesto.
- Las alertas o recomendaciones relacionadas con repuestos.
- Las reglas detalladas de trazabilidad.
- El modelo de datos.
- La estructura técnica de almacenamiento.

Estos elementos deberán desarrollarse progresivamente en los siguientes puntos de Repuestos y, cuando corresponda, en Kilometraje, Reglas de Mantenimiento, Alertas, Historial Vehicular y demás componentes relacionados.

Como principio general:

```text
VEHÍCULO
        ↓
RECIBE UNA INTERVENCIÓN
        ↓
PUEDE INVOLUCRAR
UNO O VARIOS REPUESTOS
        ↓
EL REPUESTO PUEDE SER
INSTALADO
REEMPLAZADO
RETIRADO
        ↓
SE CONSERVA SU RELACIÓN
CON LA INTERVENCIÓN
Y EL VEHÍCULO
        ↓
FORMA PARTE DE LA
TRAZABILIDAD DEL VEHÍCULO
```

La gestión de repuestos deberá permitir que Vehículos Services conozca progresivamente los elementos que han formado parte del vehículo sin reducirlos únicamente a una descripción dentro de un mantenimiento o reparación.


---
### 63.8.2 Diferenciación entre repuesto, componente e insumo

Vehículos Services deberá diferenciar conceptualmente los repuestos, componentes e insumos relacionados con las intervenciones realizadas sobre un vehículo.

Aunque estos elementos pueden encontrarse relacionados dentro de un mismo mantenimiento, reparación u otra intervención, no deberán considerarse automáticamente equivalentes.

Conceptualmente:

```text
ELEMENTOS RELACIONADOS
CON EL VEHÍCULO
        │
        ├── REPUESTOS
        │
        ├── COMPONENTES
        │
        └── INSUMOS
```

Esta diferenciación permitirá representar de manera más precisa qué elemento del vehículo fue intervenido, qué elemento fue instalado o reemplazado y qué materiales o productos fueron utilizados durante la intervención.

Como principio general:

```text
COMPONENTE
        ↓
¿SOBRE QUÉ PARTE, ELEMENTO
O SISTEMA DEL VEHÍCULO
SE REALIZA LA INTERVENCIÓN?

REPUESTO
        ↓
¿QUÉ ELEMENTO FUE
INSTALADO, SUSTITUIDO
O RETIRADO?

INSUMO
        ↓
¿QUÉ MATERIAL O PRODUCTO
FUE UTILIZADO O CONSUMIDO
DURANTE LA INTERVENCIÓN?
```

Estas preguntas representan una orientación conceptual y no deberán utilizarse como una clasificación técnica rígida para todos los casos.

#### Repuesto

Un repuesto deberá entenderse conceptualmente como un elemento que puede ser instalado, sustituido o retirado del vehículo como consecuencia de una intervención.

Por ejemplo:

```text
ACTIVIDAD:
Cambio de batería
        ↓
REPUESTO:
Batería instalada
```

Otro ejemplo:

```text
ACTIVIDAD:
Cambio de pastillas de freno
        ↓
REPUESTO:
Pastillas de freno instaladas
```

También podrán existir otros elementos que, dependiendo de la naturaleza de la intervención, sean tratados como repuestos dentro de Vehículos Services.

El repuesto deberá poder conservar su relación con la intervención en la cual fue instalado, sustituido o retirado y, cuando corresponda, con el vehículo durante el período en que permaneció instalado.

Conceptualmente:

```text
REPUESTO
        ↓
INSTALADO EN
        ↓
VEHÍCULO
        ↓
PERMANECE ASOCIADO
MIENTRAS CORRESPONDA
        ↓
PUEDE SER RETIRADO
O REEMPLAZADO
```

La información detallada asociada al repuesto, así como las reglas de instalación, reemplazo, retiro y permanencia, serán desarrolladas en los siguientes puntos de este componente.

#### Componente

Un componente deberá representar una parte, elemento, conjunto o sistema identificable del vehículo sobre el cual puedan realizarse revisiones, mantenimientos, reparaciones, sustituciones u otras intervenciones.

Por ejemplo:

```text
VEHÍCULO
        ↓
SISTEMA DE FRENOS
        ↓
COMPONENTE / SISTEMA
SOBRE EL CUAL
SE REALIZA UNA INTERVENCIÓN
```

Otros ejemplos conceptuales podrán incluir:

- Sistema de frenos.
- Sistema de suspensión.
- Sistema eléctrico.
- Sistema de refrigeración.
- Motor.
- Transmisión.
- Dirección.
- Sistema de iluminación.
- Otros componentes, conjuntos o sistemas que posteriormente sean definidos.

Un componente podrá relacionarse con uno o varios repuestos.

Por ejemplo:

```text
SISTEMA DE FRENOS
        ↓
PUEDE RELACIONARSE CON
        │
        ├── Pastillas de freno
        ├── Discos
        └── Otros elementos
```

Por lo tanto:

```text
COMPONENTE
        ≠
REPUESTO
```

El componente permite identificar conceptualmente qué parte, elemento o sistema del vehículo está siendo intervenido, mientras que el repuesto permite identificar el elemento instalado, sustituido o retirado cuando corresponda.

Por ejemplo:

```text
VEHÍCULO
        ↓
COMPONENTE:
Sistema de frenos
        ↓
ACTIVIDAD:
Cambio de pastillas
        ↓
REPUESTO:
Pastillas de freno
```

No deberá asumirse que toda intervención realizada sobre un componente implica necesariamente el reemplazo de un repuesto.

Por ejemplo:

```text
COMPONENTE:
Sistema de frenos
        ↓
ACTIVIDAD:
Inspección
        ↓
NO NECESARIAMENTE
EXISTE REEMPLAZO
DE REPUESTOS
```

De igual manera, un componente podrá existir conceptualmente dentro del vehículo independientemente de que se haya registrado previamente una intervención sobre este.

#### Insumo

Un insumo deberá entenderse conceptualmente como un material, producto o elemento consumible utilizado durante una intervención y que, por su naturaleza, no necesariamente deberá tratarse de la misma manera que un repuesto instalado en el vehículo.

Por ejemplo:

```text
ACTIVIDAD:
Cambio de aceite
        ↓
INSUMO:
Aceite de motor
```

La gestión de un insumo deberá permitir, cuando exista la información correspondiente, conocer qué producto fue utilizado durante determinada intervención.

Por ejemplo:

```text
CAMBIO DE ACEITE
        ↓
ACEITE UTILIZADO
        │
        ├── Marca
        ├── Línea / referencia
        ├── Viscosidad
        ├── Especificación
        ├── Cantidad
        └── Otra información aplicable
```

La estructura exacta de esta información deberá definirse posteriormente y podrá variar dependiendo del tipo de insumo.

Otros ejemplos conceptuales de insumos podrán incluir, cuando corresponda:

- Aceites.
- Lubricantes.
- Refrigerantes.
- Líquidos utilizados por determinados sistemas del vehículo.
- Grasas.
- Productos utilizados durante determinadas intervenciones.
- Otros materiales consumibles que posteriormente sean definidos.

La clasificación de un elemento como insumo no deberá depender únicamente de que permanezca físicamente dentro del vehículo después de la intervención.

Por ejemplo, el aceite de motor permanece dentro del motor durante su período de utilización, pero conceptualmente deberá poder tratarse como un insumo consumible utilizado durante el mantenimiento y no necesariamente como un repuesto equivalente a una batería.

Por lo tanto:

```text
PERMANECER EN EL VEHÍCULO
        ≠
SER AUTOMÁTICAMENTE
UN REPUESTO
```

Esta diferenciación será importante para que Vehículos Services pueda representar adecuadamente las características particulares de cada elemento.

Por ejemplo:

```text
CAMBIO DE ACEITE
        │
        ├── COMPONENTE:
        │   Motor
        │
        ├── ACTIVIDAD:
        │   Cambio de aceite
        │
        ├── INSUMO:
        │   Aceite de motor
        │
        └── REPUESTO:
            Filtro de aceite,
            cuando sea reemplazado
```

En una misma intervención podrán coexistir componentes, repuestos e insumos.

Otro ejemplo:

```text
MANTENIMIENTO
SISTEMA DE FRENOS
        │
        ├── COMPONENTE:
        │   Sistema de frenos
        │
        ├── ACTIVIDAD:
        │   Cambio de pastillas
        │
        ├── REPUESTO:
        │   Pastillas de freno
        │
        └── INSUMO:
            Podrá existir cuando
            la intervención utilice
            algún producto consumible
            aplicable
```

Esto permitirá que la información no quede limitada a descripciones generales como:

```text
"Se realizó mantenimiento"
```

o:

```text
"Se cambiaron los frenos"
```

Cuando exista información suficiente, Vehículos Services deberá poder representar de manera estructurada la relación entre los elementos involucrados.

Conceptualmente:

```text
VEHÍCULO
        ↓
COMPONENTE / SISTEMA
        ↓
INTERVENCIÓN
        ↓
ACTIVIDAD
        │
        ├── REPUESTO
        │
        └── INSUMO
```

La existencia de estas categorías no deberá obligar a que toda intervención contenga simultáneamente un componente, un repuesto y un insumo.

Podrán existir, por ejemplo:

```text
ACTIVIDAD
        ↓
SIN REPUESTO
SIN INSUMO
```

o:

```text
ACTIVIDAD
        ↓
REPUESTO
        ↓
SIN INSUMO
```

o:

```text
ACTIVIDAD
        ↓
REPUESTO
        +
INSUMO
```

La información requerida dependerá de la naturaleza de la intervención y de los elementos que realmente hayan participado en ella.

Vehículos Services tampoco deberá forzar una clasificación incorrecta únicamente para poder registrar una intervención.

Si determinado elemento requiere posteriormente una categoría o tratamiento diferente debido a su naturaleza, dicha clasificación podrá ampliarse dentro del levantamiento funcional correspondiente.

Por lo tanto, inicialmente:

```text
REPUESTO
        ↓
Elemento instalado,
sustituido o retirado

COMPONENTE
        ↓
Parte, elemento, conjunto
o sistema identificable
del vehículo sobre el cual
pueden realizarse intervenciones

INSUMO
        ↓
Material o producto
consumible utilizado
durante una intervención
```

Estas definiciones deberán utilizarse como base conceptual para organizar la información, pero no deberán impedir que posteriormente se definan categorías adicionales cuando exista una necesidad funcional real.

La diferenciación también permitirá que la información consultada por el propietario pueda presentarse con el contexto correspondiente.

Por ejemplo:

```text
05/09/2026
65.200 km

MANTENIMIENTO:
Cambio de aceite

COMPONENTE:
Motor

INSUMO:
Aceite de motor
Marca: Mobil
Línea: Super 2000
Viscosidad: 5W-30
Cantidad: 4 litros

REPUESTO:
Filtro de aceite
Marca: Bosch
Referencia: XXXXX
```

De esta manera, el propietario podrá conocer no solamente qué actividad fue realizada, sino también qué productos o elementos fueron utilizados o instalados cuando dicha información haya sido registrada.

La información específica que podrá almacenarse para cada repuesto, componente o insumo no deberá quedar limitada a los ejemplos anteriores.

Dependiendo de la naturaleza del elemento podrán existir características diferentes.

Por ejemplo:

```text
BATERÍA
        ↓
Puede requerir determinadas
características propias

ACEITE
        ↓
Puede requerir viscosidad,
cantidad, especificaciones
u otras características

PASTILLAS DE FRENO
        ↓
Pueden requerir marca,
referencia u otras
características aplicables
```

La definición detallada de estos atributos deberá realizarse posteriormente, evitando establecer en este punto un conjunto rígido de campos que pueda resultar incorrecto para determinados tipos de elementos.

La diferenciación entre repuesto, componente e insumo tampoco deberá modificar las reglas previamente establecidas respecto a quién puede realizar una intervención.

Cualquiera de estos elementos podrá estar relacionado con una intervención registrada de acuerdo con las reglas correspondientes, independientemente de que haya sido realizada por un Prestador de Servicios Vehiculares, un tercero o directamente por el propietario cuando corresponda.

Como principio general:

```text
VEHÍCULO
        ↓
COMPONENTE / SISTEMA
        ↓
RECIBE UNA INTERVENCIÓN
        ↓
ACTIVIDAD REALIZADA
        │
        ├── PUEDE INVOLUCRAR
        │   REPUESTOS
        │
        └── PUEDE UTILIZAR
            INSUMOS
        ↓
INFORMACIÓN ESTRUCTURADA
        ↓
HISTORIAL VEHICULAR
```

Esta separación conceptual deberá servir como base para relacionar posteriormente los repuestos con el vehículo y con las actividades realizadas, sin confundir la naturaleza de los diferentes elementos involucrados.
 
---

### 63.8.3 Relación del repuesto con el vehículo y las actividades realizadas

Los repuestos registrados en Vehículos Services deberán conservar una relación que permita identificar tanto el vehículo al cual se encuentran asociados como la intervención y actividad mediante la cual fueron instalados, reemplazados, retirados o involucrados.

Esta relación deberá permitir comprender el contexto en el que un repuesto pasó a formar parte de la información registrada del vehículo.

Conceptualmente:

```text
VEHÍCULO
        ↓
INTERVENCIÓN
        ↓
ACTIVIDAD
        ↓
REPUESTO
```

Por ejemplo:

```text
VEHÍCULO:
HWG123

MANTENIMIENTO:
15/09/2026
65.000 km

ACTIVIDAD:
Cambio de batería

REPUESTO:
Batería instalada
```

En este escenario, la batería no deberá quedar registrada únicamente como un elemento aislado asociado al vehículo.

También deberá conservarse su relación con la actividad mediante la cual fue incorporada.

Por lo tanto:

```text
REPUESTO
        ↓
RELACIONADO CON
        │
        ├── VEHÍCULO
        │
        └── ACTIVIDAD / INTERVENCIÓN
            QUE EXPLICA SU RELACIÓN
            CON EL VEHÍCULO
```

Esta relación permitirá diferenciar entre conocer que un determinado repuesto se encuentra o estuvo relacionado con el vehículo y conocer el evento que originó dicha relación.

Por ejemplo:

```text
BATERÍA
        ↓
RELACIONADA CON
VEHÍCULO HWG123
        ↓
¿POR QUÉ?
        ↓
ACTIVIDAD:
Cambio de batería
        ↓
INTERVENCIÓN:
15/09/2026
65.000 km
```

De esta manera, la información del repuesto deberá conservar contexto histórico suficiente para evitar registros aislados cuya procedencia dentro del ciclo de vida del vehículo no pueda determinarse.

La relación entre una actividad y un repuesto deberá representar el papel que dicho elemento tuvo dentro de la intervención.

Por ejemplo:

```text
ACTIVIDAD:
Cambio de pastillas de freno
        ↓
REPUESTO:
Pastillas de freno
```

o:

```text
ACTIVIDAD:
Cambio de batería
        ↓
REPUESTO:
Batería
```

Una misma actividad podrá involucrar uno o varios repuestos cuando corresponda.

Conceptualmente:

```text
ACTIVIDAD
        │
        ├── REPUESTO A
        ├── REPUESTO B
        └── REPUESTO C
```

Por ejemplo:

```text
ACTIVIDAD:
Cambio de kit de distribución
        │
        ├── Elemento A
        ├── Elemento B
        └── Elemento C
```

La identificación específica de cuáles elementos conforman determinado conjunto no deberá establecerse como una regla universal dentro de este punto, ya que podrá variar dependiendo del vehículo, su configuración, la intervención realizada y la información disponible.

De igual manera, un mismo mantenimiento podrá contener diferentes actividades y cada actividad podrá relacionarse con sus propios repuestos.

Por ejemplo:

```text
MANTENIMIENTO
        │
        ├── ACTIVIDAD A
        │       ↓
        │   REPUESTO A
        │
        ├── ACTIVIDAD B
        │       ↓
        │   REPUESTO B
        │
        └── ACTIVIDAD C
                ↓
            SIN REPUESTO
```

Esto deberá evitar que todos los repuestos registrados dentro de un mantenimiento sean atribuidos automáticamente a todas las actividades que conforman dicho mantenimiento.

Por lo tanto:

```text
REPUESTO ASOCIADO
A UN MANTENIMIENTO
        ≠
REPUESTO ASOCIADO
AUTOMÁTICAMENTE A TODAS
LAS ACTIVIDADES
DEL MANTENIMIENTO
```

Cuando exista información suficiente, la relación deberá establecerse con la actividad específica a la cual corresponda.

Por ejemplo:

```text
MANTENIMIENTO
05/09/2026
        │
        ├── ACTIVIDAD:
        │   Cambio de aceite
        │       │
        │       └── REPUESTO:
        │           Filtro de aceite
        │
        ├── ACTIVIDAD:
        │   Cambio de plumillas
        │       │
        │       └── REPUESTO:
        │           Plumillas
        │
        └── ACTIVIDAD:
            Revisión de luces
                │
                └── SIN REPUESTO
```

Esto permitirá que posteriormente la consulta del historial pueda presentar con mayor precisión qué elementos estuvieron involucrados en cada actividad.

La relación de un repuesto con el vehículo tampoco deberá depender exclusivamente de la existencia de un mantenimiento.

Tal como se estableció conceptualmente en los puntos anteriores, un repuesto podrá estar relacionado con diferentes tipos de intervenciones.

Por ejemplo:

```text
VEHÍCULO
        ↓
REPARACIÓN
        ↓
ACTIVIDAD:
Reemplazo de alternador
        ↓
REPUESTO:
Alternador
```

Por lo tanto:

```text
REPUESTO
        ↓
PUEDE ORIGINARSE EN
        │
        ├── Mantenimiento
        ├── Reparación
        ├── Sustitución
        ├── Instalación
        └── Otra intervención
            posteriormente definida
```

La relación deberá conservar el evento real mediante el cual el repuesto fue relacionado con el vehículo, sin obligar a clasificar todas las intervenciones como mantenimiento cuando conceptualmente correspondan a otro tipo de evento.

Vehículos Services deberá permitir también que una intervención relacione un repuesto con un componente o sistema del vehículo cuando dicha información resulte aplicable.

Conceptualmente:

```text
VEHÍCULO
        ↓
COMPONENTE / SISTEMA
        ↓
ACTIVIDAD
        ↓
REPUESTO
```

Por ejemplo:

```text
VEHÍCULO
        ↓
SISTEMA DE FRENOS
        ↓
ACTIVIDAD:
Cambio de pastillas
        ↓
REPUESTO:
Pastillas de freno
```

Esta relación permitirá comprender no solamente qué repuesto fue utilizado, sino también sobre qué componente o sistema se realizó la intervención cuando dicha información haya sido registrada.

Sin embargo, la identificación de un componente no deberá ser obligatoria para poder registrar un repuesto cuando la información disponible permita representar correctamente la intervención sin dicho nivel de detalle.

Por lo tanto:

```text
REPUESTO REGISTRADO
        ≠
COMPONENTE OBLIGATORIO
EN TODOS LOS CASOS
```

La aplicación deberá permitir representar la información disponible sin obligar al propietario o al actor que realiza el registro a inventar información que desconoce.

Por ejemplo, un propietario podría conocer que se realizó:

```text
Cambio de batería
```

y conocer:

```text
Marca:
XXXX

Referencia:
XXXX
```

sin necesariamente disponer de información técnica adicional sobre otros componentes relacionados.

La ausencia de información complementaria no deberá impedir el registro de la información que sí se conoce, siempre que se cumplan las reglas mínimas que posteriormente sean definidas.

La relación entre repuesto y actividad deberá conservarse independientemente de quién haya realizado la intervención.

Por ejemplo:

```text
PRESTADOR
        ↓
REALIZA ACTIVIDAD
        ↓
INSTALA REPUESTO
```

También:

```text
TERCERO
        ↓
REALIZA ACTIVIDAD
        ↓
INSTALA REPUESTO
        ↓
PROPIETARIO
REGISTRA LA INFORMACIÓN
```

Y también:

```text
PROPIETARIO
        ↓
REALIZA ACTIVIDAD
        ↓
INSTALA REPUESTO
        ↓
REGISTRA LA INFORMACIÓN
```

Por lo tanto, la relación:

```text
VEHÍCULO
        ↓
ACTIVIDAD
        ↓
REPUESTO
```

no deberá depender de que exista obligatoriamente un Prestador de Servicios Vehiculares asociado.

Esto deberá mantenerse alineado con las reglas previamente definidas para Mantenimiento e Historial Vehicular.

La relación del repuesto con la actividad también deberá permitir conservar correctamente situaciones en las que una intervención implique la sustitución de un elemento existente.

Conceptualmente:

```text
ACTIVIDAD:
Cambio de batería
        │
        ├── ELEMENTO ANTERIOR
        │   relacionado con el vehículo
        │
        └── ELEMENTO NUEVO
            relacionado mediante
            la intervención
```

En este escenario existen relaciones diferentes que posteriormente deberán poder representarse:

```text
REPUESTO ANTERIOR
        ↓
DEJA DE ESTAR INSTALADO

REPUESTO NUEVO
        ↓
PASA A ESTAR INSTALADO
```

Las reglas detalladas que determinan la instalación, reemplazo, retiro y permanencia de estos elementos no deberán desarrollarse en este punto, ya que corresponden a `63.8.4 Instalación, reemplazo, retiro y permanencia del repuesto`.

En este punto únicamente deberá establecerse que la actividad correspondiente debe permitir conservar el contexto que relaciona dichos elementos con el vehículo.

La relación entre actividad y repuesto tampoco deberá provocar la pérdida de registros anteriores.

Por ejemplo:

```text
2024
ACTIVIDAD:
Cambio de batería
        ↓
BATERÍA A

2026
ACTIVIDAD:
Cambio de batería
        ↓
BATERÍA B
```

La incorporación de la Batería B no deberá sobrescribir la existencia histórica de la Batería A.

Conceptualmente:

```text
BATERÍA A
        ↓
EVENTO HISTÓRICO
SE CONSERVA

BATERÍA B
        ↓
NUEVO EVENTO
RELACIONADO CON
EL MISMO VEHÍCULO
```

La evolución temporal detallada de los repuestos será desarrollada posteriormente en `63.8.6 Historial y trazabilidad de los repuestos del vehículo`.

La relación entre el repuesto y la actividad deberá permitir que, cuando exista información suficiente, el propietario pueda consultar posteriormente el contexto en el que determinado elemento fue instalado o reemplazado.

Por ejemplo:

```text
REPUESTO:
Batería

Marca:
XXXX

Referencia:
XXXX

Instalada:
15/09/2026

Kilometraje:
65.000 km

Actividad:
Cambio de batería

Realizado por:
Propietario
```

o:

```text
REPUESTO:
Filtro de aceite

Marca:
XXXX

Referencia:
XXXX

Instalado:
05/09/2026

Kilometraje:
64.500 km

Actividad:
Cambio de filtro de aceite

Intervención:
Mantenimiento periódico

Realizado por:
ABC Aceites
```

Los datos presentados en estos ejemplos son conceptuales.

La definición exacta de la información que podrá asociarse a cada repuesto, incluyendo marca, referencia, características, costos, garantía u otros atributos, deberá desarrollarse posteriormente en `63.8.5 Información asociada a un repuesto`.

De igual manera, este punto no deberá definir:

- Los campos técnicos utilizados para crear las relaciones.
- El modelo de datos.
- Identificadores internos.
- Catálogos de repuestos.
- Catálogos de componentes.
- Campos obligatorios u opcionales definitivos.
- Reglas detalladas de instalación.
- Reglas detalladas de reemplazo.
- Reglas detalladas de retiro.
- Permanencia del repuesto en el vehículo.
- Estados del repuesto.
- Vida útil.
- Cálculos por kilometraje o tiempo.
- Alertas.
- Recomendaciones.
- Validaciones técnicas específicas.
- Interfaces o formularios de registro.

Estos elementos deberán desarrollarse posteriormente dentro de los puntos funcionales y técnicos correspondientes.

Como principio general:

```text
VEHÍCULO
        ↓
RECIBE UNA INTERVENCIÓN
        ↓
SE REALIZA UNA ACTIVIDAD
        ↓
LA ACTIVIDAD PUEDE
INVOLUCRAR REPUESTOS
        ↓
CADA REPUESTO CONSERVA
SU RELACIÓN CON
LA ACTIVIDAD
        ↓
LA ACTIVIDAD CONSERVA
EL CONTEXTO DE
LA INTERVENCIÓN
        ↓
TODO PERMANECE RELACIONADO
CON EL MISMO VEHÍCULO
Y SU HISTORIAL
```

La relación entre vehículo, intervención, actividad y repuesto deberá permitir que Vehículos Services conserve el contexto de los elementos utilizados o instalados sin reducir los repuestos a descripciones aisladas dentro del historial.

---

### 63.8.4 Instalación, reemplazo, retiro y permanencia del repuesto

Vehículos Services deberá permitir representar la evolución de los repuestos que se relacionan con un vehículo cuando, por la naturaleza del elemento y la información disponible, resulte relevante conocer si fueron instalados, reemplazados o retirados.

La relación de un repuesto con un vehículo no deberá limitarse a registrar que dicho elemento apareció alguna vez dentro de una intervención.

Cuando corresponda, deberá ser posible diferenciar entre:

```text
REPUESTO
        │
        ├── INSTALADO
        │
        ├── REEMPLAZADO
        │
        └── RETIRADO
```

Estas situaciones permitirán representar cómo determinados repuestos entran, permanecen y dejan de formar parte del vehículo a lo largo del tiempo.

No todos los repuestos deberán requerir obligatoriamente este mismo nivel de seguimiento.

Su aplicación dependerá de la naturaleza del elemento, de la intervención realizada, de la información disponible y de las reglas que posteriormente sean definidas.

#### Instalación de un repuesto

La instalación deberá representar el momento en que un repuesto pasa a formar parte del vehículo como consecuencia de una intervención.

Conceptualmente:

```text
VEHÍCULO
        ↓
INTERVENCIÓN
        ↓
ACTIVIDAD
        ↓
INSTALACIÓN
        ↓
REPUESTO
        ↓
PASA A ESTAR
RELACIONADO CON
EL VEHÍCULO
```

Por ejemplo:

```text
ACTIVIDAD:
Cambio de batería

Fecha:
15/09/2026

Kilometraje:
65.000 km

REPUESTO INSTALADO:
Batería
```

Cuando exista la información correspondiente, la instalación deberá permitir establecer desde qué momento determinado repuesto se encuentra relacionado con el vehículo.

Esta referencia podrá posteriormente utilizar información como:

```text
Fecha de instalación

Kilometraje de instalación

Intervención relacionada
```

sin que este punto defina todavía los campos específicos que deberán almacenarse.

La información detallada asociada al repuesto será desarrollada en `63.8.5 Información asociada a un repuesto`.

La instalación de un repuesto no deberá implicar obligatoriamente que otro elemento haya sido retirado o reemplazado.

Por ejemplo, podrá existir una intervención mediante la cual se incorpore un elemento que anteriormente no estaba registrado o instalado en el vehículo.

Conceptualmente:

```text
VEHÍCULO
        ↓
NO TENÍA
DETERMINADO ELEMENTO
        ↓
INTERVENCIÓN
        ↓
NUEVO REPUESTO
INSTALADO
```

Por lo tanto:

```text
INSTALACIÓN
        ≠
REEMPLAZO OBLIGATORIO
```

#### Reemplazo de un repuesto

El reemplazo deberá representar una situación en la que un repuesto que se encontraba instalado o relacionado con el vehículo es sustituido por otro.

Conceptualmente:

```text
REPUESTO ANTERIOR
        ↓
SE ENCUENTRA INSTALADO
        ↓
INTERVENCIÓN
        ↓
REEMPLAZO
        │
        ├── REPUESTO ANTERIOR
        │   DEJA DE ESTAR INSTALADO
        │
        └── REPUESTO NUEVO
            PASA A ESTAR INSTALADO
```

Por ejemplo:

```text
BATERÍA A

Instalada:
14/05/2024

Kilometraje instalación:
46.736 km
        ↓
15/09/2026
65.000 km
        ↓
CAMBIO DE BATERÍA
        ↓
BATERÍA A
DEJA DE ESTAR INSTALADA

BATERÍA B
PASA A ESTAR INSTALADA
```

El reemplazo no deberá provocar que el repuesto anterior desaparezca del historial.

Por lo tanto:

```text
REEMPLAZAR REPUESTO
        ≠
ELIMINAR REPUESTO ANTERIOR
```

El elemento anterior deberá conservarse como parte de la información histórica del vehículo, mientras que el nuevo elemento deberá representar el repuesto que pasa a estar relacionado con el vehículo a partir de la nueva intervención.

Conceptualmente:

```text
ANTES

VEHÍCULO
        ↓
BATERÍA A
INSTALADA

        ↓

REEMPLAZO

        ↓

DESPUÉS

VEHÍCULO
        ↓
BATERÍA B
INSTALADA


HISTORIAL
        │
        ├── BATERÍA A
        │   anteriormente instalada
        │
        └── BATERÍA B
            posteriormente instalada
```

Cuando exista información suficiente, esta evolución permitirá posteriormente determinar aspectos como:

```text
¿Qué repuesto estaba instalado anteriormente?

¿Cuándo fue instalado?

¿Cuándo fue reemplazado?

¿A qué kilometraje fue instalado?

¿A qué kilometraje fue reemplazado?

¿Cuánto tiempo permaneció instalado?

¿Cuántos kilómetros recorrió el vehículo
durante el período en que estuvo instalado?
```

La posibilidad de calcular o presentar estos valores dependerá de la existencia de la información necesaria.

Las fórmulas, criterios de cálculo y reglas relacionadas con kilometraje, tiempo, vida útil o seguimiento no deberán definirse en este punto.

#### Retiro de un repuesto

El retiro deberá representar una situación en la que un repuesto deja de estar instalado o relacionado activamente con el vehículo sin que necesariamente exista otro repuesto que lo sustituya inmediatamente.

Conceptualmente:

```text
REPUESTO INSTALADO
        ↓
INTERVENCIÓN
        ↓
RETIRO
        ↓
DEJA DE ESTAR
INSTALADO
        ↓
NO NECESARIAMENTE
EXISTE UN REPUESTO
NUEVO
```

Por lo tanto:

```text
RETIRO
        ≠
REEMPLAZO
```

En un reemplazo existe conceptualmente una transición entre un elemento anterior y otro que pasa a ocupar su lugar.

En un retiro, el elemento puede dejar de estar instalado sin que necesariamente se registre otro elemento sustituto dentro de la misma intervención.

Por ejemplo:

```text
ELEMENTO A
INSTALADO
        ↓
RETIRO
        ↓
ELEMENTO A
YA NO ESTÁ INSTALADO
        ↓
SIN NUEVO ELEMENTO
REGISTRADO
```

El retiro tampoco deberá eliminar el registro histórico del elemento.

Conceptualmente:

```text
RETIRADO
        ≠
ELIMINADO DEL HISTORIAL
```

La información deberá permitir conservar que dicho repuesto estuvo relacionado con el vehículo durante un período anterior.

#### Permanencia de un repuesto en el vehículo

Cuando la naturaleza del repuesto lo permita, Vehículos Services deberá poder diferenciar entre un elemento que se encuentra actualmente instalado y un elemento que estuvo instalado anteriormente.

Conceptualmente:

```text
REPUESTOS DEL VEHÍCULO
        │
        ├── ACTUALMENTE INSTALADOS
        │
        └── HISTÓRICOS
            YA RETIRADOS O REEMPLAZADOS
```

Por ejemplo:

```text
BATERÍA

Batería A
        ↓
Instalada anteriormente
        ↓
Reemplazada

Batería B
        ↓
Instalada actualmente
```

Esta diferenciación permitirá que la plataforma pueda responder, cuando exista información suficiente:

```text
¿Qué batería tiene actualmente el vehículo?
```

sin perder la capacidad de responder:

```text
¿Qué baterías ha tenido anteriormente?
```

Por lo tanto:

```text
REPUESTO ACTUAL
        ≠
ÚNICO REPUESTO
QUE HA TENIDO EL VEHÍCULO
```

La permanencia de un repuesto deberá representar su relación con el vehículo durante el período comprendido entre su instalación y el evento que determine que deja de encontrarse instalado, cuando dichos eventos se encuentren registrados.

Conceptualmente:

```text
INSTALACIÓN
        ↓
REPUESTO
PERMANECE INSTALADO
        ↓
USO DEL VEHÍCULO
        ↓
REEMPLAZO O RETIRO
```

Cuando todavía no exista un evento posterior de reemplazo o retiro, el sistema podrá considerar que el repuesto continúa relacionado como instalado siempre que la información disponible permita determinarlo y no exista otro evento que contradiga dicha situación.

Sin embargo, Vehículos Services no deberá inventar automáticamente información histórica que no haya sido registrada.

Por ejemplo, si un propietario comienza a utilizar la plataforma y registra por primera vez:

```text
BATERÍA ACTUAL:
Marca XXXX
```

pero desconoce:

```text
Fecha de instalación
Kilometraje de instalación
Lugar de instalación
Batería anterior
```

la plataforma deberá poder conservar la información conocida sin exigir que el propietario proporcione datos históricos que no posee.

Conceptualmente:

```text
INFORMACIÓN CONOCIDA
        ↓
SE REGISTRA

INFORMACIÓN DESCONOCIDA
        ↓
NO SE INVENTA
```

Por lo tanto, la ausencia de una fecha o kilometraje de instalación conocido no deberá significar automáticamente que el repuesto fue instalado en la fecha o kilometraje en que se creó el registro dentro de Vehículos Services.

Deberá mantenerse la diferenciación entre:

```text
FECHA DE INSTALACIÓN
        ≠
FECHA DE REGISTRO
EN VEHÍCULOS SERVICES
```

y, cuando corresponda:

```text
KILOMETRAJE DE INSTALACIÓN
        ≠
KILOMETRAJE ACTUAL
AL MOMENTO DE REGISTRAR
LA INFORMACIÓN
```

Esto deberá mantenerse alineado con los principios previamente definidos para la temporalidad y procedencia de la información dentro del Historial Vehicular.

La plataforma tampoco deberá asumir que el registro de un nuevo repuesto significa automáticamente el reemplazo de otro.

Por ejemplo:

```text
SE REGISTRA
REPUESTO B
        ↓
NO SIGNIFICA
AUTOMÁTICAMENTE
        ↓
REPUESTO A
FUE REEMPLAZADO
```

Para establecer una relación de reemplazo deberá existir información suficiente que permita identificar que una intervención sustituyó un elemento anterior por uno nuevo.

Esto evitará generar relaciones históricas incorrectas.

Un mismo tipo de repuesto también podrá existir simultáneamente más de una vez dentro de un vehículo cuando su naturaleza lo permita.

Por ejemplo:

```text
VEHÍCULO
        ↓
PLUMILLAS
        │
        ├── Plumilla izquierda
        └── Plumilla derecha
```

o cualquier otro escenario en el cual el vehículo pueda contener múltiples elementos del mismo tipo.

Por lo tanto:

```text
MISMO TIPO DE REPUESTO
        ≠
UNA ÚNICA INSTANCIA
OBLIGATORIA EN EL VEHÍCULO
```

Vehículos Services no deberá reemplazar automáticamente todos los elementos de un mismo tipo cuando solamente uno de ellos haya sido intervenido.

La identificación exacta de posiciones, ubicaciones, cantidades o características necesarias para diferenciar múltiples elementos deberá definirse posteriormente cuando corresponda.

La instalación, reemplazo o retiro podrá provenir de una intervención realizada por:

```text
PRESTADOR DE SERVICIOS VEHICULARES

TERCERO

PROPIETARIO
```

de acuerdo con las reglas previamente establecidas.

Por ejemplo:

```text
PROPIETARIO
        ↓
CAMBIA BATERÍA
        ↓
BATERÍA ANTERIOR
DEJA DE ESTAR INSTALADA
        ↓
BATERÍA NUEVA
PASA A ESTAR INSTALADA
        ↓
PROPIETARIO REGISTRA
LA INTERVENCIÓN
```

La participación directa del propietario no deberá modificar las reglas de conservación histórica del repuesto.

De igual manera, la instalación, reemplazo o retiro deberá conservar su relación con la actividad e intervención que originó el cambio cuando dicha información se encuentre disponible.

Conceptualmente:

```text
INTERVENCIÓN
        ↓
ACTIVIDAD
        ↓
CAMBIO SOBRE EL REPUESTO
        │
        ├── Instalación
        ├── Reemplazo
        └── Retiro
        ↓
EVOLUCIÓN DE LA RELACIÓN
REPUESTO ↔ VEHÍCULO
```

Este punto no deberá definir todavía:

- Los atributos específicos de cada repuesto.
- Marca.
- Referencia.
- Fabricante.
- Número de parte.
- Serial, cuando corresponda.
- Garantía.
- Costo.
- Estado físico.
- Condición nuevo/usado u otras clasificaciones.
- Campos obligatorios u opcionales definitivos.
- Catálogos.
- Vida útil estimada.
- Reglas de duración.
- Intervalos por kilometraje.
- Intervalos por tiempo.
- Cálculos de kilómetros recorridos.
- Cálculos de tiempo de permanencia.
- Estados de mantenimiento asociados.
- Alertas.
- Recomendaciones.
- Modelo de datos.
- Implementación técnica.

La información específica asociada a cada repuesto será desarrollada en `63.8.5 Información asociada a un repuesto`.

La conservación histórica y trazabilidad de los diferentes repuestos que han estado relacionados con el vehículo será desarrollada en `63.8.6 Historial y trazabilidad de los repuestos del vehículo`.

Como principio general:

```text
REPUESTO
        ↓
SE INSTALA
        ↓
PUEDE PERMANECER
RELACIONADO CON
EL VEHÍCULO
        ↓
POSTERIORMENTE
PUEDE
        │
        ├── SER REEMPLAZADO
        │
        └── SER RETIRADO
        ↓
DEJA DE ESTAR
INSTALADO
        ↓
SU INFORMACIÓN
HISTÓRICA SE CONSERVA
```

La evolución de un repuesto deberá representar los cambios reales registrados sobre el vehículo, evitando tanto la pérdida de información histórica como la generación automática de eventos que no hayan sido registrados o que no puedan determinarse a partir de la información disponible.

---
### 63.8.5 Información asociada a un repuesto

Cada repuesto registrado en Vehículos Services deberá poder conservar información que permita identificarlo y describirlo con el nivel de detalle disponible y aplicable según su naturaleza.

El propósito de esta información será evitar que el historial del vehículo se limite únicamente a indicar que determinado elemento fue cambiado, instalado o retirado.

Cuando exista información suficiente, deberá ser posible conocer qué repuesto específico estuvo relacionado con la intervención.

Conceptualmente:

```text
INTERVENCIÓN
        ↓
ACTIVIDAD
        ↓
REPUESTO
        ↓
INFORMACIÓN DEL REPUESTO
        │
        ├── ¿Qué elemento es?
        ├── ¿Qué marca?
        ├── ¿Qué referencia?
        ├── ¿Qué características posee?
        ├── ¿Cuándo fue instalado?
        ├── ¿A qué kilometraje?
        └── ¿Qué otra información
            relevante se conoce?
```

Por ejemplo, no debería conservarse únicamente:

```text
ACTIVIDAD:
Cambio de batería
```

Cuando se disponga de mayor información, Vehículos Services deberá poder representar conceptualmente algo como:

```text
ACTIVIDAD:
Cambio de batería

REPUESTO INSTALADO:
Batería

Marca:
XXXX

Referencia:
XXXX

Características:
Información aplicable
al tipo de batería

Fecha de instalación:
15/09/2026

Kilometraje de instalación:
65.000 km
```

De esta manera, el historial podrá conservar no solamente la actividad realizada, sino también información sobre el elemento que fue instalado.

La información asociada a un repuesto podrá incluir, cuando corresponda y se encuentre disponible:

- Tipo o identificación general del repuesto.
- Nombre o descripción.
- Marca.
- Fabricante, cuando corresponda.
- Referencia.
- Número de parte, cuando corresponda.
- Serial u otro identificador individual, cuando exista y resulte relevante.
- Características o especificaciones aplicables al tipo de repuesto.
- Cantidad, cuando corresponda.
- Posición o ubicación dentro del vehículo, cuando resulte necesaria para diferenciar elementos del mismo tipo.
- Fecha de instalación, cuando sea conocida.
- Kilometraje de instalación, cuando sea conocido.
- Fecha de retiro o reemplazo, cuando corresponda y sea conocida.
- Kilometraje de retiro o reemplazo, cuando corresponda y sea conocido.
- Costo, cuando corresponda.
- Información de garantía, cuando corresponda.
- Observaciones.
- Documentos o evidencias relacionadas, cuando existan.
- Otra información que posteriormente sea determinada como necesaria según la naturaleza del repuesto.

La inclusión conceptual de estos elementos no deberá significar que todos sean obligatorios para registrar cualquier repuesto.

Por lo tanto:

```text
INFORMACIÓN POSIBLE
DE UN REPUESTO
        ≠
INFORMACIÓN OBLIGATORIA
PARA TODOS LOS REPUESTOS
```

Los datos aplicables podrán variar dependiendo del tipo de elemento.

Por ejemplo, una batería podría requerir información diferente de unas pastillas de freno, una llanta, un filtro o una plumilla.

Conceptualmente:

```text
BATERÍA
        │
        ├── Marca
        ├── Referencia
        ├── Características aplicables
        ├── Serial, cuando exista
        ├── Garantía, cuando exista
        └── Otros datos aplicables


LLANTA
        │
        ├── Marca
        ├── Referencia / modelo
        ├── Medida
        ├── Características aplicables
        ├── Posición, cuando corresponda
        └── Otros datos aplicables


FILTRO
        │
        ├── Marca
        ├── Referencia
        └── Otros datos aplicables


PLUMILLA
        │
        ├── Marca
        ├── Referencia / modelo
        ├── Medida, cuando corresponda
        ├── Posición, cuando corresponda
        └── Otros datos aplicables
```

Estos ejemplos son únicamente conceptuales y no deberán interpretarse todavía como la definición definitiva de campos para cada tipo de repuesto.

Vehículos Services deberá permitir que diferentes tipos de repuestos puedan tener características particulares sin obligar a que todos compartan exactamente la misma información descriptiva.

Conceptualmente:

```text
INFORMACIÓN GENERAL
DEL REPUESTO
        +
CARACTERÍSTICAS
SEGÚN EL TIPO
DE ELEMENTO
```

La definición exacta de catálogos, atributos específicos por tipo de repuesto, obligatoriedad, validaciones y estructura técnica deberá realizarse posteriormente.

La ausencia de información detallada tampoco deberá impedir necesariamente registrar un repuesto cuando exista información suficiente para representar correctamente la intervención.

Por ejemplo, un propietario podría conocer:

```text
Actividad:
Cambio de batería

Marca:
XXXX

Fecha:
15/09/2026

Kilometraje:
65.000 km
```

pero desconocer:

```text
Referencia

Serial

Fabricante

Garantía
```

La plataforma deberá poder conservar la información conocida sin obligar al usuario a inventar los datos faltantes.

Por lo tanto:

```text
INFORMACIÓN DESCONOCIDA
        ↓
NO SE INVENTA
        ↓
SE CONSERVA
LA INFORMACIÓN
REALMENTE DISPONIBLE
```

Esto deberá mantenerse alineado con el principio previamente definido para la incorporación de información histórica incompleta.

Cuando posteriormente se obtenga información adicional y las reglas funcionales permitan completar el registro, deberá conservarse la trazabilidad correspondiente de acuerdo con las reglas del Historial Vehicular.

La fecha y el kilometraje asociados a un repuesto deberán conservar el significado del evento al cual correspondan.

Por ejemplo:

```text
BATERÍA

Fecha de instalación:
15/09/2026

Kilometraje de instalación:
65.000 km
```

Estos datos deberán representar, cuando sean conocidos, el momento real de instalación y no necesariamente el momento en que la información fue ingresada a Vehículos Services.

Por lo tanto:

```text
FECHA DE INSTALACIÓN
        ≠
FECHA DE CREACIÓN
DEL REGISTRO
```

De igual manera:

```text
KILOMETRAJE DE INSTALACIÓN
        ≠
KILOMETRAJE ACTUAL
AL MOMENTO DE REGISTRAR
```

Por ejemplo:

```text
BATERÍA INSTALADA:
14/05/2024

Kilometraje instalación:
46.736 km

REGISTRADA EN
VEHÍCULOS SERVICES:
20/09/2026

Kilometraje actual:
70.000 km
```

La incorporación posterior de la información no deberá modificar la fecha ni el kilometraje reales de la intervención cuando estos sean conocidos.

Cuando un repuesto sea posteriormente retirado o reemplazado, podrán conservarse las referencias temporales correspondientes.

Conceptualmente:

```text
REPUESTO
        │
        ├── INSTALACIÓN
        │       ├── Fecha
        │       └── Kilometraje
        │
        └── RETIRO / REEMPLAZO
                ├── Fecha
                └── Kilometraje
```

Esto permitirá posteriormente establecer el período durante el cual determinado repuesto estuvo instalado en el vehículo cuando exista la información necesaria.

Sin embargo, los cálculos derivados de estas referencias no deberán definirse en este punto.

Por ejemplo:

```text
KM UTILIZADOS POR EL REPUESTO

TIEMPO DE PERMANENCIA

VIDA ÚTIL ESTIMADA

VIDA ÚTIL RESTANTE
```

deberán depender de las reglas de kilometraje, mantenimiento, seguimiento u otros componentes que posteriormente correspondan.

La información de costos podrá asociarse al repuesto cuando se encuentre disponible.

Por ejemplo:

```text
REPUESTO:
Batería

Costo:
$XXX.XXX
```

Sin embargo, deberá diferenciarse conceptualmente entre el costo del repuesto y el costo total de una intervención cuando ambos existan.

Por ejemplo:

```text
INTERVENCIÓN
        │
        ├── Costo del repuesto
        ├── Mano de obra,
        │   cuando corresponda
        ├── Otros elementos,
        │   cuando correspondan
        └── Costo total
```

Por lo tanto:

```text
COSTO DEL REPUESTO
        ≠
COSTO TOTAL
DE LA INTERVENCIÓN
```

La estructura detallada de costos, impuestos, descuentos, mano de obra y demás conceptos económicos deberá definirse posteriormente en el componente funcional correspondiente.

Cuando un repuesto disponga de garantía, Vehículos Services deberá poder conservar información relacionada con esta cuando resulte aplicable.

Conceptualmente:

```text
REPUESTO
        ↓
GARANTÍA
        │
        ├── Información disponible
        ├── Fecha o período aplicable
        ├── Condiciones,
        │   cuando correspondan
        └── Evidencia / documento,
            cuando exista
```

La existencia de una garantía no deberá ser obligatoria para registrar un repuesto.

De igual manera, registrar información sobre una garantía no deberá significar que Vehículos Services certifica, valida o garantiza directamente su cumplimiento.

La información deberá representar los datos registrados sobre la garantía correspondiente.

Los documentos asociados a un repuesto podrán incluir, cuando existan:

```text
Factura

Comprobante de compra

Documento de garantía

Fotografía

Orden de servicio

Otro soporte
```

Sin embargo:

```text
REGISTRAR REPUESTO
        ≠
ADJUNTAR OBLIGATORIAMENTE
UN DOCUMENTO
```

La información estructurada del repuesto y los documentos asociados deberán mantenerse como conceptos diferenciados.

Las reglas de privacidad, acceso, conservación y visibilidad de los documentos deberán regirse por los principios correspondientes del Historial Vehicular y por las reglas que posteriormente sean definidas para documentos y permisos.

Cuando existan múltiples repuestos del mismo tipo dentro del vehículo, la información disponible deberá permitir diferenciarlos cuando esto resulte necesario.

Por ejemplo:

```text
LLANTAS
        │
        ├── Delantera izquierda
        ├── Delantera derecha
        ├── Trasera izquierda
        └── Trasera derecha
```

o:

```text
PLUMILLAS
        │
        ├── Izquierda
        └── Derecha
```

La forma exacta de representar posiciones, ubicaciones, cantidades o identificadores deberá definirse posteriormente según las necesidades de cada tipo de elemento.

No deberá asumirse que todos los repuestos requieren una posición específica.

La información del repuesto también deberá permitir relacionarlo con la actividad mediante la cual fue instalado, reemplazado o retirado, conforme a lo definido en `63.8.3 Relación del repuesto con el vehículo y las actividades realizadas`.

Por ejemplo:

```text
REPUESTO:
Batería

Marca:
XXXX

Referencia:
XXXX

Fecha instalación:
15/09/2026

Kilometraje instalación:
65.000 km

        ↓

RELACIONADO CON

        ↓

ACTIVIDAD:
Cambio de batería

        ↓

INTERVENCIÓN:
Mantenimiento / reparación
correspondiente
```

Esto permitirá que la consulta del repuesto conserve el contexto de la intervención y que la consulta de la intervención permita identificar el repuesto relacionado.

Conceptualmente:

```text
INTERVENCIÓN
        ↕
ACTIVIDAD
        ↕
REPUESTO
```

La información asociada a un repuesto deberá permitir que, cuando los datos hayan sido registrados, el propietario pueda consultar información como:

```text
¿Qué repuesto se instaló?

¿Qué marca era?

¿Qué referencia tenía?

¿Qué características se registraron?

¿Cuándo fue instalado?

¿A qué kilometraje?

¿En qué actividad se instaló?

¿Quién realizó la intervención?

¿Cuánto costó?

¿Tenía garantía?

¿Existe factura o evidencia?

¿Continúa instalado?

¿Cuándo fue retirado o reemplazado?
```

La disponibilidad de cada respuesta dependerá de la información realmente registrada y de las reglas de acceso correspondientes.

Vehículos Services no deberá presentar como conocida información que no haya sido registrada o que no pueda determinarse a partir de los datos disponibles.

Este punto define conceptualmente qué tipo de información podrá estar asociada a un repuesto, pero no deberá establecer todavía:

- El modelo de datos.
- Los nombres técnicos de los campos.
- Los tipos de datos.
- Los campos obligatorios y opcionales definitivos.
- Los catálogos de marcas.
- Los catálogos de fabricantes.
- Los catálogos de referencias.
- Los catálogos de repuestos.
- La estructura de características específicas por tipo de elemento.
- Las reglas técnicas de compatibilidad entre repuesto y vehículo.
- Las validaciones contra fabricantes.
- La lectura automática de seriales o códigos.
- La estructura detallada de costos.
- Las reglas detalladas de garantía.
- Los cálculos de vida útil.
- Los cálculos de kilometraje.
- Los cálculos de permanencia.
- Los estados derivados del seguimiento.
- Las alertas.
- Las recomendaciones.
- La interfaz de captura o consulta.
- La implementación técnica.

Estos elementos deberán desarrollarse posteriormente dentro de los componentes funcionales y técnicos correspondientes.

Como principio general:

```text
REPUESTO
        ↓
SE IDENTIFICA
CON LA INFORMACIÓN
DISPONIBLE
        ↓
PUEDE CONSERVAR
        │
        ├── Tipo
        ├── Marca
        ├── Referencia
        ├── Características
        ├── Fecha / kilometraje
        ├── Costo
        ├── Garantía
        ├── Observaciones
        └── Documentos / evidencias
        ↓
SE RELACIONA CON
LA ACTIVIDAD
Y EL VEHÍCULO
        ↓
PERMITE CONOCER
QUÉ ELEMENTO
FUE UTILIZADO O INSTALADO
        ↓
FORMA PARTE DE LA
TRAZABILIDAD DEL VEHÍCULO
```

La información asociada a los repuestos deberá permitir enriquecer el historial del vehículo sin exigir datos inexistentes, sin convertir todos los atributos posibles en obligatorios y sin imponer la misma estructura descriptiva a elementos que, por su naturaleza, requieren información diferente.

---
### 63.8.6 Historial y trazabilidad de los repuestos del vehículo

Vehículos Services deberá conservar la evolución histórica de los repuestos relacionados con un vehículo, permitiendo identificar, cuando exista información suficiente, qué elementos han estado instalados, cuándo fueron incorporados, cuándo dejaron de estar instalados y mediante qué intervenciones ocurrieron dichos cambios.

La trazabilidad de los repuestos deberá formar parte del Historial Vehicular y no deberá constituir un historial independiente o desconectado del vehículo.

Conceptualmente:

```text
VEHÍCULO
        ↓
HISTORIAL VEHICULAR
        ↓
EVOLUCIÓN DE REPUESTOS
        │
        ├── Repuestos instalados
        ├── Repuestos reemplazados
        ├── Repuestos retirados
        └── Repuestos actualmente instalados,
            cuando pueda determinarse
```

El propósito de esta trazabilidad será permitir que Vehículos Services conserve la secuencia de los elementos que han formado parte del vehículo sin sobrescribir la información anterior cuando se registre un nuevo repuesto.

Por ejemplo:

```text
VEHÍCULO
        ↓
BATERÍA A
Instalada: 14/05/2024
46.736 km
        ↓
REEMPLAZO
15/09/2026
65.000 km
        ↓
BATERÍA B
Instalada: 15/09/2026
65.000 km
```

En este escenario, la incorporación de la Batería B no deberá eliminar ni reemplazar históricamente la información correspondiente a la Batería A.

Conceptualmente:

```text
BATERÍA A
        ↓
DEJA DE ESTAR INSTALADA
        ↓
PERMANECE EN EL HISTORIAL

BATERÍA B
        ↓
PASA A ESTAR INSTALADA
        ↓
CONTINÚA SU PROPIA
EVOLUCIÓN
```

Por lo tanto:

```text
NUEVO REPUESTO
        ≠
SOBRESCRIBIR
REPUESTO ANTERIOR
```

Cada repuesto deberá conservar, cuando corresponda, su relación con los eventos que expliquen su evolución dentro del vehículo.

Conceptualmente:

```text
REPUESTO
        │
        ├── Evento de instalación
        │
        ├── Intervención relacionada
        │
        ├── Actividad relacionada
        │
        ├── Evento de reemplazo,
        │   cuando exista
        │
        └── Evento de retiro,
            cuando exista
```

La trazabilidad deberá permitir relacionar estos acontecimientos con sus respectivas referencias temporales y de kilometraje cuando dicha información haya sido registrada.

Por ejemplo:

```text
REPUESTO:
Batería A

INSTALACIÓN
Fecha: 14/05/2024
Kilometraje: 46.736 km

        ↓

PERÍODO EN EL VEHÍCULO

        ↓

REEMPLAZO
Fecha: 15/09/2026
Kilometraje: 65.000 km
```

Cuando exista la información necesaria, esta secuencia podrá permitir posteriormente obtener información derivada como:

```text
Tiempo que permaneció instalado

Kilómetros recorridos durante
el período de instalación
```

Sin embargo, este punto no deberá establecer las fórmulas ni las reglas de cálculo correspondientes.

Dichos cálculos deberán apoyarse posteriormente en los componentes de Kilometraje y en las reglas funcionales que correspondan.

La trazabilidad deberá permitir también consultar la sucesión histórica de repuestos de un mismo tipo cuando hayan ocurrido varios reemplazos.

Por ejemplo:

```text
HISTORIAL DE BATERÍAS

BATERÍA A
        ↓
Instalada
        ↓
Reemplazada

BATERÍA B
        ↓
Instalada
        ↓
Reemplazada

BATERÍA C
        ↓
Instalada
        ↓
Actualmente instalada,
cuando pueda determinarse
```

De esta manera, Vehículos Services deberá poder conservar tanto la situación actual como las situaciones anteriores.

Por lo tanto:

```text
REPUESTO ACTUAL
        +
REPUESTOS ANTERIORES
        ↓
EVOLUCIÓN HISTÓRICA
DEL ELEMENTO
```

La consulta de esta información no deberá limitarse a mostrar únicamente el último repuesto registrado.

Cuando exista información histórica, el propietario deberá poder consultar los elementos anteriores y los eventos mediante los cuales fueron instalados, reemplazados o retirados.

Por ejemplo:

```text
BATERÍAS DEL VEHÍCULO

Actual:
Batería C
Instalada: 10/08/2028
Kilometraje: 82.000 km

Anterior:
Batería B
Instalada: 15/09/2026
Kilometraje: 65.000 km
Reemplazada: 10/08/2028
Kilometraje: 82.000 km

Anterior:
Batería A
Instalada: 14/05/2024
Kilometraje: 46.736 km
Reemplazada: 15/09/2026
Kilometraje: 65.000 km
```

Los datos anteriores son únicamente un ejemplo conceptual de consulta y no representan todavía una definición de interfaz.

La trazabilidad deberá conservar igualmente la relación entre el repuesto y las actividades que originaron los diferentes cambios.

Por ejemplo:

```text
BATERÍA A
        ↓
INSTALADA MEDIANTE
        ↓
Actividad:
Cambio de batería
14/05/2024
46.736 km

        ↓

REEMPLAZADA MEDIANTE
        ↓
Actividad:
Cambio de batería
15/09/2026
65.000 km

        ↓

BATERÍA B
PASA A ESTAR INSTALADA
```

Esto permitirá reconstruir no solamente qué repuestos estuvieron relacionados con el vehículo, sino también por qué ocurrió cada cambio dentro de su historial.

La trazabilidad deberá mantenerse independientemente del actor que haya realizado la intervención.

Por ejemplo:

```text
BATERÍA A
        ↓
Instalada por:
Prestador de Servicios Vehiculares

        ↓
REEMPLAZO

BATERÍA B
        ↓
Instalada directamente por:
Propietario
```

Ambos eventos deberán poder formar parte de la misma evolución histórica del vehículo.

La participación de diferentes actores no deberá fragmentar la trazabilidad del repuesto ni crear historiales independientes.

Conceptualmente:

```text
PRESTADOR
        │
        └── Intervención A
                ↓
            REPUESTO A

PROPIETARIO
        │
        └── Intervención B
                ↓
            REPUESTO B

                ↓

MISMO VEHÍCULO
        ↓
MISMO HISTORIAL
        ↓
EVOLUCIÓN CONTINUA
```

Esto deberá mantenerse alineado con el principio previamente establecido de que el Historial Vehicular pertenece a la identidad del vehículo y conserva continuidad independientemente de los actores que incorporen o realicen las diferentes intervenciones.

La trazabilidad tampoco deberá depender de que toda la información histórica del repuesto se encuentre disponible.

Podrán existir situaciones en las que Vehículos Services conozca únicamente una parte de su evolución.

Por ejemplo:

```text
BATERÍA ACTUAL:
Marca XXXX

Fecha de instalación:
Desconocida

Kilometraje de instalación:
Desconocido

Batería anterior:
Desconocida
```

En este escenario, la ausencia de información anterior no deberá impedir conservar la información actualmente conocida.

Por lo tanto:

```text
HISTORIAL INCOMPLETO
        ≠
INFORMACIÓN INVÁLIDA
```

Siempre que la información cumpla con las reglas correspondientes, Vehículos Services deberá conservar lo que realmente se conoce sin inventar los acontecimientos faltantes.

De igual manera:

```text
NO EXISTE REGISTRO
DE UN REPUESTO ANTERIOR
        ≠
SE PUEDE AFIRMAR
QUE NUNCA EXISTIÓ
```

La ausencia de información dentro de Vehículos Services deberá interpretarse únicamente como ausencia de información registrada cuando no exista evidencia suficiente para establecer otra conclusión.

La incorporación posterior de información histórica podrá ampliar la trazabilidad cuando las reglas funcionales permitan registrar acontecimientos anteriores.

Por ejemplo:

```text
HOY
        ↓
PROPIETARIO REGISTRA
BATERÍA ACTUAL

POSTERIORMENTE
        ↓
ENCUENTRA FACTURA
DE BATERÍA ANTERIOR

        ↓
INCORPORA INFORMACIÓN
HISTÓRICA
```

La incorporación posterior deberá conservar las fechas, kilometrajes y referencias reales del evento cuando sean conocidas y no deberá utilizar automáticamente la fecha de creación del registro como fecha del acontecimiento.

Esto deberá regirse por las reglas de temporalidad, procedencia, modificación y trazabilidad ya establecidas para el Historial Vehicular.

La trazabilidad deberá permitir igualmente que diferentes tipos de repuestos evolucionen de manera independiente dentro del mismo vehículo.

Por ejemplo:

```text
VEHÍCULO
        │
        ├── BATERÍAS
        │       ├── Batería A
        │       └── Batería B
        │
        ├── PASTILLAS DE FRENO
        │       ├── Juego A
        │       └── Juego B
        │
        ├── LLANTAS
        │       ├── Elementos actuales
        │       └── Elementos anteriores
        │
        └── OTROS REPUESTOS
                ↓
            Su propia evolución
            registrada
```

La existencia de estas diferentes evoluciones no deberá generar historiales vehiculares separados.

Todas deberán formar parte del mismo Historial Vehicular y podrán ser consultadas desde diferentes perspectivas según la funcionalidad que posteriormente sea definida.

Conceptualmente:

```text
HISTORIAL VEHICULAR
        │
        ├── Mantenimientos
        ├── Reparaciones
        ├── Kilometraje
        ├── Documentos
        ├── Otros eventos
        │
        └── REPUESTOS
                │
                ├── Evolución batería
                ├── Evolución frenos
                ├── Evolución llantas
                └── Otros elementos
```

Cuando un mismo tipo de repuesto pueda existir simultáneamente varias veces dentro del vehículo, la trazabilidad deberá conservar la evolución de los elementos de forma que puedan diferenciarse cuando exista información suficiente.

Por ejemplo:

```text
LLANTAS
        │
        ├── Delantera izquierda
        │       ↓
        │   Evolución propia
        │
        ├── Delantera derecha
        │       ↓
        │   Evolución propia
        │
        ├── Trasera izquierda
        │       ↓
        │   Evolución propia
        │
        └── Trasera derecha
                ↓
            Evolución propia
```

La forma exacta de identificar posiciones, ubicaciones, conjuntos o elementos individuales deberá definirse posteriormente según la naturaleza del repuesto y las necesidades funcionales correspondientes.

Vehículos Services no deberá asumir que todos los repuestos de un mismo tipo fueron reemplazados cuando solamente exista evidencia del reemplazo de uno de ellos.

Por lo tanto:

```text
CAMBIO DE UN ELEMENTO
        ≠
CAMBIO AUTOMÁTICO
DE TODOS LOS ELEMENTOS
DEL MISMO TIPO
```

La trazabilidad de repuestos también deberá conservarse ante un cambio de propietario del vehículo.

El cambio de propietario no deberá reiniciar, eliminar ni crear nuevamente la evolución de los repuestos.

Conceptualmente:

```text
PROPIETARIO A
        ↓
VEHÍCULO
        ↓
REPUESTO A
        ↓
CAMBIO DE PROPIETARIO
        ↓
PROPIETARIO B
        ↓
MISMO VEHÍCULO
        ↓
CONTINUIDAD DE LA
EVOLUCIÓN DEL REPUESTO
```

Por lo tanto:

```text
CAMBIO DE PROPIETARIO
        ≠
REINICIO DEL HISTORIAL
DE REPUESTOS
```

La conservación de esta información no deberá confundirse con los derechos de acceso de propietarios anteriores o actuales.

La existencia y continuidad histórica de los registros deberá permanecer separada de las reglas que determinan quién puede consultar determinada información, conforme a lo establecido en Historial Vehicular, Relación Propietario ↔ Vehículo y Permisos.

De igual manera, un cambio de Prestador de Servicios Vehiculares no deberá fragmentar la evolución de los repuestos.

Por ejemplo:

```text
PRESTADOR A
        ↓
INSTALA REPUESTO A

POSTERIORMENTE

PRESTADOR B
        ↓
REEMPLAZA REPUESTO A
POR REPUESTO B
```

Ambas intervenciones podrán formar parte de la evolución histórica del mismo elemento o tipo de repuesto, conservando la procedencia correspondiente de cada registro.

La existencia de una secuencia histórica tampoco deberá permitir que un prestador modifique registros pertenecientes a otro prestador únicamente porque posteriormente intervino el mismo elemento.

Las reglas de modificación, corrección, procedencia y acceso deberán continuar regidas por los apartados correspondientes del Historial Vehicular y de la Relación Prestador ↔ Vehículo.

Cuando exista información suficiente, la trazabilidad de repuestos deberá permitir posteriormente soportar consultas y análisis como:

```text
¿Qué repuestos están registrados
actualmente en el vehículo?

¿Qué repuestos fueron reemplazados?

¿Cuáles estuvieron instalados anteriormente?

¿Cuándo se instaló cada uno?

¿A qué kilometraje?

¿Cuándo fue reemplazado o retirado?

¿En qué intervención ocurrió?

¿Qué actividad produjo el cambio?

¿Quién realizó la intervención?

¿Qué características tenía el repuesto?

¿Qué elemento fue instalado después?

¿Cuánto tiempo permaneció instalado?

¿Cuántos kilómetros recorrió el vehículo
durante ese período?
```

No todas estas respuestas deberán encontrarse disponibles para todos los registros.

Su disponibilidad dependerá de la información realmente registrada y de las reglas funcionales aplicables.

La trazabilidad de repuestos deberá diferenciar además entre información histórica registrada y resultados derivados posteriormente mediante cálculos o reglas.

Por ejemplo:

```text
DATOS REGISTRADOS

Fecha instalación:
14/05/2024

Kilometraje instalación:
46.736 km

Fecha reemplazo:
15/09/2026

Kilometraje reemplazo:
65.000 km

        ↓

INFORMACIÓN DERIVADA
POSTERIORMENTE

Tiempo de permanencia

Kilómetros recorridos
durante la permanencia
```

Por lo tanto:

```text
INFORMACIÓN HISTÓRICA
REGISTRADA
        ≠
INFORMACIÓN CALCULADA
O DERIVADA
```

Los cálculos correspondientes deberán definirse en los componentes responsables y no deberán duplicarse dentro del historial de repuestos.

Este punto tampoco deberá definir:

- El modelo de datos.
- Los identificadores técnicos de los repuestos.
- Los campos técnicos de trazabilidad.
- Los mecanismos físicos de almacenamiento.
- Los catálogos.
- La interfaz de consulta.
- La representación visual de líneas de tiempo.
- Los filtros de consulta.
- Los cálculos de kilometraje.
- Los cálculos de tiempo de permanencia.
- Las reglas de vida útil.
- Los intervalos de reemplazo.
- Los estados derivados.
- Las alertas.
- Las recomendaciones.
- Los permisos detallados.
- Las reglas técnicas de auditoría.
- Las integraciones con Prestadores de Servicios Vehiculares.

Estos elementos deberán desarrollarse posteriormente dentro de los componentes funcionales y técnicos correspondientes.

Como principio general:

```text
VEHÍCULO
        ↓
REPUESTO A
        ↓
INSTALACIÓN
        ↓
PERMANENCIA
        ↓
REEMPLAZO / RETIRO
        ↓
EL REGISTRO SE CONSERVA
        ↓
REPUESTO B
        ↓
NUEVA ETAPA
        ↓
EVOLUCIÓN CONTINUA
        ↓
HISTORIAL VEHICULAR
```

La trazabilidad de los repuestos deberá permitir reconstruir progresivamente qué elementos han formado parte del vehículo, cómo se relacionaron con las intervenciones realizadas y cómo evolucionaron a lo largo del tiempo, conservando tanto la situación actual como los acontecimientos históricos conocidos sin sobrescribir, fragmentar ni inventar información.
---
## 63.9 KILOMETRAJE
### 63.9.1 Gestión y actualización del kilometraje

Vehículos Services deberá mantener un kilometraje actual para cada vehículo como referencia vigente de la distancia acumulada registrada dentro de la plataforma.

El kilometraje deberá considerarse información propia del vehículo y deberá permanecer asociado a este durante su ciclo de vida dentro de Vehículos Services.

Por lo tanto:

```text
CAMBIO DE PROPIETARIO
        ≠
REINICIO DEL KILOMETRAJE
```

y:

```text
CAMBIO DE PRESTADOR
        ≠
REINICIO DEL KILOMETRAJE
```

El kilometraje actual deberá poder actualizarse a partir de nuevas lecturas del vehículo de acuerdo con las reglas de procedencia y consistencia que se definan para este componente.

Conceptualmente:

```text
VEHÍCULO
        ↓
KILOMETRAJE ACTUAL
        ↓
NUEVA LECTURA
        ↓
VALIDACIÓN CORRESPONDIENTE
        ↓
CUANDO PROCEDA
        ↓
ACTUALIZACIÓN DEL
KILOMETRAJE ACTUAL
```

Vehículos Services no deberá depender únicamente de actualizaciones espontáneas realizadas por los usuarios para mantener esta información.

La plataforma deberá solicitar periódicamente al propietario que ingrese el kilometraje actual de su vehículo, con el propósito de disponer de una referencia suficientemente reciente para los procesos que dependan de la distancia recorrida.

Por ejemplo:

```text
KILOMETRAJE REGISTRADO:
70.000 km

        ↓

VEHÍCULOS SERVICES
SOLICITA ACTUALIZACIÓN
PERIÓDICA

        ↓

PROPIETARIO CONSULTA
EL VEHÍCULO

        ↓

NUEVA LECTURA:
72.500 km

        ↓

SE ACTUALIZA
EL KILOMETRAJE ACTUAL
CUANDO CORRESPONDA
```

La periodicidad exacta de esta solicitud deberá definirse posteriormente. Inicialmente podrá contemplarse, por ejemplo, una solicitud mensual, sin establecer todavía dicha frecuencia como una regla definitiva e invariable.

El objetivo de esta actualización periódica será mantener una referencia reciente del recorrido del vehículo para que las funcionalidades dependientes del kilometraje puedan utilizar información actualizada.

Entre otros usos, el kilometraje actual podrá servir como referencia para el seguimiento de:

- Mantenimientos.
- Reparaciones o intervenciones cuando corresponda.
- Repuestos.
- Componentes.
- Elementos cuyo seguimiento dependa de la distancia recorrida.
- Preparación para viajes.
- Otras funcionalidades que posteriormente utilicen el kilometraje.

Por ejemplo:

```text
CAMBIO DE ACEITE
REALIZADO EN:
70.000 km

        ↓

NUEVO KILOMETRAJE ACTUAL:
73.500 km

        ↓

EL SISTEMA DISPONE
DE UNA REFERENCIA ACTUALIZADA
PARA EL SEGUIMIENTO
DEL MANTENIMIENTO
```

La definición de los cálculos derivados de esta relación no deberá repetirse en este punto y deberá mantenerse en los componentes en los cuales dichos cálculos y reglas hayan sido definidos.

Además de las actualizaciones periódicas solicitadas al propietario, una nueva lectura podrá originarse cuando se realice una intervención sobre el vehículo.

Por ejemplo:

```text
VEHÍCULO
        ↓
INTERVENCIÓN
        ↓
SE REGISTRA EL
KILOMETRAJE OBSERVADO
        ↓
LA LECTURA PODRÁ
CONTRIBUIR A ACTUALIZAR
EL KILOMETRAJE ACTUAL
CUANDO CORRESPONDA
```

El propietario o un Prestador de Servicios Vehiculares podrán registrar kilometraje en los escenarios que posteriormente correspondan a sus permisos y responsabilidades.

La determinación de quién aportó la lectura, de dónde provino y en qué contexto fue obtenida deberá desarrollarse en `63.9.2 Fuentes y procedencia del kilometraje`.

La existencia de una lectura asociada a una intervención no deberá significar automáticamente que esta sustituya el kilometraje actual del vehículo.

Por ejemplo:

```text
KILOMETRAJE ACTUAL:
75.300 km

        ↓

SE INCORPORA
UNA INTERVENCIÓN HISTÓRICA

KILOMETRAJE DEL EVENTO:
68.000 km

        ↓

68.000 km
NO REEMPLAZA
AUTOMÁTICAMENTE
75.300 km
```

Por lo tanto:

```text
KILOMETRAJE DE UN EVENTO
        ≠
KILOMETRAJE ACTUAL
DEL VEHÍCULO
```

Esta diferenciación permitirá incorporar información histórica sin alterar incorrectamente la referencia vigente del vehículo.

La determinación de cuándo una lectura puede actualizar el kilometraje actual, así como el tratamiento de lecturas inferiores, atípicas, incorrectas o correspondientes a otros momentos, deberá desarrollarse en `63.9.3 Validación y consistencia del kilometraje`.

Cada actualización aceptada del kilometraje actual deberá conservarse como parte de la evolución del vehículo y no deberá eliminar las lecturas anteriores.

La definición detallada de dicha conservación corresponderá a `63.9.4 Historial y trazabilidad del kilometraje`.

Conceptualmente:

```text
KILOMETRAJE ACTUAL
        ↓
SE MANTIENE COMO
REFERENCIA DEL VEHÍCULO
        ↓
VEHÍCULOS SERVICES
SOLICITA PERIÓDICAMENTE
NUEVAS LECTURAS
        ↓
TAMBIÉN PUEDEN EXISTIR
LECTURAS GENERADAS
DURANTE INTERVENCIONES
        ↓
LAS LECTURAS SE EVALÚAN
SEGÚN LAS REGLAS
CORRESPONDIENTES
        ↓
CUANDO PROCEDA
SE ACTUALIZA EL
KILOMETRAJE ACTUAL
        ↓
LOS PROCESOS QUE
DEPENDEN DEL RECORRIDO
UTILIZAN LA NUEVA
REFERENCIA
```

La gestión del kilometraje deberá permitir que Vehículos Services mantenga una referencia suficientemente actualizada del recorrido del vehículo, principalmente mediante las actualizaciones periódicas solicitadas al propietario y mediante otras lecturas válidas que puedan generarse durante su ciclo de vida, sin confundir el kilometraje actual con lecturas históricas ni trasladar a este punto las reglas específicas de validación, historial, mantenimiento, alertas o cálculos derivados.

---
### 63.9.2 Fuentes y procedencia del kilometraje


Vehículos Services deberá permitir que las lecturas de kilometraje puedan provenir de diferentes fuentes y contextos durante el ciclo de vida del vehículo.

La procedencia deberá permitir identificar, cuando la información se encuentre disponible, el origen de una lectura y el actor o mecanismo mediante el cual fue incorporada a Vehículos Services.

Conceptualmente:

```text
LECTURA DE KILOMETRAJE
        ↓
PUEDE PROVENIR DE
        │
        ├── Propietario
        ├── Prestador de Servicios Vehiculares
        ├── Intervención o evento
        ├── Información histórica
        └── Otras fuentes
            posteriormente habilitadas
```

El propietario deberá poder registrar directamente una lectura de kilometraje de su vehículo sin depender de la existencia de una relación activa con un Prestador de Servicios Vehiculares.

Esto permitirá, entre otros escenarios, responder a las solicitudes periódicas de actualización establecidas en `63.9.1 Gestión y actualización del kilometraje`, registrar una lectura directamente o aportar el kilometraje correspondiente a una intervención realizada por él o por un tercero.

Por lo tanto:

```text
REGISTRO DE KILOMETRAJE
POR EL PROPIETARIO
        ≠
DEPENDENCIA OBLIGATORIA
DE UN PRESTADOR
```

Cuando un Prestador de Servicios Vehiculares realice una intervención y cuente con la relación y los permisos correspondientes, podrá registrar el kilometraje asociado al momento de dicha intervención.

Por ejemplo:

```text
VEHÍCULO INGRESA
AL TALLER
        ↓
KILOMETRAJE:
75.450 km
        ↓
PRESTADOR REALIZA
LA INTERVENCIÓN
        ↓
REGISTRA
LA INTERVENCIÓN
Y SU KILOMETRAJE
```

El registro de una lectura por parte de un Prestador de Servicios Vehiculares no deberá otorgarle permisos adicionales sobre el vehículo ni sobre información para la cual no se encuentre autorizado.

Una lectura también podrá incorporarse posteriormente como parte de información histórica.

Por ejemplo:

```text
MANTENIMIENTO REALIZADO:
15/02/2026

KILOMETRAJE:
64.800 km

        ↓

LA INFORMACIÓN
NO FUE REGISTRADA
EN ESE MOMENTO

        ↓

SE INCORPORA
POSTERIORMENTE
A VEHÍCULOS SERVICES
```

La incorporación posterior de una lectura no deberá modificar el momento histórico al cual corresponde cuando este sea conocido.

Por lo tanto:

```text
FECHA A LA QUE
CORRESPONDE LA LECTURA
        ≠
FECHA EN QUE SE INCORPORA
A VEHÍCULOS SERVICES
```

De igual manera, cuando corresponda, deberá diferenciarse entre el origen de la información y el actor que la incorpora a la plataforma, de acuerdo con las reglas generales de procedencia establecidas para el Historial Vehicular.

Por ejemplo:

```text
TALLER NO REGISTRADO
        ↓
REALIZA MANTENIMIENTO
        ↓
FACTURA INDICA:
55.000 km
        ↓
PROPIETARIO
INCORPORA POSTERIORMENTE
LA INFORMACIÓN
```

En este escenario:

```text
ORIGEN DE LA INFORMACIÓN
        ≠
ACTOR QUE LA INCORPORA
A VEHÍCULOS SERVICES
```

Cuando la información se encuentre disponible, una lectura podrá conservar conceptualmente elementos como:

```text
LECTURA
        ↓
FECHA A LA QUE
CORRESPONDE
        ↓
FUENTE O PROCEDENCIA
        ↓
ACTOR O MECANISMO
QUE LA INCORPORA
        ↓
EVENTO O CONTEXTO
ASOCIADO
```

Estos elementos podrán coincidir en determinados escenarios, pero no deberán considerarse obligatoriamente equivalentes.

Vehículos Services no deberá exigir que toda la información relacionada con la procedencia sea conocida cuando el contexto funcional permita registrar la lectura.

La plataforma deberá conservar la información disponible sin obligar al usuario a completar mediante suposiciones los datos desconocidos.

Por lo tanto:

```text
INFORMACIÓN DESCONOCIDA
        ≠
INFORMACIÓN QUE DEBA
SER INVENTADA
```

La ausencia de determinada información sobre la procedencia no deberá decidir por sí sola la validez de una lectura. Su consistencia deberá evaluarse conforme a `63.9.3 Validación y consistencia del kilometraje`.

La gestión del kilometraje tampoco deberá asumir que todas las lecturas serán incorporadas manualmente por una persona.

En etapas posteriores podrán habilitarse otras fuentes de kilometraje, como dispositivos, sistemas del vehículo, integraciones externas u otros mecanismos autorizados.

Conceptualmente:

```text
FUENTES ACTUALES
        │
        ├── Propietario
        └── Prestador
                +
FUENTES FUTURAS
        │
        ├── Vehículo
        ├── Dispositivo
        ├── Integración externa
        └── Otros mecanismos
            autorizados
```

La consideración de estas fuentes futuras no implica que deban implementarse desde las primeras etapas del proyecto.

La procedencia de una lectura tampoco deberá establecer por sí sola que dicha lectura es correcta ni que debe convertirse automáticamente en el kilometraje actual.

Por lo tanto:

```text
PROCEDENCIA
        ≠
VALIDACIÓN
```

y:

```text
FUENTE DE LA LECTURA
        ≠
PRIORIDAD AUTOMÁTICA
SOBRE OTRAS FUENTES
```

La comparación entre lecturas, su consistencia y la determinación de cuándo una lectura puede modificar el kilometraje actual deberán regirse por `63.9.3 Validación y consistencia del kilometraje`.

Como principio general:

```text
LECTURA DE KILOMETRAJE
        ↓
TIENE UN ORIGEN
O CONTEXTO
        ↓
ES INCORPORADA
A VEHÍCULOS SERVICES
        ↓
SE CONSERVA
LA PROCEDENCIA DISPONIBLE
        ↓
SE APLICAN LAS REGLAS
QUE CORRESPONDAN
```

Vehículos Services deberá permitir que las lecturas de kilometraje provengan de diferentes fuentes y contextos, conservando la procedencia disponible sin obligar a completar información desconocida mediante suposiciones y sin asumir que el origen de una lectura determina por sí solo su validez o su condición como kilometraje actual.

---
### 63.9.3 Validación y consistencia del kilometraje

Vehículos Services deberá validar la consistencia de las lecturas de kilometraje antes de utilizarlas para modificar el kilometraje actual del vehículo.

La validación deberá considerar la información disponible sobre la lectura, incluyendo su valor, fecha, procedencia y contexto cuando estos datos se encuentren disponibles.

Conceptualmente:

```text
NUEVA LECTURA
        ↓
SE IDENTIFICA
SU CONTEXTO
        ↓
SE COMPARA CON
LA INFORMACIÓN
DISPONIBLE
        ↓
SE EVALÚA
SU CONSISTENCIA
        ↓
SE DETERMINA
SI PUEDE ACTUALIZAR
EL KILOMETRAJE ACTUAL
```

Por lo tanto:

```text
NUEVA LECTURA
        ≠
NUEVO KILOMETRAJE ACTUAL
AUTOMÁTICAMENTE
```

Cuando una nueva lectura corresponda a un momento posterior y resulte consistente con la información existente, podrá utilizarse para actualizar el kilometraje actual.

Por ejemplo:

```text
LECTURA ACTUAL:

75.300 km
01/09/2026

        ↓

NUEVA LECTURA:

76.100 km
20/09/2026

        ↓

LECTURA POSTERIOR
Y CONSISTENTE

        ↓

PUEDE ACTUALIZAR
EL KILOMETRAJE ACTUAL
```

Una lectura inferior al kilometraje actual no deberá provocar automáticamente una disminución del kilometraje vigente.

Por ejemplo:

```text
KILOMETRAJE ACTUAL:
75.300 km

        ↓

SE INTENTA REGISTRAR
COMO NUEVA LECTURA ACTUAL:

74.300 km
```

En este escenario, Vehículos Services deberá identificar una posible inconsistencia antes de modificar el kilometraje actual.

Conceptualmente:

```text
NUEVA LECTURA ACTUAL
        <
KILOMETRAJE ACTUAL

        ↓

POSIBLE INCONSISTENCIA

        ↓

NO ACTUALIZAR
AUTOMÁTICAMENTE
```

Sin embargo, un kilometraje inferior al actual no deberá considerarse inconsistente únicamente por ser menor.

La plataforma deberá diferenciar una nueva lectura actual de una lectura correspondiente a un momento histórico.

Por ejemplo:

```text
KILOMETRAJE ACTUAL:
75.300 km

        ↓

SE INCORPORA
MANTENIMIENTO ANTERIOR

Fecha:
15/05/2026

Kilometraje:
68.000 km
```

En este escenario, los `68.000 km` podrán ser coherentes con el momento histórico del mantenimiento y no deberán intentar sustituir los `75.300 km` actuales.

Por lo tanto:

```text
LECTURA HISTÓRICA
INFERIOR AL KM ACTUAL
        ≠
INCONSISTENCIA
AUTOMÁTICA
```

La consistencia deberá evaluarse teniendo en cuenta la secuencia temporal de las lecturas disponibles.

Por ejemplo:

```text
01/01/2026
60.000 km

        ↓

01/04/2026
65.000 km

        ↓

01/07/2026
70.000 km
```

representa una evolución coherente de acuerdo con la información registrada.

En cambio:

```text
01/01/2026
60.000 km

        ↓

01/04/2026
70.000 km

        ↓

01/07/2026
65.000 km
```

presenta una posible inconsistencia que deberá ser identificada y tratada antes de utilizar la última lectura como referencia vigente.

La validación tampoco deberá limitarse únicamente a identificar lecturas inferiores.

Una lectura considerablemente superior a las referencias disponibles podrá requerir validación cuando su comportamiento resulte potencialmente atípico.

Por ejemplo:

```text
KILOMETRAJE ACTUAL:
75.300 km

        ↓

NUEVA LECTURA:
753.000 km
```

El hecho de que:

```text
753.000 km
>
75.300 km
```

no deberá ser suficiente por sí solo para determinar que la nueva lectura es correcta.

Podría tratarse, por ejemplo, de un error de digitación.

Por lo tanto:

```text
LECTURA MAYOR
AL KILOMETRAJE ACTUAL
        ≠
LECTURA AUTOMÁTICAMENTE
CONSISTENTE
```

La identificación de una lectura potencialmente atípica deberá considerar también el tiempo transcurrido y demás información disponible, evitando establecer en este punto una diferencia máxima universal entre dos lecturas.

Por ejemplo, una diferencia determinada de kilometraje puede tener una interpretación distinta si ocurrió:

```text
EN UN DÍA

EN UN MES

EN SEIS MESES

EN UN AÑO
```

Por esta razón, la consistencia no deberá evaluarse exclusivamente mediante la diferencia numérica entre la lectura anterior y la nueva.

Vehículos Services deberá contemplar la posibilidad de errores de registro.

Cuando se determine que una lectura fue registrada incorrectamente, deberá poder realizarse una corrección controlada sin perder la trazabilidad correspondiente.

Conceptualmente:

```text
LECTURA INCORRECTA
        ↓
CORRECCIÓN CONTROLADA
        ↓
CONSERVACIÓN DE
LA TRAZABILIDAD
```

Las reglas generales aplicables a la modificación, corrección y conservación de registros deberán mantenerse alineadas con lo definido para el Historial Vehicular. La trazabilidad específica de las lecturas de kilometraje se complementará con lo establecido en `63.9.4 Historial y trazabilidad del kilometraje`.

La procedencia de una lectura tampoco deberá determinar automáticamente su validez.

Las lecturas provenientes de diferentes fuentes deberán evaluarse considerando su fecha, contexto, procedencia disponible y relación con la información existente, sin asumir una prioridad universal entre ellas.

Por lo tanto:

```text
FUENTE DE LA LECTURA
        ≠
GARANTÍA AUTOMÁTICA
DE CONSISTENCIA
```

La plataforma también deberá poder reconocer cuando la última lectura disponible puede encontrarse desactualizada.

Por ejemplo:

```text
ÚLTIMA LECTURA:
70.000 km

FECHA:
01/01/2026

        ↓

TRANSCURRE UN PERÍODO
SIN NUEVAS LECTURAS
```

Los `70.000 km` continuarán siendo la última lectura disponible, pero no deberá asumirse que representan necesariamente la distancia real recorrida por el vehículo en el momento actual.

Por lo tanto:

```text
ÚLTIMA LECTURA DISPONIBLE
        ≠
LECTURA NECESARIAMENTE
RECIENTE
```

Esta condición resulta especialmente relevante porque Vehículos Services solicitará periódicamente al propietario la actualización del kilometraje, de acuerdo con lo definido en `63.9.1 Gestión y actualización del kilometraje`.

La periodicidad o las condiciones a partir de las cuales una lectura pueda considerarse desactualizada deberán definirse posteriormente dentro de las reglas correspondientes.

La ausencia de una lectura reciente tampoco deberá provocar que Vehículos Services invente un nuevo kilometraje para el vehículo.

Conceptualmente:

```text
ÚLTIMA LECTURA:
70.000 km

        ↓

NO EXISTE
UNA LECTURA RECIENTE

        ↓

SE REQUIERE
ACTUALIZACIÓN

        ≠

INVENTAR O ASUMIR
UN NUEVO KM REAL
```

Si posteriormente se incorporan estimaciones o proyecciones de kilometraje, estas deberán mantenerse diferenciadas de las lecturas reales registradas.

Podrán existir situaciones especiales que alteren la evolución convencional del kilometraje, como el cambio o reparación del odómetro, correcciones de información, ausencia de registros anteriores u otros escenarios posteriormente identificados.

Estos casos deberán recibir un tratamiento específico mediante las reglas que posteriormente sean definidas y no deberán resolverse modificando arbitrariamente las lecturas existentes.

La detección de una posible inconsistencia tampoco deberá significar automáticamente la eliminación de una lectura.

Por lo tanto:

```text
POSIBLE INCONSISTENCIA
        ≠
ELIMINACIÓN AUTOMÁTICA
```

Dependiendo del contexto, una lectura podrá requerir confirmación, corrección, conservación como información histórica u otro tratamiento posteriormente definido.

Este punto no deberá definir los cálculos de mantenimiento, intervalos, kilometrajes objetivo, kilómetros transcurridos, kilómetros restantes, estados, tolerancias, alertas o recomendaciones, debido a que estos elementos corresponden a los componentes funcionales en los cuales dichas reglas sean desarrolladas.

Como principio general:

```text
NUEVA LECTURA
        ↓
VALOR
+
FECHA
+
PROCEDENCIA
+
CONTEXTO DISPONIBLE
        ↓
COMPARACIÓN CON
LA INFORMACIÓN EXISTENTE
        ↓
VALIDACIÓN DE
CONSISTENCIA
        │
        ├── CONSISTENTE
        │       ↓
        │   PUEDE ACTUALIZAR
        │   EL KILOMETRAJE ACTUAL
        │   CUANDO CORRESPONDA
        │
        └── POSIBLE INCONSISTENCIA
                ↓
            NO MODIFICAR
            AUTOMÁTICAMENTE
            EL KILOMETRAJE ACTUAL
                ↓
            APLICAR EL
            TRATAMIENTO
            CORRESPONDIENTE
```

Vehículos Services deberá proteger la consistencia del kilometraje evitando que lecturas históricas, errores de registro, valores potencialmente atípicos o información correspondiente a contextos diferentes modifiquen incorrectamente el kilometraje actual del vehículo, sin eliminar automáticamente la información y permitiendo que las correcciones necesarias se realicen de manera controlada y trazable.

---
### 63.9.4 Historial y trazabilidad del kilometraje

Vehículos Services deberá conservar la evolución de las lecturas de kilometraje asociadas al vehículo durante su ciclo de vida dentro de la plataforma.

Esta evolución deberá formar parte del Historial Vehicular y mantenerse asociada al mismo vehículo, de acuerdo con las reglas generales de conservación, continuidad y trazabilidad definidas para dicho historial.

Conceptualmente:

```text
VEHÍCULO
        ↓
HISTORIAL VEHICULAR
        ↓
EVOLUCIÓN DEL
KILOMETRAJE
```

Cada nueva lectura que corresponda conservar deberá incorporarse sin eliminar automáticamente las lecturas anteriores.

Por ejemplo:

```text
10/01/2026
60.000 km

        ↓

15/03/2026
62.500 km

        ↓

20/06/2026
65.800 km

        ↓

05/09/2026
69.200 km
```

Estas lecturas deberán permitir conocer cómo ha evolucionado el kilometraje registrado del vehículo a través del tiempo.

Por lo tanto:

```text
NUEVA LECTURA
        ≠
ELIMINACIÓN DE
LECTURAS ANTERIORES
```

El kilometraje actual y la evolución histórica del kilometraje deberán mantenerse relacionados, pero no deberán representar el mismo concepto.

Conceptualmente:

```text
KILOMETRAJE ACTUAL
        ↓
REFERENCIA VIGENTE
DEL VEHÍCULO


HISTORIAL DE KILOMETRAJE
        ↓
LECTURAS CONSERVADAS
DURANTE SU EVOLUCIÓN
```

Por ejemplo:

```text
HISTORIAL:

60.000 km
62.500 km
65.800 km
69.200 km

        ↓

KILOMETRAJE ACTUAL:

69.200 km
```

En este escenario, `69.200 km` podrá representar el kilometraje actual y, al mismo tiempo, formar parte de la evolución histórica del vehículo. Las lecturas anteriores deberán continuar conservándose.

Cuando la información se encuentre disponible, cada lectura deberá conservar el contexto necesario para poder interpretarla posteriormente, de acuerdo con las reglas de procedencia definidas en `63.9.2 Fuentes y procedencia del kilometraje`.

Esto podrá permitir conocer, entre otros elementos:

- El valor de la lectura.
- La fecha a la cual corresponde.
- Su procedencia.
- El actor o mecanismo mediante el cual fue incorporada.
- El evento o contexto con el cual se encuentre relacionada, cuando aplique.
- Las correcciones realizadas sobre la información, cuando existan.

La disponibilidad conceptual de estos elementos no implica que todos deban ser obligatorios para cada lectura.

Las lecturas históricas incorporadas posteriormente deberán poder ubicarse dentro de la evolución temporal del vehículo de acuerdo con el momento al cual correspondan, cuando este sea conocido.

Por ejemplo:

```text
HISTORIAL CONOCIDO:

01/01/2026
60.000 km

01/06/2026
68.000 km

01/09/2026
72.000 km
```

Posteriormente se incorpora una lectura correspondiente a:

```text
15/03/2026
64.000 km
```

La evolución deberá poder interpretarse como:

```text
01/01/2026
60.000 km

        ↓

15/03/2026
64.000 km

        ↓

01/06/2026
68.000 km

        ↓

01/09/2026
72.000 km
```

La incorporación posterior de los `64.000 km` no deberá convertirlos en el kilometraje actual simplemente porque fueron registrados después en Vehículos Services.

Por lo tanto:

```text
ORDEN DE INCORPORACIÓN
A LA PLATAFORMA
        ≠
ORDEN CRONOLÓGICO
DE LAS LECTURAS
```

El historial de kilometraje también deberá permitir relacionar las lecturas con los acontecimientos en los cuales fueron registradas o a los cuales correspondan, cuando dicha relación exista.

Por ejemplo:

```text
60.000 km
Actualización del propietario

        ↓

62.500 km
Mantenimiento

        ↓

65.000 km
Actualización del propietario

        ↓

67.300 km
Cambio de repuesto

        ↓

69.200 km
Actualización del propietario
```

De esta manera, el kilometraje podrá interpretarse dentro del contexto general de la vida registrada del vehículo y no únicamente como una secuencia aislada de valores.

Una misma lectura podrá ser utilizada por diferentes componentes funcionales sin que esto implique crear múltiples lecturas históricas cuando corresponda al mismo registro de origen.

Por ejemplo, si durante un mantenimiento se registra:

```text
75.450 km
```

y esa misma lectura, después de las validaciones correspondientes, permite actualizar el kilometraje actual del vehículo, no deberá generarse artificialmente una segunda lectura de `75.450 km` únicamente porque el mismo valor participa en ambos procesos.

Conceptualmente:

```text
UNA LECTURA REGISTRADA
        ↓
PUEDE PARTICIPAR EN
DIFERENTES PROCESOS
        ↓
SIN CONVERTIRSE
AUTOMÁTICAMENTE EN
MÚLTIPLES LECTURAS
HISTÓRICAS
```

Esto no deberá impedir que existan diferentes lecturas reales con el mismo valor o registradas en momentos cercanos cuando efectivamente correspondan a observaciones diferentes.

Cuando una lectura requiera corrección, la modificación deberá realizarse de acuerdo con las reglas generales de corrección y conservación establecidas para el Historial Vehicular.

La corrección no deberá eliminar silenciosamente la trazabilidad de la información modificada.

Conceptualmente:

```text
LECTURA
        ↓
CORRECCIÓN
        ↓
LECTURA CORREGIDA
        ↓
TRAZABILIDAD
DEL CAMBIO
```

La implementación técnica de versiones, auditorías, identificadores o mecanismos de conservación de cambios deberá definirse posteriormente.

La evolución del kilometraje deberá permanecer asociada al vehículo y no reiniciarse por cambios de propietario o de Prestador de Servicios Vehiculares.

Esta continuidad deberá regirse por las reglas ya definidas para el ciclo de vida del vehículo, las relaciones de propiedad y el Historial Vehicular.

Por lo tanto:

```text
CAMBIO DE PROPIETARIO
O PRESTADOR
        ≠
REINICIO DEL
HISTORIAL DE KILOMETRAJE
```

La conservación histórica de las lecturas tampoco deberá interpretarse como acceso irrestricto a dicha información.

La visibilidad deberá continuar rigiéndose por las reglas de propiedad, relaciones, autorizaciones y permisos definidas en los componentes correspondientes.

Por lo tanto:

```text
CONSERVACIÓN
DE LA INFORMACIÓN
        ≠
ACCESO IRRESTRICTO
A LA INFORMACIÓN
```

La evolución histórica del kilometraje podrá ser utilizada posteriormente por otros componentes funcionales para determinar distancias entre eventos, intervenciones u otros puntos de referencia cuando exista información suficiente.

Las fórmulas y reglas específicas utilizadas para dichos cálculos no deberán repetirse en este punto y deberán permanecer en los componentes funcionales correspondientes.

La ausencia de lecturas durante un período no deberá interpretarse como ausencia de recorrido del vehículo.

Por ejemplo:

```text
01/01/2026
60.000 km

        ↓

NO EXISTEN
LECTURAS INTERMEDIAS

        ↓

01/04/2026
65.000 km
```

En este escenario, Vehículos Services únicamente conoce las lecturas registradas y no deberá asumir qué ocurrió entre ambas.

Por lo tanto:

```text
AUSENCIA DE LECTURAS
        ≠
AUSENCIA DE RECORRIDO
```

De igual manera, la primera lectura conocida por Vehículos Services no deberá interpretarse automáticamente como el inicio del recorrido real del vehículo.

Conceptualmente:

```text
PRIMERA LECTURA
CONOCIDA
        ≠
INICIO DEL RECORRIDO
DEL VEHÍCULO
```

Esta situación deberá mantenerse alineada con las reglas ya establecidas para vehículos nuevos y usados en `63.1.9 Vehículos nuevos y usados`.

La existencia de información incompleta no deberá impedir conservar las lecturas conocidas ni deberá provocar que Vehículos Services invente lecturas inexistentes para completar los períodos sin información.

Como principio general:

```text
VEHÍCULO
        ↓
LECTURAS DE
KILOMETRAJE
        ↓
SE CONSERVAN
DENTRO DEL
HISTORIAL VEHICULAR
        ↓
SE ORGANIZAN SEGÚN
SU CONTEXTO TEMPORAL
CUANDO ES CONOCIDO
        ↓
PUEDEN RELACIONARSE
CON EVENTOS
        ↓
NUEVAS LECTURAS
NO ELIMINAN
LAS ANTERIORES
        ↓
CORRECCIONES
CONSERVAN
TRAZABILIDAD
        ↓
MISMO VEHÍCULO
        ↓
EVOLUCIÓN CONTINUA
DEL KILOMETRAJE
```

Vehículos Services deberá conservar la evolución conocida del kilometraje como parte del Historial Vehicular, permitiendo reconstruir las lecturas registradas y su contexto sin confundir el orden de incorporación con el momento al cual corresponde cada lectura, sin duplicar innecesariamente una misma lectura cuando sea utilizada por diferentes procesos y sin perder la trazabilidad de las modificaciones realizadas.


---
## 63.10 GESTIÓN DE ABASTECIMIENTO Y CONSUMO
### 63.10.1 Concepto y propósito del abastecimiento

Dentro de Vehículos Services, un abastecimiento representa el suministro de combustible, energía u otra fuente aplicable que permita al vehículo disponer de los recursos necesarios para su funcionamiento y desplazamiento, de acuerdo con su tipo y tecnología.

El concepto de abastecimiento deberá ser suficientemente amplio para representar diferentes tipos de vehículos y no deberá limitarse exclusivamente a los vehículos de combustión ni a los vehículos eléctricos.

Conceptualmente:

```text
VEHÍCULO
        ↓
REQUIERE UNA FUENTE
PARA SU FUNCIONAMIENTO
        ↓
ABASTECIMIENTO
        │
        ├── Combustible
        │      ↓
        │   Tanqueo
        │
        ├── Electricidad
        │      ↓
        │   Recarga
        │
        └── Otras fuentes
            aplicables según
            la tecnología
            del vehículo
```

Para un vehículo de combustión, el abastecimiento podrá corresponder, por ejemplo, a un tanqueo de gasolina o diésel.

Para un vehículo eléctrico, podrá corresponder a una recarga de energía eléctrica.

En vehículos que utilicen más de una fuente para su funcionamiento, como determinados vehículos híbridos, podrán existir diferentes tipos de abastecimiento de acuerdo con las características del vehículo.

Por lo tanto:

```text
TIPO Y TECNOLOGÍA
DEL VEHÍCULO
        ↓
DETERMINAN
        ↓
TIPOS DE ABASTECIMIENTO
QUE LE PUEDEN APLICAR
```

Vehículos Services no deberá asumir que todos los vehículos utilizan el mismo tipo de abastecimiento ni exigir información que no corresponda con su tecnología.

El abastecimiento deberá considerarse un evento asociado al vehículo y podrá formar parte de su Historial Vehicular.

Conceptualmente:

```text
VEHÍCULO
        ↓
ABASTECIMIENTO
        ↓
REGISTRO DEL EVENTO
        ↓
HISTORIAL VEHICULAR
```

Un abastecimiento no deberá considerarse automáticamente como un mantenimiento.

Por ejemplo:

```text
TANQUEAR GASOLINA
        ≠
REALIZAR UN MANTENIMIENTO

RECARGAR UN VEHÍCULO ELÉCTRICO
        ≠
REALIZAR UN MANTENIMIENTO
```

Aunque un abastecimiento y un mantenimiento puedan ocurrir en fechas cercanas o incluso durante una misma visita a un establecimiento, deberán conservarse como conceptos funcionales diferentes cuando representen eventos distintos.

La gestión de abastecimientos deberá permitir que el propietario lleve un registro de los recursos suministrados al vehículo y que, a partir de dichos registros y de otra información disponible, Vehículos Services pueda posteriormente generar información relacionada con consumo, rendimiento y costos.

Conceptualmente:

```text
ABASTECIMIENTOS
REGISTRADOS
        +
INFORMACIÓN DEL VEHÍCULO
        ↓
DATOS DISPONIBLES
PARA CÁLCULOS
        ↓
CONSUMO
RENDIMIENTO
COSTOS
OTRAS MÉTRICAS
POSTERIORMENTE DEFINIDAS
```

Esto no significa que todos los datos obtenidos posteriormente sean información ingresada directamente durante el abastecimiento.

Por lo tanto:

```text
INFORMACIÓN REGISTRADA
EN EL ABASTECIMIENTO
        ≠
INFORMACIÓN CALCULADA
POSTERIORMENTE
POR VEHÍCULOS SERVICES
```

Por ejemplo, el propietario podrá registrar información correspondiente a un tanqueo y, cuando exista información suficiente, Vehículos Services podrá utilizar diferentes registros para determinar posteriormente indicadores de consumo o rendimiento.

Las reglas, datos y condiciones necesarias para realizar estos cálculos no deberán definirse en este punto y serán desarrolladas en `63.10.4 Consumo, rendimiento y costos asociados`.

Un abastecimiento también podrá encontrarse relacionado con una lectura de kilometraje.

Por ejemplo:

```text
TANQUEO
        ↓
KILOMETRAJE OBSERVADO:
75.300 km
```

La existencia de esa lectura dentro del abastecimiento no deberá significar que el módulo de abastecimiento determine por sí mismo el nuevo kilometraje actual del vehículo.

Por lo tanto:

```text
KILOMETRAJE REGISTRADO
EN UN ABASTECIMIENTO
        ↓
LECTURA DE KILOMETRAJE
        ↓
SU TRATAMIENTO
SE RIGE POR
63.9 KILOMETRAJE
```

De esta manera se evita que la gestión de abastecimientos duplique las responsabilidades ya definidas para la gestión, procedencia, validación, consistencia e historial del kilometraje.

El abastecimiento deberá permanecer asociado al vehículo al cual corresponde y contribuir a construir información sobre su uso y operación durante el tiempo.

Como principio general:

```text
VEHÍCULO
        ↓
TIPO Y TECNOLOGÍA
        ↓
TIPO DE ABASTECIMIENTO
APLICABLE
        ↓
ABASTECIMIENTO REALIZADO
        ↓
REGISTRO
        ↓
HISTORIAL VEHICULAR
        ↓
INFORMACIÓN DISPONIBLE
PARA ANÁLISIS DE
CONSUMO, RENDIMIENTO
Y COSTOS
```

Vehículos Services deberá gestionar los abastecimientos como eventos propios de la operación del vehículo, diferenciándolos de los mantenimientos y permitiendo representar distintas fuentes de abastecimiento según el tipo y la tecnología del vehículo, sin duplicar las responsabilidades correspondientes al kilometraje ni anticipar las reglas específicas de cálculo de consumo, rendimiento y costos.

---

### 63.10.2 Registro de abastecimientos y recargas

Vehículos Services deberá permitir que el propietario registre los abastecimientos realizados a su vehículo con el propósito de llevar un control progresivo de su consumo, recorrido y gastos asociados.

El registro deberá adaptarse al tipo de combustible o fuente de energía previamente definido para el vehículo, sin volver a solicitar o redefinir como parte de cada abastecimiento una característica que ya pertenece a la información general del vehículo.

Conceptualmente:

```text
VEHÍCULO
        ↓
TIPO DE COMBUSTIBLE
O FUENTE DE ENERGÍA
YA DEFINIDO
        ↓
PROPIETARIO REALIZA
UN ABASTECIMIENTO
        ↓
REGISTRA EL EVENTO
EN VEHÍCULOS SERVICES
        ↓
SE ACUMULA INFORMACIÓN
PARA EL CONTROL
DEL VEHÍCULO
```

Cada abastecimiento registrado deberá representar un evento independiente ocurrido durante la utilización del vehículo.

Por ejemplo:

```text
TANQUEO 1
Kilometraje: 64.100 km
Valor pagado: $120.000

        ↓

TANQUEO 2
Kilometraje: 64.320 km
Valor pagado: $105.000

        ↓

TANQUEO 3
Kilometraje: 64.510 km
Valor pagado: $130.000
```

La acumulación de estos registros permitirá posteriormente analizar el comportamiento del vehículo durante diferentes períodos.

El registro de un abastecimiento podrá conservar la información disponible y aplicable para identificar el evento y soportar posteriormente los cálculos de consumo, rendimiento y costos que puedan realizarse.

Dependiendo del tipo de abastecimiento y de la información disponible, podrán registrarse conceptualmente datos como:

- Fecha del abastecimiento.
- Kilometraje observado al momento del abastecimiento.
- Cantidad abastecida.
- Unidad de medida correspondiente.
- Valor total pagado.
- Precio unitario, cuando se encuentre disponible o pueda determinarse a partir de otros datos registrados.
- Indicación de abastecimiento completo o parcial, cuando resulte aplicable.
- Lugar o establecimiento donde se realizó el abastecimiento, cuando el propietario desee registrarlo.
- Observaciones.
- Soportes o evidencias, cuando el propietario desee conservarlos.
- Otra información que posteriormente se determine necesaria según el tipo de abastecimiento.

No toda esta información deberá ser obligatoria para registrar un abastecimiento.

Vehículos Services deberá permitir que el propietario registre la información que tenga disponible, entendiendo que el nivel de detalle de cada registro podrá variar.

Por ejemplo:

```text
ABASTECIMIENTO A

Kilometraje: 64.100 km
Valor pagado: $120.000
Cantidad abastecida: 8,2 galones
```

mientras que otro registro podría contener únicamente:

```text
ABASTECIMIENTO B

Kilometraje: 64.320 km
Valor pagado: $105.000
```

Ambos registros podrán formar parte del control del vehículo, aunque la información disponible en cada uno permitirá realizar diferentes niveles de análisis.

Por lo tanto:

```text
MAYOR INFORMACIÓN REGISTRADA
        ↓
MAYOR POSIBILIDAD DE
CÁLCULO Y ANÁLISIS

MENOR INFORMACIÓN REGISTRADA
        ↓
SE CONSERVA LO DISPONIBLE
        ↓
SE CALCULA ÚNICAMENTE
LO QUE LOS DATOS PERMITAN
```

Vehículos Services deberá evitar solicitar manualmente información que pueda determinarse de manera confiable a partir de otros datos registrados.

Por ejemplo, cuando se conozcan:

```text
VALOR TOTAL PAGADO
        +
CANTIDAD ABASTECIDA
```

podrá determinarse posteriormente:

```text
PRECIO UNITARIO
=
VALOR TOTAL PAGADO
/
CANTIDAD ABASTECIDA
```

De esta manera, el propietario no deberá realizar manualmente cálculos que Vehículos Services pueda obtener utilizando la información registrada.

El kilometraje registrado durante un abastecimiento deberá considerarse una lectura asociada a dicho evento.

Conceptualmente:

```text
ABASTECIMIENTO
        ↓
KILOMETRAJE OBSERVADO
        ↓
LECTURA ASOCIADA
AL EVENTO
```

El tratamiento de esta lectura, incluyendo su procedencia, validación, consistencia y posible utilización para actualizar el kilometraje actual del vehículo, deberá regirse por lo establecido en `63.9 KILOMETRAJE`.

Por lo tanto:

```text
REGISTRAR UN ABASTECIMIENTO
CON 64.500 km
        ≠
MODIFICAR AUTOMÁTICAMENTE
EL KILOMETRAJE ACTUAL
SIN APLICAR LAS REGLAS
CORRESPONDIENTES
```

Los abastecimientos podrán ser completos o parciales cuando esta diferenciación resulte aplicable.

Esta condición podrá ser relevante para determinados cálculos, debido a que el propietario no necesariamente abastecerá siempre el vehículo bajo las mismas condiciones.

Por ejemplo:

```text
ABASTECIMIENTO 1
Tanque lleno

ABASTECIMIENTO 2
Abastecimiento parcial

ABASTECIMIENTO 3
Tanque lleno
```

Vehículos Services deberá conservar esta condición cuando sea registrada y utilizarla posteriormente únicamente en aquellos cálculos para los cuales resulte relevante.

El propietario podrá registrar múltiples abastecimientos durante un mismo mes o período.

Por ejemplo:

```text
SEPTIEMBRE

Tanqueo 1
Tanqueo 2
Tanqueo 3
Tanqueo 4
Tanqueo 5
Tanqueo 6
Tanqueo 7
Tanqueo 8
Tanqueo 9
Tanqueo 10
```

Cada registro deberá conservarse individualmente, mientras que Vehículos Services podrá utilizar posteriormente el conjunto de registros disponibles para generar información consolidada.

Sin embargo, Vehículos Services no deberá asumir que el propietario registrará todos los abastecimientos realizados al vehículo.

Podrán existir períodos en los cuales el propietario registre todos sus abastecimientos, otros en los que registre solamente algunos y otros en los que no registre ninguno.

Por ejemplo:

```text
TANQUEO 1
Registrado

TANQUEO 2
No registrado

TANQUEO 3
Registrado

TANQUEO 4
Registrado
```

La ausencia del registro correspondiente al Tanqueo 2 no significa que dicho abastecimiento no haya ocurrido.

Por lo tanto:

```text
ABASTECIMIENTO NO REGISTRADO
        ≠
ABASTECIMIENTO NO REALIZADO
```

Vehículos Services no deberá inventar, estimar ni crear automáticamente abastecimientos faltantes únicamente porque exista una diferencia de kilometraje, consumo, gasto u otra información que pueda sugerir que el vehículo fue abastecido durante dicho período.

De igual manera, cuando un abastecimiento haya sido registrado de manera parcial, la plataforma no deberá inventar los datos faltantes.

Por ejemplo:

```text
KILOMETRAJE:      64.500 km
VALOR PAGADO:     $120.000
CANTIDAD:         No registrada
```

Vehículos Services deberá conservar la información disponible, pero no deberá asumir cuántos galones, litros o unidades de energía fueron abastecidos.

Como principio:

```text
DATO NO REGISTRADO
        ≠
DATO CON VALOR CERO
        ≠
DATO QUE PUEDE INVENTARSE
```

Las métricas, indicadores y análisis deberán generarse utilizando únicamente la información disponible y suficiente para cada cálculo.

Por esta razón, la disponibilidad y el nivel de precisión de determinadas métricas dependerán directamente de la cantidad, continuidad y nivel de detalle de los abastecimientos registrados por el propietario.

Por ejemplo, si durante septiembre el propietario realizó diferentes abastecimientos pero solamente registró algunos de ellos y estos suman:

```text
ABASTECIMIENTOS REGISTRADOS
SEPTIEMBRE

$350.000
```

Vehículos Services podrá informar:

```text
VALOR REGISTRADO EN
ABASTECIMIENTOS:
$350.000
```

pero no deberá afirmar necesariamente:

```text
GASTO TOTAL REAL
DEL VEHÍCULO:
$350.000
```

debido a que podrían existir abastecimientos realizados que no hayan sido registrados.

De igual manera, cuando exista información suficiente para determinados cálculos pero no para otros, Vehículos Services deberá generar únicamente aquellos resultados que puedan obtenerse de manera confiable.

Conceptualmente:

```text
INFORMACIÓN REGISTRADA
        ↓
INFORMACIÓN DISPONIBLE
        ↓
VALIDACIÓN DE DATOS
NECESARIOS PARA CADA CÁLCULO
        ↓
MÉTRICAS QUE PUEDEN
CALCULARSE
        ↓
RESULTADOS
```

Mientras que:

```text
INFORMACIÓN NO REGISTRADA
        ↓
NO SE INVENTA
NO SE ASUME
NO SE COMPLETA
SIN FUNDAMENTO
```

Vehículos Services deberá diferenciar, cuando corresponda, entre la información registrada directamente por el propietario y los resultados calculados a partir de dicha información.

Por ejemplo:

```text
INFORMACIÓN REGISTRADA

Kilometraje
Valor pagado
Cantidad abastecida

        ↓

INFORMACIÓN CALCULADA

Distancia recorrida
Precio unitario
Consumo
Rendimiento
Costo por kilómetro
Promedios
Variaciones
```

La existencia de información suficiente para calcular un resultado no deberá modificar ni reemplazar los datos originales registrados por el propietario.

Cada nuevo abastecimiento deberá agregarse al control del vehículo sin reemplazar los abastecimientos anteriores.

Conceptualmente:

```text
REGISTROS INDIVIDUALES
DE ABASTECIMIENTO
        ↓
ACUMULACIÓN PROGRESIVA
DE INFORMACIÓN
        ↓
CONTROL DEL CONSUMO
Y DEL GASTO
        ↓
MÉTRICAS Y
COMPARACIONES
POR PERÍODOS
```

La definición detallada de los cálculos relacionados con consumo y rendimiento deberá desarrollarse en `63.10.3 Control de consumo y rendimiento`.

La gestión específica de costos y gastos deberá desarrollarse en `63.10.4 Control de costos y gastos de abastecimiento`.

Las comparaciones mensuales, anuales y entre otros períodos deberán desarrollarse en `63.10.5 Métricas y análisis por períodos`.

La conservación histórica y trazabilidad de los abastecimientos deberá desarrollarse en `63.10.6 Historial y trazabilidad de abastecimientos y recargas`.

Como principio general:

```text
PROPIETARIO
        ↓
REALIZA TANQUEO
O RECARGA
        ↓
DECIDE REGISTRARLO
EN VEHÍCULOS SERVICES
        ↓
REGISTRA LA INFORMACIÓN
QUE TIENE DISPONIBLE
        ↓
VEHÍCULOS SERVICES
CONSERVA LOS DATOS
        ↓
UTILIZA ÚNICAMENTE
INFORMACIÓN SUFICIENTE
PARA CADA CÁLCULO
        ↓
GENERA LOS CONTROLES
Y MÉTRICAS POSIBLES
        ↓
RECORRIDO
CONSUMO
RENDIMIENTO
GASTOS
MÉTRICAS
COMPARACIONES
```

Vehículos Services deberá permitir que el propietario construya progresivamente su propio control de abastecimiento mediante los registros que decida incorporar, sin exigir que exista una continuidad perfecta de información y sin asumir datos que no hayan sido registrados.

La calidad, continuidad y nivel de detalle de los resultados obtenidos dependerán de la información disponible, manteniendo siempre la distinción entre lo efectivamente registrado y lo que pueda calcularse de manera confiable a partir de dichos registros.

---

### 63.10.3 Control de consumo y rendimiento

Vehículos Services deberá utilizar la información disponible de los abastecimientos y las lecturas de kilometraje para proporcionar al propietario información que le permita conocer y analizar progresivamente el comportamiento de consumo y rendimiento de su vehículo.

El control deberá construirse a partir de los datos efectivamente registrados y de aquellos resultados que puedan calcularse de manera confiable, sin asumir que todos los abastecimientos realizados al vehículo se encuentran registrados.

Conceptualmente:

```text
ABASTECIMIENTOS REGISTRADOS
        +
LECTURAS DE KILOMETRAJE
        +
CANTIDADES ABASTECIDAS
CUANDO ESTÉN DISPONIBLES
        ↓
INFORMACIÓN SUFICIENTE
PARA CADA CÁLCULO
        ↓
CONTROL DE
RECORRIDO
CONSUMO
RENDIMIENTO
```

Vehículos Services deberá diferenciar conceptualmente entre recorrido, consumo y rendimiento.

El recorrido representa la distancia existente entre lecturas de kilometraje que puedan relacionarse de manera válida.

Por ejemplo:

```text
ABASTECIMIENTO A
64.100 km

ABASTECIMIENTO B
64.300 km

        ↓

DISTANCIA ENTRE
AMBAS LECTURAS:
200 km
```

Cuando las lecturas sean válidas y comparables:

```text
DISTANCIA ENTRE LECTURAS
=
KILOMETRAJE POSTERIOR
-
KILOMETRAJE ANTERIOR
```

Este cálculo representa una distancia recorrida entre dos lecturas conocidas, pero por sí solo no determina cuánto combustible o energía fue consumido durante dicho recorrido.

Por lo tanto:

```text
DISTANCIA RECORRIDA
        ≠
CONSUMO
```

El consumo deberá relacionarse con la cantidad de combustible o energía utilizada durante un recorrido o período determinado, siempre que exista información suficiente para establecer dicha relación.

El rendimiento deberá representar la relación entre la distancia recorrida y el combustible o energía utilizado.

Conceptualmente:

```text
DISTANCIA RECORRIDA
        +
CONSUMO DETERMINABLE
        ↓
RENDIMIENTO
```

Dependiendo del tipo de vehículo, fuente de energía y unidad utilizada, el rendimiento podrá expresarse posteriormente mediante indicadores apropiados, como distancia por unidad consumida u otras medidas que correspondan.

Por ejemplo, para un vehículo cuya información se gestione en galones:

```text
DISTANCIA:
200 km

CONSUMO DETERMINABLE:
8 galones

        ↓

RENDIMIENTO:
25 km/galón
```

Conceptualmente:

```text
RENDIMIENTO
=
DISTANCIA RECORRIDA
/
CANTIDAD CONSUMIDA
```

Sin embargo, Vehículos Services no deberá asumir automáticamente que la cantidad registrada en un abastecimiento corresponde exactamente al combustible o energía consumido desde el abastecimiento registrado inmediatamente anterior.

Por ejemplo:

```text
REGISTRO A
64.100 km
8 galones

REGISTRO B
64.300 km
7 galones
```

La existencia de ambos registros no demuestra por sí sola que los 7 galones registrados en el segundo abastecimiento correspondan exactamente al consumo realizado durante los 200 km existentes entre ambas lecturas.

Podrían existir situaciones como:

```text
ABASTECIMIENTO A
Registrado

        ↓

ABASTECIMIENTO INTERMEDIO
No registrado

        ↓

ABASTECIMIENTO B
Registrado
```

También podrían existir abastecimientos parciales o diferentes niveles de combustible o energía antes de cada abastecimiento.

Por esta razón:

```text
ABASTECIMIENTOS CONSECUTIVOS
EN VEHÍCULOS SERVICES
        ≠
ABASTECIMIENTOS NECESARIAMENTE
CONSECUTIVOS EN LA REALIDAD
```

Vehículos Services deberá calcular indicadores de consumo y rendimiento únicamente cuando la información disponible permita establecer una relación suficientemente confiable entre la distancia recorrida y la cantidad consumida.

Cuando dicha relación no pueda establecerse de manera confiable, la plataforma podrá continuar mostrando la información registrada y aquellos cálculos independientes que sí sean válidos, sin generar un indicador de consumo o rendimiento que pueda resultar engañoso.

Por ejemplo:

```text
KM ANTERIOR:
64.100 km

KM POSTERIOR:
64.300 km

        ↓

DISTANCIA:
200 km
```

La distancia podrá ser calculable aunque no exista información suficiente para determinar el consumo correspondiente.

Por lo tanto:

```text
PUEDO CALCULAR DISTANCIA
        ≠
PUEDO CALCULAR AUTOMÁTICAMENTE
CONSUMO Y RENDIMIENTO
```

Cuando se utilicen abastecimientos completos como referencia para determinados cálculos, Vehículos Services deberá considerar la continuidad y suficiencia de la información disponible.

Por ejemplo, conceptualmente:

```text
TANQUE LLENO
        ↓
RECORRIDO
        ↓
TANQUE LLENO
        ↓
CANTIDAD NECESARIA
PARA COMPLETAR NUEVAMENTE
        ↓
POSIBILIDAD DE ESTABLECER
UNA RELACIÓN MÁS CONFIABLE
ENTRE RECORRIDO Y CONSUMO
```

La existencia de abastecimientos parciales entre dos abastecimientos completos no deberá provocar que dichas cantidades sean ignoradas cuando sean necesarias para determinar correctamente el consumo del período.

Por ejemplo:

```text
TANQUE LLENO
        ↓
ABASTECIMIENTO PARCIAL
        ↓
ABASTECIMIENTO PARCIAL
        ↓
TANQUE LLENO
```

Cuando todos estos eventos hayan sido registrados y exista información suficiente, el análisis podrá considerar conjuntamente las cantidades abastecidas necesarias para determinar el consumo correspondiente al recorrido evaluado.

Si uno o varios abastecimientos intermedios no fueron registrados, Vehículos Services no deberá inventar las cantidades faltantes ni presentar como exacto un rendimiento que dependa de ellas.

Por lo tanto:

```text
INFORMACIÓN COMPLETA
Y SUFICIENTE
        ↓
CÁLCULO DISPONIBLE


INFORMACIÓN PARCIAL
PERO SUFICIENTE
PARA UN CÁLCULO
        ↓
CÁLCULO DISPONIBLE
SEGÚN CORRESPONDA


INFORMACIÓN INSUFICIENTE
        ↓
NO SE INVENTA
EL RESULTADO
```

El control también deberá permitir analizar la evolución del rendimiento cuando existan suficientes datos comparables.

Por ejemplo:

```text
PERÍODO A
Rendimiento calculable:
25 km/galón

PERÍODO B
Rendimiento calculable:
23 km/galón

PERÍODO C
Rendimiento calculable:
26 km/galón
```

Esta información podrá permitir al propietario observar variaciones en el comportamiento registrado de su vehículo.

Sin embargo, una variación del rendimiento no deberá interpretarse automáticamente como una falla mecánica.

Por lo tanto:

```text
VARIACIÓN DEL
RENDIMIENTO REGISTRADO
        ≠
DIAGNÓSTICO AUTOMÁTICO
DE UNA FALLA
```

El consumo y rendimiento pueden verse afectados por múltiples condiciones que no necesariamente estarán registradas o disponibles dentro de Vehículos Services.

La plataforma podrá informar las variaciones que puedan determinarse a partir de los datos disponibles, pero no deberá atribuir automáticamente una causa específica sin información o reglas suficientes para hacerlo.

Vehículos Services deberá conservar además la diferencia entre información registrada e información calculada.

Por ejemplo:

```text
INFORMACIÓN REGISTRADA

Kilometraje
Cantidad abastecida
Condición del abastecimiento

        ↓

INFORMACIÓN CALCULADA

Distancia
Consumo determinable
Rendimiento
Variaciones de rendimiento
```

Los resultados calculados no deberán reemplazar ni modificar los datos originales utilizados para obtenerlos.

Cuando la información registrada no permita calcular una métrica determinada, esto no deberá impedir que el propietario continúe registrando nuevos abastecimientos.

La incorporación progresiva de nuevos registros podrá permitir que posteriormente existan períodos con mayor información y mejores posibilidades de análisis.

Conceptualmente:

```text
POCOS DATOS
        ↓
CONTROL LIMITADO

MÁS DATOS
        ↓
MAYOR CAPACIDAD
DE ANÁLISIS

DATOS SUFICIENTES
Y COMPARABLES
        ↓
MÉTRICAS DE CONSUMO
Y RENDIMIENTO
MÁS COMPLETAS
```

El tratamiento del kilometraje utilizado para estos cálculos deberá continuar sujeto a las reglas establecidas en `63.9 KILOMETRAJE`.

La información relacionada con valores pagados, costos acumulados y costo asociado al recorrido deberá desarrollarse en `63.10.4 Control de costos y gastos de abastecimiento`.

Las agrupaciones, tendencias y comparaciones entre meses, años u otros períodos deberán desarrollarse en `63.10.5 Métricas y análisis por períodos`.

Como principio general:

```text
VEHÍCULOS SERVICES
        ↓
UTILIZA LOS DATOS
REALMENTE DISPONIBLES
        ↓
DETERMINA QUÉ PUEDE
CALCULARSE DE FORMA CONFIABLE
        ↓
DISTANCIA
CONSUMO
RENDIMIENTO
        ↓
PERMITE AL PROPIETARIO
CONOCER LA EVOLUCIÓN
DEL COMPORTAMIENTO
DE SU VEHÍCULO
```

Vehículos Services deberá proporcionar al propietario herramientas para controlar el consumo y rendimiento de su vehículo sin presentar como completos o exactos aquellos resultados que dependan de información que no haya sido registrada o que resulte insuficiente para realizar el cálculo correspondiente.

---
### 63.10.4 Control de costos y gastos de abastecimiento

Vehículos Services deberá utilizar la información económica registrada en los abastecimientos para permitir que el propietario lleve un control de los gastos asociados al combustible o energía de su vehículo.

Este control deberá construirse exclusivamente con la información disponible en los abastecimientos registrados y no deberá asumir que todos los gastos realizados por el propietario han sido incorporados a la plataforma.

Conceptualmente:

```text
ABASTECIMIENTOS REGISTRADOS
        ↓
VALORES PAGADOS
        ↓
ACUMULACIÓN DE GASTOS
REGISTRADOS
        ↓
CONTROL ECONÓMICO
DEL ABASTECIMIENTO
```

Cada abastecimiento podrá tener asociado un valor pagado cuando esta información sea suministrada por el propietario.

Por ejemplo:

```text
TANQUEO 1
$120.000

TANQUEO 2
$105.000

TANQUEO 3
$130.000

        ↓

GASTO REGISTRADO:
$355.000
```

Vehículos Services podrá acumular los valores correspondientes a los abastecimientos registrados para determinar cuánto dinero ha sido registrado durante un período determinado.

Por lo tanto:

```text
GASTO REGISTRADO
=
SUMA DE LOS VALORES
DE LOS ABASTECIMIENTOS
REGISTRADOS
```

Este resultado deberá interpretarse como el gasto conocido por Vehículos Services a partir de la información incorporada por el propietario.

No deberá asumirse automáticamente que representa la totalidad del dinero realmente gastado en abastecimiento durante el período.

Por ejemplo:

```text
ENERO

Tanqueo 1: $120.000
Tanqueo 2: $110.000
Tanqueo 3: No registrado
Tanqueo 4: $125.000

        ↓

VALOR REGISTRADO:
$355.000
```

Vehículos Services podrá indicar que existen `$355.000` registrados en abastecimientos durante enero, pero no deberá afirmar que ese fue necesariamente el gasto total real del propietario durante el mes.

Por lo tanto:

```text
GASTO REGISTRADO
        ≠
GASTO TOTAL REAL
CUANDO PUEDEN EXISTIR
ABASTECIMIENTOS
NO REGISTRADOS
```

La plataforma tampoco deberá interpretar la ausencia de gastos registrados como ausencia de gastos reales.

Por ejemplo:

```text
FEBRERO

SIN ABASTECIMIENTOS
REGISTRADOS
```

no deberá interpretarse automáticamente como:

```text
GASTO REAL:
$0
```

Por lo tanto:

```text
SIN REGISTROS
        ≠
SIN GASTOS
```

Vehículos Services podrá utilizar el valor pagado junto con otra información disponible para generar indicadores económicos adicionales cuando existan datos suficientes.

Cuando se conozcan el valor total pagado y la cantidad abastecida, podrá determinarse el precio unitario correspondiente.

Conceptualmente:

```text
VALOR PAGADO
        /
CANTIDAD ABASTECIDA
        ↓
PRECIO UNITARIO
```

Por ejemplo:

```text
VALOR PAGADO:
$120.000

CANTIDAD:
8 galones

        ↓

PRECIO UNITARIO:
$15.000 por galón
```

Cuando el precio unitario haya sido registrado directamente y también pueda calcularse a partir del valor total y la cantidad abastecida, Vehículos Services deberá conservar la información registrada y posteriormente aplicar las reglas de validación o consistencia que correspondan, sin reemplazar silenciosamente un dato suministrado por el propietario.

La plataforma podrá conservar los precios unitarios correspondientes a diferentes abastecimientos para permitir posteriormente analizar su evolución.

Por ejemplo:

```text
TANQUEO 1
$15.000 / galón

TANQUEO 2
$15.200 / galón

TANQUEO 3
$14.900 / galón
```

Esta información podrá utilizarse posteriormente para determinar valores promedio, variaciones y comparaciones entre abastecimientos o períodos.

Cuando exista información suficiente sobre el gasto registrado y la distancia recorrida correspondiente, Vehículos Services podrá determinar indicadores relacionados con el costo del recorrido.

Conceptualmente:

```text
GASTO ASOCIABLE
AL RECORRIDO
        +
DISTANCIA
CORRESPONDIENTE
        ↓
COSTO POR DISTANCIA
```

Por ejemplo:

```text
GASTO:
$120.000

DISTANCIA:
300 km

        ↓

COSTO:
$400 por km
```

Conceptualmente:

```text
COSTO POR KM
=
GASTO ASOCIABLE
/
DISTANCIA CORRESPONDIENTE
```

Sin embargo, este cálculo solamente deberá realizarse cuando exista información suficiente para relacionar de manera válida el gasto considerado con el recorrido correspondiente.

La existencia de un valor pagado y una diferencia de kilometraje no deberá provocar automáticamente un cálculo de costo por kilómetro cuando existan registros faltantes o condiciones que impidan establecer correctamente dicha relación.

Por lo tanto:

```text
VALOR PAGADO
        +
DIFERENCIA DE KM
        ≠
COSTO POR KM
AUTOMÁTICAMENTE
```

Vehículos Services deberá aplicar el mismo principio de suficiencia de información definido para los cálculos de consumo y rendimiento.

Cuando no exista información suficiente para una métrica económica determinada, la plataforma deberá conservar los gastos registrados y continuar proporcionando aquellos resultados que sí puedan calcularse de manera confiable.

Por ejemplo:

```text
VALOR PAGADO:
$120.000

CANTIDAD:
No registrada

KILOMETRAJE:
64.500 km
```

permite conservar:

```text
GASTO REGISTRADO:
$120.000
```

pero no necesariamente permite determinar:

```text
PRECIO POR GALÓN
CONSUMO
RENDIMIENTO
COSTO POR KM
```

si no existe la demás información necesaria para cada cálculo.

Por lo tanto:

```text
UN MISMO REGISTRO
        ↓
PUEDE SER SUFICIENTE
PARA ALGUNAS MÉTRICAS
        ↓
E INSUFICIENTE
PARA OTRAS
```

El control económico deberá permitir acumular progresivamente los gastos registrados sin exigir que exista una continuidad perfecta en la información.

Por ejemplo:

```text
ENERO
$420.000 registrados

FEBRERO
$310.000 registrados

MARZO
$465.000 registrados
```

Estos valores podrán utilizarse posteriormente para que el propietario consulte y compare sus gastos registrados entre diferentes períodos.

Sin embargo, cuando la continuidad de los registros sea diferente entre períodos, Vehículos Services deberá evitar presentar las diferencias observadas como si necesariamente representaran una reducción o aumento real del gasto.

Por ejemplo:

```text
ENERO
10 abastecimientos registrados
$500.000

FEBRERO
5 abastecimientos registrados
$300.000
```

no permite concluir automáticamente:

```text
EL PROPIETARIO
GASTÓ $200.000 MENOS
EN FEBRERO
```

porque podrían existir abastecimientos no registrados.

Vehículos Services podrá mostrar la diferencia existente entre los valores registrados, manteniendo claro que el resultado corresponde a la información disponible.

Cuando exista información suficientemente completa y comparable, podrán obtenerse análisis económicos más representativos.

La plataforma también podrá permitir conocer cuánto representa el abastecimiento dentro del uso registrado del vehículo mediante indicadores como:

- Valor registrado por abastecimiento.
- Gasto registrado acumulado.
- Precio unitario cuando pueda determinarse.
- Precio unitario promedio cuando exista información suficiente.
- Costo por kilómetro cuando pueda establecerse de manera confiable.
- Variaciones de los costos registrados.
- Otros indicadores económicos que posteriormente se determinen aplicables.

La existencia de estos indicadores no deberá implicar que todos estarán disponibles para todos los vehículos o períodos.

Conceptualmente:

```text
DATOS DISPONIBLES
        ↓
INDICADORES ECONÓMICOS
QUE PUEDEN CALCULARSE
        ↓
CONTROL DE GASTOS
DEL PROPIETARIO
```

Vehículos Services deberá diferenciar entre los valores registrados directamente y los valores calculados.

Por ejemplo:

```text
DATOS REGISTRADOS

Valor pagado
Cantidad abastecida
Kilometraje

        ↓

DATOS CALCULADOS

Precio unitario
Gasto acumulado
Promedios
Costo por km
Variaciones
```

Los cálculos realizados no deberán modificar ni reemplazar los valores originales registrados en cada abastecimiento.

El control de gastos deberá mantenerse asociado al vehículo correspondiente.

Cuando un propietario tenga varios vehículos, los gastos registrados para cada uno deberán poder distinguirse de manera independiente, sin mezclarse automáticamente.

Conceptualmente:

```text
PROPIETARIO

├── VEHÍCULO A
│      ↓
│   GASTOS DE
│   ABASTECIMIENTO A
│
└── VEHÍCULO B
       ↓
    GASTOS DE
    ABASTECIMIENTO B
```

Posteriormente podrán definirse reportes o consolidaciones que permitan al propietario consultar información conjunta de varios vehículos cuando corresponda, sin perder la identificación del vehículo al cual pertenece cada gasto.

La plataforma deberá conservar la relación entre cada gasto y el abastecimiento que lo originó.

Por lo tanto:

```text
ABASTECIMIENTO
        ↓
VALOR PAGADO
        ↓
REGISTRO ECONÓMICO
ASOCIADO AL EVENTO
```

El gasto de abastecimiento no deberá tratarse como un valor aislado sin relación con el evento del cual proviene.

Los análisis mensuales, anuales y las comparaciones entre diferentes períodos deberán desarrollarse en `63.10.5 Métricas y análisis por períodos`.

La conservación histórica de cada abastecimiento y de la información asociada deberá desarrollarse en `63.10.6 Historial y trazabilidad de abastecimientos y recargas`.

Como principio general:

```text
PROPIETARIO
        ↓
REGISTRA ABASTECIMIENTOS
        ↓
REGISTRA LOS VALORES
QUE TIENE DISPONIBLES
        ↓
VEHÍCULOS SERVICES
CONSERVA LOS GASTOS
REGISTRADOS
        ↓
UTILIZA LA INFORMACIÓN
SUFICIENTE PARA CADA CÁLCULO
        ↓
GASTO REGISTRADO
PRECIO UNITARIO
COSTO POR KM
PROMEDIOS
VARIACIONES
OTROS INDICADORES
        ↓
CONTROL ECONÓMICO
DEL VEHÍCULO
```

Vehículos Services deberá permitir que el propietario conozca y analice progresivamente cuánto dinero ha registrado en abastecimiento para cada vehículo, utilizando exclusivamente la información disponible y evitando presentar como gasto total real, o como indicador exacto, aquellos resultados que dependan de abastecimientos o datos que no hayan sido registrados.

---

### 63.10.5 Métricas y análisis por períodos

Vehículos Services deberá permitir que el propietario consulte y analice la información registrada y calculada de los abastecimientos agrupándola por diferentes períodos de tiempo.

El propósito será transformar los registros individuales de abastecimiento en información que permita al propietario observar la evolución del uso, consumo, rendimiento y gastos de su vehículo.

Conceptualmente:

```text
ABASTECIMIENTOS
INDIVIDUALES
        ↓
AGRUPACIÓN POR
PERÍODOS
        ↓
CONSOLIDACIÓN DE
INFORMACIÓN
        ↓
MÉTRICAS
        ↓
COMPARACIONES
        ↓
EVOLUCIÓN DEL
VEHÍCULO
```

Los períodos de análisis podrán contemplar inicialmente agrupaciones como:

- Mes.
- Año.
- Otros períodos que posteriormente se determinen necesarios.

La definición de períodos adicionales no deberá modificar los registros originales de abastecimiento.

Cada abastecimiento continuará existiendo como un evento individual, mientras que las agrupaciones deberán representar diferentes formas de consultar y analizar dicha información.

Por lo tanto:

```text
REGISTROS ORIGINALES
        ↓
SE CONSERVAN

AGRUPACIONES
Y MÉTRICAS
        ↓
SE CALCULAN
A PARTIR DE ELLOS
```

Dependiendo de la información disponible, Vehículos Services podrá presentar por período métricas relacionadas con:

- Cantidad de abastecimientos registrados.
- Valor total registrado en abastecimientos.
- Distancia recorrida que pueda determinarse con la información disponible.
- Cantidad abastecida registrada.
- Precio unitario promedio, cuando pueda determinarse.
- Consumo, cuando exista información suficiente.
- Rendimiento, cuando pueda determinarse de manera confiable.
- Costo por kilómetro, cuando exista información suficiente.
- Promedios relacionados con los abastecimientos registrados.
- Variaciones respecto a otros períodos comparables.
- Otros indicadores que posteriormente se determinen aplicables.

No todas las métricas deberán encontrarse disponibles para todos los períodos.

La disponibilidad de cada resultado dependerá de que existan los datos necesarios para realizar el cálculo correspondiente.

Conceptualmente:

```text
PERÍODO
        ↓
¿QUÉ INFORMACIÓN
EXISTE?
        ↓
¿QUÉ MÉTRICAS PUEDEN
CALCULARSE?
        ↓
MOSTRAR ÚNICAMENTE
RESULTADOS SOPORTADOS
POR LOS DATOS
```

Por ejemplo, un propietario podría tener durante un mes:

```text
ENERO

Abastecimientos registrados: 8
Valor registrado: $720.000
Cantidad abastecida: disponible
Kilometraje: disponible
```

y durante otro:

```text
FEBRERO

Abastecimientos registrados: 5
Valor registrado: $430.000
Cantidad abastecida: incompleta
Kilometraje: disponible
```

Vehículos Services podrá generar para enero más métricas que para febrero si la información registrada permite realizar cálculos adicionales.

Por lo tanto:

```text
MISMO VEHÍCULO
        ≠
MISMAS MÉTRICAS
DISPONIBLES
EN TODOS LOS PERÍODOS
```

La plataforma deberá permitir comparar períodos cuando exista información que pueda ser relacionada de manera válida.

Por ejemplo:

```text
ENERO
Valor registrado: $720.000

FEBRERO
Valor registrado: $650.000

MARZO
Valor registrado: $690.000
```

Vehículos Services podrá mostrar la evolución de los valores registrados y sus diferencias entre períodos.

Sin embargo, deberá mantenerse la distinción entre comparar información registrada y afirmar que se está comparando la totalidad del gasto real.

Si el propietario registró información de manera incompleta en alguno de los períodos, una diferencia entre los valores registrados no deberá interpretarse automáticamente como una variación equivalente del gasto real.

Por ejemplo:

```text
ENERO
10 abastecimientos registrados
$800.000

FEBRERO
6 abastecimientos registrados
$500.000
```

permite establecer que:

```text
VALOR REGISTRADO EN FEBRERO
<
VALOR REGISTRADO EN ENERO
```

pero no necesariamente permite concluir:

```text
EL GASTO REAL DEL VEHÍCULO
DISMINUYÓ EN ESA MISMA
PROPORCIÓN
```

si no existe suficiente información para garantizar que ambos períodos contienen registros comparables.

El mismo principio deberá aplicarse a las demás métricas.

Por ejemplo, si existe información suficiente y comparable, el propietario podrá observar:

```text
ENERO
Rendimiento calculado:
25 km/galón

FEBRERO
Rendimiento calculado:
24 km/galón

MARZO
Rendimiento calculado:
26 km/galón
```

Esto permitirá identificar la evolución del rendimiento calculado a partir de la información disponible.

La variación observada deberá tratarse como una diferencia entre los resultados obtenidos y no automáticamente como evidencia de una causa específica.

Por lo tanto:

```text
VARIACIÓN OBSERVADA
        ≠
CAUSA DETERMINADA
AUTOMÁTICAMENTE
```

Vehículos Services también deberá permitir analizar conjuntamente diferentes métricas cuando exista información suficiente.

Por ejemplo:

```text
PERÍODO A

Distancia registrada/calculable
        +
Cantidad abastecida registrada
        +
Gasto registrado
        ↓
Consumo
Rendimiento
Costo por km
```

Esto permitirá que el propietario no analice únicamente cuánto dinero registró, sino también cómo se relaciona ese gasto con el uso registrado del vehículo.

Por ejemplo, dos meses podrían presentar:

```text
ENERO

Distancia calculable:
1.000 km

Gasto registrado:
$600.000


AGOSTO

Distancia calculable:
1.020 km

Gasto registrado:
$520.000
```

Vehículos Services podrá mostrar que para distancias registradas similares existe una diferencia entre los gastos registrados de ambos períodos.

Si adicionalmente existe información suficiente sobre cantidades abastecidas y precios unitarios, la plataforma podrá proporcionar más elementos para comprender dicha diferencia.

Por ejemplo:

```text
ENERO

Distancia:
1.000 km

Cantidad abastecida:
40 galones

Precio promedio registrado:
$15.000 / galón


AGOSTO

Distancia:
1.020 km

Cantidad abastecida:
40 galones

Precio promedio registrado:
$13.000 / galón
```

Con información de este tipo podrán identificarse diferencias objetivas entre los datos registrados de ambos períodos.

Sin embargo, Vehículos Services no deberá atribuir automáticamente una diferencia en el gasto a una única causa cuando puedan intervenir múltiples variables.

Por lo tanto:

```text
MENOR GASTO REGISTRADO
        ≠
AUTOMÁTICAMENTE
MENOR PRECIO DEL COMBUSTIBLE
```

La plataforma deberá utilizar los datos disponibles para mostrar qué variables registradas cambiaron, evitando establecer explicaciones que no puedan sustentarse con la información disponible.

Las comparaciones podrán realizarse sobre diferentes períodos del mismo vehículo.

Por ejemplo:

```text
MES ACTUAL
        ↔
MES ANTERIOR

ENERO 2026
        ↔
ENERO 2027

PRIMER SEMESTRE
        ↔
SEGUNDO SEMESTRE

AÑO 2026
        ↔
AÑO 2027
```

La definición exacta de las opciones de comparación que estarán disponibles para el usuario deberá establecerse posteriormente durante el diseño funcional y de interfaz.

En esta etapa se establece únicamente que la información deberá conservarse de manera que permita realizar análisis temporales sin alterar los registros originales.

Cuando se realicen comparaciones, Vehículos Services deberá considerar la disponibilidad y suficiencia de los datos correspondientes a cada período.

Conceptualmente:

```text
PERÍODO A
        +
PERÍODO B
        ↓
VALIDAR INFORMACIÓN
DISPONIBLE
        ↓
DETERMINAR MÉTRICAS
COMPARABLES
        ↓
REALIZAR COMPARACIÓN
```

La ausencia de registros durante un período deberá diferenciarse de un resultado igual a cero.

Por ejemplo:

```text
MARZO

Sin abastecimientos registrados
```

no deberá mostrarse automáticamente como:

```text
Gasto: $0
Consumo: 0
Cantidad abastecida: 0
```

cuando en realidad no existe información suficiente para determinar esos resultados.

Por lo tanto:

```text
SIN INFORMACIÓN
        ≠
VALOR CERO
```

Vehículos Services deberá distinguir entre:

```text
DATO REGISTRADO
        ↓
Información suministrada

DATO CALCULADO
        ↓
Resultado obtenido a partir
de información suficiente

DATO NO DISPONIBLE
        ↓
No existe información
suficiente para determinarlo
```

Esta diferenciación deberá mantenerse al presentar métricas y comparaciones al propietario.

Las métricas calculadas deberán poder actualizarse cuando se incorporen nuevos registros que afecten el período analizado.

Por ejemplo:

```text
ENERO

Inicialmente:
5 abastecimientos registrados

        ↓

Posteriormente el propietario
incorpora un abastecimiento
realizado en enero

        ↓

ENERO

6 abastecimientos registrados
        ↓
MÉTRICAS DEL PERÍODO
ACTUALIZADAS
```

La incorporación posterior de información histórica deberá conservar la fecha correspondiente al abastecimiento y permitir que este sea considerado dentro del período al cual realmente pertenece, de acuerdo con las reglas generales del Historial Vehicular.

Por lo tanto:

```text
FECHA DE REGISTRO
EN LA PLATAFORMA
        ≠
NECESARIAMENTE
FECHA DEL ABASTECIMIENTO
```

Las métricas por períodos deberán recalcularse utilizando la información disponible vigente, sin modificar los registros originales que las sustentan.

Cuando el propietario tenga varios vehículos, las métricas deberán mantenerse diferenciadas por vehículo.

Por ejemplo:

```text
PROPIETARIO
        ↓
VEHÍCULO A
        ↓
MÉTRICAS A

PROPIETARIO
        ↓
VEHÍCULO B
        ↓
MÉTRICAS B
```

Posteriormente podrán existir consolidaciones que permitan analizar información de varios vehículos, cuando esta funcionalidad sea definida, pero dichas consolidaciones no deberán eliminar la posibilidad de identificar el origen de cada registro y métrica.

Vehículos Services deberá permitir que las métricas evolucionen a medida que aumenta la información registrada.

Conceptualmente:

```text
REGISTROS
        ↓
INFORMACIÓN DISPONIBLE
        ↓
MÉTRICAS
        ↓
ACUMULACIÓN EN EL TIEMPO
        ↓
COMPARACIONES
        ↓
TENDENCIAS
        ↓
MAYOR CONOCIMIENTO
DEL COMPORTAMIENTO
DEL VEHÍCULO
```

Las métricas relacionadas con consumo y rendimiento deberán utilizar los principios establecidos en `63.10.3 Control de consumo y rendimiento`.

Las métricas económicas deberán utilizar los principios establecidos en `63.10.4 Control de costos y gastos de abastecimiento`.

Este punto no deberá redefinir las reglas de cálculo correspondientes a dichas métricas, sino establecer cómo podrán agruparse, analizarse y compararse temporalmente.

Como principio general:

```text
INFORMACIÓN DISPONIBLE
DE CADA PERÍODO
        ↓
MÉTRICAS QUE PUEDEN
CALCULARSE
        ↓
COMPARACIÓN ENTRE
RESULTADOS COMPATIBLES
        ↓
EVOLUCIÓN
TENDENCIAS
DIFERENCIAS
        ↓
INFORMACIÓN ÚTIL
PARA EL PROPIETARIO
```

Vehículos Services deberá permitir que el propietario comprenda cómo evolucionan los abastecimientos, el consumo, el rendimiento y los gastos registrados de su vehículo a través del tiempo, manteniendo siempre visible la diferencia entre información registrada, información calculada y datos que no se encuentran disponibles.

---
### 63.10.6 Historial y trazabilidad de abastecimientos y recargas

Los abastecimientos y recargas registrados en Vehículos Services deberán formar parte del Historial Vehicular y conservarse asociados al vehículo al cual corresponden.

Este punto deberá aplicar los principios generales establecidos en `63.6 HISTORIAL VEHICULAR` al contexto específico de los abastecimientos, sin crear un historial independiente para este tipo de información.

Conceptualmente:

```text
VEHÍCULO
        ↓
HISTORIAL VEHICULAR
        ↓
ABASTECIMIENTOS
Y RECARGAS
REGISTRADOS
```

Por lo tanto:

```text
HISTORIAL DE
ABASTECIMIENTOS
        ≠
HISTORIAL INDEPENDIENTE
DEL VEHÍCULO
```

Cada abastecimiento registrado deberá conservarse como un evento individual dentro de la evolución del vehículo.

Por ejemplo:

```text
VEHÍCULO

├── Abastecimiento A
├── Abastecimiento B
├── Abastecimiento C
└── Abastecimiento D
```

El registro de un nuevo abastecimiento no deberá reemplazar ni eliminar los abastecimientos registrados anteriormente.

Conceptualmente:

```text
ABASTECIMIENTO A
        ↓
ABASTECIMIENTO B
        ↓
ABASTECIMIENTO C
        ↓
ABASTECIMIENTO D
```

representa una acumulación progresiva de eventos registrados y no la sustitución del evento anterior por el más reciente.

Cada abastecimiento deberá conservar la información registrada que corresponda al evento, de acuerdo con los datos disponibles.

Esta información podrá incluir, entre otros datos aplicables:

- Fecha del abastecimiento.
- Kilometraje asociado.
- Cantidad abastecida.
- Unidad de medida.
- Valor pagado.
- Precio unitario registrado o calculable.
- Condición de abastecimiento completo o parcial, cuando aplique.
- Lugar o establecimiento, cuando haya sido registrado.
- Observaciones.
- Soportes o evidencias, cuando existan.
- Información adicional que posteriormente se determine aplicable.

La ausencia de alguno de estos datos no deberá impedir la conservación del abastecimiento cuando exista información suficiente para registrar el evento.

Por lo tanto:

```text
REGISTRO PARCIAL
        ≠
REGISTRO INEXISTENTE
```

Un abastecimiento podrá formar parte del historial aun cuando no contenga toda la información que podría registrarse para este tipo de evento.

Vehículos Services deberá conservar la diferencia entre la fecha en la cual ocurrió el abastecimiento y la fecha en la cual la información fue incorporada a la plataforma.

Por ejemplo:

```text
ABASTECIMIENTO REALIZADO
10 DE ENERO

        ↓

REGISTRADO EN
VEHÍCULOS SERVICES
15 DE ENERO
```

En este caso:

```text
FECHA DEL ABASTECIMIENTO
        ≠
FECHA DE REGISTRO
EN LA PLATAFORMA
```

Esta diferenciación permitirá que un abastecimiento incorporado posteriormente pueda ubicarse dentro del período histórico al cual realmente corresponde cuando dicha información sea conocida.

Por ejemplo:

```text
ENERO

Tanqueo 1
Tanqueo 2
Tanqueo 3

        ↓

EN FEBRERO
EL PROPIETARIO REGISTRA
UN TANQUEO QUE HABÍA
REALIZADO EN ENERO

        ↓

EL EVENTO CORRESPONDE
HISTÓRICAMENTE A ENERO
```

La incorporación posterior del evento no deberá provocar que el abastecimiento sea considerado como ocurrido en febrero únicamente porque fue registrado durante ese mes.

Por lo tanto:

```text
ORDEN DE INCORPORACIÓN
        ≠
ORDEN CRONOLÓGICO
DE LOS EVENTOS
```

Cuando un abastecimiento incorporado posteriormente afecte métricas correspondientes a un período anterior, Vehículos Services podrá recalcular los resultados derivados de dicho período utilizando la nueva información disponible.

Por ejemplo:

```text
ENERO
5 abastecimientos registrados
        ↓
MÉTRICAS CALCULADAS

        ↓

POSTERIORMENTE
SE INCORPORA OTRO
ABASTECIMIENTO DE ENERO

        ↓

ENERO
6 abastecimientos registrados
        ↓
MÉTRICAS RECALCULADAS
```

Este recálculo deberá afectar los resultados derivados cuando corresponda, pero no deberá modificar los datos originales de los demás abastecimientos utilizados para obtenerlos.

Conceptualmente:

```text
NUEVA INFORMACIÓN HISTÓRICA
        ↓
ACTUALIZACIÓN DE
RESULTADOS CALCULADOS
        ≠
ALTERACIÓN DE
REGISTROS ORIGINALES
```

Vehículos Services deberá permitir la corrección controlada de información correspondiente a un abastecimiento cuando un dato haya sido registrado incorrectamente.

Por ejemplo:

```text
VALOR REGISTRADO:
$120.000

        ↓

SE IDENTIFICA ERROR

        ↓

VALOR CORRECTO:
$102.000
```

La corrección deberá aplicar los principios generales de modificación, conservación y trazabilidad establecidos para el Historial Vehicular.

No deberá realizarse mediante una alteración silenciosa que impida conocer que existió una modificación relevante.

Por lo tanto:

```text
CORRECCIÓN
        ≠
SOBRESCRITURA SILENCIOSA
SIN TRAZABILIDAD
```

Vehículos Services deberá conservar información suficiente para determinar, cuando corresponda, que un registro fue modificado y aplicar las reglas generales de auditoría definidas para la plataforma.

Este punto no deberá crear reglas de auditoría diferentes exclusivamente para los abastecimientos.

El kilometraje asociado a un abastecimiento deberá conservarse como parte de la información histórica del evento.

Por ejemplo:

```text
ABASTECIMIENTO
15/09/2026

Kilometraje:
64.500 km
```

Esta lectura deberá relacionarse con el sistema general de kilometraje establecido en `63.9 KILOMETRAJE`.

La posterior existencia de un kilometraje actual superior no deberá modificar la lectura histórica registrada para el abastecimiento.

Por ejemplo:

```text
ABASTECIMIENTO
64.500 km

        ↓

TIEMPO DESPUÉS

KM ACTUAL:
66.200 km
```

deberá conservar:

```text
KM DEL ABASTECIMIENTO:
64.500 km
```

Por lo tanto:

```text
KILOMETRAJE DEL EVENTO
        ≠
KILOMETRAJE ACTUAL
DEL VEHÍCULO
```

La evolución del kilometraje deberá mantenerse conforme a las reglas establecidas en `63.9`, sin que este punto cree un tratamiento paralelo para las lecturas provenientes de abastecimientos.

La ausencia de determinados abastecimientos dentro del historial no deberá interpretarse como evidencia de que dichos abastecimientos no ocurrieron.

Por ejemplo:

```text
REGISTRO A
        ↓
¿?
        ↓
REGISTRO C
```

Vehículos Services conoce los eventos A y C, pero no deberá concluir automáticamente que no existieron otros abastecimientos entre ambos.

Por lo tanto:

```text
SIN REGISTRO
        ≠
SIN EVENTO REAL
```

De igual manera, Vehículos Services no deberá crear retrospectivamente abastecimientos inexistentes en la plataforma únicamente para completar aparentes vacíos entre registros.

Conceptualmente:

```text
VACÍO DE INFORMACIÓN
        ↓
SE CONSERVA COMO
INFORMACIÓN NO DISPONIBLE

        ≠

CREAR UN EVENTO
QUE NO FUE REGISTRADO
```

La incorporación de información histórica deberá respetar el principio general de no inventar datos desconocidos.

Cuando un abastecimiento sea registrado con información parcial y posteriormente el propietario disponga de datos adicionales, estos podrán incorporarse conforme a las reglas de modificación y trazabilidad correspondientes.

Por ejemplo:

```text
REGISTRO INICIAL

Fecha
Kilometraje
Valor pagado

        ↓

POSTERIORMENTE
SE INCORPORA

Cantidad abastecida
```

La ampliación de información deberá complementar el evento existente cuando corresponda y no crear artificialmente un segundo abastecimiento para representar el mismo evento.

Por lo tanto:

```text
MISMO ABASTECIMIENTO
+
INFORMACIÓN ADICIONAL
        ↓
COMPLEMENTAR
EL EVENTO EXISTENTE

        ≠

CREAR AUTOMÁTICAMENTE
UN NUEVO ABASTECIMIENTO
```

Cuando existan varios abastecimientos reales, cada uno deberá mantenerse como un evento independiente.

Vehículos Services deberá evitar consolidar diferentes abastecimientos reales en un único evento histórico solamente porque hayan ocurrido durante el mismo día o período.

Por ejemplo:

```text
MISMO DÍA

Abastecimiento A
$50.000

Abastecimiento B
$80.000
```

deberán poder mantenerse como:

```text
DOS EVENTOS
DIFERENTES
```

cuando correspondan efectivamente a dos abastecimientos distintos.

Por lo tanto:

```text
MISMA FECHA
        ≠
MISMO EVENTO
```

Los cambios de propietario no deberán reiniciar ni eliminar el historial de abastecimientos asociado al vehículo.

Conceptualmente:

```text
PROPIETARIO A
        ↓
ABASTECIMIENTOS
REGISTRADOS
        ↓
CAMBIO DE PROPIETARIO
        ↓
PROPIETARIO B
        ↓
NUEVOS ABASTECIMIENTOS
REGISTRADOS
```

El vehículo deberá mantener una evolución histórica continua.

Sin embargo:

```text
CONSERVACIÓN
DEL HISTORIAL
        ≠
ACCESO AUTOMÁTICO
A TODA LA INFORMACIÓN
```

La visibilidad de información correspondiente a períodos de propiedad anteriores deberá continuar sujeta a las reglas generales de acceso, privacidad y períodos de propiedad ya establecidas en `63.4 RELACIÓN PROPIETARIO ↔ VEHÍCULO` y `63.6 HISTORIAL VEHICULAR`.

Este punto no deberá redefinir dichas reglas.

De igual manera, la existencia de una relación con un prestador de servicios no deberá modificar por sí sola la propiedad, conservación o visibilidad de los registros de abastecimiento.

Cualquier acceso de un prestador deberá depender de las reglas generales de relación, permisos y visibilidad definidas para la plataforma.

Los registros de abastecimiento deberán poder utilizarse como fuente para los cálculos definidos en los puntos anteriores:

```text
ABASTECIMIENTOS
HISTÓRICOS REGISTRADOS
        ↓
63.10.3
CONSUMO Y RENDIMIENTO

        ↓
63.10.4
COSTOS Y GASTOS

        ↓
63.10.5
MÉTRICAS Y ANÁLISIS
POR PERÍODOS
```

La existencia de nuevos registros, correcciones o información complementaria podrá provocar que los resultados calculados cambien.

Por lo tanto:

```text
DATOS HISTÓRICOS
DISPONIBLES
        ↓
RESULTADOS CALCULADOS

NUEVA INFORMACIÓN
O CORRECCIÓN
        ↓
NUEVO CÁLCULO
        ↓
RESULTADO ACTUALIZADO
```

Esto no deberá interpretarse como una modificación arbitraria del historial, sino como la actualización de información derivada a partir del conjunto vigente de datos disponibles.

Como principio general:

```text
ABASTECIMIENTO REALIZADO
        ↓
REGISTRO DEL EVENTO
        ↓
CONSERVACIÓN
        ↓
POSIBLE COMPLEMENTACIÓN
O CORRECCIÓN CONTROLADA
        ↓
PERMANENCIA DENTRO DEL
HISTORIAL VEHICULAR
        ↓
UTILIZACIÓN EN
CÁLCULOS Y MÉTRICAS
        ↓
EVOLUCIÓN HISTÓRICA
DEL VEHÍCULO
```

Vehículos Services deberá conservar los abastecimientos y recargas registrados como parte de la evolución histórica del vehículo, manteniendo la información original disponible, la relación temporal y de kilometraje correspondiente, y la trazabilidad de las modificaciones relevantes, sin inventar eventos faltantes ni confundir la ausencia de registros con la ausencia de abastecimientos reales.

---
## 63.11 REGLAS DE MANTENIMIENTO
### 63.11.1 Definición y aplicabilidad de una regla de mantenimiento

Los criterios de seguimiento definidos previamente permiten establecer si una actividad deberá controlarse por kilometraje, por tiempo, por la combinación de ambos o mediante otros criterios que posteriormente puedan ser incorporados.

Una regla de mantenimiento deberá complementar dicho criterio estableciendo las condiciones concretas necesarias para realizar el seguimiento de una actividad determinada.

Por lo tanto:

```text
CRITERIO DE SEGUIMIENTO
        ↓
DEFINE MEDIANTE QUÉ
CONDICIÓN SE REALIZA
EL SEGUIMIENTO

        +

REGLA DE MANTENIMIENTO
        ↓
DEFINE LAS CONDICIONES
CONCRETAS QUE DEBERÁN
SER EVALUADAS
```

Por ejemplo:

```text
ACTIVIDAD:
Cambio de aceite

CRITERIO DE SEGUIMIENTO:
Kilometraje

REGLA:
Cada 5.000 km
```

En este caso, el criterio establece que la actividad deberá controlarse utilizando el kilometraje, mientras que la regla establece el intervalo concreto utilizado para realizar dicho seguimiento.

De igual manera:

```text
ACTIVIDAD:
Cambio de aceite

CRITERIO DE SEGUIMIENTO:
Kilometraje y tiempo

REGLA:
Cada 5.000 km
o
cada 3 meses
```

Los valores utilizados en estos ejemplos son únicamente ilustrativos y no deberán interpretarse como reglas técnicas universales aplicables a todos los vehículos.

Una regla deberá encontrarse relacionada con la actividad sobre la cual se realiza el seguimiento.

Conceptualmente:

```text
ACTIVIDAD
        ↓
REQUIERE SEGUIMIENTO
        ↓
CRITERIO DE SEGUIMIENTO
        ↓
REGLA APLICABLE
        ↓
CONDICIONES QUE
PUEDEN SER EVALUADAS
```

La existencia de una actividad registrada dentro del historial no deberá implicar automáticamente que exista una regla de mantenimiento asociada.

Únicamente aquellas actividades para las cuales corresponda realizar un seguimiento deberán requerir las condiciones necesarias para determinar su próxima intervención.

Por lo tanto:

```text
ACTIVIDAD REGISTRADA
        ↓
¿REQUIERE SEGUIMIENTO?
        │
    ┌───┴───┐
    ↓       ↓
   SÍ       NO
    │       │
    ↓       ↓
PUEDE      PERMANECE
TENER      COMO EVENTO
REGLA      HISTÓRICO
APLICABLE  SIN PRÓXIMO
           OBJETIVO
           AUTOMÁTICO
```

Cuando varias actividades formen parte de un mismo mantenimiento, la aplicabilidad de una regla deberá evaluarse para cada actividad que requiera seguimiento.

La existencia de un mismo mantenimiento no deberá provocar que todas las actividades que lo conforman compartan automáticamente una misma regla.

Conceptualmente:

```text
MANTENIMIENTO
        │
        ├── ACTIVIDAD A
        │       ↓
        │   REGLA A
        │
        ├── ACTIVIDAD B
        │       ↓
        │   REGLA B
        │
        └── ACTIVIDAD C
                ↓
            SIN REGLA
            CUANDO NO
            REQUIERA
            SEGUIMIENTO
```

Una misma actividad tampoco deberá asumir necesariamente una regla idéntica para todos los vehículos.

La regla aplicable podrá variar cuando existan condiciones que justifiquen un comportamiento diferente de seguimiento.

Por lo tanto:

```text
MISMA ACTIVIDAD
        │
        ├── VEHÍCULO A
        │       ↓
        │   REGLA APLICABLE
        │
        └── VEHÍCULO B
                ↓
            REGLA APLICABLE
            QUE PUEDE SER
            DIFERENTE
```

Vehículos Services no deberá establecer como regla técnica universal un intervalo únicamente porque corresponda al mismo tipo de actividad.

La aplicabilidad deberá depender de la información y de las condiciones disponibles para determinar la regla correspondiente.

Una regla podrá contemplar, según el criterio de seguimiento aplicable, condiciones relacionadas con:

- Un intervalo de kilometraje.
- Un intervalo de tiempo.
- La combinación de un intervalo de kilometraje y un intervalo de tiempo.
- Otras condiciones que posteriormente puedan ser definidas.

Por ejemplo:

```text
REGLA POR KILOMETRAJE
Cada 10.000 km

REGLA POR TIEMPO
Cada 12 meses

REGLA COMBINADA
Cada 10.000 km
o
cada 12 meses
```

La existencia de una regla no deberá representar por sí misma que una intervención haya sido realizada.

Por lo tanto:

```text
REGLA DE MANTENIMIENTO
        ≠
INTERVENCIÓN REALIZADA
```

La regla deberá establecer las condiciones utilizadas para realizar el seguimiento, mientras que la intervención realizada deberá permanecer registrada como un evento del Historial Vehicular.

De igual manera, la existencia de una regla no deberá representar por sí sola un diagnóstico sobre el estado mecánico real del vehículo o de alguno de sus componentes.

Conceptualmente:

```text
REGLA
        ↓
PERMITE REALIZAR
SEGUIMIENTO

        ≠

DIAGNÓSTICO
DEL ESTADO REAL
DEL COMPONENTE
```

La evaluación de una regla deberá utilizar la información disponible y válida correspondiente al vehículo y a la actividad sobre la cual se realiza el seguimiento.

Cuando la información necesaria para evaluar una determinada condición no se encuentre disponible, Vehículos Services no deberá inventar valores ni asumir que la condición se encuentra cumplida, vigente o vencida.

Por lo tanto:

```text
INFORMACIÓN
INSUFICIENTE
        ↓
NO INVENTAR
VALORES
        ↓
NO DETERMINAR
UNA CONDICIÓN
QUE LOS DATOS
NO PERMITAN
SUSTENTAR
```

La regla deberá mantenerse conceptualmente separada de los resultados obtenidos al evaluarla.

Por lo tanto:

```text
REGLA
        ↓
SE EVALÚA
        ↓
RESULTADO
```

La regla define las condiciones que deben evaluarse.

El resultado deberá representar la situación obtenida después de aplicar dichas condiciones utilizando la información disponible del vehículo.

Los estados, alertas y recomendaciones que posteriormente puedan generarse deberán corresponder a resultados derivados de esta evaluación y no deberán confundirse con la propia regla.

Conceptualmente:

```text
ACTIVIDAD
        ↓
CRITERIO DE SEGUIMIENTO
        ↓
REGLA
        ↓
INFORMACIÓN DEL VEHÍCULO
        ↓
EVALUACIÓN
        ↓
RESULTADO
        ↓
ESTADO / ALERTA /
RECOMENDACIÓN
CUANDO CORRESPONDA
```

Este punto deberá limitarse a establecer la definición funcional y aplicabilidad de una regla de mantenimiento.

Las condiciones específicas de los intervalos por kilometraje, intervalos por tiempo, combinación de ambos criterios, determinación de próximos objetivos, cumplimiento de objetivos, renovación del seguimiento, tolerancias y modificación de reglas deberán desarrollarse en los puntos posteriores de `63.11 REGLAS DE MANTENIMIENTO`.

Como principio general:

```text
ACTIVIDAD QUE
REQUIERE SEGUIMIENTO
        ↓
CRITERIO
        ↓
REGLA APLICABLE
        ↓
CONDICIONES CONCRETAS
        ↓
EVALUACIÓN
        ↓
RESULTADO DEL
SEGUIMIENTO
```

Vehículos Services deberá utilizar las reglas de mantenimiento para establecer las condiciones concretas mediante las cuales se evalúa el seguimiento de una actividad, sin confundir la regla con el criterio de seguimiento, la intervención realizada, el historial del vehículo ni los resultados derivados de su evaluación.

---
### 63.11.2 Reglas e intervalos por kilometraje

Cuando una actividad requiera seguimiento mediante kilometraje, la regla de mantenimiento deberá permitir establecer un intervalo de kilometraje que represente la distancia de referencia después de la cual corresponde realizar nuevamente el seguimiento de dicha actividad.

Conceptualmente:

```text
ACTIVIDAD
        ↓
CRITERIO DE SEGUIMIENTO:
KILOMETRAJE
        ↓
REGLA
        ↓
INTERVALO DE
KILOMETRAJE
```

Por ejemplo:

```text
ACTIVIDAD:
Cambio de aceite

CRITERIO:
Kilometraje

INTERVALO:
5.000 km
```

En este escenario, los `5.000 km` representan el intervalo de seguimiento aplicable a la actividad.

El intervalo no deberá confundirse con el kilometraje en el cual fue realizada una intervención ni con el kilometraje objetivo de la siguiente intervención.

Por lo tanto:

```text
KILOMETRAJE DE
LA INTERVENCIÓN
        ≠
INTERVALO DE
KILOMETRAJE
        ≠
PRÓXIMO KILOMETRAJE
OBJETIVO
```

Por ejemplo:

```text
INTERVENCIÓN REALIZADA:
70.000 km

INTERVALO:
5.000 km

PRÓXIMO OBJETIVO:
75.000 km
```

En este caso:

```text
70.000 km
        ↓
KILOMETRAJE DE REFERENCIA

5.000 km
        ↓
INTERVALO

75.000 km
        ↓
PRÓXIMO OBJETIVO
```

Cuando exista una intervención válida que pueda utilizarse como referencia y una regla con un intervalo de kilometraje aplicable, el próximo kilometraje objetivo podrá determinarse conceptualmente mediante:

```text
PRÓXIMO KILOMETRAJE OBJETIVO
=
KILOMETRAJE DE REFERENCIA
+
INTERVALO DE KILOMETRAJE
```

Ejemplo:

```text
70.000 km
+
5.000 km
=
75.000 km
```

La utilización de un kilometraje como referencia deberá depender de que corresponda efectivamente a la intervención o situación desde la cual debe comenzar el ciclo de seguimiento.

Vehículos Services no deberá utilizar automáticamente cualquier lectura de kilometraje del vehículo como punto de inicio de una regla de mantenimiento.

Por ejemplo:

```text
CAMBIO DE ACEITE REALIZADO:
70.000 km

LECTURA POSTERIOR
DEL VEHÍCULO:
72.000 km

INTERVALO:
5.000 km
```

La lectura posterior de `72.000 km` representa la evolución del kilometraje del vehículo, pero no deberá sustituir automáticamente el kilometraje de referencia de la intervención.

Por lo tanto:

```text
KILOMETRAJE ACTUAL
        ≠
KILOMETRAJE DE REFERENCIA
DE LA INTERVENCIÓN
```

En el ejemplo anterior, mientras no exista una nueva intervención válida que establezca un nuevo punto de referencia:

```text
REFERENCIA:
70.000 km

INTERVALO:
5.000 km

OBJETIVO:
75.000 km
```

y el kilometraje actual podrá utilizarse para evaluar el avance hacia dicho objetivo.

Conceptualmente:

```text
INTERVENCIÓN
70.000 km
        ↓
INTERVALO
5.000 km
        ↓
OBJETIVO
75.000 km
        ↑
        │
KILOMETRAJE ACTUAL
EVOLUCIONA
```

La regla deberá mantenerse separada de la evolución del kilometraje actual.

Una actualización del kilometraje actual no deberá modificar por sí misma:

- El intervalo definido.
- El kilometraje de referencia de la intervención.
- El kilometraje objetivo previamente determinado.

Por ejemplo:

```text
REFERENCIA:
70.000 km

INTERVALO:
5.000 km

OBJETIVO:
75.000 km
```

Si el kilometraje actual evoluciona:

```text
71.000 km
        ↓
72.500 km
        ↓
74.000 km
        ↓
75.000 km
```

el objetivo continuará siendo `75.000 km` mientras no ocurra una situación que, de acuerdo con las reglas correspondientes, genere un nuevo ciclo de seguimiento.

La diferencia entre el kilometraje actual y los puntos de referencia podrá utilizarse para determinar el avance de la actividad.

Los conceptos de kilómetros transcurridos y kilómetros restantes deberán continuar rigiéndose por las definiciones ya establecidas en los componentes correspondientes y no deberán redefinirse dentro de este punto.

Conceptualmente:

```text
REFERENCIA
        ↓
INTERVALO
        ↓
OBJETIVO

        +

KILOMETRAJE ACTUAL

        ↓

SEGUIMIENTO DEL
AVANCE HACIA
EL OBJETIVO
```

Una regla por kilometraje solamente deberá poder producir un próximo objetivo cuando exista información suficiente para realizar el cálculo.

Por ejemplo, si se conoce:

```text
INTERVALO:
5.000 km
```

pero no se conoce un kilometraje válido de referencia:

```text
KILOMETRAJE DE REFERENCIA:
DESCONOCIDO
```

Vehículos Services no deberá inventar un kilometraje inicial para determinar artificialmente un próximo objetivo.

Por lo tanto:

```text
INTERVALO CONOCIDO
+
REFERENCIA DESCONOCIDA
        ↓
NO EXISTE INFORMACIÓN
SUFICIENTE PARA CALCULAR
UN PRÓXIMO OBJETIVO
```

De igual manera, la existencia de un kilometraje de intervención sin un intervalo aplicable no deberá permitir inferir automáticamente cuándo corresponde la siguiente intervención.

```text
REFERENCIA CONOCIDA
+
INTERVALO DESCONOCIDO
        ↓
NO EXISTE INFORMACIÓN
SUFICIENTE PARA CALCULAR
UN PRÓXIMO OBJETIVO
```

Vehículos Services no deberá inventar intervalos de mantenimiento a partir de la diferencia observada entre intervenciones históricas.

Por ejemplo:

```text
INTERVENCIÓN A:
50.000 km

INTERVENCIÓN B:
55.000 km
```

La existencia de una diferencia de `5.000 km` entre ambos registros no deberá significar automáticamente que la regla de mantenimiento sea:

```text
CADA 5.000 km
```

Por lo tanto:

```text
DISTANCIA HISTÓRICA
ENTRE INTERVENCIONES
        ≠
INTERVALO DE MANTENIMIENTO
AUTOMÁTICAMENTE
```

La información histórica podrá utilizarse posteriormente como referencia o fuente para otras funcionalidades cuando corresponda, pero no deberá transformarse automáticamente en una regla sin una condición que permita establecerla como tal.

Cuando una nueva intervención correspondiente a la actividad sea realizada y pueda utilizarse válidamente como una nueva referencia, podrá generarse posteriormente un nuevo objetivo de kilometraje conforme al intervalo aplicable.

La nueva referencia deberá corresponder a la información válida de la intervención efectivamente realizada y no deberá sustituirse automáticamente por el objetivo anterior que había sido calculado.

El tratamiento funcional de cuándo una intervención cierra el seguimiento anterior, establece una nueva referencia y genera un nuevo ciclo deberá regirse por lo definido en `63.11.6 Cumplimiento y renovación del ciclo de seguimiento`.

Una regla por kilometraje deberá utilizar únicamente lecturas de kilometraje que puedan ser utilizadas válidamente según las reglas establecidas en `63.9 KILOMETRAJE`.

La existencia de una lectura inconsistente, pendiente de validación o que corresponda a un momento histórico diferente no deberá provocar automáticamente la modificación del seguimiento actual.

Conceptualmente:

```text
LECTURA DE
KILOMETRAJE
        ↓
REGLAS DE
63.9 KILOMETRAJE
        ↓
LECTURA UTILIZABLE
CUANDO CORRESPONDA
        ↓
EVALUACIÓN DE
LA REGLA
```

De esta manera, `63.11` no deberá asumir las responsabilidades correspondientes a la validación, procedencia, consistencia o conservación histórica de las lecturas de kilometraje.

La definición de cuándo una actividad deberá considerarse próxima a su objetivo o cuándo deberá considerarse vencida tampoco deberá establecerse únicamente por la existencia del intervalo.

Por ejemplo:

```text
INTERVALO:
5.000 km

OBJETIVO:
75.000 km
```

no determina por sí mismo desde qué kilometraje deberá mostrarse:

```text
PRÓXIMO A VENCER
```

La definición de márgenes o tolerancias deberá desarrollarse específicamente en `63.11.7 Tolerancias y condiciones de proximidad`.

Como principio general:

```text
ACTIVIDAD
        ↓
SEGUIMIENTO POR
KILOMETRAJE
        ↓
KILOMETRAJE
DE REFERENCIA
        +
INTERVALO
        ↓
PRÓXIMO OBJETIVO
        ↓
KILOMETRAJE ACTUAL
        ↓
EVALUACIÓN DEL
SEGUIMIENTO
```

Vehículos Services deberá utilizar los intervalos por kilometraje para establecer objetivos de seguimiento a partir de referencias válidas de una actividad, manteniendo diferenciados el kilometraje de la intervención, el intervalo definido, el kilometraje actual y el próximo objetivo calculado, sin inventar referencias o intervalos cuando la información disponible sea insuficiente.


---

### 63.11.3 Reglas e intervalos por tiempo

Cuando una actividad requiera seguimiento mediante tiempo, la regla de mantenimiento deberá permitir establecer un intervalo temporal que represente el período de referencia después del cual corresponde realizar nuevamente el seguimiento de dicha actividad.

Conceptualmente:

```text
ACTIVIDAD
        ↓
CRITERIO DE SEGUIMIENTO:
TIEMPO
        ↓
REGLA
        ↓
INTERVALO
DE TIEMPO
```

Por ejemplo:

```text
ACTIVIDAD:
Servicio específico

CRITERIO:
Tiempo

INTERVALO:
6 meses
```

En este escenario, los `6 meses` representan el intervalo temporal utilizado para realizar el seguimiento de la actividad.

El intervalo de tiempo no deberá confundirse con la fecha en la cual fue realizada la intervención ni con la próxima fecha objetivo.

Por lo tanto:

```text
FECHA DE LA
INTERVENCIÓN
        ≠
INTERVALO
DE TIEMPO
        ≠
PRÓXIMA FECHA
OBJETIVO
```

Por ejemplo:

```text
INTERVENCIÓN REALIZADA:
15/08/2026

INTERVALO:
3 meses

PRÓXIMO OBJETIVO:
15/11/2026
```

En este caso:

```text
15/08/2026
        ↓
FECHA DE REFERENCIA

3 meses
        ↓
INTERVALO

15/11/2026
        ↓
PRÓXIMA FECHA
OBJETIVO
```

Cuando exista una intervención válida que pueda utilizarse como referencia y una regla con un intervalo temporal aplicable, la próxima fecha objetivo podrá determinarse conceptualmente mediante:

```text
PRÓXIMA FECHA OBJETIVO
=
FECHA DE REFERENCIA
+
INTERVALO DE TIEMPO
```

Ejemplo:

```text
15/08/2026
+
3 meses
=
15/11/2026
```

La fecha utilizada como referencia deberá corresponder al momento desde el cual deba comenzar el ciclo de seguimiento de la actividad.

Vehículos Services no deberá utilizar automáticamente la fecha de creación del registro en la plataforma como fecha de referencia del mantenimiento.

Por ejemplo:

```text
INTERVENCIÓN REALIZADA:
15/08/2026

REGISTRO INCORPORADO
A LA PLATAFORMA:
20/08/2026

INTERVALO:
3 meses
```

Cuando la intervención realmente ocurrió el `15/08/2026` y esa fecha sea conocida y válida, el seguimiento deberá utilizar dicha fecha como referencia.

Por lo tanto:

```text
FECHA DE LA INTERVENCIÓN
        ≠
FECHA DE REGISTRO
EN LA PLATAFORMA
```

En este ejemplo:

```text
REFERENCIA:
15/08/2026

INTERVALO:
3 meses

OBJETIVO:
15/11/2026
```

y no:

```text
REFERENCIA:
20/08/2026

OBJETIVO:
20/11/2026
```

únicamente porque el registro haya sido incorporado a Vehículos Services cinco días después.

Esta separación deberá mantenerse alineada con las reglas generales de temporalidad y trazabilidad del Historial Vehicular.

De igual manera, la fecha actual no deberá sustituir automáticamente la fecha de referencia.

Conceptualmente:

```text
FECHA DE REFERENCIA
        ↓
ESTABLECE EL INICIO
DEL CICLO

FECHA ACTUAL
        ↓
PERMITE EVALUAR
EL AVANCE DEL CICLO
```

Por lo tanto:

```text
FECHA ACTUAL
        ≠
FECHA DE REFERENCIA
```

La evolución del tiempo no deberá modificar por sí misma:

- La fecha de referencia.
- El intervalo temporal definido.
- La fecha objetivo previamente determinada.

Por ejemplo:

```text
REFERENCIA:
15/08/2026

INTERVALO:
3 meses

OBJETIVO:
15/11/2026
```

Con el paso del tiempo:

```text
01/09/2026
        ↓
01/10/2026
        ↓
01/11/2026
        ↓
15/11/2026
```

el objetivo continuará siendo `15/11/2026` mientras no ocurra una situación que genere un nuevo ciclo de seguimiento o una modificación válida de la regla.

Conceptualmente:

```text
FECHA DE REFERENCIA
        ↓
INTERVALO
        ↓
FECHA OBJETIVO

        +

FECHA ACTUAL

        ↓

SEGUIMIENTO DEL
AVANCE HACIA
EL OBJETIVO
```

Una regla por tiempo solamente deberá poder producir una próxima fecha objetivo cuando exista información suficiente para realizar el cálculo.

Por ejemplo:

```text
INTERVALO:
6 meses

FECHA DE REFERENCIA:
DESCONOCIDA
```

En este escenario, Vehículos Services no deberá inventar una fecha inicial para generar artificialmente una próxima fecha objetivo.

Por lo tanto:

```text
INTERVALO CONOCIDO
+
REFERENCIA DESCONOCIDA
        ↓
NO EXISTE INFORMACIÓN
SUFICIENTE PARA CALCULAR
UNA PRÓXIMA FECHA OBJETIVO
```

De igual manera:

```text
FECHA DE REFERENCIA
CONOCIDA
+
INTERVALO
DESCONOCIDO
        ↓
NO EXISTE INFORMACIÓN
SUFICIENTE PARA CALCULAR
UNA PRÓXIMA FECHA OBJETIVO
```

Vehículos Services tampoco deberá inferir automáticamente un intervalo temporal a partir de la separación observada entre intervenciones históricas.

Por ejemplo:

```text
INTERVENCIÓN A:
15/01/2026

INTERVENCIÓN B:
15/04/2026
```

La existencia de aproximadamente tres meses entre ambas intervenciones no deberá significar automáticamente que la regla aplicable sea:

```text
CADA 3 MESES
```

Por lo tanto:

```text
TIEMPO HISTÓRICO
ENTRE INTERVENCIONES
        ≠
INTERVALO TEMPORAL
AUTOMÁTICAMENTE
```

La información histórica podrá ser utilizada posteriormente por otras funcionalidades cuando corresponda, pero la recurrencia observada no deberá convertirse por sí sola en una regla de mantenimiento.

Cuando una nueva intervención correspondiente a la actividad sea realizada y pueda utilizarse válidamente como una nueva referencia temporal, podrá generarse posteriormente una nueva fecha objetivo conforme al intervalo aplicable.

La nueva referencia temporal deberá corresponder a la fecha válida de la intervención efectivamente realizada y no deberá sustituirse automáticamente por la fecha objetivo anterior.

El tratamiento funcional de cuándo una intervención cierra el seguimiento anterior, establece una nueva referencia temporal y genera un nuevo ciclo deberá regirse por lo definido en `63.11.6 Cumplimiento y renovación del ciclo de seguimiento`.

La existencia de registros incorporados de forma posterior también deberá respetar su contexto temporal.

Por ejemplo:

```text
HOY:
20/09/2026

SE INCORPORA
UN MANTENIMIENTO HISTÓRICO:

Fecha real:
15/03/2026
```

La incorporación del registro el `20/09/2026` no deberá transformar su fecha de referencia en esa fecha de incorporación.

Cuando dicho mantenimiento corresponda válidamente a la actividad utilizada como referencia, deberá conservarse:

```text
FECHA DEL EVENTO:
15/03/2026
```

como referencia temporal correspondiente.

Vehículos Services deberá evitar utilizar fechas administrativas o técnicas del sistema como sustituto de la fecha real del evento cuando esta sea conocida.

La regla temporal también deberá poder conservar su funcionamiento a través de cambios de año.

Por ejemplo:

```text
REFERENCIA:
15/11/2026

INTERVALO:
3 meses

OBJETIVO:
15/02/2027
```

El cambio de mes o de año no deberá reiniciar el seguimiento.

Conceptualmente:

```text
CICLO TEMPORAL
        ↓
PUEDE ATRAVESAR
MESES Y AÑOS
        ↓
SIN REINICIARSE
POR EL CAMBIO
DE PERÍODO
```

Los detalles técnicos necesarios para resolver particularidades de calendario, representación de fechas y cálculos temporales deberán definirse posteriormente durante el diseño funcional y técnico correspondiente.

Cuando una actividad tenga exclusivamente seguimiento por tiempo, la evolución del kilometraje del vehículo no deberá modificar por sí misma la fecha objetivo.

Conceptualmente:

```text
CRITERIO:
TIEMPO

        ↓

REFERENCIA TEMPORAL
+
INTERVALO TEMPORAL
        ↓
FECHA OBJETIVO
```

Por lo tanto, una variación del kilometraje:

```text
70.000 km
        ↓
75.000 km
        ↓
80.000 km
```

no deberá alterar automáticamente una fecha objetivo determinada exclusivamente por tiempo.

Cuando una actividad combine kilometraje y tiempo, cada condición deberá mantener su propia referencia y objetivo.

El comportamiento conjunto de ambas condiciones deberá regirse por lo definido en `63.11.4 Combinación de kilometraje y tiempo`.

La existencia de una fecha objetivo tampoco deberá determinar por sí misma desde qué momento una actividad deberá considerarse próxima a dicha fecha.

Por ejemplo:

```text
OBJETIVO:
15/11/2026
```

no deberá determinar automáticamente si la actividad debe considerarse próxima:

```text
7 días antes
15 días antes
30 días antes
```

Los márgenes y condiciones de proximidad deberán regirse por lo definido en `63.11.7 Tolerancias y condiciones de proximidad`.

Como principio general:

```text
ACTIVIDAD
        ↓
SEGUIMIENTO POR
TIEMPO
        ↓
FECHA DE
REFERENCIA
        +
INTERVALO
TEMPORAL
        ↓
PRÓXIMA FECHA
OBJETIVO
        ↓
FECHA ACTUAL
        ↓
EVALUACIÓN DEL
SEGUIMIENTO
```

Vehículos Services deberá utilizar los intervalos temporales para establecer objetivos de seguimiento a partir de referencias válidas de una actividad, manteniendo diferenciados la fecha real de la intervención, la fecha de registro en la plataforma, el intervalo temporal, la fecha actual y la próxima fecha objetivo, sin inventar referencias o intervalos cuando la información disponible sea insuficiente.


---
### 63.11.4 Combinación de kilometraje y tiempo

Cuando una actividad requiera seguimiento mediante la combinación de kilometraje y tiempo, la regla de mantenimiento deberá permitir mantener simultáneamente una condición asociada al kilometraje y una condición asociada al tiempo.

Conceptualmente:

```text
ACTIVIDAD
        ↓
CRITERIO DE SEGUIMIENTO:
KILOMETRAJE Y TIEMPO
        ↓
REGLA
        │
        ├── INTERVALO
        │   DE KILOMETRAJE
        │
        └── INTERVALO
            DE TIEMPO
```

Por ejemplo:

```text
ACTIVIDAD:
Cambio de aceite

REGLA:

Cada 5.000 km
o
cada 3 meses
```

En este escenario deberán coexistir dos objetivos de seguimiento:

```text
INTERVENCIÓN:

70.000 km
15/08/2026

        ↓

REGLA:

5.000 km
o
3 meses

        ↓

OBJETIVO POR
KILOMETRAJE:
75.000 km

        +

OBJETIVO POR
TIEMPO:
15/11/2026
```

Ambos objetivos deberán mantenerse diferenciados.

Por lo tanto:

```text
OBJETIVO POR
KILOMETRAJE
        ≠
OBJETIVO POR
TIEMPO
```

aunque ambos pertenezcan al seguimiento de la misma actividad.

Las reglas específicas utilizadas para determinar cada objetivo deberán continuar rigiéndose por lo establecido en:

```text
63.11.2
REGLAS E INTERVALOS
POR KILOMETRAJE

        +

63.11.3
REGLAS E INTERVALOS
POR TIEMPO
```

Este punto no deberá redefinir dichos cálculos.

La combinación de ambas condiciones deberá permitir evaluar independientemente la evolución del kilometraje y la evolución del tiempo.

Conceptualmente:

```text
MISMA ACTIVIDAD
        │
        ├── CONDICIÓN
        │   POR KILOMETRAJE
        │       ↓
        │   EVOLUCIONA CON
        │   EL KM ACTUAL
        │
        └── CONDICIÓN
            POR TIEMPO
                ↓
            EVOLUCIONA CON
            EL TIEMPO
```

El avance de una condición no deberá modificar artificialmente el avance de la otra.

Por ejemplo:

```text
REFERENCIA:
70.000 km
15/08/2026

OBJETIVOS:
75.000 km
15/11/2026
```

Si posteriormente el vehículo se encuentra en:

```text
74.500 km
01/09/2026
```

la condición por kilometraje podrá encontrarse mucho más cerca de su objetivo que la condición temporal.

De igual manera, podría ocurrir:

```text
71.000 km
10/11/2026
```

En este escenario, la condición temporal podrá encontrarse mucho más cerca de su objetivo que la condición por kilometraje.

Por lo tanto:

```text
PROXIMIDAD POR
KILOMETRAJE
        ≠
PROXIMIDAD POR
TIEMPO
```

Las dos condiciones deberán evaluarse utilizando la información correspondiente a cada una.

Cuando una regla combinada establezca que la actividad debe realizarse al cumplirse cualquiera de las dos condiciones, Vehículos Services deberá considerar que la condición que se alcance primero puede determinar la necesidad de realizar la intervención.

Conceptualmente:

```text
REGLA:

5.000 km
O
3 meses

        ↓

SE EVALÚAN
AMBAS CONDICIONES

        ↓

LA PRIMERA
QUE CORRESPONDA
SEGÚN LA REGLA

        ↓

PUEDE DETERMINAR
LA NECESIDAD
DE INTERVENCIÓN
```

Por ejemplo:

```text
OBJETIVO KM:
75.000 km

OBJETIVO TIEMPO:
15/11/2026
```

Si el vehículo alcanza:

```text
75.000 km
20/10/2026
```

la condición de kilometraje habrá alcanzado su objetivo antes que la condición temporal.

Conceptualmente:

```text
75.000 km
ALCANZADO
        ↓
CONDICIÓN DE
KILOMETRAJE CUMPLIDA

MIENTRAS

15/11/2026
AÚN NO HA LLEGADO
```

En una regla definida bajo el principio de:

```text
KILOMETRAJE
O
TIEMPO
```

no deberá ser necesario esperar obligatoriamente a que ambas condiciones alcancen simultáneamente sus objetivos para considerar que corresponde realizar la intervención.

De igual manera, podría ocurrir el escenario contrario:

```text
FECHA OBJETIVO:
15/11/2026

KM OBJETIVO:
75.000 km

AL 15/11/2026:

KM ACTUAL:
72.300 km
```

En este caso:

```text
CONDICIÓN TEMPORAL
ALCANZADA

        +

CONDICIÓN DE
KILOMETRAJE
AÚN NO ALCANZADA
```

La condición temporal podrá determinar que corresponde realizar la intervención cuando la regla aplicable establezca el cumplimiento por cualquiera de las dos condiciones.

Por lo tanto:

```text
KILOMETRAJE
O
TIEMPO

        ≠

KILOMETRAJE
Y
TIEMPO
OBLIGATORIAMENTE
AL MISMO TIEMPO
```

Vehículos Services deberá conservar explícitamente la lógica mediante la cual se combinan las condiciones y no deberá asumir que toda regla que contenga kilometraje y tiempo utiliza necesariamente el mismo comportamiento.

Inicialmente, el caso contemplado para las reglas combinadas será aquel en el cual cualquiera de las condiciones pueda determinar que corresponde realizar la intervención.

Conceptualmente:

```text
CONDICIÓN A
ALCANZADA
        │
        ├──────────────┐
        ↓              │
PUEDE CORRESPONDER     │
REALIZAR LA            │
INTERVENCIÓN           │
                       │
CONDICIÓN B            │
ALCANZADA              │
        │              │
        └──────────────┘
```

Sin embargo, la estructura conceptual de las reglas no deberá impedir que posteriormente puedan existir otros comportamientos de combinación cuando una necesidad funcional o técnica válida así lo requiera.

Cualquier comportamiento diferente deberá encontrarse expresamente definido y no deberá inferirse automáticamente.

Por lo tanto:

```text
DOS CONDICIONES
CONFIGURADAS
        ≠
FORMA DE COMBINACIÓN
IMPLÍCITA
```

La regla deberá indicar cómo se relacionan las condiciones cuando corresponda.

Cuando solamente exista información suficiente para evaluar una de las condiciones, Vehículos Services deberá evitar inventar la información faltante de la otra.

Por ejemplo:

```text
REGLA:
5.000 km
o
3 meses

FECHA DE REFERENCIA:
15/08/2026

KILOMETRAJE DE REFERENCIA:
DESCONOCIDO
```

En este escenario podrá existir información suficiente para determinar:

```text
OBJETIVO TEMPORAL:
15/11/2026
```

pero no para determinar:

```text
OBJETIVO POR
KILOMETRAJE
```

Por lo tanto:

```text
UNA CONDICIÓN
CALCULABLE
        ≠
AMBAS CONDICIONES
CALCULABLES
```

La ausencia de información para una condición no deberá impedir necesariamente evaluar la otra cuando esta cuente con información suficiente.

Conceptualmente:

```text
CONDICIÓN KM
SIN INFORMACIÓN
SUFICIENTE
        ↓
NO CALCULABLE

CONDICIÓN TIEMPO
CON INFORMACIÓN
SUFICIENTE
        ↓
CALCULABLE
```

Vehículos Services deberá reflejar esta diferencia sin completar artificialmente la condición desconocida.

De igual manera:

```text
KILOMETRAJE
CALCULABLE
+
TIEMPO
NO CALCULABLE
```

deberá permitir conservar y evaluar únicamente la condición respaldada por la información disponible.

La imposibilidad de evaluar una de las condiciones deberá distinguirse de una condición que haya sido evaluada y todavía no haya alcanzado su objetivo.

Por lo tanto:

```text
NO CALCULABLE
        ≠
NO CUMPLIDA
```

Por ejemplo:

```text
CONDICIÓN A:
No puede evaluarse
por falta de información

CONDICIÓN B:
Evaluada y todavía
no alcanzada
```

representan situaciones diferentes y deberán mantenerse diferenciadas.

Cuando ambas condiciones puedan evaluarse, Vehículos Services deberá conservar el resultado correspondiente a cada una antes de determinar el resultado conjunto de la regla.

Conceptualmente:

```text
CONDICIÓN POR KM
        ↓
RESULTADO KM

        +

CONDICIÓN POR TIEMPO
        ↓
RESULTADO TIEMPO

        ↓

EVALUACIÓN DE
LA REGLA COMBINADA
```

La evaluación conjunta no deberá eliminar la información individual de cada condición.

Esto permitirá explicar posteriormente por qué una actividad se encuentra próxima, alcanzó su objetivo o superó una condición determinada.

Por ejemplo:

```text
ACTIVIDAD:
Cambio de aceite

OBJETIVO KM:
75.000 km

KM ACTUAL:
75.200 km

OBJETIVO TIEMPO:
15/11/2026

FECHA ACTUAL:
20/10/2026
```

Vehículos Services podrá determinar conceptualmente:

```text
KILOMETRAJE:
OBJETIVO SUPERADO

TIEMPO:
OBJETIVO AÚN
NO ALCANZADO

        ↓

REGLA COMBINADA
        ↓
RESULTADO DERIVADO
DE LA CONDICIÓN
QUE CORRESPONDA
```

La definición de los estados específicos resultantes deberá permanecer en el componente correspondiente y no deberá duplicarse dentro de este punto.

Cuando se realice una nueva intervención válida sobre la actividad, la renovación del seguimiento deberá considerar las nuevas referencias correspondientes.

Por ejemplo:

```text
NUEVA INTERVENCIÓN:

74.800 km
10/11/2026
```

podrá proporcionar, cuando corresponda:

```text
NUEVA REFERENCIA
DE KILOMETRAJE:
74.800 km

        +

NUEVA REFERENCIA
TEMPORAL:
10/11/2026
```

A partir de estas referencias podrán determinarse los nuevos objetivos utilizando los intervalos aplicables.

El tratamiento detallado del cierre del ciclo anterior y la generación del nuevo ciclo deberá desarrollarse en `63.11.6 Cumplimiento y renovación del ciclo de seguimiento`.

La combinación de condiciones tampoco deberá definir por sí misma los márgenes utilizados para determinar cuándo una actividad se encuentra próxima a alcanzar alguno de sus objetivos.

Por ejemplo:

```text
OBJETIVO KM:
75.000 km

OBJETIVO TIEMPO:
15/11/2026
```

no deberá establecer automáticamente:

```text
PRÓXIMO POR KM:
¿500 km antes?
¿1.000 km antes?

PRÓXIMO POR TIEMPO:
¿7 días antes?
¿15 días antes?
¿30 días antes?
```

Estas condiciones deberán desarrollarse en `63.11.7 Tolerancias y condiciones de proximidad`.

Como principio general:

```text
ACTIVIDAD
        ↓
SEGUIMIENTO POR
KILOMETRAJE Y TIEMPO
        │
        ├── REFERENCIA KM
        │       +
        │   INTERVALO KM
        │       ↓
        │   OBJETIVO KM
        │       ↓
        │   EVALUACIÓN KM
        │
        └── REFERENCIA TIEMPO
                +
            INTERVALO TIEMPO
                ↓
            OBJETIVO TIEMPO
                ↓
            EVALUACIÓN TIEMPO

                ↓

        REGLA DE COMBINACIÓN

                ↓

        RESULTADO DEL
        SEGUIMIENTO
```

Vehículos Services deberá permitir que una actividad sea controlada simultáneamente mediante kilometraje y tiempo, manteniendo independientes las referencias, objetivos y evaluaciones de cada condición y aplicando posteriormente la forma de combinación definida por la regla, sin exigir que ambas condiciones se alcancen simultáneamente cuando la regla establezca que cualquiera de ellas puede determinar la necesidad de realizar la intervención.

---

### 63.11.5 Determinación del próximo objetivo de mantenimiento

Vehículos Services deberá poder determinar el próximo objetivo de mantenimiento de una actividad cuando exista una regla aplicable y se disponga de la información necesaria para evaluarla.

El próximo objetivo deberá representar la referencia futura utilizada para realizar el seguimiento de una actividad y determinar su evolución conforme al criterio correspondiente.

Conceptualmente:

```text
ACTIVIDAD
        ↓
REGLA APLICABLE
        ↓
REFERENCIA VÁLIDA
        ↓
PRÓXIMO OBJETIVO
```

Dependiendo del criterio de seguimiento, el próximo objetivo podrá corresponder a:

```text
KILOMETRAJE
        ↓
PRÓXIMO KILOMETRAJE
OBJETIVO
```

o:

```text
TIEMPO
        ↓
PRÓXIMA FECHA
OBJETIVO
```

o, cuando exista una regla combinada:

```text
KILOMETRAJE + TIEMPO
        ↓
OBJETIVO KM
        +
OBJETIVO TEMPORAL
```

Los cálculos específicos utilizados para determinar estos objetivos deberán regirse por:

- `63.11.2 Reglas e intervalos por kilometraje`.
- `63.11.3 Reglas e intervalos por tiempo`.
- `63.11.4 Combinación de kilometraje y tiempo`.

Este punto no deberá redefinir dichos cálculos, sino establecer las condiciones funcionales bajo las cuales un próximo objetivo puede considerarse determinable.

La existencia de una actividad que requiera seguimiento no deberá significar automáticamente que pueda calcularse un próximo objetivo.

Conceptualmente:

```text
ACTIVIDAD
        ↓
REQUIERE
SEGUIMIENTO

        ≠

OBJETIVO
AUTOMÁTICAMENTE
CALCULABLE
```

Para determinar un objetivo deberá existir información suficiente conforme a la regla aplicable.

Por ejemplo:

```text
ACTIVIDAD:
Cambio de aceite

REGLA:
Cada 5.000 km

KILOMETRAJE DE REFERENCIA:
70.000 km
```

permite determinar:

```text
PRÓXIMO OBJETIVO:
75.000 km
```

En cambio:

```text
REGLA:
Cada 5.000 km

KILOMETRAJE DE REFERENCIA:
Desconocido
```

no deberá producir artificialmente un próximo objetivo.

Por lo tanto:

```text
EXISTE REGLA
        ≠
EXISTE NECESARIAMENTE
UN PRÓXIMO OBJETIVO
CALCULABLE
```

La misma condición deberá aplicarse para el seguimiento temporal.

Por ejemplo:

```text
REGLA:
Cada 3 meses

FECHA DE REFERENCIA:
Desconocida
```

no deberá permitir inventar una fecha desde la cual calcular el próximo mantenimiento.

En estos casos, Vehículos Services deberá conservar la diferencia entre:

```text
ACTIVIDAD SIN
SEGUIMIENTO
```

y:

```text
ACTIVIDAD CON
SEGUIMIENTO

PERO

SIN INFORMACIÓN
SUFICIENTE PARA
CALCULAR EL OBJETIVO
```

Por lo tanto:

```text
SIN SEGUIMIENTO
        ≠
CON SEGUIMIENTO
PERO SIN OBJETIVO
CALCULABLE
```

Esta diferenciación permitirá evitar que la ausencia de un objetivo calculado sea interpretada automáticamente como ausencia de una regla o de una necesidad de seguimiento.

Cuando exista una regla combinada por kilometraje y tiempo, cada objetivo deberá poder determinarse de forma independiente conforme a la información disponible.

Por ejemplo:

```text
REGLA:
5.000 km
o
3 meses
```

Si se dispone de:

```text
KILOMETRAJE DE REFERENCIA:
70.000 km

FECHA DE REFERENCIA:
Desconocida
```

podrá determinarse:

```text
OBJETIVO KM:
75.000 km
```

mientras que:

```text
OBJETIVO TEMPORAL:
NO CALCULABLE
```

La imposibilidad de calcular una de las condiciones no deberá eliminar el objetivo válido de la otra.

Conceptualmente:

```text
OBJETIVO KM
CALCULABLE
        +
OBJETIVO TIEMPO
NO CALCULABLE
        ↓
CONSERVAR
OBJETIVO KM
```

y no:

```text
UNA CONDICIÓN
NO CALCULABLE
        ↓
ELIMINAR TODO
EL SEGUIMIENTO
```

Este comportamiento deberá mantenerse alineado con lo definido en `63.11.4 Combinación de kilometraje y tiempo`.

La incorporación posterior de información válida podrá permitir determinar un objetivo que anteriormente no era calculable.

Por ejemplo:

```text
REGLA:
Cada 3 meses

FECHA DE REFERENCIA:
Desconocida

        ↓

OBJETIVO:
NO CALCULABLE
```

Si posteriormente se incorpora de manera válida información histórica que permite establecer:

```text
FECHA DE REFERENCIA:
15/08/2026
```

podrá determinarse:

```text
OBJETIVO:
15/11/2026
```

La incorporación posterior de esta información no deberá modificar arbitrariamente el evento histórico original.

Deberá representar una actualización de los resultados derivados a partir de información que ahora permite realizar el cálculo.

Conceptualmente:

```text
INFORMACIÓN
INSUFICIENTE
        ↓
OBJETIVO
NO CALCULABLE

        ↓

NUEVA INFORMACIÓN
VÁLIDA

        ↓

OBJETIVO
CALCULABLE
```

El próximo objetivo deberá permanecer vinculado conceptualmente con la actividad y el ciclo de seguimiento del cual fue derivado.

No deberá interpretarse como un evento histórico ya realizado.

Por lo tanto:

```text
PRÓXIMO OBJETIVO
        ≠
MANTENIMIENTO
REALIZADO
```

Alcanzar o superar un objetivo tampoco deberá permitir inferir por sí mismo que la intervención correspondiente fue realizada.

La diferencia entre el cumplimiento o superación de un objetivo, la realización efectiva de una intervención y la renovación del ciclo deberá regirse por lo definido en `63.11.6 Cumplimiento y renovación del ciclo de seguimiento`.

El próximo objetivo tampoco deberá reemplazar las referencias que permitieron calcularlo.

Vehículos Services deberá mantener conceptualmente diferenciados:

```text
REFERENCIA
        ↓
PUNTO DESDE EL CUAL
SE INICIA EL CICLO

INTERVALO
        ↓
CONDICIÓN DEFINIDA
POR LA REGLA

OBJETIVO
        ↓
REFERENCIA FUTURA
CALCULADA PARA
EL SEGUIMIENTO
```

Por ejemplo:

```text
REFERENCIA:
70.000 km

INTERVALO:
5.000 km

OBJETIVO:
75.000 km
```

Los tres valores cumplen responsabilidades diferentes y no deberán sustituirse entre sí.

El próximo objetivo deberá poder evolucionar únicamente cuando exista una causa funcional que justifique su modificación o reemplazo.

Entre dichas situaciones podrán encontrarse, cuando corresponda:

- La realización de una nueva intervención que genere un nuevo ciclo.
- La corrección válida de información utilizada como referencia.
- La modificación válida de la regla aplicable.
- La incorporación posterior de información histórica relevante.
- Otras situaciones funcionales que posteriormente puedan ser definidas.

Una simple actualización del kilometraje actual o el avance de la fecha actual no deberá recalcular desplazando continuamente el objetivo.

Por ejemplo:

```text
REFERENCIA:
70.000 km

INTERVALO:
5.000 km

OBJETIVO:
75.000 km
```

Si el kilometraje actual cambia:

```text
71.000 km
        ↓
72.000 km
        ↓
73.000 km
```

el objetivo no deberá transformarse sucesivamente en:

```text
76.000 km
77.000 km
78.000 km
```

El objetivo deberá continuar siendo:

```text
75.000 km
```

hasta que exista una condición válida que genere un nuevo ciclo o modifique la regla correspondiente.

De igual manera:

```text
REFERENCIA:
15/08/2026

INTERVALO:
3 meses

OBJETIVO:
15/11/2026
```

el paso de los días no deberá desplazar continuamente la fecha objetivo.

Por lo tanto:

```text
EVOLUCIÓN DE LA
VARIABLE ACTUAL
        ↓
PERMITE EVALUAR
EL OBJETIVO

        ≠

DESPLAZAR
AUTOMÁTICAMENTE
EL OBJETIVO
```

Cuando un objetivo haya sido determinado y posteriormente cambie alguno de los elementos que lo originaron mediante una modificación válida, Vehículos Services deberá poder recalcular el resultado correspondiente conservando la trazabilidad necesaria.

Por ejemplo:

```text
REGLA ANTERIOR:
Cada 5.000 km

REFERENCIA:
70.000 km

OBJETIVO:
75.000 km
```

Si posteriormente la regla aplicable cambia válidamente:

```text
NUEVA REGLA:
Cada 7.500 km
```

podrá ser necesario determinar un nuevo objetivo conforme a las reglas de modificación y evolución establecidas en `63.11.8 Modificación y evolución de las reglas`.

Este punto no deberá determinar si la nueva regla afecta el ciclo actualmente activo, únicamente los ciclos futuros o ambos casos.

Ese comportamiento deberá regirse por lo establecido en `63.11.8` y no deberá asumirse automáticamente.

El objetivo deberá poder utilizarse posteriormente como referencia para determinar:

- El avance del seguimiento.
- La distancia o tiempo restante, cuando pueda calcularse.
- El cumplimiento o superación de la condición.
- La proximidad al objetivo.
- Los estados derivados correspondientes.
- Las alertas o recomendaciones que puedan generarse.

Sin embargo:

```text
OBJETIVO
        ≠
ESTADO

OBJETIVO
        ≠
ALERTA

OBJETIVO
        ≠
RECOMENDACIÓN
```

El objetivo constituye una referencia utilizada para producir dichos resultados mediante la evaluación correspondiente.

Conceptualmente:

```text
REGLA
        +
REFERENCIA
        ↓
OBJETIVO
        +
INFORMACIÓN ACTUAL
        ↓
EVALUACIÓN
        ↓
RESULTADOS
        ↓
ESTADOS / ALERTAS /
RECOMENDACIONES
CUANDO CORRESPONDA
```

Cuando existan varios objetivos correspondientes a diferentes actividades del mismo mantenimiento, cada actividad deberá conservar su propio seguimiento.

Por ejemplo:

```text
MANTENIMIENTO
        │
        ├── ACTIVIDAD A
        │       ↓
        │   OBJETIVO A
        │
        ├── ACTIVIDAD B
        │       ↓
        │   OBJETIVO B
        │
        └── ACTIVIDAD C
                ↓
            SIN OBJETIVO
            CUANDO NO
            REQUIERA
            SEGUIMIENTO
```

Vehículos Services no deberá consolidar artificialmente estos objetivos en un único objetivo general cuando las actividades tengan reglas independientes.

La determinación de un próximo objetivo tampoco deberá implicar que dicho objetivo sea técnicamente correcto para todos los vehículos únicamente por haber sido calculado.

Su validez dependerá de la regla aplicable y de la información utilizada para establecerla.

Los valores utilizados por una regla no deberán presentarse como diagnóstico mecánico ni como garantía del estado real del componente.

Como principio general:

```text
ACTIVIDAD
        ↓
REGLA APLICABLE
        ↓
REFERENCIA VÁLIDA
        ↓
OBJETIVO CALCULABLE
        ↓
OBJETIVO DE
SEGUIMIENTO
        ↓
INFORMACIÓN ACTUAL
        ↓
EVALUACIÓN
```

Vehículos Services deberá determinar los próximos objetivos de mantenimiento únicamente cuando exista una regla aplicable y la información necesaria para sustentarlos, manteniendo diferenciados la referencia, el intervalo, el objetivo calculado, la información actual y la intervención efectivamente realizada, sin inventar objetivos cuando los datos disponibles sean insuficientes.

---
### 63.11.6 Cumplimiento y renovación del ciclo de seguimiento

Vehículos Services deberá diferenciar entre el cumplimiento de una condición de seguimiento y la realización efectiva de la intervención asociada a una actividad.

Una condición podrá alcanzar o superar su objetivo sin que exista evidencia de que la intervención correspondiente haya sido realizada.

Conceptualmente:

```text
OBJETIVO
        ↓
SE ALCANZA
O SUPERA
        ↓
CONDICIÓN DE
SEGUIMIENTO
ALCANZADA O SUPERADA

        ≠

INTERVENCIÓN
REALIZADA
```

Por ejemplo:

```text
OBJETIVO:
75.000 km

KM ACTUAL:
75.300 km
```

En este escenario, Vehículos Services podrá determinar que el objetivo de kilometraje fue alcanzado o superado.

Sin embargo:

```text
75.300 km
        ↓
NO DEMUESTRA
POR SÍ SOLO
        ↓
QUE EL MANTENIMIENTO
FUE REALIZADO
```

La misma regla deberá aplicarse para el seguimiento temporal.

Por ejemplo:

```text
FECHA OBJETIVO:
15/11/2026

FECHA ACTUAL:
20/11/2026
```

El hecho de haber superado la fecha objetivo deberá representar una condición del seguimiento, pero no deberá crear ni inferir automáticamente una intervención.

Por lo tanto:

```text
OBJETIVO SUPERADO
        ≠
INTERVENCIÓN REALIZADA
        ≠
NUEVO CICLO
AUTOMÁTICO
```

Mientras no exista una nueva intervención válida que corresponda a la actividad bajo seguimiento, el ciclo existente deberá conservar su referencia y su objetivo.

Por ejemplo:

```text
REFERENCIA:
70.000 km

INTERVALO:
5.000 km

OBJETIVO:
75.000 km
```

Si el vehículo posteriormente registra:

```text
76.000 km
        ↓
78.000 km
        ↓
80.000 km
```

sin que exista una nueva intervención correspondiente a la actividad, Vehículos Services no deberá desplazar automáticamente el objetivo a:

```text
80.000 km
        ↓
85.000 km
        ↓
90.000 km
```

El objetivo original deberá continuar asociado al ciclo pendiente hasta que ocurra una condición válida que permita renovar dicho ciclo.

Conceptualmente:

```text
CICLO ACTIVO

Referencia:
70.000 km

Objetivo:
75.000 km

        ↓

Objetivo alcanzado
o superado

        ↓

SIN NUEVA
INTERVENCIÓN

        ↓

EL CICLO NO
SE RENUEVA
AUTOMÁTICAMENTE
```

La renovación de un ciclo de seguimiento deberá ocurrir cuando exista una nueva intervención válida correspondiente a la actividad y dicha intervención pueda establecer una nueva referencia conforme a la regla aplicable.

Conceptualmente:

```text
CICLO ANTERIOR
        ↓
NUEVA INTERVENCIÓN
VÁLIDA
        ↓
NUEVA REFERENCIA
        ↓
REGLA APLICABLE
        ↓
NUEVO OBJETIVO
        ↓
NUEVO CICLO
DE SEGUIMIENTO
```

Por ejemplo:

```text
ACTIVIDAD:
Cambio de aceite

REFERENCIA ANTERIOR:
70.000 km

INTERVALO:
5.000 km

OBJETIVO ANTERIOR:
75.000 km
```

La intervención es realizada posteriormente en:

```text
75.300 km
```

Cuando dicha intervención corresponda efectivamente al cambio de aceite bajo seguimiento:

```text
NUEVA REFERENCIA:
75.300 km

INTERVALO:
5.000 km

        ↓

NUEVO OBJETIVO:
80.300 km
```

Por lo tanto:

```text
NUEVO OBJETIVO
=
NUEVA REFERENCIA REAL
+
INTERVALO APLICABLE
```

El nuevo ciclo no deberá calcularse automáticamente utilizando el objetivo anterior como nueva referencia.

Por ejemplo:

```text
OBJETIVO ANTERIOR:
75.000 km

INTERVENCIÓN REAL:
75.300 km
```

La nueva referencia deberá ser:

```text
75.300 km
```

y no:

```text
75.000 km
```

cuando la intervención efectivamente realizada sea la condición que establece el inicio del nuevo ciclo.

Por lo tanto:

```text
OBJETIVO ANTERIOR
        ≠
NUEVA REFERENCIA
AUTOMÁTICAMENTE
```

Esta regla permitirá conservar la diferencia entre lo que estaba previsto y lo que realmente ocurrió.

El mismo principio deberá aplicarse cuando la intervención sea realizada antes del objetivo.

Por ejemplo:

```text
OBJETIVO:
75.000 km

INTERVENCIÓN REAL:
74.500 km
```

Si dicha intervención corresponde válidamente a la actividad bajo seguimiento, podrá establecerse:

```text
NUEVA REFERENCIA:
74.500 km

INTERVALO:
5.000 km

NUEVO OBJETIVO:
79.500 km
```

Vehículos Services no deberá obligar a mantener como referencia los `75.000 km` originalmente calculados cuando la intervención fue realizada realmente a los `74.500 km`.

Conceptualmente:

```text
OBJETIVO PREVISTO
        ↓
75.000 km

INTERVENCIÓN REAL
        ↓
74.500 km

        ↓

NUEVO CICLO
DESDE LA
INTERVENCIÓN REAL
```

La misma lógica deberá aplicarse para reglas temporales.

Por ejemplo:

```text
REFERENCIA ANTERIOR:
15/08/2026

INTERVALO:
3 meses

OBJETIVO:
15/11/2026
```

Si la intervención se realiza:

```text
10/11/2026
```

y corresponde válidamente a la actividad:

```text
NUEVA REFERENCIA:
10/11/2026

INTERVALO:
3 meses

NUEVO OBJETIVO:
10/02/2027
```

Si la intervención se realiza después:

```text
25/11/2026
```

podrá establecerse:

```text
NUEVA REFERENCIA:
25/11/2026

INTERVALO:
3 meses

NUEVO OBJETIVO:
25/02/2027
```

cuando la regla aplicable continúe siendo la misma.

De esta manera:

```text
FECHA OBJETIVO ANTERIOR
        ≠
NUEVA FECHA DE REFERENCIA
AUTOMÁTICAMENTE
```

La nueva referencia deberá provenir de la intervención efectivamente realizada cuando corresponda.

En reglas combinadas por kilometraje y tiempo, una nueva intervención podrá renovar conjuntamente las referencias utilizadas para ambas condiciones cuando exista información suficiente.

Por ejemplo:

```text
INTERVENCIÓN REAL:

74.800 km
10/11/2026
```

podrá establecer:

```text
NUEVA REFERENCIA
POR KILOMETRAJE:
74.800 km

NUEVA REFERENCIA
POR TIEMPO:
10/11/2026
```

Si la regla continúa siendo:

```text
5.000 km
o
3 meses
```

podrán determinarse:

```text
NUEVO OBJETIVO KM:
79.800 km

NUEVO OBJETIVO TIEMPO:
10/02/2027
```

Conceptualmente:

```text
NUEVA INTERVENCIÓN
        │
        ├── KM REAL
        │       ↓
        │   NUEVA REFERENCIA KM
        │       ↓
        │   NUEVO OBJETIVO KM
        │
        └── FECHA REAL
                ↓
            NUEVA REFERENCIA
            TEMPORAL
                ↓
            NUEVO OBJETIVO
            TEMPORAL
```

Cuando una intervención no disponga de toda la información necesaria para renovar todas las condiciones de una regla combinada, Vehículos Services no deberá inventar los datos faltantes.

Por ejemplo:

```text
NUEVA INTERVENCIÓN:

Fecha:
10/11/2026

Kilometraje:
Desconocido
```

En este escenario podrá existir información suficiente para establecer una nueva referencia temporal, pero no deberá inventarse un kilometraje para generar artificialmente una nueva referencia por kilometraje.

Por lo tanto:

```text
INFORMACIÓN DISPONIBLE
        ↓
RENOVAR ÚNICAMENTE
LO QUE PUEDA
SUSTENTARSE

        ≠

COMPLETAR DATOS
INEXISTENTES
```

El tratamiento específico de una regla combinada deberá conservar la independencia de sus condiciones y la información disponible para cada una.

La nueva intervención utilizada para renovar el ciclo deberá corresponder a la actividad que se encuentra bajo seguimiento.

La realización de otra actividad dentro del mismo mantenimiento no deberá renovar automáticamente el ciclo.

Por ejemplo:

```text
MANTENIMIENTO
75.000 km

        │
        ├── Cambio de aceite
        │
        └── Revisión de frenos
```

Si solamente existe una nueva intervención correspondiente a:

```text
REVISIÓN DE FRENOS
```

Vehículos Services no deberá asumir que también fue realizado:

```text
CAMBIO DE ACEITE
```

ni deberá renovar automáticamente el ciclo asociado a este último.

Por lo tanto:

```text
NUEVO MANTENIMIENTO
GENERAL
        ≠
RENOVACIÓN AUTOMÁTICA
DE TODAS LAS ACTIVIDADES
QUE TENGAN SEGUIMIENTO
```

La renovación deberá producirse únicamente para las actividades efectivamente realizadas y registradas cuando corresponda.

Conceptualmente:

```text
MANTENIMIENTO
        │
        ├── ACTIVIDAD A
        │   REALIZADA
        │       ↓
        │   PUEDE RENOVAR
        │   SU CICLO
        │
        └── ACTIVIDAD B
            NO REALIZADA
                ↓
            CONSERVA SU
            SEGUIMIENTO
            ANTERIOR
```

La existencia de una recomendación, una actividad pendiente, una programación futura o una alerta tampoco deberá renovar un ciclo.

Por lo tanto:

```text
RECOMENDACIÓN
        ≠
INTERVENCIÓN REALIZADA

PENDIENTE
        ≠
INTERVENCIÓN REALIZADA

PROGRAMACIÓN
        ≠
INTERVENCIÓN REALIZADA

ALERTA
        ≠
INTERVENCIÓN REALIZADA
```

En el contexto de la renovación de un ciclo mediante una nueva intervención, solamente una intervención efectivamente realizada y registrada de forma válida podrá utilizarse como nueva referencia cuando corresponda.

La renovación del ciclo no deberá eliminar el ciclo anterior ni la información que permitió evaluarlo.

Conceptualmente:

```text
CICLO 1
        ↓
REFERENCIA
        ↓
OBJETIVO
        ↓
EVOLUCIÓN
        ↓
NUEVA INTERVENCIÓN

        ↓

CICLO 2
        ↓
NUEVA REFERENCIA
        ↓
NUEVO OBJETIVO
```

El inicio del `CICLO 2` no deberá provocar la eliminación del `CICLO 1`.

Esto permitirá conservar la evolución histórica del seguimiento y comprender, cuando exista información suficiente:

- Cuál era la referencia anterior.
- Cuál era el objetivo anterior.
- Cuándo se realizó realmente la siguiente intervención.
- Si la intervención ocurrió antes, al alcanzar o después del objetivo.
- Cuál fue la nueva referencia.
- Cuál fue el nuevo objetivo generado.

Por ejemplo:

```text
CICLO 1

Referencia:
70.000 km

Objetivo:
75.000 km

Intervención real:
75.300 km

        ↓

CICLO 2

Referencia:
75.300 km

Objetivo:
80.300 km
```

Esta información deberá conservarse como parte de la trazabilidad del seguimiento sin modificar los registros históricos originales de las intervenciones.

Una corrección válida de una intervención utilizada como referencia podrá requerir la reevaluación de los resultados derivados.

Por ejemplo:

```text
REFERENCIA REGISTRADA:
75.300 km
```

Si posteriormente se corrige de manera válida y trazable a:

```text
75.030 km
```

los objetivos derivados podrán requerir recálculo conforme a la información corregida.

Conceptualmente:

```text
CORRECCIÓN VÁLIDA
DE LA REFERENCIA
        ↓
REEVALUACIÓN
DEL CICLO
        ↓
RECALCULAR
RESULTADOS DERIVADOS
CUANDO CORRESPONDA
```

La corrección no deberá ejecutarse mediante una alteración silenciosa del historial y deberá respetar las reglas generales de trazabilidad previamente definidas.

La modificación de la regla aplicable también podrá afectar la continuidad o renovación del seguimiento.

Sin embargo, este punto no deberá determinar si una regla modificada afecta:

- El ciclo actualmente activo.
- Únicamente los ciclos futuros.
- Ambos casos bajo determinadas condiciones.

Ese comportamiento deberá desarrollarse en `63.11.8 Modificación y evolución de las reglas`.

La renovación de un ciclo tampoco deberá confundirse con la determinación del estado de seguimiento.

Conceptualmente:

```text
ESTADO
        ↓
REPRESENTA LA
SITUACIÓN DEL
CICLO ACTUAL

RENOVACIÓN
        ↓
GENERA UN NUEVO
CICLO A PARTIR
DE UNA NUEVA
REFERENCIA
```

Por lo tanto:

```text
CAMBIO DE ESTADO
        ≠
RENOVACIÓN DEL CICLO
```

Un ciclo podrá cambiar de condición conforme evolucione el kilometraje o el tiempo sin que por ello deba renovarse.

La renovación deberá depender de una situación funcional que establezca válidamente una nueva referencia.

Como principio general:

```text
CICLO ACTUAL
        ↓
REFERENCIA
        ↓
OBJETIVO
        ↓
EVOLUCIÓN DEL
KILOMETRAJE /
TIEMPO
        ↓
OBJETIVO PUEDE
SER ALCANZADO
O SUPERADO
        ↓
EL CICLO CONTINÚA
MIENTRAS NO EXISTA
UNA NUEVA INTERVENCIÓN
VÁLIDA
        ↓
NUEVA INTERVENCIÓN
        ↓
NUEVA REFERENCIA
        ↓
NUEVO OBJETIVO
        ↓
NUEVO CICLO
```

Vehículos Services deberá renovar el ciclo de seguimiento de una actividad únicamente cuando exista una condición válida que establezca una nueva referencia, manteniendo diferenciados el cumplimiento o superación del objetivo y la realización efectiva de la intervención, y conservando la trazabilidad entre los ciclos anteriores y posteriores.

---

### 63.11.7 Tolerancias y condiciones de proximidad

Vehículos Services deberá permitir establecer condiciones de proximidad que permitan determinar cuándo una actividad se encuentra cercana a alcanzar el objetivo definido por su regla de mantenimiento.

La existencia de un próximo objetivo no deberá determinar por sí sola desde qué momento una actividad deberá considerarse próxima a dicho objetivo.

Por ejemplo:

```text
OBJETIVO:
75.000 km
```

no deberá implicar automáticamente que la actividad se considere próxima:

```text
500 km antes
1.000 km antes
2.000 km antes
```

De igual manera:

```text
OBJETIVO:
15/11/2026
```

no deberá implicar automáticamente que la actividad se considere próxima:

```text
7 días antes
15 días antes
30 días antes
```

Por lo tanto:

```text
OBJETIVO
        ≠
CONDICIÓN DE
PROXIMIDAD
AUTOMÁTICA
```

La condición de proximidad deberá establecer el margen previo al objetivo dentro del cual el seguimiento podrá reconocer que la actividad se encuentra cercana a requerir atención.

Conceptualmente:

```text
OBJETIVO
        +
MARGEN DE
PROXIMIDAD
        ↓
CONDICIÓN DE
PROXIMIDAD
```

Cuando el seguimiento se realice por kilometraje, la condición de proximidad podrá expresarse mediante una distancia previa al kilometraje objetivo.

Por ejemplo:

```text
OBJETIVO:
75.000 km

MARGEN DE PROXIMIDAD:
1.000 km
```

Conceptualmente:

```text
74.000 km
        ↓
INICIO DE LA
CONDICIÓN DE
PROXIMIDAD

        ↓

75.000 km
        ↓
OBJETIVO
```

En este ejemplo, cuando el kilometraje actual alcance el margen definido antes del objetivo, Vehículos Services podrá reconocer que la actividad se encuentra dentro de la condición de proximidad correspondiente.

Esto no deberá significar que `1.000 km` sea un margen universal para todas las actividades o vehículos.

Los valores utilizados en los ejemplos de este punto deberán considerarse únicamente ilustrativos.

Por lo tanto:

```text
MISMO TIPO
DE ACTIVIDAD
        ≠
MISMO MARGEN
UNIVERSAL
PARA TODOS
LOS VEHÍCULOS
```

Cuando el seguimiento se realice por tiempo, la condición de proximidad podrá expresarse mediante un período previo a la fecha objetivo.

Por ejemplo:

```text
OBJETIVO:
15/11/2026

MARGEN DE PROXIMIDAD:
15 días
```

Conceptualmente:

```text
31/10/2026
        ↓
INICIO DE LA
CONDICIÓN DE
PROXIMIDAD

        ↓

15/11/2026
        ↓
OBJETIVO
```

El margen temporal deberá formar parte de las condiciones utilizadas para evaluar la proximidad y no deberá modificar la fecha objetivo original.

Por lo tanto:

```text
FECHA OBJETIVO
        +
MARGEN DE PROXIMIDAD

        ↓

PERMITE DETERMINAR
PROXIMIDAD

        ≠

MODIFICAR LA
FECHA OBJETIVO
```

La misma separación deberá mantenerse para kilometraje.

Por ejemplo:

```text
OBJETIVO:
75.000 km

MARGEN:
1.000 km
```

no deberá transformar el objetivo en:

```text
74.000 km
```

El valor de `74.000 km` representa únicamente el punto desde el cual puede comenzar la condición de proximidad en este ejemplo.

Conceptualmente:

```text
74.000 km
        ↓
UMBRAL DE
PROXIMIDAD

75.000 km
        ↓
OBJETIVO REAL
```

Por lo tanto:

```text
UMBRAL DE PROXIMIDAD
        ≠
OBJETIVO
```

Vehículos Services deberá mantener diferenciados:

```text
REFERENCIA
        ↓
INICIO DEL CICLO

INTERVALO
        ↓
CONDICIÓN DE
RECURRENCIA

OBJETIVO
        ↓
PUNTO FUTURO
DE SEGUIMIENTO

MARGEN DE PROXIMIDAD
        ↓
CONDICIÓN PREVIA
AL OBJETIVO
```

Cuando exista información suficiente, el margen podrá utilizarse para determinar un umbral de proximidad.

Conceptualmente, para kilometraje:

```text
UMBRAL DE PROXIMIDAD
=
OBJETIVO DE KILOMETRAJE
-
MARGEN DE PROXIMIDAD
```

Por ejemplo:

```text
75.000 km
-
1.000 km
=
74.000 km
```

Para tiempo, conceptualmente:

```text
UMBRAL DE PROXIMIDAD
=
FECHA OBJETIVO
-
MARGEN TEMPORAL
```

Por ejemplo:

```text
15/11/2026
-
15 días
=
31/10/2026
```

Estos cálculos deberán realizarse únicamente cuando exista información suficiente para determinar tanto el objetivo como el margen correspondiente.

Por lo tanto:

```text
OBJETIVO CONOCIDO
+
MARGEN CONOCIDO
        ↓
UMBRAL
CALCULABLE
```

Mientras que:

```text
OBJETIVO CONOCIDO
+
MARGEN DESCONOCIDO
        ↓
NO EXISTE
UMBRAL DE PROXIMIDAD
CALCULABLE
```

La ausencia de un margen de proximidad no deberá modificar ni invalidar el objetivo existente.

Por ejemplo:

```text
OBJETIVO:
75.000 km

MARGEN:
No definido
```

deberá permitir conservar:

```text
OBJETIVO:
75.000 km
```

aunque no exista información suficiente para determinar anticipadamente cuándo deberá considerarse próximo.

Por lo tanto:

```text
SIN MARGEN
DE PROXIMIDAD
        ≠
SIN OBJETIVO
```

Vehículos Services tampoco deberá inventar un margen cuando este no se encuentre definido.

Conceptualmente:

```text
MARGEN NO DEFINIDO
        ↓
NO INVENTAR
UMBRAL
        ↓
CONSERVAR EL
OBJETIVO DISPONIBLE
```

Cuando una regla utilice simultáneamente kilometraje y tiempo, cada condición podrá disponer de su propio margen de proximidad.

Por ejemplo:

```text
OBJETIVO KM:
75.000 km

MARGEN KM:
1.000 km

        +

OBJETIVO TIEMPO:
15/11/2026

MARGEN TIEMPO:
15 días
```

Esto permitirá obtener conceptualmente:

```text
UMBRAL KM:
74.000 km

UMBRAL TIEMPO:
31/10/2026
```

Ambas condiciones deberán mantenerse independientes.

Por lo tanto:

```text
MARGEN POR
KILOMETRAJE
        ≠
MARGEN POR
TIEMPO
```

Una actividad podrá encontrarse dentro de la condición de proximidad por uno de los criterios y todavía encontrarse fuera de la condición de proximidad por el otro.

Por ejemplo:

```text
OBJETIVO KM:
75.000 km

UMBRAL KM:
74.000 km

KM ACTUAL:
74.500 km
```

mientras:

```text
OBJETIVO TIEMPO:
15/11/2026

UMBRAL TIEMPO:
31/10/2026

FECHA ACTUAL:
15/10/2026
```

En este escenario:

```text
KILOMETRAJE
        ↓
DENTRO DE LA
CONDICIÓN DE
PROXIMIDAD

TIEMPO
        ↓
TODAVÍA FUERA
DE LA CONDICIÓN
DE PROXIMIDAD
```

La evaluación conjunta deberá respetar posteriormente la forma de combinación definida por la regla.

La proximidad tampoco deberá confundirse con el cumplimiento o superación del objetivo.

Conceptualmente:

```text
ANTES DEL UMBRAL
        ↓
OBJETIVO TODAVÍA
NO PRÓXIMO SEGÚN
EL MARGEN DEFINIDO

        ↓

DENTRO DEL MARGEN
        ↓
PRÓXIMO AL
OBJETIVO

        ↓

OBJETIVO
ALCANZADO
        ↓
CONDICIÓN
ALCANZADA

        ↓

OBJETIVO
SUPERADO
        ↓
CONDICIÓN
SUPERADA
```

Por ejemplo:

```text
UMBRAL:
74.000 km

OBJETIVO:
75.000 km
```

podrán existir conceptualmente situaciones como:

```text
73.500 km
        ↓
ANTES DEL UMBRAL

74.500 km
        ↓
DENTRO DEL MARGEN
DE PROXIMIDAD

75.000 km
        ↓
OBJETIVO ALCANZADO

75.500 km
        ↓
OBJETIVO SUPERADO
```

Estas situaciones representan resultados diferentes de la evaluación del seguimiento.

El margen de proximidad no deberá actuar como una extensión automática del intervalo ni como una modificación de la regla principal.

Por ejemplo:

```text
INTERVALO:
5.000 km

MARGEN:
1.000 km
```

no deberá interpretarse como:

```text
INTERVALO:
4.000 km
```

ni como:

```text
INTERVALO:
6.000 km
```

Por lo tanto:

```text
INTERVALO
        ≠
MARGEN DE
PROXIMIDAD
```

El intervalo determina el objetivo conforme a la regla, mientras que el margen permite evaluar anticipadamente la cercanía a dicho objetivo.

De igual manera, una tolerancia posterior al objetivo, cuando funcionalmente corresponda, no deberá modificar el momento en el cual el objetivo fue realmente alcanzado.

Conceptualmente:

```text
OBJETIVO
        ↓
PUNTO DEFINIDO
POR LA REGLA

TOLERANCIA
POSTERIOR
        ↓
MARGEN ADICIONAL
DE EVALUACIÓN
CUANDO EXISTA
```

Por lo tanto:

```text
TOLERANCIA
        ≠
NUEVO OBJETIVO
```

Si posteriormente se determina que una determinada regla requiere una tolerancia posterior, esta deberá mantenerse explícitamente diferenciada del objetivo y del margen previo de proximidad.

Por ejemplo:

```text
OBJETIVO:
75.000 km

TOLERANCIA POSTERIOR:
500 km
```

no deberá transformar el objetivo en:

```text
75.500 km
```

El objetivo continuará siendo:

```text
75.000 km
```

y cualquier comportamiento entre el objetivo y el límite de tolerancia deberá interpretarse conforme a la regla específica que corresponda.

Vehículos Services no deberá asumir que todas las actividades requieren una tolerancia posterior.

Por lo tanto:

```text
OBJETIVO
        ≠
TOLERANCIA POSTERIOR
OBLIGATORIA
```

La existencia, valor y comportamiento de una tolerancia deberá encontrarse expresamente definidos cuando corresponda.

Las tolerancias tampoco deberán utilizarse para afirmar que es técnicamente seguro continuar utilizando un componente o postergar una intervención.

Por ejemplo:

```text
TOLERANCIA:
500 km
```

no deberá interpretarse automáticamente como:

```text
ES SEGURO UTILIZAR
EL VEHÍCULO DURANTE
500 km ADICIONALES
```

Por lo tanto:

```text
TOLERANCIA FUNCIONAL
DE SEGUIMIENTO
        ≠
CERTIFICACIÓN
DE SEGURIDAD
        ≠
DIAGNÓSTICO
MECÁNICO
```

Vehículos Services deberá utilizar las tolerancias únicamente dentro del contexto funcional definido para el seguimiento.

Los márgenes y tolerancias podrán variar entre reglas cuando corresponda.

La plataforma no deberá asumir que todas las actividades, vehículos o criterios utilizan necesariamente los mismos valores.

Conceptualmente:

```text
REGLA A
        ↓
MARGEN A

REGLA B
        ↓
MARGEN B

REGLA C
        ↓
SIN MARGEN
CUANDO CORRESPONDA
```

La definición de estos valores deberá permanecer asociada a la regla aplicable y deberá poder evolucionar conforme a las condiciones funcionales definidas posteriormente.

Una modificación válida de un margen o tolerancia podrá requerir la reevaluación del seguimiento activo.

Por ejemplo:

```text
OBJETIVO:
75.000 km

MARGEN ANTERIOR:
500 km

UMBRAL ANTERIOR:
74.500 km
```

Si el margen cambia válidamente a:

```text
NUEVO MARGEN:
1.000 km
```

el umbral derivado podrá pasar a:

```text
74.000 km
```

La modificación del margen no deberá alterar:

```text
OBJETIVO:
75.000 km
```

cuando únicamente haya cambiado la condición de proximidad.

Conceptualmente:

```text
CAMBIO DE MARGEN
        ↓
RECALCULAR
UMBRAL DERIVADO

        ≠

MODIFICAR
AUTOMÁTICAMENTE
EL OBJETIVO
```

El tratamiento general de las modificaciones de reglas y su efecto sobre ciclos activos o futuros deberá desarrollarse en `63.11.8 Modificación y evolución de las reglas`.

La determinación de una condición de proximidad tampoco deberá significar por sí misma que una alerta o notificación haya sido enviada.

Por lo tanto:

```text
CONDICIÓN DE
PROXIMIDAD
        ≠
ALERTA ENVIADA
        ≠
NOTIFICACIÓN ENVIADA
```

La condición de proximidad representa un resultado que posteriormente podrá ser utilizado por los componentes de estados, alertas, recomendaciones o notificaciones según las reglas que correspondan.

Conceptualmente:

```text
REGLA
        ↓
OBJETIVO
        +
MARGEN
        ↓
EVALUACIÓN
        ↓
CONDICIÓN DE
PROXIMIDAD
        ↓
RESULTADO DISPONIBLE
PARA OTROS
COMPONENTES
```

Como principio general:

```text
REFERENCIA
        +
INTERVALO
        ↓
OBJETIVO
        +
MARGEN DE
PROXIMIDAD
        ↓
UMBRAL DE
PROXIMIDAD
        +
INFORMACIÓN ACTUAL
        ↓
EVALUACIÓN
        ↓
ANTES DEL UMBRAL
/
PRÓXIMO AL OBJETIVO
/
OBJETIVO ALCANZADO
/
OBJETIVO SUPERADO
```

Vehículos Services deberá permitir evaluar la proximidad de una actividad respecto de sus objetivos mediante márgenes definidos por la regla aplicable, manteniendo diferenciados el intervalo, el objetivo, el margen de proximidad, las tolerancias y los resultados derivados, sin establecer valores universales ni interpretar dichos márgenes como diagnósticos o garantías de seguridad.

---
### 63.11.8 Modificación y evolución de las reglas

Las reglas de mantenimiento deberán poder evolucionar cuando exista una modificación válida de las condiciones utilizadas para realizar el seguimiento de una actividad.

Una regla no deberá considerarse necesariamente permanente e inmutable durante todo el ciclo de vida del vehículo.

Conceptualmente:

```text
REGLA ACTUAL
        ↓
PUEDE EXISTIR
UNA MODIFICACIÓN
VÁLIDA
        ↓
NUEVA DEFINICIÓN
DE LA REGLA
```

Una modificación podrá afectar, según corresponda, elementos como:

- El intervalo de kilometraje.
- El intervalo de tiempo.
- La combinación de condiciones.
- Los márgenes de proximidad.
- Las tolerancias.
- La aplicabilidad de la regla.
- Otras condiciones de seguimiento que posteriormente puedan ser definidas.

Por ejemplo:

```text
REGLA ANTERIOR:

Cada 5.000 km
```

podrá posteriormente cambiar válidamente a:

```text
NUEVA REGLA:

Cada 7.500 km
```

La existencia de una nueva regla no deberá provocar que la regla anterior desaparezca conceptualmente de los procesos históricos en los cuales fue utilizada.

Por lo tanto:

```text
NUEVA REGLA
        ≠
REESCRITURA AUTOMÁTICA
DE LA REGLA ANTERIOR
```

Vehículos Services deberá diferenciar entre:

```text
REGLA UTILIZADA
HISTÓRICAMENTE

        ≠

REGLA ACTUALMENTE
APLICABLE
```

Esta diferenciación deberá permitir comprender qué condiciones fueron utilizadas para realizar el seguimiento de una actividad en diferentes momentos.

Por ejemplo:

```text
PERÍODO / CICLO 1

Regla aplicable:
Cada 5.000 km

Referencia:
70.000 km

Objetivo:
75.000 km
```

Posteriormente:

```text
NUEVA REGLA:
Cada 7.500 km
```

La existencia de la nueva regla no deberá transformar artificialmente el objetivo histórico del ciclo anterior en:

```text
77.500 km
```

si dicho ciclo ya corresponde a un seguimiento histórico que fue evaluado utilizando la regla anterior.

Conceptualmente:

```text
CICLO HISTÓRICO
        ↓
CONSERVA EL CONTEXTO
DE LA REGLA QUE
LE CORRESPONDIÓ
```

Esto permitirá conservar la trazabilidad entre:

```text
ACTIVIDAD
        ↓
REGLA APLICABLE
EN ESE MOMENTO
        ↓
REFERENCIA
        ↓
OBJETIVO
        ↓
RESULTADO DEL
SEGUIMIENTO
```

Una modificación de la regla deberá diferenciarse de una corrección de la regla.

Conceptualmente:

```text
MODIFICACIÓN
        ↓
CAMBIO VÁLIDO DE
LAS CONDICIONES
APLICABLES

        ≠

CORRECCIÓN
        ↓
RECTIFICACIÓN DE
INFORMACIÓN QUE
ESTABA REGISTRADA
INCORRECTAMENTE
```

Por ejemplo, si una regla realmente debía ser:

```text
Cada 5.000 km
```

pero fue registrada incorrectamente como:

```text
Cada 50.000 km
```

la rectificación de dicho valor deberá tratarse como una corrección y no necesariamente como una nueva decisión de mantenimiento.

En cambio:

```text
REGLA VÁLIDA ANTERIOR:
Cada 5.000 km

        ↓

NUEVA CONDICIÓN
VÁLIDAMENTE DEFINIDA:
Cada 7.500 km
```

representa una evolución de la regla.

Vehículos Services deberá conservar trazabilidad suficiente para evitar que ambos escenarios sean tratados como si fueran equivalentes.

Las correcciones deberán respetar además las reglas generales de integridad y trazabilidad definidas para la información del vehículo.

Cuando una regla sea modificada durante un ciclo de seguimiento activo, Vehículos Services no deberá asumir automáticamente cómo deberá aplicarse dicha modificación.

Deberá existir una condición que determine si la modificación:

- Aplica únicamente a los ciclos futuros.
- Aplica al ciclo actualmente activo.
- Requiere una reevaluación del ciclo actual.
- O corresponde a otra situación expresamente definida.

Por lo tanto:

```text
REGLA MODIFICADA
        ≠
RECALCULAR
AUTOMÁTICAMENTE
TODO EL SEGUIMIENTO
```

Por ejemplo:

```text
CICLO ACTIVO

Referencia:
70.000 km

Regla utilizada:
5.000 km

Objetivo:
75.000 km
```

Posteriormente la regla cambia a:

```text
7.500 km
```

Vehículos Services no deberá asumir automáticamente que el objetivo activo debe convertirse en:

```text
77.500 km
```

sin determinar previamente si la nueva regla debe aplicarse al ciclo actual.

Conceptualmente:

```text
CAMBIO DE REGLA
        ↓
DETERMINAR
APLICABILIDAD
DEL CAMBIO
        │
        ├── CICLO ACTUAL
        │
        ├── CICLOS FUTUROS
        │
        └── AMBOS
            CUANDO
            CORRESPONDA
```

Cuando la modificación aplique únicamente a ciclos futuros, el ciclo activo deberá poder conservar las condiciones con las cuales fue generado.

Por ejemplo:

```text
CICLO ACTUAL

Regla:
5.000 km

Objetivo:
75.000 km
```

y:

```text
PRÓXIMO CICLO

Nueva regla:
7.500 km
```

Cuando ocurra una nueva intervención válida y se genere el siguiente ciclo:

```text
NUEVA REFERENCIA:
75.300 km

NUEVA REGLA:
7.500 km

        ↓

NUEVO OBJETIVO:
82.800 km
```

En este escenario:

```text
CICLO ANTERIOR
        ↓
CONSERVA SU REGLA

NUEVO CICLO
        ↓
UTILIZA LA NUEVA REGLA
```

Cuando una modificación deba aplicarse al ciclo actualmente activo, los resultados derivados podrán requerir una reevaluación.

Conceptualmente:

```text
CICLO ACTIVO
        +
NUEVA REGLA
APLICABLE AL CICLO
        ↓
REEVALUACIÓN
        ↓
NUEVOS RESULTADOS
DERIVADOS
CUANDO CORRESPONDA
```

La reevaluación podrá afectar elementos derivados como:

- El próximo objetivo.
- El umbral de proximidad.
- Las condiciones de seguimiento.
- Otros resultados dependientes de la regla.

Sin embargo, la reevaluación no deberá modificar los eventos históricos reales utilizados como referencia.

Por ejemplo:

```text
INTERVENCIÓN REAL:
70.000 km
```

deberá continuar siendo:

```text
70.000 km
```

aunque cambie el intervalo utilizado para determinar el siguiente objetivo.

Por lo tanto:

```text
CAMBIO DE REGLA
        ↓
PUEDE MODIFICAR
RESULTADOS DERIVADOS

        ≠

MODIFICAR
ARBITRARIAMENTE
LA INTERVENCIÓN
HISTÓRICA
```

La misma separación deberá mantenerse para reglas temporales.

Por ejemplo:

```text
INTERVENCIÓN REAL:
15/08/2026

REGLA ANTERIOR:
3 meses

OBJETIVO:
15/11/2026
```

Si una nueva regla aplicable al ciclo activo establece:

```text
6 meses
```

podrá requerirse determinar un nuevo objetivo:

```text
15/02/2027
```

sin modificar:

```text
FECHA REAL
DE LA INTERVENCIÓN:
15/08/2026
```

Cuando una modificación afecte únicamente un elemento de la regla, Vehículos Services deberá evitar modificar otros elementos que no hayan cambiado.

Por ejemplo:

```text
OBJETIVO:
75.000 km

MARGEN ANTERIOR:
500 km
```

Si únicamente cambia el margen a:

```text
1.000 km
```

podrá cambiar:

```text
UMBRAL ANTERIOR:
74.500 km

        ↓

NUEVO UMBRAL:
74.000 km
```

sin que necesariamente cambie:

```text
OBJETIVO:
75.000 km
```

Por lo tanto:

```text
CAMBIO DE
UN COMPONENTE
DE LA REGLA
        ↓
REEVALUAR LOS
RESULTADOS QUE
DEPENDAN DE ÉL

        ≠

MODIFICAR TODOS
LOS ELEMENTOS
DEL SEGUIMIENTO
```

La desactivación o sustitución de una regla tampoco deberá eliminar los registros históricos asociados a los ciclos en los cuales fue utilizada.

Conceptualmente:

```text
REGLA A
        ↓
UTILIZADA EN
CICLOS HISTÓRICOS
        ↓
POSTERIORMENTE
SUSTITUIDA POR
REGLA B
```

deberá conservar:

```text
CICLOS HISTÓRICOS
        ↓
REGLA A

CICLOS POSTERIORES
        ↓
REGLA B
```

cuando esa haya sido la aplicabilidad correspondiente.

Por lo tanto:

```text
REGLA YA NO
APLICABLE
        ≠
REGLA HISTÓRICAMENTE
INEXISTENTE
```

Vehículos Services deberá evitar que una modificación actual produzca una reinterpretación silenciosa del pasado.

La evolución de una regla también deberá permitir que una actividad deje de requerir determinado seguimiento cuando exista una condición válida que así lo establezca.

Conceptualmente:

```text
ACTIVIDAD
        ↓
TENÍA REGLA
DE SEGUIMIENTO

        ↓

CAMBIO VÁLIDO

        ↓

YA NO REQUIERE
ESE SEGUIMIENTO
```

Esta situación no deberá eliminar:

- Las intervenciones históricas.
- Los ciclos históricos.
- Los objetivos que fueron utilizados históricamente.
- La trazabilidad de las reglas anteriormente aplicadas.

Por lo tanto:

```text
FIN DE LA
APLICABILIDAD
DE UNA REGLA
        ≠
ELIMINACIÓN
DEL HISTORIAL
```

De igual manera, una actividad que anteriormente no requería seguimiento podrá comenzar a requerirlo cuando exista una regla válida aplicable.

Conceptualmente:

```text
ACTIVIDAD
SIN SEGUIMIENTO
        ↓
NUEVA REGLA
APLICABLE
        ↓
PUEDE COMENZAR
UN SEGUIMIENTO
```

La existencia de una nueva regla no deberá permitir inventar automáticamente una referencia histórica para iniciar el ciclo.

Si no existe información suficiente para determinar desde dónde debe comenzar el seguimiento:

```text
NUEVA REGLA
        +
REFERENCIA
DESCONOCIDA
        ↓
OBJETIVO
NO CALCULABLE
HASTA DISPONER
DE INFORMACIÓN
SUFICIENTE
```

Vehículos Services deberá aplicar los mismos principios de suficiencia de información definidos en los puntos anteriores.

Cuando existan diferentes reglas históricas para una misma actividad, deberá poder conservarse la secuencia correspondiente.

Por ejemplo:

```text
ACTIVIDAD:
Cambio de aceite

        ↓

REGLA A
Cada 5.000 km

        ↓

CICLOS
1 - 2 - 3

        ↓

CAMBIO DE REGLA

        ↓

REGLA B
Cada 7.500 km

        ↓

CICLOS
4 - 5 - 6
```

Conceptualmente:

```text
ACTIVIDAD
        ↓
EVOLUCIÓN DE
LAS REGLAS
        ↓
EVOLUCIÓN DE
LOS CICLOS
```

Esta trazabilidad deberá permitir comprender qué regla correspondía a cada ciclo sin convertir las reglas históricas en reglas actualmente aplicables.

La modificación de una regla tampoco deberá confundirse con la modificación de una intervención.

Por lo tanto:

```text
MODIFICAR REGLA
        ≠
MODIFICAR
INTERVENCIÓN

MODIFICAR REGLA
        ≠
CREAR NUEVA
INTERVENCIÓN

MODIFICAR REGLA
        ≠
ELIMINAR
INTERVENCIONES
ANTERIORES
```

Las intervenciones deberán continuar sujetas a las reglas generales del Historial Vehicular.

Cuando una modificación produzca cambios en resultados derivados, Vehículos Services deberá poder distinguir entre:

```text
DATO HISTÓRICO
REGISTRADO
        ↓
SE CONSERVA

        +

RESULTADO
DERIVADO
        ↓
PUEDE SER
REEVALUADO
```

Por ejemplo:

```text
INTERVENCIÓN:
70.000 km

        ↓
SE CONSERVA
```

mientras:

```text
OBJETIVO CALCULADO
        ↓
PUEDE CAMBIAR
SI CAMBIA VÁLIDAMENTE
LA REGLA APLICABLE
AL CICLO
```

Esta separación deberá impedir que los cálculos derivados sean tratados como si fueran hechos históricos inmutables y, al mismo tiempo, impedir que los hechos históricos sean modificados únicamente porque cambió una regla.

Las reglas tampoco deberán modificarse silenciosamente cuando su cambio pueda afectar el seguimiento de una actividad.

La plataforma deberá conservar información suficiente para identificar, cuando corresponda:

- Que una regla fue modificada.
- Cuál era la condición anterior.
- Cuál es la nueva condición.
- Desde cuándo corresponde la nueva definición.
- Qué ciclos o seguimientos resultan afectados.
- Los elementos necesarios para mantener la trazabilidad del cambio.

La definición técnica exacta de versiones, estructuras de almacenamiento, auditoría, identificadores o mecanismos de persistencia deberá establecerse posteriormente durante el diseño técnico y no deberá determinarse en este punto.

Conceptualmente:

```text
REGLA
        ↓
PUEDE EVOLUCIONAR
        ↓
CAMBIO CONTROLADO
        ↓
DETERMINAR
APLICABILIDAD
        ↓
CONSERVAR
TRAZABILIDAD
        ↓
REEVALUAR
ÚNICAMENTE LO
QUE CORRESPONDA
```

Como principio general:

```text
REGLA APLICABLE
        ↓
GENERA Y EVALÚA
UN CICLO
        ↓
LA REGLA PUEDE
CAMBIAR
        ↓
DETERMINAR SI
EL CAMBIO AFECTA
EL CICLO ACTUAL,
LOS FUTUROS
O AMBOS
        ↓
CONSERVAR
CONTEXTO HISTÓRICO
        ↓
APLICAR LA NUEVA
REGLA DONDE
CORRESPONDA
```

Vehículos Services deberá permitir la evolución controlada de las reglas de mantenimiento sin reescribir silenciosamente los ciclos, objetivos, intervenciones o resultados históricos, conservando la diferencia entre una modificación, una corrección y una sustitución de regla, y determinando expresamente la aplicabilidad de cada cambio sobre el seguimiento actual y futuro.

---
## 63.12 ALERTAS
### 63.12.1 Definición y propósito de una alerta

Una alerta deberá representar una condición identificada por Vehículos Services que requiere ser puesta en conocimiento del propietario debido a que existe una situación relevante relacionada con el vehículo, su seguimiento, mantenimiento u otro aspecto funcional que posteriormente pueda ser contemplado por la plataforma.

Conceptualmente:

```text
INFORMACIÓN DEL VEHÍCULO
        +
REGLAS APLICABLES
        +
CONDICIONES EVALUADAS
        ↓
SITUACIÓN RELEVANTE
IDENTIFICADA
        ↓
ALERTA
```

El propósito de una alerta será llamar la atención del propietario sobre una condición que merece ser conocida o atendida, permitiéndole identificar oportunamente situaciones derivadas de la información disponible en Vehículos Services.

Por ejemplo, dentro del seguimiento de una actividad de mantenimiento podrá existir:

```text
CAMBIO DE ACEITE
        ↓
OBJETIVO:
75.000 km
        ↓
KILOMETRAJE ACTUAL:
74.300 km
        ↓
REGLA Y CONDICIONES
APLICABLES
        ↓
SE IDENTIFICA UNA
SITUACIÓN RELEVANTE
        ↓
PUEDE ORIGINARSE
UNA ALERTA
```

La existencia de una condición evaluada no deberá significar automáticamente que siempre deba generarse una alerta.

Deberá existir una condición funcional que determine cuándo un determinado resultado requiere ser comunicado al propietario mediante una alerta.

Por lo tanto:

```text
RESULTADO DE UNA
EVALUACIÓN
        ≠
ALERTA AUTOMÁTICA
EN TODOS LOS CASOS
```

Una alerta deberá derivarse de información disponible y de condiciones funcionales aplicables, evitando generar afirmaciones que no puedan sustentarse con los datos existentes.

Cuando la información disponible sea insuficiente, Vehículos Services no deberá inventar datos con el propósito de generar una alerta.

Conceptualmente:

```text
INFORMACIÓN
DISPONIBLE
        ↓
EVALUACIÓN
        ↓
CONDICIÓN
SUSTENTABLE
        ↓
ALERTA
CUANDO CORRESPONDA
```

Una alerta deberá diferenciarse de la condición que la originó.

Por ejemplo:

```text
CONDICIÓN DETECTADA:
Cambio de aceite próximo
a su objetivo
        ↓
PUEDE ORIGINAR
        ↓
ALERTA
```

Por lo tanto:

```text
CONDICIÓN DETECTADA
        ≠
ALERTA
```

La condición corresponde al resultado funcional identificado por la plataforma, mientras que la alerta corresponde al mecanismo mediante el cual dicha situación se pone en conocimiento del propietario dentro del contexto funcional de Vehículos Services.

La alerta tampoco deberá confundirse con una recomendación.

Una recomendación podrá orientar al propietario respecto de una acción que podría considerar, mientras que una alerta deberá comunicar principalmente la existencia de una condición relevante identificada.

Conceptualmente:

```text
ALERTA
        ↓
INFORMA SOBRE UNA
CONDICIÓN RELEVANTE

RECOMENDACIÓN
        ↓
ORIENTA SOBRE UNA
POSIBLE ACCIÓN
```

Por lo tanto:

```text
ALERTA
        ≠
RECOMENDACIÓN
```

Una misma situación podrá posteriormente originar tanto una alerta como una recomendación cuando las reglas funcionales correspondientes así lo determinen, sin que ambos conceptos deban considerarse equivalentes.

Una alerta tampoco deberá interpretarse como un diagnóstico mecánico, una evaluación profesional ni una certificación sobre el estado real del vehículo o de alguno de sus componentes.

Por ejemplo, una alerta que indique que una actividad de mantenimiento alcanzó o se aproxima a su objetivo deberá representar el resultado del seguimiento realizado por Vehículos Services con base en la información disponible.

No deberá significar automáticamente que el componente relacionado:

- Se encuentre averiado.
- Se encuentre en mal estado.
- Haya fallado.
- Sea inseguro.
- Requiera necesariamente una reparación específica.

Por lo tanto:

```text
ALERTA
        ≠
DIAGNÓSTICO

ALERTA
        ≠
EVALUACIÓN PROFESIONAL

ALERTA
        ≠
CERTIFICACIÓN DEL
ESTADO DEL VEHÍCULO
```

La existencia de una alerta tampoco deberá significar que la intervención relacionada haya sido realizada.

Conceptualmente:

```text
ALERTA DE
MANTENIMIENTO
        ≠
MANTENIMIENTO
REALIZADO
```

La realización efectiva de una intervención deberá continuar dependiendo de la información válida registrada sobre el evento correspondiente y no de la existencia, visualización o tratamiento de una alerta.

Una alerta también deberá diferenciarse de una notificación.

La alerta representa la condición comunicable que existe dentro del funcionamiento de Vehículos Services, mientras que una notificación corresponde al mecanismo mediante el cual determinada información podrá ser comunicada al propietario a través de un canal específico cuando corresponda.

Conceptualmente:

```text
CONDICIÓN RELEVANTE
        ↓
ALERTA
        ↓
PUEDE ORIGINAR
UNA NOTIFICACIÓN
CUANDO CORRESPONDA
```

Por lo tanto:

```text
ALERTA
        ≠
NOTIFICACIÓN
```

La existencia de una alerta no deberá implicar automáticamente que deba enviarse una notificación por todos los canales disponibles ni que necesariamente deba producirse una comunicación externa a la plataforma.

Los canales, condiciones de envío, frecuencia, destinatarios y demás comportamientos relacionados con las notificaciones deberán definirse posteriormente en el componente funcional correspondiente.

De igual manera, este punto no deberá definir todavía:

- Las condiciones específicas que originan cada tipo de alerta.
- Los niveles de prioridad o relevancia.
- La duración o vigencia de una alerta.
- Las condiciones para actualizarla, resolverla o cerrarla.
- Su conservación histórica.
- Los canales utilizados para comunicarla.
- La frecuencia de las notificaciones.
- Su representación visual.
- Colores, iconos o componentes de interfaz.
- La estructura técnica utilizada para almacenarla.
- Los mecanismos técnicos utilizados para procesarla.

Estos aspectos deberán desarrollarse en los puntos posteriores de `63.12 ALERTAS` y en los demás componentes funcionales o técnicos que correspondan.

Como principio general:

```text
INFORMACIÓN DISPONIBLE
        ↓
REGLAS Y CONDICIONES
APLICABLES
        ↓
EVALUACIÓN
        ↓
CONDICIÓN RELEVANTE
        ↓
ALERTA
        │
        ├── Puede relacionarse
        │   con una recomendación
        │
        └── Puede posteriormente
            originar una notificación
            cuando corresponda
```

Vehículos Services deberá utilizar las alertas para poner en conocimiento del propietario condiciones relevantes identificadas a partir de la información disponible y las reglas aplicables, manteniendo diferenciadas la condición que origina la alerta, la alerta generada, las recomendaciones que puedan derivarse, las notificaciones utilizadas para comunicar información y las intervenciones efectivamente realizadas sobre el vehículo.

---
### 63.12.2 Condiciones que pueden originar una alerta

Una alerta podrá originarse cuando Vehículos Services identifique, a partir de información disponible y reglas aplicables, una condición relevante que deba ser puesta en conocimiento del propietario.

La generación de una alerta deberá estar sustentada en una condición identificable y no únicamente en la existencia de información relacionada con el vehículo.

Conceptualmente:

```text
INFORMACIÓN DISPONIBLE
        +
REGLA O CONDICIÓN
APLICABLE
        ↓
EVALUACIÓN
        ↓
¿EXISTE UNA SITUACIÓN
QUE REQUIERE ALERTA?
        │
    ┌───┴───┐
    ↓       ↓
   SÍ       NO
    │       │
    ↓       ↓
ALERTA     SIN ALERTA
```

Por lo tanto:

```text
EXISTENCIA DE INFORMACIÓN
        ≠
EXISTENCIA AUTOMÁTICA
DE UNA ALERTA
```

Las condiciones que puedan originar alertas deberán depender de la naturaleza del elemento evaluado y de las reglas funcionales aplicables en cada caso.

Dentro del seguimiento de mantenimiento, una alerta podrá originarse, por ejemplo, cuando una actividad:

- Se encuentre próxima a un objetivo de seguimiento.
- Haya alcanzado un objetivo de seguimiento.
- Haya superado un objetivo de seguimiento.
- Presente otra condición que posteriormente sea definida como relevante para generar una alerta.

Por ejemplo:

```text
ACTIVIDAD:
Cambio de aceite

OBJETIVO:
75.000 km

MARGEN DE PROXIMIDAD:
1.000 km

KILOMETRAJE ACTUAL:
74.300 km

        ↓

CONDICIÓN:
DENTRO DEL MARGEN
DE PROXIMIDAD

        ↓

REGLA DE ALERTA
APLICABLE

        ↓

ALERTA
CUANDO CORRESPONDA
```

En este escenario, la alerta no deberá originarse simplemente porque exista un próximo objetivo de `75.000 km`.

La generación de la alerta dependerá de que la evaluación produzca una condición para la cual exista un comportamiento de alerta aplicable.

Conceptualmente:

```text
OBJETIVO EXISTENTE
        ≠
ALERTA AUTOMÁTICA
```

De igual manera:

```text
OBJETIVO:
75.000 km

KILOMETRAJE ACTUAL:
75.300 km

        ↓

OBJETIVO SUPERADO
        ↓
REGLA DE ALERTA
APLICABLE
        ↓
ALERTA
CUANDO CORRESPONDA
```

La misma lógica deberá poder aplicarse al seguimiento por tiempo.

Por ejemplo:

```text
PRÓXIMA FECHA OBJETIVO:
15/11/2026

FECHA DE EVALUACIÓN:
05/11/2026

MARGEN DE PROXIMIDAD:
15 días

        ↓

CONDICIÓN:
DENTRO DEL MARGEN
DE PROXIMIDAD

        ↓

PUEDE ORIGINARSE
UNA ALERTA
```

Cuando una actividad tenga seguimiento combinado por kilometraje y tiempo, las condiciones individuales deberán conservarse de acuerdo con lo definido en `63.11.4 Combinación de kilometraje y tiempo`.

La generación de una alerta deberá respetar la lógica de combinación definida por la regla aplicable.

Por ejemplo:

```text
CAMBIO DE ACEITE

REGLA:
5.000 km
O
3 meses

        ↓

CONDICIÓN POR KM:
DENTRO DEL MARGEN
DE PROXIMIDAD

CONDICIÓN POR TIEMPO:
ANTES DEL UMBRAL

        ↓

EVALUACIÓN DE LA
REGLA COMBINADA

        ↓

ALERTA
CUANDO CORRESPONDA
```

La existencia de dos condiciones de seguimiento tampoco deberá significar automáticamente que deban generarse dos alertas independientes.

La forma en que las condiciones relacionadas con una misma actividad se representen mediante una o varias alertas deberá responder a las reglas funcionales que posteriormente correspondan, evitando duplicaciones innecesarias para una misma situación.

Por lo tanto:

```text
DOS CONDICIONES
EVALUADAS
        ≠
DOS ALERTAS
OBLIGATORIAS
```

Las alertas no deberán limitarse exclusivamente al mantenimiento.

Vehículos Services deberá permitir conceptualmente que otros componentes funcionales puedan originar alertas cuando exista una condición relevante definida por sus propias reglas.

Por ejemplo, podrán existir posteriormente condiciones relacionadas con:

- Documentos del vehículo.
- Abastecimiento o consumo energético.
- Preparación para viajes.
- Información pendiente o relevante para el seguimiento.
- Otras funcionalidades incorporadas a la plataforma.

La inclusión de estos escenarios no deberá significar que cualquier dato faltante, documento registrado, abastecimiento realizado o evento del vehículo genere automáticamente una alerta.

Cada componente deberá establecer las condiciones bajo las cuales una determinada situación puede considerarse relevante para alertar al propietario.

Conceptualmente:

```text
MANTENIMIENTO
        │
DOCUMENTOS
        │
ABASTECIMIENTO
        │
VIAJES
        │
OTROS COMPONENTES
        ↓
REGLAS PROPIAS
DE CADA COMPONENTE
        ↓
CONDICIONES
RELEVANTES
        ↓
ALERTAS
CUANDO CORRESPONDA
```

Una alerta podrá depender de información histórica, información actual o de la evaluación conjunta de diferentes datos, siempre que exista una regla funcional que permita sustentar la condición identificada.

Sin embargo, la plataforma no deberá convertir automáticamente la ausencia de información en una condición negativa.

Por ejemplo:

```text
FECHA DEL ÚLTIMO CAMBIO
DE UN COMPONENTE:
DESCONOCIDA
```

no deberá interpretarse automáticamente como:

```text
COMPONENTE VENCIDO
```

ni como:

```text
MANTENIMIENTO NO REALIZADO
```

ni necesariamente como:

```text
ALERTA DE MANTENIMIENTO
VENCIDO
```

La ausencia de información deberá mantenerse diferenciada de una condición que haya podido ser efectivamente determinada.

Por lo tanto:

```text
INFORMACIÓN DESCONOCIDA
        ≠
CONDICIÓN NEGATIVA
CONFIRMADA
```

Cuando la falta de información sea por sí misma una situación que deba ser comunicada al propietario, deberá existir una condición funcional específica que permita generar una alerta relacionada con dicha ausencia.

Por ejemplo, conceptualmente podrá definirse:

```text
INFORMACIÓN NECESARIA
PARA UN SEGUIMIENTO
        ↓
NO DISPONIBLE
        ↓
REGLA ESPECÍFICA:
INFORMACIÓN REQUERIDA
NO DISPONIBLE
        ↓
ALERTA INFORMATIVA
CUANDO CORRESPONDA
```

En este caso, la alerta deberá comunicar la falta de información y no transformar dicha ausencia en una afirmación sobre el estado real del vehículo.

De igual manera, una inconsistencia o información pendiente de validación no deberá utilizarse automáticamente como si fuera información confirmada para generar una alerta sobre el estado del elemento evaluado.

Podrá existir, cuando las reglas funcionales así lo definan, una alerta relacionada específicamente con la inconsistencia o necesidad de revisión de la información.

Conceptualmente:

```text
INFORMACIÓN
INCONSISTENTE
        ↓
NO UTILIZAR COMO
HECHO CONFIRMADO
        ↓
PUEDE ORIGINAR
UNA ALERTA SOBRE
LA INFORMACIÓN
CUANDO CORRESPONDA
```

Por lo tanto, deberá mantenerse diferenciada:

```text
ALERTA SOBRE EL
ESTADO DEL VEHÍCULO
        ≠
ALERTA SOBRE LA
CALIDAD O AUSENCIA
DE INFORMACIÓN
```

Una condición que anteriormente hubiera originado una alerta podrá dejar de cumplir las condiciones que la generaron como consecuencia de nueva información, una intervención realizada, una corrección válida, una modificación de una regla u otro evento funcional aplicable.

Sin embargo, la forma en que una alerta deberá actualizarse, resolverse o cerrarse como consecuencia de estos cambios no deberá definirse en este punto y corresponderá a los puntos posteriores de `63.12 ALERTAS`.

Este punto tampoco deberá definir:

- La prioridad de cada alerta.
- Su nivel de relevancia.
- Su duración.
- Su vigencia.
- Su cierre o resolución.
- La cantidad de veces que debe mostrarse.
- Si debe generar una notificación.
- El canal mediante el cual podría notificarse.
- Su representación visual.
- Su estructura técnica o mecanismo de almacenamiento.

Como principio general:

```text
INFORMACIÓN
        ↓
REGLA APLICABLE
        ↓
EVALUACIÓN
        ↓
CONDICIÓN IDENTIFICADA
        ↓
¿LA CONDICIÓN ESTÁ
DEFINIDA PARA ALERTAR?
        │
    ┌───┴───┐
    ↓       ↓
   SÍ       NO
    │       │
    ↓       ↓
ALERTA     SIN ALERTA
```

Vehículos Services deberá generar alertas únicamente cuando exista una condición funcional sustentable que determine que una situación relevante debe ser puesta en conocimiento del propietario, evitando convertir automáticamente cualquier dato, ausencia de información, objetivo de seguimiento o resultado de evaluación en una alerta.

---

### 63.12.3 Relación entre reglas, evaluación y alertas

La generación de una alerta deberá entenderse como el resultado de una secuencia funcional en la que intervienen, de manera diferenciada, la información disponible, las reglas aplicables, la evaluación de dicha información y las condiciones definidas para generar alertas.

Conceptualmente:

```text
INFORMACIÓN DISPONIBLE
        ↓
REGLA APLICABLE
        ↓
EVALUACIÓN
        ↓
RESULTADO O CONDICIÓN
IDENTIFICADA
        ↓
REGLA O CONDICIÓN
DE ALERTA APLICABLE
        ↓
ALERTA
CUANDO CORRESPONDA
```

Estos elementos deberán mantenerse diferenciados.

Por lo tanto:

```text
REGLA
   ≠
EVALUACIÓN
   ≠
RESULTADO DE LA EVALUACIÓN
   ≠
ALERTA
```

Una regla deberá establecer las condiciones funcionales utilizadas para realizar determinado seguimiento o evaluación.

La evaluación deberá aplicar dichas condiciones sobre la información disponible.

El resultado de la evaluación deberá representar la condición identificada.

La alerta solamente deberá generarse cuando dicho resultado cumpla las condiciones establecidas para alertar al propietario.

Por ejemplo:

```text
ACTIVIDAD:
Cambio de aceite

REGLA DE MANTENIMIENTO:
Cada 5.000 km

KILOMETRAJE DE REFERENCIA:
70.000 km

PRÓXIMO OBJETIVO:
75.000 km

MARGEN DE PROXIMIDAD:
1.000 km

KILOMETRAJE ACTUAL:
74.300 km
```

La evaluación podrá determinar:

```text
UMBRAL DE PROXIMIDAD:
74.000 km

KILOMETRAJE ACTUAL:
74.300 km

        ↓

RESULTADO:
DENTRO DEL MARGEN
DE PROXIMIDAD
```

Si existe una condición aplicable que determine que este resultado debe originar una alerta:

```text
RESULTADO:
DENTRO DEL MARGEN
DE PROXIMIDAD
        ↓
CONDICIÓN DE ALERTA
APLICABLE
        ↓
ALERTA:
CAMBIO DE ACEITE
PRÓXIMO A SU OBJETIVO
```

En este caso, la regla de mantenimiento permitió determinar y evaluar el objetivo, mientras que la condición de alerta determinó que el resultado obtenido debía ser puesto en conocimiento del propietario.

Por lo tanto:

```text
REGLA DE MANTENIMIENTO
        ↓
PERMITE REALIZAR
EL SEGUIMIENTO

CONDICIÓN DE ALERTA
        ↓
DETERMINA CUÁNDO
UN RESULTADO REQUIERE
GENERAR UNA ALERTA
```

La existencia de una regla de mantenimiento no deberá implicar automáticamente la existencia de una alerta.

Por ejemplo:

```text
REGLA:
Cambio de aceite
cada 5.000 km

        ≠

ALERTA PERMANENTE
POR CAMBIO DE ACEITE
```

Mientras la evaluación no produzca una condición definida para alertar, podrá existir seguimiento sin que exista una alerta asociada.

Conceptualmente:

```text
ACTIVIDAD CON
SEGUIMIENTO
        ↓
EVALUACIÓN
        ↓
CONDICIÓN QUE NO
REQUIERE ALERTA
        ↓
SIN ALERTA
```

De igual manera, alcanzar o superar un objetivo no deberá convertirse por sí solo en una alerta si no existe una condición funcional aplicable que determine dicho comportamiento.

Esto permite mantener diferenciados:

```text
QUÉ SE EVALÚA
        ↓
REGLAS DEL COMPONENTE

QUÉ RESULTADO SE OBTIENE
        ↓
EVALUACIÓN

CUÁNDO SE ALERTA
        ↓
CONDICIONES DE ALERTA
```

Esta separación deberá permitir que una misma condición evaluada pueda tener diferentes tratamientos funcionales según corresponda.

Por ejemplo, una condición podrá:

- No requerir ninguna alerta.
- Originar una alerta.
- Relacionarse con una recomendación.
- Originar posteriormente una notificación cuando corresponda.
- Participar en otros comportamientos funcionales definidos en el futuro.

Por lo tanto:

```text
CONDICIÓN IDENTIFICADA
        ↓
NO DETERMINA POR SÍ SOLA
TODAS LAS ACCIONES
POSTERIORES
```

Cuando una alerta dependa de una regla de mantenimiento, deberá utilizar los resultados obtenidos conforme a las reglas definidas en `63.11 REGLAS DE MANTENIMIENTO`, sin alterar la lógica mediante la cual fueron determinados.

Por ejemplo, si `63.11` determina:

```text
PRÓXIMO OBJETIVO:
75.000 km
```

el componente de alertas no deberá modificar dicho objetivo para producir una alerta.

Por lo tanto:

```text
OBJETIVO DETERMINADO:
75.000 km

        ↓

ALERTA UTILIZA
EL RESULTADO

        ≠

ALERTA MODIFICA
EL OBJETIVO
```

La misma separación deberá mantenerse respecto de los márgenes de proximidad y tolerancias definidos conforme a las reglas aplicables.

Una alerta podrá utilizar una condición de proximidad previamente determinada, pero no deberá redefinir por sí misma el objetivo, intervalo, referencia, margen o tolerancia que dio origen a dicha evaluación.

Conceptualmente:

```text
REGLAS DE
MANTENIMIENTO
        ↓
DETERMINAN Y EVALÚAN
LAS CONDICIONES
        ↓
ALERTAS
        ↓
UTILIZAN LOS RESULTADOS
CUANDO CORRESPONDA
```

Cuando una actividad tenga seguimiento combinado por kilometraje y tiempo, la generación de alertas deberá respetar el resultado de la evaluación combinada y las condiciones individuales determinadas conforme a `63.11.4 Combinación de kilometraje y tiempo`.

El componente de alertas no deberá alterar la lógica de combinación definida para la actividad.

Por ejemplo:

```text
REGLA:
5.000 km O 3 meses
        ↓
EVALUACIÓN DE
AMBAS CONDICIONES
        ↓
RESULTADO SEGÚN
LA REGLA APLICABLE
        ↓
CONDICIÓN DE ALERTA
        ↓
ALERTA
CUANDO CORRESPONDA
```

Por lo tanto:

```text
LÓGICA DE COMBINACIÓN
        ↓
PERTENECE A LA REGLA
DE SEGUIMIENTO

GENERACIÓN DE ALERTA
        ↓
UTILIZA EL RESULTADO
DE ESA EVALUACIÓN
```

Cuando una condición no pueda ser determinada por falta de información suficiente, el componente de alertas no deberá completar, asumir o inventar el resultado faltante con el propósito de generar una alerta.

Por ejemplo:

```text
REGLA:
Cada 5.000 km

KILOMETRAJE DE
REFERENCIA:
DESCONOCIDO

        ↓

NO ES POSIBLE
DETERMINAR EL
PRÓXIMO OBJETIVO

        ↓

NO INVENTAR
OBJETIVO

        ↓

NO GENERAR UNA ALERTA
BASADA EN UN OBJETIVO
INEXISTENTE
```

Esto no impedirá que pueda existir una alerta diferente relacionada específicamente con la ausencia de información cuando dicha situación tenga su propia condición funcional de alerta, conforme a lo establecido en `63.12.2 Condiciones que pueden originar una alerta`.

Por lo tanto:

```text
NO PUEDO DETERMINAR
EL OBJETIVO
        ≠
OBJETIVO VENCIDO
```

pero podrá existir, cuando corresponda:

```text
INFORMACIÓN NECESARIA
NO DISPONIBLE
        ↓
CONDICIÓN ESPECÍFICA
DE ALERTA
        ↓
ALERTA SOBRE
INFORMACIÓN FALTANTE
```

La generación de una alerta tampoco deberá modificar el resultado que la originó.

Por ejemplo, si una actividad se encuentra dentro del margen de proximidad:

```text
CONDICIÓN:
DENTRO DEL MARGEN
DE PROXIMIDAD
        ↓
GENERA ALERTA
```

la creación de la alerta no deberá transformar la condición en:

```text
OBJETIVO ALCANZADO
```

ni en:

```text
OBJETIVO SUPERADO
```

La condición solamente deberá cambiar cuando nueva información o una nueva evaluación válida determine un resultado diferente.

Conceptualmente:

```text
ALERTA GENERADA
        ≠
CAMBIO DE LA
CONDICIÓN EVALUADA
```

De igual manera, la visualización, lectura o tratamiento de una alerta por parte del propietario no deberá modificar automáticamente la condición funcional que la originó.

Por ejemplo:

```text
PROPIETARIO
CONSULTA LA ALERTA
        ↓
ALERTA VISUALIZADA
```

no deberá significar:

```text
MANTENIMIENTO
REALIZADO
```

ni:

```text
CONDICIÓN
RESUELTA
```

ni:

```text
NUEVO CICLO DE
MANTENIMIENTO
```

Una nueva intervención, una actualización válida de información, una corrección, una modificación de regla u otro evento funcional aplicable podrá provocar una nueva evaluación y, como consecuencia, modificar la condición relacionada con una alerta.

Conceptualmente:

```text
NUEVA INFORMACIÓN
O EVENTO VÁLIDO
        ↓
NUEVA EVALUACIÓN
        ↓
NUEVO RESULTADO
        ↓
REEVALUACIÓN DE
LA ALERTA
```

La forma específica en que una alerta existente deberá permanecer vigente, actualizarse, resolverse o cerrarse como consecuencia de estos cambios deberá definirse en los puntos posteriores de `63.12 ALERTAS`.

Como principio general:

```text
REGLA
        ↓
DEFINE QUÉ Y CÓMO
SE EVALÚA
        ↓
EVALUACIÓN
        ↓
DETERMINA UNA
CONDICIÓN
        ↓
CONDICIÓN DE ALERTA
        ↓
DETERMINA SI ESA
SITUACIÓN REQUIERE
ALERTAR
        ↓
ALERTA
        ↓
PONE LA SITUACIÓN
EN CONOCIMIENTO
DEL PROPIETARIO
```

Vehículos Services deberá mantener separadas las responsabilidades de las reglas, la evaluación y las alertas, de manera que una alerta utilice resultados funcionales previamente determinados sin modificar, sustituir o reinterpretar arbitrariamente las condiciones que dieron origen a dichos resultados.

---
### 63.12.4 Ciclo de vida y vigencia de una alerta

Una alerta deberá tener un ciclo de vida relacionado con la condición que le dio origen.

La existencia de una alerta no deberá considerarse permanente por el solo hecho de haber sido generada. Su vigencia deberá depender de la evolución de la condición asociada y de las reglas funcionales aplicables.

Conceptualmente:

```text
CONDICIÓN RELEVANTE
IDENTIFICADA
        ↓
GENERACIÓN DE
LA ALERTA
        ↓
ALERTA VIGENTE
        ↓
NUEVA INFORMACIÓN
O EVENTO
        ↓
REEVALUACIÓN
        ↓
LA ALERTA PUEDE
CONTINUAR, CAMBIAR
O DEJAR DE ESTAR VIGENTE
```

Por lo tanto:

```text
ALERTA GENERADA
        ≠
ALERTA PERMANENTE
```

La vigencia de una alerta deberá representar que la condición que justificó su existencia continúa siendo relevante de acuerdo con la información disponible y las reglas aplicables.

Por ejemplo:

```text
CAMBIO DE ACEITE

OBJETIVO:
75.000 km

KILOMETRAJE ACTUAL:
74.300 km

        ↓

CONDICIÓN:
DENTRO DEL MARGEN
DE PROXIMIDAD

        ↓

ALERTA GENERADA
        ↓
ALERTA VIGENTE
```

Si posteriormente el kilometraje actual cambia a:

```text
75.300 km
```

la condición deberá ser evaluada nuevamente.

Conceptualmente:

```text
ALERTA EXISTENTE
        +
NUEVA INFORMACIÓN
        ↓
NUEVA EVALUACIÓN
        ↓
OBJETIVO SUPERADO
```

En este escenario, la alerta no deberá continuar representando una condición de proximidad como si nada hubiera cambiado.

La plataforma deberá poder reconocer que la situación funcional evolucionó.

Por lo tanto:

```text
CONDICIÓN ANTERIOR:
PRÓXIMO AL OBJETIVO

        ↓

NUEVA EVALUACIÓN

        ↓

CONDICIÓN ACTUAL:
OBJETIVO SUPERADO
```

La evolución de la condición podrá requerir que la alerta relacionada también evolucione conforme a las reglas funcionales aplicables.

Esto no deberá interpretarse necesariamente como la creación obligatoria de una alerta completamente independiente cada vez que cambie una condición.

Deberá evitarse que la evolución normal de una misma situación produzca duplicaciones innecesarias.

Por ejemplo:

```text
CAMBIO DE ACEITE
        ↓
PRÓXIMO AL OBJETIVO
        ↓
OBJETIVO ALCANZADO
        ↓
OBJETIVO SUPERADO
```

representa la evolución del seguimiento de una misma actividad.

Por lo tanto:

```text
EVOLUCIÓN DE UNA
MISMA CONDICIÓN
        ≠
NUEVA ALERTA
INDEPENDIENTE
OBLIGATORIA EN
CADA ETAPA
```

La decisión sobre si una alerta existente debe mantenerse, actualizarse o dar lugar a otra alerta deberá depender de las reglas funcionales correspondientes.

La vigencia de una alerta tampoco deberá depender únicamente del tiempo transcurrido desde su generación.

Una alerta podrá continuar vigente mientras la condición que la sustenta continúe siendo relevante, salvo que exista una regla específica que determine otro comportamiento.

Por lo tanto:

```text
ANTIGÜEDAD DE
LA ALERTA
        ≠
PÉRDIDA AUTOMÁTICA
DE VIGENCIA
```

Por ejemplo, si existe una alerta asociada a un mantenimiento cuyo objetivo fue superado, el simple transcurso de varios días no deberá permitir asumir que el mantenimiento fue realizado.

Conceptualmente:

```text
OBJETIVO SUPERADO
        ↓
ALERTA

PASAN VARIOS DÍAS
        ↓
NO EXISTE REGISTRO
DE NUEVA INTERVENCIÓN
        ↓
NO ASUMIR QUE
LA SITUACIÓN FUE
SOLUCIONADA
```

De igual manera:

```text
PASO DEL TIEMPO
        ≠
INTERVENCIÓN REALIZADA
```

La consulta o visualización de una alerta por parte del propietario tampoco deberá provocar automáticamente la pérdida de su vigencia.

Por ejemplo:

```text
PROPIETARIO
CONSULTA LA ALERTA
        ↓
ALERTA VISUALIZADA
```

no deberá significar automáticamente:

```text
ALERTA RESUELTA
```

ni:

```text
CONDICIÓN RESUELTA
```

ni:

```text
MANTENIMIENTO
REALIZADO
```

Por lo tanto:

```text
ALERTA VISUALIZADA
        ≠
ALERTA RESUELTA
```

La visualización representa únicamente que el propietario tuvo acceso a la información correspondiente, sin demostrar que la situación que originó la alerta haya cambiado.

Cuando se produzca nueva información relevante, Vehículos Services deberá poder reevaluar la condición relacionada con una alerta.

Dicha información podrá provenir, según el contexto funcional correspondiente, de situaciones como:

- Una nueva intervención registrada.
- Una actualización válida del kilometraje.
- El avance del tiempo.
- La incorporación posterior de información histórica.
- Una corrección válida de información.
- Una modificación de una regla aplicable.
- Un cambio relacionado con el elemento que originó la alerta.
- Otros eventos funcionales que posteriormente puedan definirse.

Conceptualmente:

```text
ALERTA VIGENTE
        ↓
NUEVA INFORMACIÓN
        ↓
REEVALUACIÓN
        ↓
CONDICIÓN ACTUAL
        ↓
REEVALUACIÓN DE
LA VIGENCIA DE
LA ALERTA
```

La reevaluación deberá utilizar la información válida disponible en ese momento y no deberá alterar arbitrariamente la información histórica que dio origen a evaluaciones anteriores.

Por ejemplo, una alerta generada cuando el vehículo tenía `74.300 km` pudo haber sido válida de acuerdo con la información disponible en ese momento.

Si posteriormente el vehículo registra `75.300 km`, la nueva evaluación podrá producir una condición diferente.

Esto no significa que la evaluación anterior haya sido necesariamente incorrecta.

Conceptualmente:

```text
EVALUACIÓN ANTERIOR
        ↓
VÁLIDA SEGÚN LA
INFORMACIÓN DISPONIBLE
EN ESE MOMENTO

NUEVA INFORMACIÓN
        ↓
NUEVA EVALUACIÓN
        ↓
NUEVA CONDICIÓN
```

Por lo tanto:

```text
CAMBIO DE CONDICIÓN
        ≠
ERROR EN LA
CONDICIÓN ANTERIOR
```

Esta distinción permitirá conservar la coherencia entre la evolución real del seguimiento y el historial de las alertas.

Cuando una nueva intervención válida corresponda a la actividad que originó una alerta de mantenimiento, dicha intervención podrá modificar la condición que sustentaba la alerta.

Por ejemplo:

```text
CAMBIO DE ACEITE

OBJETIVO ANTERIOR:
75.000 km

KILOMETRAJE ACTUAL:
75.300 km

        ↓

ALERTA RELACIONADA
CON OBJETIVO SUPERADO

        ↓

SE REALIZA Y REGISTRA
VÁLIDAMENTE EL
CAMBIO DE ACEITE
A LOS 75.300 km

        ↓

NUEVA REFERENCIA
CUANDO CORRESPONDA

        ↓

NUEVO CICLO DE
SEGUIMIENTO
```

En este escenario, la alerta correspondiente al ciclo anterior no deberá mantenerse indefinidamente como si la intervención no hubiera ocurrido.

Sin embargo, deberá mantenerse la separación entre:

```text
NUEVA INTERVENCIÓN
        ↓
MODIFICA LA CONDICIÓN
FUNCIONAL

        ≠

ELIMINACIÓN DEL
HECHO HISTÓRICO
DE QUE EXISTIÓ
UNA ALERTA
```

La pérdida de vigencia de una alerta no deberá implicar necesariamente la eliminación de su existencia histórica.

Conceptualmente:

```text
ALERTA DEJA DE
ESTAR VIGENTE
        ≠
ALERTA NUNCA EXISTIÓ
```

Esta separación será necesaria para permitir posteriormente la trazabilidad de las situaciones que fueron identificadas durante la vida del vehículo.

La conservación histórica de las alertas y la información necesaria para su trazabilidad se desarrollará específicamente en `63.12.7 Historial y trazabilidad de alertas`.

Cuando una regla aplicable sea modificada, la vigencia de las alertas relacionadas deberá evaluarse de acuerdo con el efecto funcional que dicha modificación tenga sobre el seguimiento correspondiente.

No deberá asumirse automáticamente que:

```text
REGLA MODIFICADA
        =
TODAS LAS ALERTAS
ANTERIORES DEJAN
DE SER VÁLIDAS
```

ni tampoco que:

```text
REGLA MODIFICADA
        =
TODAS LAS ALERTAS
ANTERIORES DEBEN
PERMANECER VIGENTES
```

El comportamiento deberá depender de la aplicabilidad de la modificación y de la nueva evaluación que corresponda, respetando los principios definidos en `63.11.8 Modificación y evolución de las reglas`.

Una alerta también podrá perder vigencia como consecuencia de una corrección válida de información.

Por ejemplo, si una alerta fue generada a partir de un kilometraje que posteriormente se determina que fue registrado incorrectamente:

```text
KILOMETRAJE
REGISTRADO:
75.300 km

        ↓
ALERTA

        ↓
CORRECCIÓN VÁLIDA:
73.300 km

        ↓
NUEVA EVALUACIÓN
```

la condición deberá volver a evaluarse con la información corregida.

Esto no deberá significar que el registro anterior deba desaparecer sin trazabilidad.

Por lo tanto:

```text
CORRECCIÓN DE
INFORMACIÓN
        ↓
PUEDE MODIFICAR
LA VIGENCIA DE
UNA ALERTA

        ≠

BORRADO SILENCIOSO
DE LA HISTORIA
```

La existencia de varias alertas relacionadas con un mismo vehículo tampoco deberá provocar que todas compartan automáticamente el mismo ciclo de vida.

Cada alerta deberá conservar relación con la condición que la originó.

Por ejemplo:

```text
VEHÍCULO
   │
   ├── Alerta relacionada
   │   con cambio de aceite
   │
   ├── Alerta relacionada
   │   con otro mantenimiento
   │
   └── Alerta relacionada
       con otro componente
       funcional
```

La modificación de la condición correspondiente a una de ellas no deberá resolver automáticamente las demás.

Por lo tanto:

```text
RESOLUCIÓN DE UNA
CONDICIÓN
        ≠
RESOLUCIÓN AUTOMÁTICA
DE TODAS LAS ALERTAS
DEL VEHÍCULO
```

El ciclo de vida conceptual de una alerta podrá representarse de manera general como:

```text
CONDICIÓN RELEVANTE
IDENTIFICADA
        ↓
ALERTA GENERADA
        ↓
ALERTA VIGENTE
        ↓
NUEVA INFORMACIÓN
O EVENTO
        ↓
REEVALUACIÓN
        ↓
┌──────────────────────────────┐
│ LA CONDICIÓN CONTINÚA        │
│ → LA ALERTA PUEDE CONTINUAR  │
│                              │
│ LA CONDICIÓN EVOLUCIONA      │
│ → LA ALERTA PUEDE CAMBIAR    │
│                              │
│ LA CONDICIÓN DEJA DE APLICAR │
│ → LA ALERTA PUEDE DEJAR      │
│   DE ESTAR VIGENTE           │
└──────────────────────────────┘
```

Este ciclo representa el comportamiento funcional general y no deberá utilizarse todavía para establecer estados técnicos, códigos internos o estructuras de almacenamiento.

En particular, este punto no deberá definir todavía:

- Los niveles de prioridad de una alerta.
- La clasificación de su relevancia.
- Las acciones específicas mediante las cuales se considera resuelta.
- Los mecanismos mediante los cuales se realiza su cierre.
- Su tratamiento histórico detallado.
- Los canales de notificación.
- La frecuencia de las notificaciones.
- Su representación visual.
- Estados técnicos de base de datos.
- Identificadores, tablas o estructuras de almacenamiento.

Estos aspectos deberán desarrollarse en los puntos posteriores de `63.12 ALERTAS` o en los componentes funcionales y técnicos correspondientes.

Como principio general:

```text
LA ALERTA EXISTE
POR UNA CONDICIÓN

        ↓

LA CONDICIÓN PUEDE
EVOLUCIONAR

        ↓

LA ALERTA DEBE PODER
REFLEJAR ESA EVOLUCIÓN

        ↓

SIN CONFUNDIR:

VISUALIZACIÓN
CON RESOLUCIÓN

PASO DEL TIEMPO
CON RESOLUCIÓN

ALERTA NO VIGENTE
CON ALERTA ELIMINADA
```

Vehículos Services deberá mantener el ciclo de vida de las alertas relacionado con la evolución de las condiciones que las originaron, permitiendo que puedan permanecer vigentes, evolucionar o dejar de estar vigentes cuando corresponda, sin asumir intervenciones inexistentes, sin eliminar silenciosamente su historia y sin afectar de manera automática otras alertas independientes del mismo vehículo.

---
### 63.12.5 Priorización y nivel de relevancia de las alertas

Las alertas podrán diferenciarse según su nivel de relevancia cuando las reglas funcionales correspondientes así lo requieran.

El propósito de esta diferenciación será permitir que Vehículos Services pueda reconocer que no todas las situaciones comunicadas mediante alertas necesariamente requieren el mismo nivel de atención por parte del propietario.

Conceptualmente:

```text
CONDICIÓN IDENTIFICADA
        ↓
ALERTA
        ↓
CRITERIOS APLICABLES
        ↓
NIVEL DE RELEVANCIA
CUANDO CORRESPONDA
```

Por lo tanto:

```text
EXISTENCIA DE ALERTA
        ≠
MISMO NIVEL DE
RELEVANCIA PARA
TODAS LAS ALERTAS
```

Sin embargo, el nivel de relevancia de una alerta deberá mantenerse diferenciado del estado funcional del elemento que originó dicha alerta.

En el caso del mantenimiento, Vehículos Services contempla estados como:

```text
VIGENTE

PRÓXIMO A VENCER

VENCIDO
```

Estos estados corresponden al seguimiento del mantenimiento y no deberán utilizarse automáticamente como niveles de relevancia de las alertas.

Por lo tanto:

```text
ESTADO DEL
MANTENIMIENTO
        ≠
NIVEL DE RELEVANCIA
DE LA ALERTA
```

Por ejemplo, si una actividad de mantenimiento se encuentra:

```text
PRÓXIMA A VENCER
```

dicha condición podrá originar una alerta cuando las reglas correspondientes así lo determinen.

Sin embargo:

```text
PRÓXIMO A VENCER
```

deberá continuar representando el estado del mantenimiento y no convertirse automáticamente en el nombre de un nivel de relevancia de la alerta.

Conceptualmente:

```text
ESTADO:
PRÓXIMO A VENCER
        ↓
PUEDE ORIGINAR
UNA ALERTA
        ↓
LA ALERTA PODRÁ
TENER UN NIVEL DE
RELEVANCIA CUANDO
CORRESPONDA
```

De igual manera:

```text
ESTADO:
VENCIDO
        ≠
NIVEL DE RELEVANCIA:
VENCIDO
```

La plataforma deberá mantener separados ambos conceptos para evitar que el estado del mantenimiento y la clasificación de una alerta representen la misma información con responsabilidades diferentes.

El nivel de relevancia deberá determinarse mediante criterios funcionales aplicables a la alerta y no únicamente por el hecho de que exista una determinada condición o estado.

Conceptualmente:

```text
CONDICIÓN O ESTADO
DEL ELEMENTO
        ↓
PUEDE ORIGINAR
UNA ALERTA
        ↓
CRITERIOS DE
RELEVANCIA
        ↓
NIVEL DE RELEVANCIA
CUANDO CORRESPONDA
```

Los criterios utilizados para determinar la relevancia podrán depender de la naturaleza de la alerta y del componente funcional que la origine.

Podrán considerar, cuando corresponda, elementos como:

- La condición identificada.
- El elemento o actividad relacionada.
- La evolución de la condición.
- El grado de avance respecto de un objetivo.
- La existencia de un objetivo alcanzado o superado.
- La persistencia de una situación.
- Las reglas específicas aplicables.
- Otros criterios funcionales que posteriormente puedan definirse.

La inclusión de estos posibles criterios no deberá significar que todos deban utilizarse para todas las alertas.

Cada tipo de alerta deberá utilizar únicamente los criterios que resulten aplicables a su naturaleza.

Por ejemplo:

```text
ALERTA DE
MANTENIMIENTO
        ↓
CRITERIOS APLICABLES
AL MANTENIMIENTO
```

mientras que:

```text
ALERTA RELACIONADA
CON DOCUMENTACIÓN
        ↓
CRITERIOS APLICABLES
A LA DOCUMENTACIÓN
```

podrá responder a condiciones diferentes.

Por lo tanto:

```text
MISMO SISTEMA
DE ALERTAS
        ≠
MISMOS CRITERIOS
FUNCIONALES PARA
TODAS LAS ALERTAS
```

El nivel de relevancia tampoco deberá interpretarse como una modificación de la condición que originó la alerta.

Por ejemplo:

```text
CONDICIÓN:
DENTRO DEL MARGEN
DE PROXIMIDAD

        ↓

ALERTA

        ↓

NIVEL DE RELEVANCIA
CUANDO CORRESPONDA
```

La asignación o modificación del nivel de relevancia no deberá transformar la condición original en:

```text
OBJETIVO ALCANZADO
```

ni en:

```text
OBJETIVO SUPERADO
```

La condición solamente deberá cambiar cuando una nueva evaluación sustentada en información válida determine un resultado diferente.

Por lo tanto:

```text
CAMBIO DE
RELEVANCIA
        ≠
CAMBIO AUTOMÁTICO
DE LA CONDICIÓN
```

De igual manera, el nivel de relevancia no deberá modificar el estado funcional del mantenimiento u otro elemento relacionado.

Conceptualmente:

```text
NIVEL DE RELEVANCIA
DE LA ALERTA
        ≠
ESTADO DEL
ELEMENTO EVALUADO
```

Una alerta podrá cambiar de relevancia cuando cambien las condiciones o criterios que permiten determinar dicha relevancia.

Por ejemplo:

```text
CONDICIÓN INICIAL
        ↓
ALERTA
        ↓
RELEVANCIA
APLICABLE

        ↓

NUEVA INFORMACIÓN

        ↓

NUEVA EVALUACIÓN
        ↓
CONDICIÓN
ACTUALIZADA
        ↓
REEVALUACIÓN DE
LA ALERTA
        ↓
LA RELEVANCIA
PUEDE CAMBIAR
CUANDO CORRESPONDA
```

Por lo tanto:

```text
NIVEL DE RELEVANCIA
        ≠
VALOR NECESARIAMENTE
PERMANENTE
```

Sin embargo, un cambio de relevancia deberá estar sustentado en los criterios funcionales aplicables.

El simple paso del tiempo no deberá aumentar automáticamente la relevancia de una alerta.

Por lo tanto:

```text
ALERTA MÁS ANTIGUA
        ≠
AUTOMÁTICAMENTE
ALERTA MÁS RELEVANTE
```

La antigüedad o persistencia de una condición solamente deberá participar en la determinación de relevancia cuando exista una regla funcional que expresamente la considere.

La relevancia tampoco deberá utilizarse como diagnóstico sobre el estado físico o mecánico del vehículo.

Por lo tanto:

```text
MAYOR RELEVANCIA
DE UNA ALERTA
        ≠
VEHÍCULO AVERIADO
```

```text
MAYOR RELEVANCIA
DE UNA ALERTA
        ≠
VEHÍCULO INSEGURO
```

```text
MAYOR RELEVANCIA
DE UNA ALERTA
        ≠
DIAGNÓSTICO
PROFESIONAL
```

El nivel de relevancia deberá expresar únicamente la importancia funcional asignada a la alerta dentro de Vehículos Services de acuerdo con las reglas correspondientes.

Cuando no exista información suficiente para aplicar un criterio de relevancia, la plataforma no deberá inventar, completar o asumir los datos faltantes con el propósito de asignar un determinado nivel.

Conceptualmente:

```text
INFORMACIÓN
INSUFICIENTE
        ↓
NO INVENTAR
CRITERIOS
        ↓
NO DETERMINAR
ARBITRARIAMENTE
LA RELEVANCIA
```

Esto no deberá impedir necesariamente la existencia de la alerta.

Podrá existir una condición suficientemente sustentada para generar una alerta aunque todavía no exista información suficiente para aplicar una clasificación adicional de relevancia.

Por lo tanto:

```text
ALERTA VÁLIDA
        ≠
NIVEL DE RELEVANCIA
OBLIGATORIAMENTE
DETERMINADO
```

cuando el nivel de relevancia no sea necesario o no pueda determinarse de acuerdo con las reglas disponibles.

La priorización deberá mantenerse relacionada, pero diferenciada, del nivel de relevancia.

Conceptualmente:

```text
RELEVANCIA
        =
CARACTERÍSTICA FUNCIONAL
DE LA ALERTA


PRIORIZACIÓN
        =
FORMA DE DETERMINAR
LA IMPORTANCIA RELATIVA
ENTRE ALERTAS
CUANDO CORRESPONDA
```

Por lo tanto:

```text
RELEVANCIA
        ≠
PRIORIZACIÓN
```

aunque la relevancia podrá ser uno de los criterios utilizados posteriormente para priorizar alertas.

Por ejemplo:

```text
VEHÍCULO
   │
   ├── ALERTA A
   │
   ├── ALERTA B
   │
   └── ALERTA C
        ↓
CRITERIOS DE
PRIORIZACIÓN
        ↓
ORDEN RELATIVO
CUANDO CORRESPONDA
```

La priorización no deberá depender automáticamente del orden en que fueron generadas las alertas.

Por lo tanto:

```text
PRIMERA ALERTA
GENERADA
        ≠
ALERTA DE MAYOR
PRIORIDAD
```

De igual manera:

```text
ÚLTIMA ALERTA
GENERADA
        ≠
ALERTA DE MAYOR
PRIORIDAD
```

La priorización tampoco deberá modificar la vigencia de las demás alertas.

Por ejemplo:

```text
ALERTA A
TIENE MAYOR PRIORIDAD
QUE ALERTA B
```

no deberá significar:

```text
ALERTA B
DEJA DE SER VÁLIDA
```

Una alerta podrá continuar vigente aunque exista otra que funcionalmente tenga mayor prioridad.

En esta etapa del proyecto no deberán establecerse todavía niveles concretos de relevancia como:

```text
BAJA
MEDIA
ALTA
CRÍTICA
```

ni cualquier otra escala equivalente.

Estos nombres representan únicamente ejemplos posibles de una clasificación futura y no deberán considerarse categorías oficiales de Vehículos Services mientras no sean definidos y aprobados expresamente.

Por lo tanto:

```text
SE ADMITE EL CONCEPTO
DE RELEVANCIA
        ↓
PERO
        ↓
NO SE DEFINE TODAVÍA
UNA ESCALA OFICIAL
```

De igual manera, no deberá establecerse todavía una fórmula universal de priorización entre alertas.

Los niveles concretos, criterios definitivos y reglas de priorización deberán establecerse posteriormente cuando las necesidades funcionales del proyecto permitan determinar qué clasificación resulta realmente necesaria.

Esto permitirá evitar la incorporación prematura de categorías que posteriormente no sean necesarias o que no representen correctamente las diferentes funcionalidades de Vehículos Services.

El nivel de relevancia o la prioridad tampoco deberán determinar automáticamente:

- El envío de una notificación.
- El canal de notificación.
- La frecuencia de comunicación.
- La cantidad de notificaciones.
- El cierre de una alerta.
- La resolución de una alerta.
- Un diagnóstico mecánico.
- La ejecución de una intervención.
- Colores, iconos o componentes visuales.

Estos comportamientos deberán depender de sus propias reglas funcionales o de los componentes correspondientes.

Como principio general:

```text
CONDICIÓN O ESTADO
DEL ELEMENTO
        ↓
ALERTA
        ↓
RELEVANCIA
CUANDO CORRESPONDA
        ↓
PRIORIZACIÓN
CUANDO CORRESPONDA
```

manteniendo siempre diferenciados:

```text
ESTADO DEL
MANTENIMIENTO
        ≠
CONDICIÓN EVALUADA
        ≠
ALERTA
        ≠
NIVEL DE RELEVANCIA
        ≠
PRIORIZACIÓN
```

Vehículos Services deberá permitir que las alertas puedan diferenciarse y priorizarse cuando funcionalmente sea necesario, manteniendo separados el estado del elemento evaluado, la condición identificada, la alerta generada y su posible relevancia o prioridad, sin establecer todavía una escala oficial ni reglas universales de priorización que no hayan sido definidas y aprobadas para el proyecto.

---
### 63.12.6 Actualización, resolución y cierre de alertas

Una alerta deberá poder actualizarse, resolverse o cerrarse de acuerdo con la evolución de la condición que le dio origen y con las reglas funcionales aplicables.

Estos conceptos deberán mantenerse diferenciados, ya que representan situaciones distintas dentro del ciclo de vida de una alerta.

Conceptualmente:

```text
ALERTA
   │
   ├── PUEDE ACTUALIZARSE
   │
   ├── PUEDE RESOLVERSE
   │
   └── PUEDE CERRARSE
```

Por lo tanto:

```text
ACTUALIZACIÓN
      ≠
RESOLUCIÓN
      ≠
CIERRE
```

La actualización de una alerta deberá representar un cambio en la información o condición asociada a una alerta existente, sin significar necesariamente que la situación que la originó haya dejado de existir.

Por ejemplo:

```text
CAMBIO DE ACEITE

OBJETIVO:
75.000 km

KILOMETRAJE ACTUAL:
74.300 km

        ↓

CONDICIÓN:
DENTRO DEL MARGEN
DE PROXIMIDAD

        ↓

ALERTA
```

Posteriormente:

```text
NUEVO KILOMETRAJE:
75.300 km

        ↓

NUEVA EVALUACIÓN

        ↓

CONDICIÓN:
OBJETIVO SUPERADO
```

En este escenario, la situación relacionada con la actividad continúa existiendo, pero ha evolucionado.

La alerta podrá actualizarse para reflejar la nueva condición conforme a las reglas aplicables.

Conceptualmente:

```text
ALERTA EXISTENTE
        ↓
NUEVA INFORMACIÓN
        ↓
REEVALUACIÓN
        ↓
CAMBIO DE CONDICIÓN
        ↓
ACTUALIZACIÓN
DE LA ALERTA
CUANDO CORRESPONDA
```

Por lo tanto:

```text
ALERTA ACTUALIZADA
        ≠
ALERTA RESUELTA
```

Una actualización tampoco deberá interpretarse automáticamente como la creación de una nueva alerta independiente.

Cuando la nueva condición corresponda a la evolución de una misma situación, Vehículos Services deberá evitar duplicaciones innecesarias.

Por ejemplo:

```text
CAMBIO DE ACEITE
        ↓
PRÓXIMO AL OBJETIVO
        ↓
OBJETIVO ALCANZADO
        ↓
OBJETIVO SUPERADO
```

podrá representar la evolución de una misma situación de seguimiento.

Por lo tanto:

```text
CAMBIO DE CONDICIÓN
        ≠
NUEVA ALERTA
OBLIGATORIA
```

Sin embargo, cuando una nueva condición corresponda funcionalmente a una situación diferente, podrá originarse una alerta independiente si las reglas aplicables así lo determinan.

La resolución de una alerta deberá representar que la condición que justificaba su vigencia ha dejado de requerir dicha alerta como consecuencia de información o de un evento funcional válido.

Conceptualmente:

```text
ALERTA VIGENTE
        ↓
EVENTO O INFORMACIÓN
RELEVANTE
        ↓
REEVALUACIÓN
        ↓
LA CONDICIÓN QUE
SUSTENTABA LA ALERTA
DEJA DE REQUERIRLA
        ↓
ALERTA RESUELTA
CUANDO CORRESPONDA
```

Dentro del mantenimiento, una intervención efectivamente realizada y registrada de forma válida podrá resolver una alerta relacionada con el ciclo anterior cuando dicha intervención corresponda a la actividad que originó la alerta.

Por ejemplo:

```text
ACTIVIDAD:
Cambio de aceite

OBJETIVO:
75.000 km

KILOMETRAJE ACTUAL:
75.300 km

        ↓

ALERTA RELACIONADA
CON EL OBJETIVO
SUPERADO

        ↓

CAMBIO DE ACEITE
REALIZADO Y
REGISTRADO VÁLIDAMENTE
A LOS 75.300 km

        ↓

NUEVA EVALUACIÓN

        ↓

LA CONDICIÓN DEL
CICLO ANTERIOR
DEJA DE REQUERIR
LA ALERTA

        ↓

ALERTA RESUELTA
CUANDO CORRESPONDA
```

Esta resolución deberá mantener coherencia con lo definido en `63.11.6 Cumplimiento y renovación del ciclo de seguimiento`.

La intervención deberá corresponder a la actividad relacionada.

Por ejemplo, si existe:

```text
ALERTA:
Cambio de aceite
con objetivo superado
```

y posteriormente se registra:

```text
INTERVENCIÓN:
Cambio de pastillas
de freno
```

no deberá asumirse:

```text
ALERTA DE CAMBIO
DE ACEITE RESUELTA
```

Por lo tanto:

```text
CUALQUIER
INTERVENCIÓN
        ≠
RESOLUCIÓN DE
CUALQUIER ALERTA
```

La resolución deberá guardar relación funcional con la condición que originó la alerta.

De igual manera, registrar un mantenimiento general no deberá resolver automáticamente todas las alertas de mantenimiento del vehículo.

Conceptualmente:

```text
MANTENIMIENTO
REGISTRADO
        ≠
TODAS LAS ALERTAS
DE MANTENIMIENTO
RESUELTAS
```

Deberá evaluarse qué actividades fueron efectivamente realizadas y qué condiciones fueron modificadas como consecuencia de la intervención registrada.

Una alerta también podrá resolverse como consecuencia de otros eventos válidos diferentes de una intervención, dependiendo de la naturaleza de la alerta.

Por ejemplo, una alerta relacionada con información faltante podrá dejar de ser necesaria cuando la información requerida sea incorporada válidamente.

Conceptualmente:

```text
ALERTA:
INFORMACIÓN
NECESARIA NO
DISPONIBLE
        ↓
INFORMACIÓN
INCORPORADA
VÁLIDAMENTE
        ↓
REEVALUACIÓN
        ↓
ALERTA PUEDE
RESOLVERSE
```

De igual manera, una alerta originada por una inconsistencia de información podrá resolverse cuando dicha inconsistencia sea corregida o aclarada de forma válida.

Por lo tanto, la resolución deberá depender de la naturaleza de la condición que originó cada alerta.

La visualización de una alerta por parte del propietario no deberá considerarse una resolución.

Conceptualmente:

```text
PROPIETARIO
VISUALIZA
LA ALERTA
        ≠
ALERTA RESUELTA
```

De igual manera:

```text
PROPIETARIO
CONOCE LA ALERTA
        ≠
CONDICIÓN RESUELTA
```

La visualización únicamente deberá representar que el propietario tuvo acceso a la información correspondiente.

Tampoco deberá considerarse resuelta una alerta únicamente porque el propietario deje de consultarla o porque haya transcurrido determinado tiempo desde su generación.

Por lo tanto:

```text
PASO DEL TIEMPO
        ≠
RESOLUCIÓN
AUTOMÁTICA
```

salvo que la naturaleza de una alerta y una regla funcional específica establezcan expresamente que su vigencia depende de una condición temporal determinada.

Una recomendación tampoco deberá resolver por sí misma una alerta.

Conceptualmente:

```text
ALERTA
        ↓
PUEDE RELACIONARSE
CON UNA RECOMENDACIÓN

        ≠

CONDICIÓN
RESUELTA
```

De igual manera, el envío o recepción de una notificación no deberá resolver automáticamente la alerta que la originó.

Por lo tanto:

```text
NOTIFICACIÓN ENVIADA
        ≠
ALERTA RESUELTA
```

y:

```text
NOTIFICACIÓN RECIBIDA
        ≠
ALERTA RESUELTA
```

La resolución deberá depender de la evolución real de la condición funcional y no únicamente de las acciones utilizadas para comunicarla.

El cierre de una alerta deberá mantenerse diferenciado de su resolución.

Conceptualmente, la resolución deberá responder principalmente a:

```text
¿LA CONDICIÓN QUE
JUSTIFICABA LA ALERTA
DEJÓ DE REQUERIRLA?
```

mientras que el cierre deberá representar la finalización del tratamiento de la alerta dentro de su ciclo de vida, conforme a las reglas funcionales aplicables.

Por lo tanto:

```text
RESOLUCIÓN
        ≠
CIERRE
```

Esta separación permitirá que, cuando sea necesario, Vehículos Services pueda conservar información sobre cómo terminó el tratamiento de una alerta sin confundir dicho tratamiento con la condición funcional que le dio origen.

Conceptualmente:

```text
CONDICIÓN
        ↓
ALERTA
        ↓
TRATAMIENTO
        ↓
RESOLUCIÓN
CUANDO CORRESPONDA
        ↓
CIERRE
CUANDO CORRESPONDA
```

No deberá asumirse que toda alerta necesariamente requiere una acción manual del propietario para poder cerrarse.

Dependiendo de la naturaleza de la alerta y de las reglas aplicables, su tratamiento podrá derivarse de cambios funcionales identificados por Vehículos Services.

Por ejemplo:

```text
ALERTA DE
MANTENIMIENTO
        ↓
INTERVENCIÓN
CORRESPONDIENTE
REGISTRADA
        ↓
REEVALUACIÓN
        ↓
CONDICIÓN RESUELTA
        ↓
CIERRE DE LA ALERTA
CUANDO CORRESPONDA
```

Sin embargo, tampoco deberá asumirse que toda resolución deba producir un cierre inmediato en todos los escenarios.

La relación exacta entre resolución y cierre deberá responder a las reglas funcionales aplicables al tipo de alerta.

Por lo tanto:

```text
ALERTA RESUELTA
        ≠
CIERRE INMEDIATO
OBLIGATORIO EN
TODOS LOS CASOS
```

Una alerta tampoco deberá poder considerarse resuelta únicamente porque el propietario decida dejar de verla.

Si posteriormente se incorpora una funcionalidad que permita ocultar, descartar o gestionar la visualización de determinadas alertas, dicha acción deberá mantenerse separada de la resolución de la condición funcional.

Conceptualmente:

```text
OCULTAR O DEJAR
DE MOSTRAR UNA ALERTA
        ≠
RESOLVER LA CONDICIÓN
QUE LA ORIGINÓ
```

Esto será especialmente importante para evitar que una decisión de presentación modifique indebidamente el seguimiento real del vehículo.

Cuando una alerta sea resuelta o cerrada, no deberá eliminarse automáticamente la información que permita conocer que dicha alerta existió.

Por lo tanto:

```text
ALERTA RESUELTA
        ≠
ALERTA ELIMINADA
DEL HISTORIAL
```

y:

```text
ALERTA CERRADA
        ≠
ALERTA NUNCA EXISTIÓ
```

La conservación y trazabilidad histórica se desarrollará específicamente en `63.12.7 Historial y trazabilidad de alertas`.

Una alerta resuelta tampoco deberá impedir que una condición equivalente pueda aparecer nuevamente en un ciclo posterior.

Por ejemplo:

```text
CICLO 1

CAMBIO DE ACEITE
PRÓXIMO / VENCIDO
        ↓
ALERTA
        ↓
INTERVENCIÓN
        ↓
RESOLUCIÓN
        ↓
NUEVO CICLO
```

Posteriormente:

```text
CICLO 2

NUEVO OBJETIVO
        ↓
NUEVA EVOLUCIÓN
DEL SEGUIMIENTO
        ↓
NUEVA CONDICIÓN
DE ALERTA
        ↓
NUEVA ALERTA
CUANDO CORRESPONDA
```

Por lo tanto:

```text
ALERTA ANTERIOR
RESUELTA
        ≠
ACTIVIDAD EXCLUIDA
DE FUTURAS ALERTAS
```

Cada nuevo ciclo deberá poder evaluarse de acuerdo con su propia información, referencias, objetivos y reglas aplicables.

Cuando una corrección de información determine que una alerta fue generada a partir de información posteriormente corregida, la plataforma deberá poder reevaluar su tratamiento sin borrar silenciosamente el hecho histórico.

Por ejemplo:

```text
KILOMETRAJE
REGISTRADO:
75.300 km
        ↓
ALERTA GENERADA
        ↓
CORRECCIÓN VÁLIDA:
73.300 km
        ↓
REEVALUACIÓN
        ↓
LA CONDICIÓN ANTERIOR
DEJA DE APLICAR
```

La alerta podrá resolverse o recibir el tratamiento que corresponda, pero deberá conservarse la trazabilidad suficiente para comprender por qué existió y qué cambio provocó su modificación.

De manera general:

```text
ALERTA VIGENTE
        ↓
NUEVA INFORMACIÓN
O EVENTO
        ↓
REEVALUACIÓN
        ↓
┌──────────────────────────────┐
│ CONDICIÓN CONTINÚA           │
│ → ALERTA PUEDE CONTINUAR     │
│                              │
│ CONDICIÓN CAMBIA             │
│ → ALERTA PUEDE ACTUALIZARSE  │
│                              │
│ CONDICIÓN DEJA DE REQUERIR   │
│ LA ALERTA                    │
│ → ALERTA PUEDE RESOLVERSE    │
│                              │
│ FINALIZA SU TRATAMIENTO       │
│ → ALERTA PUEDE CERRARSE      │
└──────────────────────────────┘
```

Este comportamiento deberá mantenerse separado de:

- La visualización de la alerta.
- La generación de recomendaciones.
- El envío de notificaciones.
- La realización automática de intervenciones.
- La eliminación de información histórica.

Este punto tampoco deberá definir todavía:

- La estructura técnica de los estados de una alerta.
- Los códigos utilizados para representarlos.
- Las tablas o atributos donde se almacenen.
- Los mecanismos técnicos de actualización.
- Procesos automáticos específicos de backend.
- La representación visual de alertas resueltas o cerradas.
- Los colores, iconos o componentes de interfaz.
- Los canales de notificación.

Estos aspectos deberán definirse posteriormente en los componentes funcionales o técnicos correspondientes.

Como principio general:

```text
ACTUALIZAR
        =
REFLEJAR LA EVOLUCIÓN
DE UNA ALERTA

RESOLVER
        =
DETERMINAR QUE LA
CONDICIÓN YA NO REQUIERE
ESA ALERTA

CERRAR
        =
FINALIZAR EL TRATAMIENTO
DE LA ALERTA CUANDO
CORRESPONDA
```

Vehículos Services deberá permitir que las alertas evolucionen de acuerdo con las condiciones que las originaron, manteniendo diferenciadas su actualización, resolución y cierre, sin considerar la visualización, el paso del tiempo, una notificación o una intervención no relacionada como evidencia automática de que la situación ha sido resuelta.

---

### 63.12.7 Historial y trazabilidad de alertas

Las alertas deberán conservar una trazabilidad que permita comprender su existencia y evolución dentro de Vehículos Services.

La actualización, resolución o cierre de una alerta no deberá eliminar automáticamente el hecho de que dicha alerta existió.

Conceptualmente:

```text
ALERTA GENERADA
        ↓
EVOLUCIÓN
        ↓
ACTUALIZACIÓN
CUANDO CORRESPONDA
        ↓
RESOLUCIÓN
CUANDO CORRESPONDA
        ↓
CIERRE
CUANDO CORRESPONDA
        ↓
CONSERVACIÓN DE
SU TRAZABILIDAD
```

Por lo tanto:

```text
ALERTA NO VIGENTE
        ≠
ALERTA ELIMINADA
DE LA HISTORIA
```

La trazabilidad deberá permitir comprender, cuando corresponda:

- Qué situación originó la alerta.
- Con qué elemento del vehículo estaba relacionada.
- Qué condición había sido identificada.
- Qué información sustentaba dicha condición.
- Cuándo fue identificada la alerta.
- Cómo evolucionó la condición relacionada.
- Qué cambios relevantes experimentó la alerta.
- Qué situación provocó su resolución o cierre, cuando corresponda.

La definición de esta información no deberá interpretarse todavía como una estructura técnica de almacenamiento ni como la definición de campos obligatorios de una base de datos.

Conceptualmente:

```text
CONDICIÓN
IDENTIFICADA
        ↓
ALERTA
        ↓
EVOLUCIÓN
        ↓
RESULTADO FINAL
        ↓
TRAZABILIDAD
```

El historial de una alerta deberá mantenerse relacionado con la condición y el elemento que le dieron origen.

Por ejemplo:

```text
ACTIVIDAD:
Cambio de aceite

OBJETIVO:
75.000 km

        ↓

KILOMETRAJE:
74.300 km

        ↓

CONDICIÓN:
DENTRO DEL MARGEN
DE PROXIMIDAD

        ↓

ALERTA
```

Posteriormente:

```text
KILOMETRAJE:
75.300 km

        ↓

NUEVA EVALUACIÓN

        ↓

CONDICIÓN:
OBJETIVO SUPERADO

        ↓

EVOLUCIÓN DE
LA ALERTA
```

Y posteriormente:

```text
CAMBIO DE ACEITE
REALIZADO Y
REGISTRADO VÁLIDAMENTE
A LOS 75.300 km

        ↓

NUEVA EVALUACIÓN

        ↓

LA CONDICIÓN ANTERIOR
DEJA DE REQUERIR
LA ALERTA

        ↓

RESOLUCIÓN
CUANDO CORRESPONDA
```

La trazabilidad deberá permitir comprender esta secuencia sin sustituir la información histórica propia de la actividad de mantenimiento.

Por lo tanto:

```text
HISTORIAL DE
LA ALERTA
        ≠
HISTORIAL DEL
MANTENIMIENTO
```

Ambos podrán estar relacionados, pero representan información funcional diferente.

El mantenimiento deberá conservar la información correspondiente a las intervenciones realizadas.

La alerta deberá conservar la información correspondiente a la situación que fue identificada y a la evolución de su tratamiento.

Conceptualmente:

```text
MANTENIMIENTO
        ↓
REGISTRA LO QUE
OCURRIÓ SOBRE
EL VEHÍCULO


ALERTA
        ↓
REGISTRA QUE UNA
CONDICIÓN RELEVANTE
FUE IDENTIFICADA
Y CÓMO EVOLUCIONÓ
```

Por lo tanto, la existencia histórica de una alerta no deberá utilizarse como evidencia de que una intervención fue realizada.

```text
ALERTA HISTÓRICA
        ≠
INTERVENCIÓN
HISTÓRICA
```

De igual manera, la resolución histórica de una alerta no deberá sustituir el registro del evento que provocó dicha resolución.

Por ejemplo, si una alerta de cambio de aceite se resolvió debido a una nueva intervención:

```text
ALERTA RESUELTA
        ≠
REGISTRO DEL
CAMBIO DE ACEITE
```

El mantenimiento realizado deberá continuar existiendo como su propio evento dentro del historial correspondiente.

La trazabilidad de una alerta deberá permitir conservar la evolución de sus condiciones relevantes sin sobrescribir silenciosamente la información anterior.

Por ejemplo:

```text
CONDICIÓN INICIAL:
PRÓXIMO AL OBJETIVO

        ↓

CONDICIÓN POSTERIOR:
OBJETIVO SUPERADO
```

no deberá convertirse históricamente en:

```text
LA ALERTA SIEMPRE
ESTUVO EN CONDICIÓN
DE OBJETIVO SUPERADO
```

La plataforma deberá poder conservar conceptualmente que existieron diferentes momentos dentro de la evolución de la misma situación.

Por lo tanto:

```text
CONDICIÓN ACTUAL
        ≠
REESCRITURA DE
CONDICIONES ANTERIORES
```

Esto permitirá diferenciar entre:

```text
QUÉ SE CONOCÍA
EN UN MOMENTO

        ↓

QUÉ CAMBIÓ
POSTERIORMENTE

        ↓

CUÁL ES LA
SITUACIÓN ACTUAL
```

Cuando una alerta cambie como consecuencia de nueva información, deberá poder mantenerse la relación entre la información incorporada y la evolución producida.

Por ejemplo:

```text
NUEVA LECTURA
DE KILOMETRAJE
        ↓
NUEVA EVALUACIÓN
        ↓
CAMBIO DE CONDICIÓN
        ↓
ACTUALIZACIÓN
DE LA ALERTA
```

De igual manera:

```text
NUEVA INTERVENCIÓN
VÁLIDA
        ↓
NUEVA EVALUACIÓN
        ↓
CONDICIÓN ANTERIOR
DEJA DE APLICAR
        ↓
RESOLUCIÓN
DE LA ALERTA
CUANDO CORRESPONDA
```

La trazabilidad deberá permitir relacionar estos acontecimientos sin confundir la alerta con el evento que provocó su modificación.

Por lo tanto:

```text
EVENTO QUE PROVOCA
UN CAMBIO
        ≠
CAMBIO DE LA ALERTA
```

aunque ambos deberán poder mantenerse relacionados cuando corresponda.

Cuando una alerta cambie debido a una corrección de información, deberá conservarse suficiente trazabilidad para distinguir una evolución normal de la condición frente a una modificación causada por la corrección de un dato.

Por ejemplo:

```text
LECTURA REGISTRADA:
75.300 km

        ↓

ALERTA GENERADA
POR OBJETIVO SUPERADO

        ↓

SE DETERMINA QUE
LA LECTURA ERA
INCORRECTA

        ↓

CORRECCIÓN VÁLIDA:
73.300 km

        ↓

REEVALUACIÓN

        ↓

CAMBIO EN LA ALERTA
```

La corrección no deberá provocar que desaparezca silenciosamente el contexto que permita comprender por qué la alerta había sido generada.

Conceptualmente:

```text
CORRECCIÓN
        ≠
REESCRITURA
SILENCIOSA DE
LA HISTORIA
```

De igual manera, cuando una modificación de una regla afecte una alerta, deberá poder mantenerse la relación suficiente para comprender que el cambio fue consecuencia de la evolución de la regla y no necesariamente de un cambio físico o de una nueva intervención sobre el vehículo.

Por ejemplo:

```text
REGLA APLICABLE
        ↓
ALERTA EXISTENTE

        ↓

MODIFICACIÓN VÁLIDA
DE LA REGLA

        ↓

REEVALUACIÓN

        ↓

CAMBIO EN LA
ALERTA CUANDO
CORRESPONDA
```

Por lo tanto:

```text
CAMBIO DE ALERTA
POR CAMBIO DE REGLA
        ≠
NUEVA INTERVENCIÓN
SOBRE EL VEHÍCULO
```

La trazabilidad deberá permitir conservar esta distinción.

Cuando una alerta sea resuelta, deberá poder conocerse conceptualmente qué condición o evento permitió determinar dicha resolución.

Por ejemplo:

```text
ALERTA:
CAMBIO DE ACEITE
CON OBJETIVO SUPERADO

        ↓

EVENTO:
CAMBIO DE ACEITE
REALIZADO Y
REGISTRADO VÁLIDAMENTE

        ↓

REEVALUACIÓN

        ↓

ALERTA RESUELTA
```

En cambio:

```text
ALERTA:
INFORMACIÓN
REQUERIDA NO
DISPONIBLE

        ↓

EVENTO:
INFORMACIÓN
INCORPORADA
VÁLIDAMENTE

        ↓

REEVALUACIÓN

        ↓

ALERTA RESUELTA
```

Los eventos que permiten resolver una alerta podrán ser diferentes dependiendo de la naturaleza de la condición que la originó.

Por ello:

```text
RESOLUCIÓN
        ≠
MISMO EVENTO
PARA TODAS
LAS ALERTAS
```

Cuando una alerta sea cerrada, deberá mantenerse la trazabilidad suficiente para diferenciar su cierre de su eliminación.

Conceptualmente:

```text
ALERTA CERRADA
        ↓
FINALIZA SU
TRATAMIENTO
        ↓
PERMANECE SU
TRAZABILIDAD
CUANDO CORRESPONDA
```

Por lo tanto:

```text
CIERRE
        ≠
ELIMINACIÓN
```

La conservación histórica también deberá permitir distinguir alertas pertenecientes a diferentes ciclos de seguimiento de una misma actividad.

Por ejemplo:

```text
CAMBIO DE ACEITE

CICLO 1
70.000 km → 75.000 km
        ↓
ALERTA
        ↓
INTERVENCIÓN
        ↓
RESOLUCIÓN


CICLO 2
75.300 km → 80.300 km
        ↓
NUEVA ALERTA
CUANDO CORRESPONDA
```

La alerta correspondiente al segundo ciclo no deberá sobrescribir la alerta perteneciente al primero.

Por lo tanto:

```text
MISMA ACTIVIDAD
        ≠
MISMA ALERTA
PARA TODA LA VIDA
DEL VEHÍCULO
```

Cada ciclo podrá producir sus propias condiciones y alertas cuando corresponda.

Esta separación permitirá conocer, por ejemplo, que una misma actividad presentó situaciones de alerta en diferentes momentos de la vida del vehículo sin convertirlas en un único evento permanente.

Las alertas también deberán conservar su relación con el vehículo al que pertenecen.

La continuidad histórica del vehículo deberá permitir que las alertas anteriores puedan permanecer como parte de su trazabilidad aunque posteriormente cambien otras relaciones asociadas al vehículo.

Sin embargo:

```text
CONSERVACIÓN
HISTÓRICA
        ≠
VISIBILIDAD
AUTOMÁTICA PARA
CUALQUIER ACTOR
```

La existencia de información histórica no deberá otorgar por sí misma permisos de consulta.

La visibilidad de dicha información deberá respetar las reglas de acceso y permisos que posteriormente se definan para Vehículos Services.

Esto deberá mantener el principio general:

```text
EXISTENCIA DEL
HISTORIAL
        ≠
AUTORIZACIÓN
PARA CONSULTARLO
```

La trazabilidad de alertas tampoco deberá depender de que exista una notificación asociada.

Podrá existir:

```text
ALERTA
        ↓
SIN NOTIFICACIÓN
EXTERNA
```

y aun así la alerta deberá poder conservar su propia trazabilidad cuando corresponda.

De igual manera:

```text
HISTORIAL DE ALERTA
        ≠
HISTORIAL DE
NOTIFICACIONES
```

Una futura notificación podrá conservar su propia información relacionada con el envío o comunicación, mientras que la alerta deberá conservar la información relacionada con la condición funcional que representó.

La trazabilidad tampoco deberá utilizarse para modificar retroactivamente la interpretación de una alerta utilizando información que no estaba disponible cuando fue evaluada.

Por ejemplo:

```text
MOMENTO A
INFORMACIÓN DISPONIBLE
        ↓
ALERTA VÁLIDA SEGÚN
ESA INFORMACIÓN

        ↓

MOMENTO B
APARECE NUEVA
INFORMACIÓN
        ↓
NUEVA EVALUACIÓN
```

La nueva información podrá modificar la situación actual, pero no deberá convertir automáticamente la evaluación anterior en un error.

Por lo tanto:

```text
NUEVA INFORMACIÓN
        ≠
EVALUACIÓN ANTERIOR
NECESARIAMENTE
INCORRECTA
```

Deberá diferenciarse entre una evolución normal de la información y una corrección que determine que un dato anterior era incorrecto.

Conceptualmente:

```text
NUEVA INFORMACIÓN
        │
        ├── EVOLUCIÓN NORMAL
        │
        └── CORRECCIÓN
            DE INFORMACIÓN

        ↓

PUEDEN PRODUCIR
EFECTOS DIFERENTES
SOBRE LA TRAZABILIDAD
```

Vehículos Services deberá conservar suficiente contexto para poder distinguir ambos escenarios cuando corresponda.

Este punto no deberá definir todavía:

- Tablas de historial.
- Identificadores técnicos.
- Versiones técnicas de registros.
- Estructuras de auditoría.
- Tipos de datos.
- Fechas técnicas de creación o modificación.
- Estrategias de almacenamiento.
- Políticas técnicas de retención.
- Logs de aplicación.
- Mecanismos de persistencia.
- APIs para consultar el historial.
- Componentes visuales para representar la trazabilidad.

Estos elementos deberán definirse posteriormente en el modelo de datos, arquitectura, backend, auditoría, seguridad, interfaz u otros componentes técnicos que correspondan.

Como principio general:

```text
CONDICIÓN
        ↓
ALERTA
        ↓
EVOLUCIÓN
        ↓
ACTUALIZACIÓN /
RESOLUCIÓN /
CIERRE
        ↓
TRAZABILIDAD
CONSERVADA
```

manteniendo siempre diferenciados:

```text
HISTORIAL DE ALERTAS

HISTORIAL DE
MANTENIMIENTOS

HISTORIAL DE
KILOMETRAJE

HISTORIAL DE
NOTIFICACIONES

OTROS HISTORIALES
FUNCIONALES
```

Estos historiales podrán relacionarse cuando corresponda, pero no deberán sustituirse entre sí.

Vehículos Services deberá conservar la trazabilidad suficiente de las alertas para comprender qué condición las originó, cómo evolucionaron y qué provocó su actualización, resolución o cierre, evitando sobrescrituras silenciosas y manteniendo diferenciada la historia de la alerta de los eventos, intervenciones y demás información funcional relacionada con el vehículo.

---

### 63.12.8 Diferencia entre alerta, recomendación y notificación

Vehículos Services deberá mantener diferenciados los conceptos de alerta, recomendación y notificación.

Aunque estos elementos podrán relacionarse dentro de un mismo flujo funcional, deberán representar responsabilidades diferentes y no deberán utilizarse como términos equivalentes.

Conceptualmente:

```text
ALERTA
        ≠
RECOMENDACIÓN
        ≠
NOTIFICACIÓN
```

De manera general:

```text
ALERTA
        ↓
INFORMA QUE EXISTE
UNA CONDICIÓN RELEVANTE


RECOMENDACIÓN
        ↓
ORIENTA AL PROPIETARIO
SOBRE UNA POSIBLE
ACCIÓN O CONSIDERACIÓN


NOTIFICACIÓN
        ↓
COMUNICA INFORMACIÓN
AL PROPIETARIO MEDIANTE
UN MECANISMO O CANAL
DE COMUNICACIÓN
```

Una alerta deberá representar una condición relevante identificada por Vehículos Services de acuerdo con la información disponible y las reglas funcionales aplicables, conforme a lo definido en los puntos anteriores de `63.12 ALERTAS`.

Por ejemplo:

```text
CAMBIO DE ACEITE

OBJETIVO:
75.000 km

KILOMETRAJE ACTUAL:
74.300 km

        ↓

CONDICIÓN:
DENTRO DEL MARGEN
DE PROXIMIDAD

        ↓

ALERTA
CUANDO CORRESPONDA
```

La alerta deberá responder principalmente a:

```text
¿QUÉ SITUACIÓN
RELEVANTE FUE
IDENTIFICADA?
```

Una recomendación deberá mantenerse diferenciada de dicha alerta.

La recomendación podrá orientar al propietario sobre una acción que podría considerar a partir de la información disponible, sin representar por sí misma un diagnóstico profesional ni una intervención efectivamente realizada.

Por ejemplo:

```text
ALERTA:
EL CAMBIO DE ACEITE
SE ENCUENTRA PRÓXIMO
A SU OBJETIVO

        ↓

PUEDE RELACIONARSE CON

        ↓

RECOMENDACIÓN:
CONSIDERAR LA REVISIÓN
O REALIZACIÓN DEL
CAMBIO DE ACEITE
SEGÚN CORRESPONDA
```

En este escenario:

```text
ALERTA
        ↓
COMUNICA LA
CONDICIÓN

RECOMENDACIÓN
        ↓
ORIENTA SOBRE UNA
POSIBLE ACCIÓN
```

Por lo tanto:

```text
ALERTA
        ≠
RECOMENDACIÓN
```

La existencia de una alerta no deberá implicar obligatoriamente la existencia de una recomendación.

Podrá existir:

```text
CONDICIÓN RELEVANTE
        ↓
ALERTA
        ↓
SIN RECOMENDACIÓN
ASOCIADA
```

cuando no exista una recomendación funcional aplicable o cuando la naturaleza de la situación únicamente requiera poner una condición en conocimiento del propietario.

De igual manera, una recomendación no deberá utilizarse para afirmar que el propietario necesariamente debe ejecutar una acción específica cuando Vehículos Services no disponga de información suficiente para sustentar dicha afirmación.

La recomendación deberá conservar los principios establecidos para las recomendaciones automáticas del proyecto.

Por lo tanto:

```text
RECOMENDACIÓN
AUTOMÁTICA
        ≠
DIAGNÓSTICO
PROFESIONAL
```

y:

```text
RECOMENDACIÓN
        ≠
INTERVENCIÓN
REALIZADA
```

La existencia de una recomendación tampoco deberá modificar por sí misma la condición que originó una alerta.

Por ejemplo:

```text
ALERTA:
OBJETIVO SUPERADO

        ↓

RECOMENDACIÓN:
CONSIDERAR LA
REALIZACIÓN DEL
MANTENIMIENTO

        ↓

EL PROPIETARIO
CONSULTA LA
RECOMENDACIÓN
```

no deberá significar:

```text
MANTENIMIENTO
REALIZADO
```

ni:

```text
ALERTA
RESUELTA
```

La condición solamente deberá modificarse cuando exista nueva información o un evento funcional válido que permita realizar una nueva evaluación.

La notificación deberá cumplir una responsabilidad diferente.

Una notificación deberá representar la comunicación mediante la cual determinada información de Vehículos Services puede ponerse en conocimiento del propietario cuando corresponda.

La notificación deberá mantenerse diferenciada del mecanismo o canal utilizado para realizar dicha comunicación.

Conceptualmente:

```text
INFORMACIÓN QUE
DEBE COMUNICARSE
        ↓
NOTIFICACIÓN
        ↓
PROPIETARIO
```

Por lo tanto:

```text
NOTIFICACIÓN
        ≠
CANAL O MECANISMO
DE COMUNICACIÓN
```

Una alerta podrá originar una notificación cuando las reglas correspondientes determinen que debe comunicarse mediante alguno de los mecanismos disponibles.

Por ejemplo:

```text
ALERTA:
CAMBIO DE ACEITE
PRÓXIMO A SU
OBJETIVO

        ↓

REGLA DE
NOTIFICACIÓN
        ↓

NOTIFICACIÓN
CUANDO CORRESPONDA
        ↓

PROPIETARIO
```

Por lo tanto:

```text
ALERTA
        ≠
NOTIFICACIÓN
```

La alerta representa la situación funcional identificada.

La notificación representa su comunicación cuando corresponda.

Esta separación deberá permitir que una alerta pueda existir dentro de Vehículos Services sin que necesariamente se genere una notificación externa cada vez que dicha alerta exista, cambie o sea reevaluada.

Conceptualmente:

```text
ALERTA EXISTENTE
        ≠
NOTIFICACIÓN
OBLIGATORIA
```

La decisión de generar una notificación deberá depender de las reglas funcionales que posteriormente se definan para las notificaciones.

De igual manera, una misma alerta no deberá interpretarse como una nueva alerta cada vez que se produzca una notificación relacionada con ella.

Por ejemplo:

```text
UNA ALERTA
        ↓
PUEDE SER COMUNICADA
CUANDO CORRESPONDA
        ↓
UNA O MÁS
NOTIFICACIONES
SEGÚN LAS REGLAS
APLICABLES
```

sin que esto signifique:

```text
CADA NOTIFICACIÓN
        =
NUEVA ALERTA
```

Por lo tanto:

```text
NÚMERO DE
NOTIFICACIONES
        ≠
NÚMERO DE
ALERTAS
```

La notificación tampoco deberá modificar automáticamente la alerta que comunica.

Conceptualmente:

```text
NOTIFICACIÓN
GENERADA
        ≠
ALERTA RESUELTA
```

```text
NOTIFICACIÓN
ENVIADA
        ≠
ALERTA CERRADA
```

```text
NOTIFICACIÓN
CONSULTADA
        ≠
CONDICIÓN RESUELTA
```

La actualización, resolución y cierre de la alerta deberán continuar dependiendo de las condiciones definidas en `63.12.6 Actualización, resolución y cierre de alertas`.

La relación entre alerta, recomendación y notificación podrá representarse conceptualmente de la siguiente manera:

```text
INFORMACIÓN
DEL VEHÍCULO
        +
REGLAS APLICABLES
        ↓
EVALUACIÓN
        ↓
CONDICIÓN RELEVANTE
        ↓
ALERTA
        │
        ├───────────────┐
        ↓               ↓
PUEDE ORIGINAR     PUEDE RELACIONARSE
UNA NOTIFICACIÓN   CON UNA RECOMENDACIÓN
CUANDO             CUANDO
CORRESPONDA        CORRESPONDA
        │               │
        ↓               ↓
COMUNICACIÓN       ORIENTACIÓN PARA
AL PROPIETARIO     EL PROPIETARIO
```

Esta relación no deberá interpretarse como una secuencia obligatoria.

No siempre deberá ocurrir:

```text
ALERTA
        ↓
RECOMENDACIÓN
        ↓
NOTIFICACIÓN
```

Podrán existir diferentes escenarios.

Por ejemplo:

```text
ESCENARIO 1

CONDICIÓN
        ↓
ALERTA
```

También:

```text
ESCENARIO 2

CONDICIÓN
        ↓
ALERTA
        ↓
NOTIFICACIÓN
```

También:

```text
ESCENARIO 3

CONDICIÓN
        ↓
ALERTA
        ↓
RECOMENDACIÓN
```

Y cuando corresponda:

```text
ESCENARIO 4

CONDICIÓN
        ↓
ALERTA
        ├── RECOMENDACIÓN
        └── NOTIFICACIÓN
```

El comportamiento aplicable deberá depender de las reglas funcionales correspondientes y no de una asociación automática entre los tres conceptos.

También deberá mantenerse diferenciada la información histórica de cada elemento.

Conceptualmente:

```text
HISTORIAL DE
ALERTAS
        ≠
HISTORIAL DE
NOTIFICACIONES
```

Una alerta deberá conservar la trazabilidad de la condición que representó y de su evolución conforme a `63.12.7 Historial y trazabilidad de alertas`.

Una notificación podrá requerir posteriormente su propia trazabilidad relacionada con la comunicación realizada, sin sustituir el historial de la alerta.

De igual manera, una recomendación deberá conservar su naturaleza funcional sin convertirse en evidencia de que la acción recomendada fue ejecutada.

Por lo tanto:

```text
RECOMENDACIÓN
GENERADA
        ≠
ACCIÓN EJECUTADA
```

La confirmación de una intervención o acción realizada deberá depender del registro válido del evento correspondiente y no de la existencia de una alerta, recomendación o notificación.

Conceptualmente:

```text
ALERTA
        ≠
ACCIÓN REALIZADA

RECOMENDACIÓN
        ≠
ACCIÓN REALIZADA

NOTIFICACIÓN
        ≠
ACCIÓN REALIZADA
```

Esta separación deberá mantenerse independientemente de que los tres elementos se encuentren relacionados con una misma situación.

Por ejemplo:

```text
CAMBIO DE ACEITE
PRÓXIMO AL OBJETIVO
        ↓
ALERTA
        │
        ├── RECOMENDACIÓN:
        │   considerar realizar
        │   el mantenimiento
        │
        └── NOTIFICACIÓN:
            comunicar la alerta
            al propietario
```

Ninguno de estos elementos deberá permitir concluir:

```text
CAMBIO DE ACEITE
REALIZADO
```

La intervención solamente deberá considerarse realizada cuando exista información válida que registre el evento correspondiente.

Finalmente, este punto no deberá definir:

- Los canales específicos de notificación.
- La frecuencia de envío.
- Las condiciones de reenvío.
- Los horarios de comunicación.
- Las preferencias de comunicación del propietario.
- Los mecanismos de entrega.
- La confirmación técnica de entrega.
- La representación visual de alertas, recomendaciones o notificaciones.
- Los identificadores técnicos.
- Las estructuras de almacenamiento.
- Las APIs o servicios responsables de procesarlos.

Estos aspectos deberán desarrollarse posteriormente en los componentes funcionales o técnicos correspondientes.

Como principio general:

```text
ALERTA
        =
INFORMA UNA
CONDICIÓN RELEVANTE


RECOMENDACIÓN
        =
ORIENTA SOBRE UNA
POSIBLE ACCIÓN


NOTIFICACIÓN
        =
COMUNICA INFORMACIÓN
AL PROPIETARIO
CUANDO CORRESPONDA
```

manteniendo siempre:

```text
ALERTA
        ≠
RECOMENDACIÓN
        ≠
NOTIFICACIÓN
        ≠
INTERVENCIÓN
REALIZADA
```

Vehículos Services deberá mantener claramente diferenciadas las alertas, recomendaciones y notificaciones, permitiendo que puedan relacionarse cuando corresponda sin asumir que la existencia de una implica automáticamente la existencia de las demás ni que alguna de ellas constituye evidencia de que una intervención o acción sobre el vehículo fue efectivamente realizada.

---
## 63.13 NOTIFICACIONES
### 63.13.1 Definición y propósito de una notificación

Una notificación deberá representar una comunicación generada por Vehículos Services para poner determinada información en conocimiento del Propietario cuando exista una condición, evento o situación funcional que deba ser comunicada de acuerdo con las reglas aplicables.

Su propósito será permitir que información relevante pueda llegar al Propietario sin depender exclusivamente de que este consulte manualmente la información dentro de la plataforma.

Conceptualmente:

```text
INFORMACIÓN,
CONDICIÓN O EVENTO
        ↓
REGLAS APLICABLES
        ↓
¿CORRESPONDE
COMUNICARLO?
        ↓
NOTIFICACIÓN
CUANDO CORRESPONDA
        ↓
PROPIETARIO
```

La notificación deberá mantenerse diferenciada de la información, condición o evento que provoca su generación.

Por lo tanto:

```text
INFORMACIÓN
        ≠
NOTIFICACIÓN
```

```text
CONDICIÓN
        ≠
NOTIFICACIÓN
```

```text
EVENTO
        ≠
NOTIFICACIÓN
```

La notificación constituye la comunicación de determinada información y no el hecho funcional que dicha comunicación representa.

Por ejemplo, si una actividad de mantenimiento se aproxima a su objetivo:

```text
CAMBIO DE ACEITE

OBJETIVO:
75.000 km

KILOMETRAJE ACTUAL:
74.300 km

        ↓

CONDICIÓN
IDENTIFICADA
```

dicha condición podrá producir los resultados funcionales que correspondan y, cuando las reglas de comunicación así lo determinen, podrá originar una notificación al Propietario.

Conceptualmente:

```text
CONDICIÓN
IDENTIFICADA
        ↓
ALERTA
CUANDO CORRESPONDA
        ↓
¿DEBE COMUNICARSE?
        ↓
NOTIFICACIÓN
CUANDO CORRESPONDA
        ↓
PROPIETARIO
```

Sin embargo:

```text
CONDICIÓN
IDENTIFICADA
        ≠
NOTIFICACIÓN
AUTOMÁTICA
```

y:

```text
ALERTA
        ≠
NOTIFICACIÓN
AUTOMÁTICA
```

La existencia de una alerta no deberá significar que necesariamente deba generarse una notificación.

Podrá existir:

```text
CONDICIÓN
        ↓
ALERTA
```

sin que necesariamente exista:

```text
NOTIFICACIÓN
```

La generación de una notificación deberá depender de las reglas funcionales de comunicación que resulten aplicables.

Esta separación permitirá que Vehículos Services pueda identificar y conservar una alerta aunque no sea necesario comunicarla mediante una notificación en ese momento.

De igual manera, una notificación no deberá depender exclusivamente de la existencia previa de una alerta.

Vehículos Services podrá requerir comunicar al Propietario otros eventos o solicitudes funcionales que no representen una condición de alerta.

Por ejemplo, la plataforma podrá requerir solicitar al Propietario una actualización del kilometraje de su vehículo.

Conceptualmente:

```text
NECESIDAD DE
ACTUALIZAR
KILOMETRAJE
        ↓
SOLICITUD DE
ACTUALIZACIÓN
        ↓
NOTIFICACIÓN
CUANDO CORRESPONDA
        ↓
PROPIETARIO
```

En este escenario no deberá ser necesario afirmar:

```text
EXISTE UNA ALERTA
DEL VEHÍCULO
```

para poder generar la comunicación.

Por lo tanto:

```text
NOTIFICACIÓN
        ≠
COMUNICACIÓN
EXCLUSIVA DE ALERTAS
```

Una notificación podrá originarse a partir de diferentes situaciones funcionales cuando las reglas correspondientes determinen que determinada información debe ser comunicada.

Las condiciones específicas que podrán originar una notificación se desarrollarán en `63.13.2 Condiciones que pueden originar una notificación`.

La notificación también deberá mantenerse diferenciada de una recomendación.

Conceptualmente:

```text
RECOMENDACIÓN
        =
ORIENTACIÓN SOBRE
UNA POSIBLE ACCIÓN


NOTIFICACIÓN
        =
COMUNICACIÓN DE
INFORMACIÓN AL
PROPIETARIO
```

Por lo tanto:

```text
RECOMENDACIÓN
        ≠
NOTIFICACIÓN
```

Una recomendación podrá ser comunicada mediante una notificación cuando las reglas correspondientes así lo determinen, pero la recomendación deberá continuar existiendo conceptualmente como el contenido funcional que orienta al Propietario.

Por ejemplo:

```text
RECOMENDACIÓN:
CONSIDERAR LA REVISIÓN
DEL CAMBIO DE ACEITE

        ↓

REGLAS DE
COMUNICACIÓN

        ↓

NOTIFICACIÓN
CUANDO CORRESPONDA
```

La generación de la notificación no deberá transformar la recomendación en una alerta ni modificar su naturaleza.

De igual manera:

```text
RECOMENDACIÓN
GENERADA
        ≠
NOTIFICACIÓN
OBLIGATORIA
```

Una recomendación podrá existir dentro de Vehículos Services sin que necesariamente deba ser comunicada mediante una notificación independiente.

La notificación tampoco deberá interpretarse como evidencia de que el Propietario realizó una acción sobre el vehículo.

Por ejemplo:

```text
NOTIFICACIÓN:

CAMBIO DE ACEITE
PRÓXIMO A SU
OBJETIVO
```

no deberá significar:

```text
CAMBIO DE ACEITE
REALIZADO
```

De igual manera:

```text
NOTIFICACIÓN
GENERADA
        ≠
INTERVENCIÓN
REALIZADA
```

```text
NOTIFICACIÓN
ENVIADA
        ≠
INTERVENCIÓN
REALIZADA
```

```text
NOTIFICACIÓN
CONSULTADA
        ≠
INTERVENCIÓN
REALIZADA
```

La realización de una intervención deberá continuar dependiendo de la existencia de información válida que registre el evento correspondiente.

Una notificación tampoco deberá resolver automáticamente la condición, alerta o recomendación relacionada.

Por lo tanto:

```text
NOTIFICACIÓN
GENERADA
        ≠
CONDICIÓN
RESUELTA
```

```text
NOTIFICACIÓN
ENVIADA
        ≠
ALERTA
RESUELTA
```

```text
NOTIFICACIÓN
CONSULTADA
        ≠
ALERTA
CERRADA
```

La comunicación de una situación y la resolución de dicha situación deberán mantenerse como procesos funcionalmente diferentes.

Por ejemplo:

```text
ALERTA:
CAMBIO DE ACEITE
CON OBJETIVO
SUPERADO
        ↓
NOTIFICACIÓN
AL PROPIETARIO
        ↓
PROPIETARIO
CONOCE LA SITUACIÓN
```

Esto no deberá permitir concluir:

```text
CONDICIÓN
RESUELTA
```

La condición solamente deberá cambiar cuando nueva información o un evento funcional válido permita realizar una nueva evaluación.

La notificación tampoco deberá interpretarse como un diagnóstico sobre el estado físico, mecánico o de seguridad del vehículo.

Por ejemplo, una notificación relacionada con un mantenimiento próximo o vencido deberá comunicar la información determinada por las reglas correspondientes, pero no deberá afirmar automáticamente que:

```text
EL COMPONENTE
ESTÁ DAÑADO
```

o que:

```text
EL VEHÍCULO
PRESENTA UNA FALLA
```

o que:

```text
EL VEHÍCULO
ES INSEGURO
```

si Vehículos Services no dispone de información válida que permita sustentar dichas afirmaciones.

Por lo tanto:

```text
NOTIFICACIÓN
DE MANTENIMIENTO
        ≠
DIAGNÓSTICO
MECÁNICO
```

La notificación deberá comunicar información de acuerdo con el conocimiento disponible en Vehículos Services y con las reglas funcionales aplicables.

Cuando la información disponible sea insuficiente, la notificación no deberá inventar, completar ni presentar como confirmados datos que la plataforma desconoce.

Conceptualmente:

```text
INFORMACIÓN
DESCONOCIDA
        ↓
NO INVENTAR
INFORMACIÓN
        ↓
COMUNICAR ÚNICAMENTE
LO QUE PUEDA
SUSTENTARSE
```

Por ejemplo, si Vehículos Services desconoce la fecha del último cambio de un componente, una eventual comunicación relacionada con esa ausencia de información no deberá afirmar:

```text
EL COMPONENTE
ESTÁ VENCIDO
```

cuando lo único conocido sea:

```text
NO EXISTE INFORMACIÓN
SUFICIENTE PARA
DETERMINAR SU ESTADO
```

Por lo tanto:

```text
NOTIFICAR AUSENCIA
DE INFORMACIÓN
        ≠
NOTIFICAR COMO
CONFIRMADA UNA
CONDICIÓN DESCONOCIDA
```

La notificación deberá mantener relación con la información que justificó su generación.

Conceptualmente:

```text
ORIGEN FUNCIONAL
        ↓
INFORMACIÓN QUE
DEBE COMUNICARSE
        ↓
NOTIFICACIÓN
        ↓
PROPIETARIO
```

Esta relación permitirá posteriormente comprender por qué determinada comunicación fue generada sin convertir la notificación en el elemento funcional que le dio origen.

Por ejemplo:

```text
ALERTA
        ↓
PUEDE ORIGINAR
NOTIFICACIÓN
```

pero:

```text
ALERTA
        ≠
NOTIFICACIÓN
```

De igual manera:

```text
RECOMENDACIÓN
        ↓
PUEDE SER
COMUNICADA MEDIANTE
UNA NOTIFICACIÓN
```

pero:

```text
RECOMENDACIÓN
        ≠
NOTIFICACIÓN
```

También podrá existir:

```text
EVENTO O SOLICITUD
FUNCIONAL
        ↓
NOTIFICACIÓN
```

sin que necesariamente exista una alerta o recomendación asociada.

Por lo tanto, el concepto general deberá permitir:

```text
ALERTA
        ┐
        │
RECOMENDACIÓN
        │
        ├──→ REGLAS DE
        │    COMUNICACIÓN
EVENTO  │         ↓
        │    NOTIFICACIÓN
SOLICITUD         ↓
FUNCIONAL ┘   PROPIETARIO
```

sin establecer que todos estos orígenes deban generar siempre una notificación.

La existencia de información susceptible de ser comunicada deberá mantenerse separada de la decisión funcional de comunicarla.

Conceptualmente:

```text
INFORMACIÓN
DISPONIBLE
        ≠
NOTIFICACIÓN
OBLIGATORIA
```

La notificación solamente deberá generarse cuando las reglas correspondientes determinen que la comunicación debe producirse.

Esto será especialmente importante para evitar comunicaciones innecesarias, repetitivas o generadas únicamente porque determinada información fue reevaluada sin que exista un motivo funcional para volver a comunicarla.

Las reglas relacionadas con frecuencia, repetición y prevención de notificaciones innecesarias se desarrollarán específicamente en `63.13.6 Frecuencia, repetición y prevención de notificaciones innecesarias`.

Una notificación deberá tener un destinatario válido.

En el frente del Propietario que se encuentra actualmente en definición, el destinatario principal será el Propietario cuando corresponda.

Sin embargo, la existencia de una notificación relacionada con un vehículo no deberá otorgar automáticamente a otros actores el derecho a recibirla.

Por lo tanto:

```text
RELACIÓN CON
EL VEHÍCULO
        ≠
AUTORIZACIÓN
AUTOMÁTICA PARA
RECIBIR TODAS SUS
NOTIFICACIONES
```

La definición detallada de destinatarios y de las condiciones necesarias para recibir determinadas notificaciones se desarrollará en `63.13.4 Destinatarios y condiciones para recibir notificaciones`.

La notificación tampoco deberá confundirse con el canal utilizado para comunicarla.

Conceptualmente:

```text
NOTIFICACIÓN
        ≠
CANAL DE
NOTIFICACIÓN
```

La notificación representa la comunicación funcional.

El canal representa el medio mediante el cual dicha comunicación podrá llegar al destinatario.

Esta separación permitirá que la misma lógica funcional de una notificación no dependa necesariamente de una tecnología o mecanismo específico.

Los canales y mecanismos se desarrollarán en `63.13.5 Canales y mecanismos de notificación`.

Este punto tampoco deberá definir todavía:

- Qué canales específicos estarán disponibles.
- Qué tecnología será utilizada para las notificaciones.
- Qué proveedor técnico será utilizado.
- La frecuencia concreta de las notificaciones.
- Los intervalos de repetición.
- Los horarios de envío.
- Los criterios definitivos de reenvío.
- Las preferencias configurables por el Propietario.
- Qué comunicaciones podrán desactivarse.
- Los estados técnicos de entrega.
- La confirmación técnica de recepción.
- La representación visual de las notificaciones.
- Las tablas o estructuras de almacenamiento.
- Los identificadores técnicos.
- Las APIs o servicios responsables de generarlas o enviarlas.
- Los mecanismos de procesamiento en segundo plano.

Estos aspectos deberán desarrollarse posteriormente en los puntos funcionales o componentes técnicos correspondientes.

Como principio general:

```text
ORIGEN FUNCIONAL
        ↓
INFORMACIÓN QUE
PUEDE REQUERIR
COMUNICACIÓN
        ↓
REGLAS APLICABLES
        ↓
¿CORRESPONDE
NOTIFICAR?
        ↓
NOTIFICACIÓN
CUANDO CORRESPONDA
        ↓
PROPIETARIO
```

manteniendo siempre diferenciados:

```text
CONDICIÓN
        ≠
ESTADO
        ≠
ALERTA
        ≠
RECOMENDACIÓN
        ≠
NOTIFICACIÓN
        ≠
INTERVENCIÓN
REALIZADA
```

Vehículos Services deberá utilizar las notificaciones para comunicar al Propietario información que deba ponerse en su conocimiento, manteniendo separada la comunicación de la condición, alerta, recomendación, evento o solicitud que la origine y evitando interpretar una notificación como evidencia de que la situación comunicada fue atendida, resuelta o ejecutada.

---

### 63.13.2 Condiciones que pueden originar una notificación

Una notificación podrá originarse cuando Vehículos Services identifique que determinada información, condición, evento o solicitud funcional debe ser comunicada al Propietario de acuerdo con las reglas aplicables.

La existencia de información dentro de la plataforma no deberá significar automáticamente que deba generarse una notificación.

Conceptualmente:

```text
INFORMACIÓN,
CONDICIÓN,
EVENTO O SOLICITUD
        ↓
EVALUACIÓN DE
LAS REGLAS DE
COMUNICACIÓN
        ↓
¿REQUIERE
COMUNICACIÓN?
        │
   ┌────┴────┐
   ↓         ↓
  SÍ         NO
   │         │
   ↓         ↓
NOTIFICACIÓN NO SE GENERA
CUANDO       NOTIFICACIÓN
CORRESPONDA
```

Por lo tanto:

```text
EXISTENCIA DE
INFORMACIÓN
        ≠
NOTIFICACIÓN
AUTOMÁTICA
```

y:

```text
CAMBIO DE
INFORMACIÓN
        ≠
NOTIFICACIÓN
AUTOMÁTICA
```

La generación de una notificación deberá estar sustentada en una condición funcional que determine que determinada información debe ser comunicada.

Vehículos Services deberá permitir que diferentes situaciones funcionales puedan originar notificaciones cuando corresponda.

Conceptualmente, estas situaciones podrán provenir de elementos como:

- Alertas.
- Recomendaciones.
- Solicitudes funcionales.
- Recordatorios.
- Eventos relevantes.
- Cambios relevantes de información.
- Otras situaciones que posteriormente sean definidas por las funcionalidades de la plataforma.

Esta enumeración no deberá significar que cualquier elemento perteneciente a estas categorías genere necesariamente una notificación.

Cada situación deberá cumplir las condiciones funcionales aplicables.

#### Alertas como posible origen de una notificación

Una alerta podrá originar una notificación cuando las reglas correspondientes determinen que la condición representada por dicha alerta debe ser comunicada al Propietario.

Conceptualmente:

```text
CONDICIÓN
        ↓
ALERTA
        ↓
REGLAS DE
COMUNICACIÓN
        ↓
NOTIFICACIÓN
CUANDO CORRESPONDA
```

Por ejemplo:

```text
ACTIVIDAD:
Cambio de aceite

OBJETIVO:
75.000 km

KILOMETRAJE ACTUAL:
74.300 km

        ↓

CONDICIÓN:
PRÓXIMO AL OBJETIVO

        ↓

ALERTA
CUANDO CORRESPONDA

        ↓

REGLAS DE
COMUNICACIÓN

        ↓

NOTIFICACIÓN
CUANDO CORRESPONDA
```

Sin embargo:

```text
ALERTA GENERADA
        ≠
NOTIFICACIÓN
OBLIGATORIA
```

Una alerta podrá permanecer vigente dentro de Vehículos Services sin que necesariamente deba producir una notificación cada vez que sea evaluada.

De igual manera, una actualización de una alerta no deberá generar automáticamente una nueva notificación.

Por lo tanto:

```text
ALERTA
ACTUALIZADA
        ≠
NUEVA NOTIFICACIÓN
OBLIGATORIA
```

La decisión de volver a comunicar una situación deberá depender de las reglas correspondientes.

La frecuencia y repetición de estas comunicaciones se desarrollarán específicamente en `63.13.6 Frecuencia, repetición y prevención de notificaciones innecesarias`.

#### Recomendaciones como posible origen de una notificación

Una recomendación podrá ser comunicada mediante una notificación cuando exista una condición funcional que determine que dicha orientación debe ponerse en conocimiento del Propietario.

Conceptualmente:

```text
INFORMACIÓN
        ↓
REGLAS APLICABLES
        ↓
RECOMENDACIÓN
        ↓
¿DEBE COMUNICARSE?
        ↓
NOTIFICACIÓN
CUANDO CORRESPONDA
```

Por ejemplo:

```text
RECOMENDACIÓN:

Considerar la revisión
de determinada actividad
de mantenimiento.

        ↓

REGLAS DE
COMUNICACIÓN

        ↓

NOTIFICACIÓN
CUANDO CORRESPONDA
```

Sin embargo:

```text
RECOMENDACIÓN
GENERADA
        ≠
NOTIFICACIÓN
OBLIGATORIA
```

La recomendación deberá continuar existiendo como información funcional independiente de que sea o no comunicada mediante una notificación.

La notificación tampoco deberá transformar la recomendación en una alerta.

Por lo tanto:

```text
RECOMENDACIÓN
        ↓
NOTIFICACIÓN
        ≠
ALERTA
```

La relación detallada entre estos conceptos deberá mantenerse conforme a lo definido en `63.12.8 Diferencia entre alerta, recomendación y notificación` y `63.13.1 Definición y propósito de una notificación`.

#### Solicitudes funcionales como posible origen de una notificación

Vehículos Services podrá generar notificaciones para solicitar al Propietario determinada información o acción necesaria para mantener actualizado un proceso funcional.

Por ejemplo, la plataforma podrá requerir una actualización del kilometraje del vehículo.

Conceptualmente:

```text
ÚLTIMA LECTURA
DE KILOMETRAJE
        ↓
SE CUMPLE UNA
CONDICIÓN PARA
SOLICITAR
ACTUALIZACIÓN
        ↓
SOLICITUD
FUNCIONAL
        ↓
NOTIFICACIÓN
CUANDO CORRESPONDA
        ↓
PROPIETARIO
```

En este escenario:

```text
SOLICITUD DE
ACTUALIZACIÓN
DE KILOMETRAJE
        ≠
ALERTA DE
MANTENIMIENTO
```

La plataforma podrá comunicar una solicitud sin afirmar que exista una condición negativa sobre el vehículo.

Por ejemplo:

```text
NO EXISTE UNA
LECTURA RECIENTE
        ≠
KILOMETRAJE
INCORRECTO
```

y:

```text
SOLICITAR
ACTUALIZACIÓN
        ≠
AFIRMAR QUE EXISTE
UNA FALLA
```

La solicitud deberá comunicar únicamente la necesidad funcional correspondiente.

#### Recordatorios como posible origen de una notificación

Vehículos Services podrá utilizar notificaciones para recordar al Propietario determinada situación previamente conocida cuando las reglas funcionales establezcan que dicha comunicación debe repetirse.

Conceptualmente:

```text
SITUACIÓN
PREVIAMENTE
IDENTIFICADA
        ↓
CONTINÚA SIENDO
RELEVANTE
        ↓
SE CUMPLE UNA
CONDICIÓN DE
RECORDATORIO
        ↓
NOTIFICACIÓN
CUANDO CORRESPONDA
```

Un recordatorio no deberá interpretarse automáticamente como una nueva situación.

Por lo tanto:

```text
NUEVO RECORDATORIO
        ≠
NUEVA ALERTA
OBLIGATORIA
```

Por ejemplo, si continúa vigente una misma alerta de mantenimiento:

```text
UNA ALERTA
        ↓
PUEDE ORIGINAR
UNA NOTIFICACIÓN
        ↓
Y POSTERIORMENTE
UN RECORDATORIO
CUANDO CORRESPONDA
```

sin que esto signifique:

```text
DOS ALERTAS
DIFERENTES
```

La posibilidad de generar recordatorios tampoco deberá significar que estos deban repetirse indefinidamente o en cada nueva evaluación.

Las condiciones de repetición deberán regirse por lo que posteriormente se defina en `63.13.6 Frecuencia, repetición y prevención de notificaciones innecesarias`.

#### Eventos relevantes como posible origen de una notificación

Determinados eventos registrados en Vehículos Services podrán originar una notificación cuando exista una razón funcional para comunicar su ocurrencia al Propietario.

Conceptualmente:

```text
EVENTO
        ↓
¿ES NECESARIO
COMUNICARLO?
        ↓
NOTIFICACIÓN
CUANDO CORRESPONDA
```

Sin embargo:

```text
EVENTO REGISTRADO
        ≠
NOTIFICACIÓN
OBLIGATORIA
```

No todos los eventos del vehículo deberán producir una comunicación.

Por ejemplo, la existencia de un nuevo registro histórico no deberá significar automáticamente que deba generarse una notificación.

```text
NUEVO REGISTRO
HISTÓRICO
        ≠
NOTIFICACIÓN
AUTOMÁTICA
```

Deberá existir una condición funcional que justifique la comunicación.

Esto permitirá evitar que cada modificación o incorporación de información dentro de Vehículos Services produzca comunicaciones innecesarias.

#### Cambios relevantes de información como posible origen de una notificación

Un cambio de información podrá originar una notificación cuando dicho cambio tenga relevancia funcional suficiente para requerir comunicación al Propietario.

Conceptualmente:

```text
INFORMACIÓN
ANTERIOR
        ↓
CAMBIO VÁLIDO
        ↓
EVALUACIÓN
        ↓
¿EL CAMBIO
REQUIERE SER
COMUNICADO?
        ↓
NOTIFICACIÓN
CUANDO CORRESPONDA
```

Por lo tanto:

```text
CAMBIO DE DATO
        ≠
NOTIFICACIÓN
AUTOMÁTICA
```

La relevancia del cambio deberá depender del contexto funcional.

Por ejemplo, una corrección menor que no produzca ningún efecto relevante sobre el seguimiento podrá no requerir comunicación.

En cambio, una modificación que cambie una condición relevante podrá ser susceptible de comunicación cuando las reglas así lo establezcan.

La notificación deberá comunicar la situación que pueda sustentarse con la información disponible y no deberá atribuir al cambio consecuencias que no hayan sido determinadas.

#### Ausencia de información como posible origen de una notificación

La ausencia de determinada información podrá originar una notificación únicamente cuando exista una regla funcional que determine que dicha ausencia debe ser comunicada o que se requiere una acción del Propietario.

Por lo tanto:

```text
DATO AUSENTE
        ≠
NOTIFICACIÓN
AUTOMÁTICA
```

Por ejemplo:

```text
NO EXISTE
KILOMETRAJE
ACTUALIZADO
        ↓
REGLA DETERMINA
QUE DEBE SOLICITARSE
ACTUALIZACIÓN
        ↓
NOTIFICACIÓN
CUANDO CORRESPONDA
```

En este caso, la comunicación deberá referirse a la información faltante o a la necesidad de actualizarla.

No deberá transformar la ausencia de información en una condición no comprobada.

Por ejemplo:

```text
NO SE CONOCE
EL KILOMETRAJE ACTUAL
```

no deberá comunicarse como:

```text
EL MANTENIMIENTO
ESTÁ VENCIDO
```

si la información disponible no permite determinarlo.

Por lo tanto:

```text
INFORMACIÓN
DESCONOCIDA
        ≠
CONDICIÓN NEGATIVA
CONFIRMADA
```

#### Información inconsistente como posible origen de una notificación

Cuando exista información potencialmente inconsistente, Vehículos Services no deberá utilizarla automáticamente como si fuera un hecho confirmado para generar una notificación sobre el estado real del vehículo.

Por ejemplo:

```text
KILOMETRAJE ACTUAL
VALIDADO:
75.000 km

        ↓

NUEVA LECTURA:
45.000 km

        ↓

POSIBLE
INCONSISTENCIA
```

La plataforma no deberá concluir automáticamente:

```text
KILOMETRAJE ACTUAL:
45.000 km
```

ni utilizar dicho valor como información confirmada para comunicar condiciones derivadas que no hayan sido validadas.

Sin embargo, la inconsistencia misma podrá originar una comunicación cuando exista una regla funcional que determine que el Propietario debe conocerla o revisarla.

Conceptualmente:

```text
INFORMACIÓN
POTENCIALMENTE
INCONSISTENTE
        ↓
CONDICIÓN DE
REVISIÓN
        ↓
NOTIFICACIÓN
CUANDO CORRESPONDA
```

En este caso, deberá comunicarse la existencia de la inconsistencia o necesidad de revisión y no una conclusión que todavía no haya sido confirmada.

Por lo tanto:

```text
NOTIFICACIÓN SOBRE
UNA INCONSISTENCIA
        ≠
CONFIRMACIÓN DEL
DATO INCONSISTENTE
```

#### Una misma situación no deberá producir comunicaciones duplicadas innecesariamente

Cuando diferentes componentes funcionales se encuentren relacionados con una misma situación, Vehículos Services deberá evitar asumir que cada resultado requiere necesariamente una notificación independiente.

Por ejemplo:

```text
CONDICIÓN DE
MANTENIMIENTO
        ↓
ESTADO
        +
ALERTA
        +
RECOMENDACIÓN
```

no deberá significar automáticamente:

```text
NOTIFICACIÓN 1:
POR EL ESTADO

NOTIFICACIÓN 2:
POR LA ALERTA

NOTIFICACIÓN 3:
POR LA RECOMENDACIÓN
```

La plataforma deberá poder evaluar la situación de manera coherente y determinar qué comunicación corresponde según las reglas aplicables.

Conceptualmente:

```text
MISMA SITUACIÓN
        ↓
VARIOS RESULTADOS
FUNCIONALES
RELACIONADOS
        ↓
EVALUACIÓN DE
COMUNICACIÓN
        ↓
NOTIFICACIÓN O
NOTIFICACIONES
QUE REALMENTE
CORRESPONDAN
```

Por lo tanto:

```text
MÚLTIPLES RESULTADOS
FUNCIONALES
        ≠
MÚLTIPLES
NOTIFICACIONES
OBLIGATORIAS
```

Esto deberá evitar comunicaciones redundantes sin eliminar la posibilidad de que situaciones realmente diferentes requieran comunicaciones independientes.

#### Una misma situación podrá evolucionar sin convertirse automáticamente en un nuevo origen independiente

Una condición que ya haya originado una notificación podrá evolucionar posteriormente.

Por ejemplo:

```text
CAMBIO DE ACEITE

PRÓXIMO AL OBJETIVO
        ↓
NOTIFICACIÓN
CUANDO CORRESPONDA

        ↓

POSTERIORMENTE

OBJETIVO SUPERADO
```

La nueva condición podrá requerir una nueva comunicación si las reglas así lo determinan.

Sin embargo:

```text
CAMBIO DE CONDICIÓN
        ≠
NUEVA NOTIFICACIÓN
AUTOMÁTICA
```

Deberá evaluarse si el cambio representa una situación que requiere volver a ser comunicada.

Esta evaluación permitirá distinguir entre:

```text
MISMA SITUACIÓN
SIN NECESIDAD
DE NUEVA COMUNICACIÓN
```

y:

```text
EVOLUCIÓN RELEVANTE
QUE REQUIERE
NUEVA COMUNICACIÓN
```

La frecuencia y repetición concretas no deberán definirse en este punto.

#### La resolución de una situación también podrá ser comunicable cuando corresponda

La desaparición o resolución de una condición no deberá generar automáticamente una notificación.

Sin embargo, determinadas situaciones podrán requerir que el Propietario sea informado de que una condición previamente comunicada ha cambiado o dejado de aplicar.

Conceptualmente:

```text
CONDICIÓN
PREVIAMENTE
COMUNICADA
        ↓
NUEVA INFORMACIÓN
O EVENTO
        ↓
CONDICIÓN
RESUELTA O
MODIFICADA
        ↓
¿DEBE COMUNICARSE
EL CAMBIO?
        ↓
NOTIFICACIÓN
CUANDO CORRESPONDA
```

Por lo tanto:

```text
ALERTA RESUELTA
        ≠
NOTIFICACIÓN DE
RESOLUCIÓN
OBLIGATORIA
```

La comunicación de una resolución deberá depender de las reglas funcionales correspondientes.

#### Alcance futuro

Las notificaciones no deberán limitarse exclusivamente al mantenimiento.

A medida que Vehículos Services incorpore o detalle otros componentes funcionales, podrán existir condiciones de comunicación relacionadas, por ejemplo, con:

- Documentación del vehículo.
- Kilometraje.
- Abastecimiento y consumo energético.
- Preparación para viajes.
- Información pendiente o inconsistente.
- Relaciones o autorizaciones relevantes.
- Otras funcionalidades futuras.

La inclusión conceptual de estos componentes no deberá significar que desde este momento todas sus condiciones de notificación estén definidas.

Cada componente deberá establecer posteriormente qué situaciones son realmente comunicables.

Por lo tanto:

```text
FUNCIONALIDAD
EXISTENTE
        ≠
NOTIFICACIONES
AUTOMÁTICAMENTE
DEFINIDAS PARA
ESA FUNCIONALIDAD
```

Este punto deberá establecer únicamente el principio general de qué tipos de situaciones pueden llegar a originar una notificación.

No deberá definir todavía:

- Qué destinatarios específicos recibirán cada tipo de notificación.
- Los permisos necesarios para otros actores.
- Los canales utilizados.
- La tecnología de envío.
- La frecuencia concreta.
- Los intervalos de repetición.
- La cantidad máxima de recordatorios.
- Los horarios de comunicación.
- Las preferencias configurables por el Propietario.
- Los estados técnicos de entrega.
- La representación visual.
- Las estructuras de almacenamiento.
- Las APIs o servicios de procesamiento.

Estos aspectos deberán desarrollarse en los puntos posteriores de `63.13 NOTIFICACIONES` o en los componentes técnicos correspondientes.

Como principio general:

```text
ALERTA
        ┐
RECOMENDACIÓN
        │
SOLICITUD
        │
RECORDATORIO
        ├──→ REGLAS DE
EVENTO  │    COMUNICACIÓN
        │         ↓
CAMBIO  │    ¿CORRESPONDE
RELEVANTE       NOTIFICAR?
        │         ↓
AUSENCIA │   NOTIFICACIÓN
DE DATOS │   CUANDO
        │    CORRESPONDA
INCONSISTENCIA
        ┘
```

manteniendo siempre:

```text
SITUACIÓN
FUNCIONAL
        ≠
NOTIFICACIÓN
AUTOMÁTICA
```

Vehículos Services deberá generar notificaciones únicamente cuando exista una condición funcional que justifique comunicar determinada información al Propietario, evitando convertir cada alerta, recomendación, evento, cambio, ausencia de información o reevaluación en una comunicación automática y evitando duplicaciones innecesarias derivadas de una misma situación.

---

### 63.13.3 Relación entre alertas, recomendaciones y notificaciones

Vehículos Services deberá mantener una relación funcional clara entre las alertas, recomendaciones y notificaciones, conservando al mismo tiempo la independencia conceptual de cada una.

Estos elementos podrán participar en una misma situación, pero deberán responder a responsabilidades diferentes.

Conceptualmente:

```text
ALERTA
        =
REPRESENTA UNA
CONDICIÓN RELEVANTE


RECOMENDACIÓN
        =
ORIENTA SOBRE UNA
POSIBLE ACCIÓN


NOTIFICACIÓN
        =
COMUNICA INFORMACIÓN
AL PROPIETARIO
CUANDO CORRESPONDA
```

Por lo tanto:

```text
ALERTA
        ≠
RECOMENDACIÓN
        ≠
NOTIFICACIÓN
```

Esta separación deberá mantenerse incluso cuando los tres elementos se originen a partir de una misma situación funcional.

Por ejemplo:

```text
ACTIVIDAD:
Cambio de aceite

OBJETIVO:
75.000 km

KILOMETRAJE ACTUAL:
74.300 km

        ↓

EVALUACIÓN
        ↓

CONDICIÓN:
PRÓXIMO AL OBJETIVO
```

A partir de esta condición podrán existir, cuando las reglas correspondientes así lo determinen:

```text
CONDICIÓN
        │
        ├── ALERTA
        │
        └── RECOMENDACIÓN
```

y posteriormente:

```text
ALERTA /
RECOMENDACIÓN
        ↓
REGLAS DE
COMUNICACIÓN
        ↓
NOTIFICACIÓN
CUANDO CORRESPONDA
        ↓
PROPIETARIO
```

Esto no deberá interpretarse como una secuencia obligatoria para todas las situaciones.

No deberá asumirse:

```text
CONDICIÓN
        ↓
ALERTA
        ↓
RECOMENDACIÓN
        ↓
NOTIFICACIÓN
```

como el único flujo posible.

Dependiendo de las reglas funcionales aplicables, podrán existir diferentes combinaciones.

Por ejemplo:

```text
ESCENARIO 1

CONDICIÓN
        ↓
ALERTA
```

También:

```text
ESCENARIO 2

CONDICIÓN
        ↓
ALERTA
        ↓
NOTIFICACIÓN
```

También:

```text
ESCENARIO 3

CONDICIÓN
        ↓
RECOMENDACIÓN
```

También:

```text
ESCENARIO 4

CONDICIÓN
        ↓
RECOMENDACIÓN
        ↓
NOTIFICACIÓN
```

Y cuando corresponda:

```text
ESCENARIO 5

CONDICIÓN
        ↓
ALERTA
        +
RECOMENDACIÓN
        ↓
NOTIFICACIÓN
```

Por lo tanto:

```text
EXISTENCIA DE
ALERTA
        ≠
EXISTENCIA
OBLIGATORIA DE
RECOMENDACIÓN
```

```text
EXISTENCIA DE
RECOMENDACIÓN
        ≠
EXISTENCIA
OBLIGATORIA DE
ALERTA
```

y:

```text
EXISTENCIA DE
CUALQUIERA DE LAS
ANTERIORES
        ≠
NOTIFICACIÓN
OBLIGATORIA
```

La relación entre estos elementos deberá depender de las reglas funcionales aplicables a cada situación.

#### Relación entre alerta y notificación

Una alerta podrá ser uno de los orígenes funcionales de una notificación.

Conceptualmente:

```text
CONDICIÓN
        ↓
ALERTA
        ↓
REGLAS DE
COMUNICACIÓN
        ↓
NOTIFICACIÓN
CUANDO CORRESPONDA
```

Sin embargo, la alerta deberá continuar representando la condición relevante identificada, mientras que la notificación deberá representar la comunicación realizada al Propietario.

Por lo tanto:

```text
ALERTA
        ≠
NOTIFICACIÓN
```

La generación de una notificación no deberá sustituir la alerta.

De igual manera, la ausencia de una notificación no deberá significar que la alerta dejó de existir.

Conceptualmente:

```text
ALERTA VIGENTE
        ↓
NO SE GENERA
NOTIFICACIÓN
EN ESE MOMENTO
        ↓
LA ALERTA PUEDE
CONTINUAR VIGENTE
```

Por lo tanto:

```text
SIN NOTIFICACIÓN
        ≠
SIN ALERTA
```

Una alerta tampoco deberá duplicarse únicamente porque haya sido comunicada varias veces.

Conceptualmente:

```text
UNA ALERTA
        ↓
PUEDE ORIGINAR
NOTIFICACIONES
CUANDO CORRESPONDA
```

sin que esto signifique:

```text
CADA NOTIFICACIÓN
        =
NUEVA ALERTA
```

La cantidad de comunicaciones relacionadas con una alerta deberá mantenerse diferenciada de la cantidad de alertas existentes.

Por lo tanto:

```text
NÚMERO DE
NOTIFICACIONES
        ≠
NÚMERO DE
ALERTAS
```

La repetición de comunicaciones deberá regirse posteriormente por `63.13.6 Frecuencia, repetición y prevención de notificaciones innecesarias`.

#### Relación entre recomendación y notificación

Una recomendación podrá ser comunicada al Propietario mediante una notificación cuando las reglas aplicables determinen que dicha orientación debe ponerse en su conocimiento.

Conceptualmente:

```text
RECOMENDACIÓN
        ↓
REGLAS DE
COMUNICACIÓN
        ↓
NOTIFICACIÓN
CUANDO CORRESPONDA
```

Sin embargo:

```text
RECOMENDACIÓN
        ≠
NOTIFICACIÓN
```

La recomendación deberá conservar el contenido funcional que orienta al Propietario.

La notificación deberá representar la comunicación de dicha información.

Por ejemplo:

```text
RECOMENDACIÓN:

Considerar la revisión
del cambio de aceite
según corresponda.
```

podrá ser comunicada mediante:

```text
NOTIFICACIÓN
        ↓
PROPIETARIO
```

sin que la recomendación deje de existir como elemento funcional independiente.

Por lo tanto:

```text
RECOMENDACIÓN
NO NOTIFICADA
        ≠
RECOMENDACIÓN
INEXISTENTE
```

Una recomendación podrá existir dentro de Vehículos Services aunque no sea comunicada mediante una notificación independiente.

De igual manera, una recomendación comunicada varias veces no deberá convertirse en múltiples recomendaciones únicamente por el número de notificaciones generadas.

Conceptualmente:

```text
UNA RECOMENDACIÓN
        ↓
PUEDE SER COMUNICADA
CUANDO CORRESPONDA
        ↓
UNA O MÁS
NOTIFICACIONES
SEGÚN LAS REGLAS
APLICABLES
```

sin que esto signifique:

```text
CADA NOTIFICACIÓN
        =
NUEVA RECOMENDACIÓN
```

#### Relación entre alerta y recomendación

Una misma condición podrá originar una alerta, una recomendación o ambas cuando las reglas aplicables así lo determinen.

Por ejemplo:

```text
CONDICIÓN:

Cambio de aceite
próximo a su objetivo

        │
        ├── ALERTA:
        │   existe una condición
        │   relevante
        │
        └── RECOMENDACIÓN:
            considerar la revisión
            o realización de la
            actividad cuando
            corresponda
```

La alerta deberá informar sobre la condición relevante.

La recomendación deberá orientar al Propietario sobre una posible acción o consideración.

Por lo tanto:

```text
ALERTA
        ≠
RECOMENDACIÓN
```

aunque ambas puedan estar relacionadas con la misma condición.

La recomendación tampoco deberá utilizarse como mecanismo para cambiar el estado o resolver una alerta.

Por ejemplo:

```text
ALERTA
        ↓
RECOMENDACIÓN
GENERADA
```

no deberá significar:

```text
ALERTA
RESUELTA
```

De igual manera, que el Propietario consulte una recomendación no deberá significar que la condición asociada fue atendida.

Por lo tanto:

```text
RECOMENDACIÓN
CONSULTADA
        ≠
ACCIÓN REALIZADA
```

#### Una notificación podrá comunicar información relacionada con más de un elemento funcional

Cuando una alerta y una recomendación correspondan a una misma situación, Vehículos Services no deberá asumir que cada elemento necesita obligatoriamente una notificación independiente.

Por ejemplo:

```text
CONDICIÓN:
CAMBIO DE ACEITE
PRÓXIMO AL OBJETIVO
        │
        ├── ALERTA
        │
        └── RECOMENDACIÓN
```

no deberá producir automáticamente:

```text
NOTIFICACIÓN 1:
ALERTA

        +

NOTIFICACIÓN 2:
RECOMENDACIÓN
```

La plataforma deberá poder determinar, según las reglas de comunicación aplicables, si la información relacionada puede comunicarse de manera coherente dentro de una misma notificación.

Conceptualmente:

```text
ALERTA
        +
RECOMENDACIÓN
        ↓
MISMA SITUACIÓN
FUNCIONAL
        ↓
REGLAS DE
COMUNICACIÓN
        ↓
UNA COMUNICACIÓN
COHERENTE
CUANDO CORRESPONDA
```

Por ejemplo, conceptualmente una comunicación podría informar:

```text
CONDICIÓN:
El cambio de aceite
se encuentra próximo
a su objetivo.

ORIENTACIÓN:
Considere revisar o
realizar el mantenimiento
cuando corresponda.
```

Esto permitiría comunicar conjuntamente la condición y la orientación sin convertirlas en el mismo concepto.

Por lo tanto:

```text
MISMA NOTIFICACIÓN
        ≠
MISMO CONCEPTO
FUNCIONAL
```

Una notificación podrá contener información proveniente de elementos funcionales relacionados manteniendo diferenciada la naturaleza de cada información.

Sin embargo, esta posibilidad no deberá significar que todas las alertas y recomendaciones relacionadas deban agruparse obligatoriamente.

Cuando existan situaciones funcionalmente diferentes, podrán requerirse comunicaciones independientes.

Por ejemplo:

```text
ALERTA A:
Cambio de aceite

ALERTA B:
Documento próximo
a vencer
```

podrán requerir tratamientos de comunicación diferentes según las reglas aplicables.

Por lo tanto:

```text
MISMO VEHÍCULO
        ≠
UNA ÚNICA
NOTIFICACIÓN PARA
TODAS LAS SITUACIONES
```

La decisión de agrupar o separar comunicaciones deberá responder a criterios funcionales y no únicamente a que la información pertenezca al mismo vehículo.

#### La notificación no deberá alterar el elemento que comunica

La generación, envío o consulta de una notificación no deberá modificar automáticamente la alerta o recomendación relacionada.

Conceptualmente:

```text
ALERTA
        ↓
NOTIFICACIÓN
        ↓
PROPIETARIO
```

no deberá producir automáticamente:

```text
ALERTA RESUELTA
```

De igual manera:

```text
RECOMENDACIÓN
        ↓
NOTIFICACIÓN
        ↓
PROPIETARIO
```

no deberá producir automáticamente:

```text
RECOMENDACIÓN
EJECUTADA
```

Por lo tanto:

```text
COMUNICAR
        ≠
RESOLVER
```

y:

```text
COMUNICAR
        ≠
EJECUTAR
```

La evolución de una alerta deberá continuar dependiendo de la condición que la originó, conforme a `63.12 ALERTAS`.

La ejecución de una acción recomendada deberá depender de información válida que permita determinar que dicha acción efectivamente ocurrió.

#### La evolución de una alerta o recomendación podrá afectar futuras comunicaciones

Cuando una alerta o recomendación cambie como consecuencia de nueva información, Vehículos Services podrá reevaluar si corresponde generar una nueva notificación.

Conceptualmente:

```text
ALERTA /
RECOMENDACIÓN
        ↓
NUEVA INFORMACIÓN
        ↓
REEVALUACIÓN
        ↓
CAMBIO FUNCIONAL
        ↓
REEVALUACIÓN DE
COMUNICACIÓN
        ↓
NUEVA NOTIFICACIÓN
CUANDO CORRESPONDA
```

Por lo tanto:

```text
CAMBIO DE ALERTA
        ≠
NUEVA NOTIFICACIÓN
AUTOMÁTICA
```

y:

```text
CAMBIO DE
RECOMENDACIÓN
        ≠
NUEVA NOTIFICACIÓN
AUTOMÁTICA
```

La nueva comunicación deberá estar justificada por las reglas aplicables.

Por ejemplo:

```text
ALERTA:
PRÓXIMO AL OBJETIVO
        ↓
NOTIFICACIÓN
CUANDO CORRESPONDA

        ↓

NUEVA INFORMACIÓN

        ↓

ALERTA:
OBJETIVO SUPERADO
```

La evolución podrá justificar una nueva comunicación, pero esta no deberá generarse únicamente porque internamente haya cambiado la información.

Deberá existir una condición funcional de comunicación.

#### La resolución de una alerta deberá mantenerse separada de las notificaciones relacionadas

Cuando una alerta sea resuelta conforme a `63.12.6 Actualización, resolución y cierre de alertas`, las notificaciones que hayan sido generadas anteriormente no deberán convertirse retroactivamente en inexistentes.

Conceptualmente:

```text
ALERTA
        ↓
NOTIFICACIÓN
        ↓
POSTERIORMENTE
ALERTA RESUELTA
```

no deberá significar:

```text
LA NOTIFICACIÓN
NUNCA EXISTIÓ
```

Por lo tanto:

```text
ALERTA RESUELTA
        ≠
ELIMINACIÓN
RETROACTIVA DE
NOTIFICACIONES
```

La alerta y las notificaciones relacionadas deberán conservar sus propias responsabilidades y trazabilidad.

El tratamiento detallado de la trazabilidad de las notificaciones se desarrollará en `63.13.7 Estado, vigencia y trazabilidad de las notificaciones`.

#### La notificación tampoco deberá crear una relación funcional inexistente

Vehículos Services no deberá relacionar arbitrariamente una notificación con una alerta o recomendación cuando dicha comunicación se origine por otro motivo funcional.

Por ejemplo:

```text
SOLICITUD DE
ACTUALIZACIÓN
DE KILOMETRAJE
        ↓
NOTIFICACIÓN
```

no deberá convertirse artificialmente en:

```text
ALERTA DE
MANTENIMIENTO
        ↓
RECOMENDACIÓN
DE MANTENIMIENTO
```

si ninguna de estas condiciones existe.

Por lo tanto:

```text
NOTIFICACIÓN
        ≠
NECESIDAD DE CREAR
UNA ALERTA O
RECOMENDACIÓN
```

La notificación deberá conservar la relación con su verdadero origen funcional.

#### La trazabilidad de cada elemento deberá mantenerse diferenciada

Cuando alerta, recomendación y notificación se encuentren relacionadas, Vehículos Services deberá poder mantener conceptualmente la relación entre ellas sin convertirlas en un único registro funcional.

Por ejemplo:

```text
CONDICIÓN
        ↓
ALERTA
        │
        ├── RECOMENDACIÓN
        │
        └── NOTIFICACIÓN
```

deberá permitir conocer que los elementos están relacionados, manteniendo:

```text
ALERTA
        ≠
RECOMENDACIÓN
        ≠
NOTIFICACIÓN
```

Esto será importante porque cada elemento podrá evolucionar de forma diferente.

Por ejemplo:

```text
ALERTA
PUEDE CONTINUAR
VIGENTE

MIENTRAS

NOTIFICACIÓN
YA FUE COMUNICADA
```

o:

```text
ALERTA
POSTERIORMENTE
SE RESUELVE

MIENTRAS

NOTIFICACIÓN
PERMANECE COMO
ANTECEDENTE DE
COMUNICACIÓN
```

Por lo tanto, el estado o evolución de un elemento no deberá trasladarse automáticamente a los demás.

Conceptualmente:

```text
ESTADO DE
LA ALERTA
        ≠
ESTADO DE LA
NOTIFICACIÓN
```

y:

```text
EVOLUCIÓN DE
LA ALERTA
        ≠
EVOLUCIÓN AUTOMÁTICA
DE TODAS LAS
NOTIFICACIONES
RELACIONADAS
```

Este punto no deberá definir todavía:

- Los destinatarios concretos de cada comunicación.
- Los permisos para recibir notificaciones.
- Los canales disponibles.
- La tecnología utilizada.
- La frecuencia de envío.
- Los criterios concretos de repetición.
- Las reglas definitivas de agrupación de comunicaciones.
- Los horarios de envío.
- Las preferencias configurables por el Propietario.
- Los estados técnicos de entrega.
- Los identificadores técnicos de relación.
- Las tablas o estructuras de almacenamiento.
- Las APIs o servicios responsables de procesar las comunicaciones.

Estos aspectos deberán desarrollarse en los puntos posteriores de `63.13 NOTIFICACIONES` o en los componentes técnicos correspondientes.

Como principio general:

```text
INFORMACIÓN
DEL VEHÍCULO
        +
REGLAS
        ↓
EVALUACIÓN
        ↓
CONDICIÓN
        │
        ├── ALERTA
        │
        └── RECOMENDACIÓN
                │
                ↓
        REGLAS DE
        COMUNICACIÓN
                ↓
        NOTIFICACIÓN
        CUANDO CORRESPONDA
                ↓
        PROPIETARIO
```

sin impedir que otros eventos o solicitudes funcionales puedan originar directamente una comunicación cuando corresponda.

Manteniendo siempre:

```text
ALERTA
        ≠
RECOMENDACIÓN
        ≠
NOTIFICACIÓN
```

y:

```text
NOTIFICAR
        ≠
RESOLVER
        ≠
EJECUTAR
```

Vehículos Services deberá permitir que alertas, recomendaciones y notificaciones se relacionen cuando formen parte de una misma situación funcional, manteniendo independiente la responsabilidad de cada elemento, evitando asociaciones obligatorias, comunicaciones duplicadas innecesarias y cualquier interpretación según la cual comunicar una situación equivalga a resolverla o ejecutar la acción relacionada.

---

### 63.13.4 Destinatarios y condiciones para recibir notificaciones

Toda notificación deberá estar asociada a uno o más destinatarios válidos de acuerdo con la naturaleza de la información que se comunica, la relación existente con el vehículo y las reglas de acceso, autorización y comunicación aplicables.

En el frente del Propietario que se encuentra actualmente en definición, el destinatario principal de las notificaciones será el Propietario cuando corresponda.

Conceptualmente:

```text
INFORMACIÓN QUE
DEBE COMUNICARSE
        ↓
IDENTIFICACIÓN DEL
DESTINATARIO VÁLIDO
        ↓
VERIFICACIÓN DE
CONDICIONES APLICABLES
        ↓
NOTIFICACIÓN
CUANDO CORRESPONDA
```

La existencia de una notificación no deberá significar que cualquier actor relacionado con el vehículo se encuentre autorizado para recibirla.

Por lo tanto:

```text
NOTIFICACIÓN
EXISTENTE
        ≠
AUTORIZACIÓN PARA
CUALQUIER ACTOR
```

La determinación del destinatario deberá considerar el contexto funcional de la comunicación, la relación válida del actor con el vehículo y las condiciones de acceso, autorización o comunicación que resulten aplicables.

Conceptualmente:

```text
NOTIFICACIÓN
        +
RELACIÓN CON
EL VEHÍCULO
        +
CONDICIONES DE
ACCESO Y
AUTORIZACIÓN
        ↓
DESTINATARIO
VÁLIDO
```

No deberá asumirse que la existencia de una relación con el vehículo otorga automáticamente derecho a recibir todas las notificaciones relacionadas con este.

Por lo tanto:

```text
RELACIÓN CON
EL VEHÍCULO
        ≠
AUTORIZACIÓN
AUTOMÁTICA PARA
RECIBIR TODAS SUS
NOTIFICACIONES
```

#### El Propietario como destinatario principal

Dentro del frente funcional actualmente definido, el Propietario deberá considerarse el destinatario principal de las notificaciones relacionadas con sus vehículos cuando las condiciones correspondientes así lo permitan.

Conceptualmente:

```text
VEHÍCULO
        ↓
PROPIETARIO
ACTUAL
        ↓
INFORMACIÓN QUE
DEBE COMUNICARSE
        ↓
NOTIFICACIÓN
CUANDO CORRESPONDA
```

Sin embargo, ser Propietario de un vehículo no deberá significar que necesariamente deba recibir todas las comunicaciones posibles relacionadas con este en todo momento.

Por lo tanto:

```text
SER PROPIETARIO
        ≠
RECIBIR TODAS LAS
NOTIFICACIONES
AUTOMÁTICAMENTE
```

La generación y comunicación de cada notificación deberá continuar dependiendo de las reglas funcionales aplicables.

Por ejemplo, la existencia de información histórica relacionada con un mantenimiento no deberá generar por sí sola una comunicación al Propietario.

```text
REGISTRO
HISTÓRICO
        ≠
NOTIFICACIÓN
AUTOMÁTICA
AL PROPIETARIO
```

Deberá existir una condición funcional que justifique la comunicación.

#### La relación temporal con el vehículo deberá ser considerada

La condición de destinatario deberá considerar la relación vigente del actor con el vehículo cuando la naturaleza de la notificación así lo requiera.

Por ejemplo, si un vehículo cambia de Propietario:

```text
PROPIETARIO A
        ↓
PERÍODO DE
PROPIEDAD
        ↓
TRANSFERENCIA
DEL VEHÍCULO
        ↓
PROPIETARIO B
```

el Propietario anterior no deberá continuar recibiendo automáticamente nuevas notificaciones correspondientes al seguimiento actual del vehículo únicamente porque históricamente estuvo relacionado con este.

Por lo tanto:

```text
PROPIETARIO
ANTERIOR
        ≠
DESTINATARIO
AUTOMÁTICO DE
NUEVAS
NOTIFICACIONES
```

La conservación de la relación histórica con el vehículo deberá mantenerse diferenciada de la condición actual para recibir comunicaciones.

Conceptualmente:

```text
RELACIÓN
HISTÓRICA
        ≠
RELACIÓN
VIGENTE PARA
COMUNICACIONES
```

Esto deberá ser coherente con el principio establecido para el historial vehicular:

```text
CONSERVACIÓN DE
LA INFORMACIÓN
        ≠
DERECHO ACTUAL
DE ACCESO O
COMUNICACIÓN
```

El cambio de Propietario no deberá eliminar las notificaciones históricas que legítimamente formen parte de períodos anteriores, pero tampoco deberá utilizar dichas relaciones históricas como autorización automática para futuras comunicaciones.

#### La relación con un Prestador de Servicios Vehiculares no deberá convertirlo automáticamente en destinatario

La existencia de una relación entre un Prestador de Servicios Vehiculares y un vehículo no deberá significar que dicho Prestador deba recibir automáticamente todas las notificaciones relacionadas con el vehículo.

Por ejemplo:

```text
VEHÍCULO
        ↓
PRESTADOR REALIZA
UNA INTERVENCIÓN
```

no deberá significar:

```text
PRESTADOR
        ↓
RECIBE TODAS LAS
NOTIFICACIONES
FUTURAS DEL
VEHÍCULO
```

Por lo tanto:

```text
PRESTADOR
RELACIONADO CON
EL VEHÍCULO
        ≠
DESTINATARIO
AUTOMÁTICO DE
NOTIFICACIONES
```

La posibilidad de que un Prestador reciba determinadas comunicaciones deberá depender de las funcionalidades, relaciones, permisos y autorizaciones que posteriormente se definan para el frente correspondiente al Prestador de Servicios Vehiculares.

En consecuencia, este punto no deberá establecer todavía un modelo definitivo de notificaciones para Prestadores.

#### Consultar información no deberá equivaler a recibir notificaciones

Un actor podrá encontrarse autorizado para consultar determinada información sin que esto signifique que deba recibir automáticamente notificaciones relacionadas con dicha información.

Por lo tanto:

```text
PERMISO PARA
CONSULTAR
INFORMACIÓN
        ≠
PERMISO O CONDICIÓN
PARA RECIBIR
NOTIFICACIONES
```

De igual manera:

```text
CAPACIDAD PARA
REGISTRAR
INFORMACIÓN
        ≠
CONDICIÓN AUTOMÁTICA
PARA RECIBIR
NOTIFICACIONES
```

Por ejemplo, un Prestador podrá registrar una intervención cuando las reglas correspondientes lo permitan, pero este hecho no deberá convertirlo automáticamente en destinatario de todas las comunicaciones futuras relacionadas con el vehículo.

La consulta, registro y recepción de comunicaciones deberán mantenerse como responsabilidades diferenciadas.

#### Las autorizaciones deberán respetar su alcance

Cuando una notificación dependa de una autorización, esta deberá respetar el alcance funcional de dicha autorización.

Una autorización para acceder o participar en determinada información no deberá interpretarse automáticamente como una autorización general sobre todas las comunicaciones del vehículo.

Conceptualmente:

```text
AUTORIZACIÓN
ESPECÍFICA
        ≠
AUTORIZACIÓN
GENERAL
```

Por ejemplo:

```text
AUTORIZACIÓN PARA
DETERMINADA
INFORMACIÓN
```

no deberá significar automáticamente:

```text
AUTORIZACIÓN PARA
RECIBIR TODAS LAS
NOTIFICACIONES
DEL VEHÍCULO
```

Las condiciones específicas de permisos y autorizaciones deberán definirse posteriormente en los componentes funcionales correspondientes.

#### La existencia de varios actores relacionados no deberá generar múltiples destinatarios automáticamente

Un mismo vehículo podrá encontrarse relacionado con diferentes actores durante su ciclo de vida.

Por ejemplo:

```text
VEHÍCULO
        │
        ├── PROPIETARIO
        │
        ├── PRESTADOR A
        │
        ├── PRESTADOR B
        │
        └── OTROS ACTORES
            FUTUROS
```

La existencia de estas relaciones no deberá significar:

```text
UNA NOTIFICACIÓN
        ↓
SE ENVÍA
AUTOMÁTICAMENTE
A TODOS LOS
ACTORES
```

Cada posible destinatario deberá cumplir las condiciones funcionales aplicables.

Por lo tanto:

```text
MÚLTIPLES ACTORES
RELACIONADOS
        ≠
MÚLTIPLES
DESTINATARIOS
AUTOMÁTICOS
```

Una misma situación podrá eventualmente requerir comunicación a más de un destinatario cuando las reglas funcionales así lo determinen, pero dicha posibilidad deberá establecerse explícitamente y no inferirse únicamente por la existencia de relaciones con el vehículo.

#### El actor que origina información no deberá convertirse automáticamente en destinatario

El actor que registre, incorpore o produzca determinada información no deberá convertirse automáticamente en destinatario de las notificaciones derivadas de dicha información.

Por ejemplo:

```text
ACTOR
REGISTRA
INFORMACIÓN
        ↓
INFORMACIÓN
INCORPORADA
        ↓
EVALUACIÓN
        ↓
NOTIFICACIÓN
CUANDO CORRESPONDA
```

no deberá significar:

```text
ACTOR QUE
REGISTRÓ
        =
DESTINATARIO
AUTOMÁTICO
```

Por lo tanto:

```text
QUIÉN REGISTRÓ
LA INFORMACIÓN
        ≠
QUIÉN DEBE RECIBIR
LA NOTIFICACIÓN
```

Esta separación deberá mantenerse de manera coherente con la distinción ya establecida entre quién realiza una intervención y quién registra la información correspondiente.

#### El destinatario deberá ser válido para la información comunicada

Vehículos Services no deberá utilizar una notificación como mecanismo para proporcionar a un actor información que no se encuentre autorizado a conocer.

Conceptualmente:

```text
INFORMACIÓN
A COMUNICAR
        ↓
VALIDACIÓN DE
DESTINATARIO
        ↓
¿PUEDE RECIBIR
ESTA INFORMACIÓN?
        │
   ┌────┴────┐
   ↓         ↓
  SÍ         NO
   │         │
   ↓         ↓
PUEDE       NO DEBERÁ
CONTINUAR   COMUNICARSE
EL PROCESO  A ESE ACTOR
```

Por lo tanto:

```text
NOTIFICACIÓN
        ≠
MECANISMO PARA
EVITAR REGLAS
DE ACCESO
```

Las notificaciones deberán respetar las condiciones de privacidad, acceso y autorización aplicables a la información que contienen.

La existencia de un mecanismo técnico capaz de enviar una comunicación tampoco deberá utilizarse como criterio suficiente para determinar que un actor puede recibirla.

Conceptualmente:

```text
CAPACIDAD TÉCNICA
DE COMUNICAR
        ≠
AUTORIZACIÓN
FUNCIONAL PARA
COMUNICAR
```

#### Podrán existir múltiples destinatarios cuando funcionalmente corresponda

Vehículos Services deberá permitir conceptualmente que una comunicación pueda estar relacionada con más de un destinatario cuando una funcionalidad futura así lo requiera y las reglas de acceso y autorización lo permitan.

Sin embargo:

```text
POSIBILIDAD DE
MÚLTIPLES
DESTINATARIOS
        ≠
ENVÍO A TODOS
POR DEFECTO
```

La determinación deberá realizarse según la naturaleza de la información y las reglas aplicables a cada destinatario.

En el alcance actualmente definido para el frente del Propietario, no deberá asumirse todavía qué otros actores recibirán notificaciones ni bajo qué circunstancias específicas.

Estas condiciones deberán detallarse cuando se desarrollen los frentes y funcionalidades correspondientes.

#### La pérdida de la condición de destinatario no deberá eliminar el historial

Cuando un actor deje de cumplir las condiciones necesarias para recibir futuras notificaciones, este cambio no deberá eliminar retroactivamente las comunicaciones históricas que hayan sido generadas legítimamente durante el período correspondiente.

Conceptualmente:

```text
ACTOR ERA
DESTINATARIO VÁLIDO
        ↓
NOTIFICACIÓN
GENERADA
        ↓
POSTERIORMENTE
CAMBIA LA RELACIÓN
        ↓
DEJA DE SER
DESTINATARIO PARA
FUTURAS
COMUNICACIONES
```

Esto no deberá significar:

```text
NOTIFICACIONES
HISTÓRICAS
        ↓
ELIMINADAS
AUTOMÁTICAMENTE
```

Por lo tanto:

```text
PÉRDIDA DE
CONDICIÓN ACTUAL
DE DESTINATARIO
        ≠
ELIMINACIÓN
RETROACTIVA DEL
HISTORIAL
```

La conservación, visibilidad y acceso posterior a dichas comunicaciones deberán respetar las reglas de historial, privacidad y permisos que correspondan.

#### Destinatario y canal deberán mantenerse diferenciados

Determinar quién debe recibir una notificación no deberá definir automáticamente el medio mediante el cual esta será comunicada.

Por lo tanto:

```text
DESTINATARIO
        ≠
CANAL
```

Conceptualmente:

```text
NOTIFICACIÓN
        ↓
DESTINATARIO
VÁLIDO
        ↓
CANAL O
MECANISMO
APLICABLE
```

La definición de canales y mecanismos deberá desarrollarse específicamente en `63.13.5 Canales y mecanismos de notificación`.

#### Destinatario y preferencias de comunicación deberán mantenerse diferenciados

Que un Propietario sea un destinatario válido de determinada notificación no deberá significar que todas las condiciones relacionadas con la forma de comunicarla estén definidas únicamente por esa condición.

Por lo tanto:

```text
DESTINATARIO
VÁLIDO
        ≠
PREFERENCIAS DE
COMUNICACIÓN
```

Las preferencias del Propietario podrán influir posteriormente en determinados aspectos de las comunicaciones cuando las reglas funcionales así lo permitan.

Estas preferencias deberán desarrollarse específicamente en `63.13.8 Preferencias y control de notificaciones por parte del Propietario`.

#### La falta de información no deberá utilizarse para inventar un destinatario

Cuando Vehículos Services no disponga de información suficiente para determinar que un actor es destinatario válido de una comunicación, no deberá asumir una relación, autorización o condición que no pueda sustentarse.

Conceptualmente:

```text
DESTINATARIO
NO DETERMINABLE
        ↓
NO INVENTAR
RELACIÓN O
AUTORIZACIÓN
```

Por lo tanto:

```text
INFORMACIÓN
INSUFICIENTE
        ≠
AUTORIZACIÓN
IMPLÍCITA
```

La ausencia de información necesaria deberá tratarse conforme a las reglas funcionales correspondientes y no mediante la asignación arbitraria de un destinatario.

Este punto no deberá definir todavía:

- Los canales concretos de comunicación.
- La tecnología utilizada para enviar notificaciones.
- Direcciones de correo electrónico.
- Números telefónicos.
- Tokens de dispositivos.
- Identificadores técnicos de destinatarios.
- Proveedores externos de comunicación.
- Frecuencias de envío.
- Horarios de comunicación.
- Reglas concretas de repetición.
- Preferencias configurables.
- Estados técnicos de entrega.
- Confirmaciones técnicas de recepción.
- Estructuras de almacenamiento.
- APIs o servicios de comunicación.

Estos aspectos deberán desarrollarse en los puntos posteriores de `63.13 NOTIFICACIONES` o en los componentes técnicos correspondientes.

Como principio general:

```text
INFORMACIÓN QUE
DEBE COMUNICARSE
        ↓
POSIBLE
DESTINATARIO
        ↓
RELACIÓN VÁLIDA
CON EL VEHÍCULO
        +
CONDICIONES DE
ACCESO Y
AUTORIZACIÓN
        ↓
¿ES DESTINATARIO
VÁLIDO?
        │
   ┌────┴────┐
   ↓         ↓
  SÍ         NO
   │         │
   ↓         ↓
PUEDE       NO DEBERÁ
CONTINUAR   RECIBIR ESA
EL PROCESO  COMUNICACIÓN
```

manteniendo siempre:

```text
RELACIÓN CON
EL VEHÍCULO
        ≠
AUTORIZACIÓN
AUTOMÁTICA PARA
RECIBIR
NOTIFICACIONES
```

y:

```text
DESTINATARIO
        ≠
CANAL
        ≠
PREFERENCIA DE
COMUNICACIÓN
```

Vehículos Services deberá garantizar que las notificaciones sean dirigidas únicamente a destinatarios válidos según la relación existente con el vehículo y las reglas funcionales, de acceso y autorización aplicables, evitando asumir que cualquier actor relacionado con el vehículo se encuentra automáticamente autorizado para recibir sus comunicaciones.

---

### 63.13.5 Canales y mecanismos de notificación

Vehículos Services deberá permitir que una notificación pueda hacerse llegar al Propietario mediante uno o más canales o mecanismos habilitados cuando corresponda, manteniendo diferenciada la notificación funcional del medio utilizado para hacerla llegar al destinatario.

Conceptualmente:

```text
INFORMACIÓN QUE
DEBE COMUNICARSE
        ↓
NOTIFICACIÓN
        ↓
DESTINATARIO
VÁLIDO
        +
CANAL O
MECANISMO
APLICABLE
```

La notificación deberá representar la comunicación funcional mediante la cual Vehículos Services pone determinada información en conocimiento del destinatario cuando corresponda.

El canal deberá representar el medio utilizado para hacer llegar dicha notificación al destinatario.

Por lo tanto:

```text
NOTIFICACIÓN
        ≠
CANAL DE
NOTIFICACIÓN
```

Esta separación deberá permitir que la lógica funcional que determina la existencia de una notificación no dependa directamente de una tecnología específica de comunicación.

Por ejemplo:

```text
CONDICIÓN
        ↓
REGLAS DE
COMUNICACIÓN
        ↓
NOTIFICACIÓN
```

deberá mantenerse conceptualmente independiente de:

```text
CANAL O
MECANISMO
UTILIZADO PARA
HACERLA LLEGAR
AL DESTINATARIO
```

La modificación, incorporación o sustitución futura de un canal no deberá requerir redefinir el significado funcional de la notificación.

#### La generación de una notificación no deberá depender de un canal específico

Vehículos Services deberá poder determinar funcionalmente que corresponde generar una notificación antes de establecer el mecanismo concreto mediante el cual será puesta a disposición del destinatario.

Conceptualmente:

```text
ORIGEN
FUNCIONAL
        ↓
REGLAS DE
COMUNICACIÓN
        ↓
NOTIFICACIÓN
        ↓
DETERMINACIÓN DEL
CANAL APLICABLE
```

Por lo tanto:

```text
NO EXISTENCIA DE
UN CANAL ESPECÍFICO
        ≠
NO EXISTENCIA DE
LA NOTIFICACIÓN
FUNCIONAL
```

La disponibilidad o indisponibilidad de un mecanismo concreto de comunicación no deberá modificar la condición, alerta, recomendación, evento o solicitud funcional que haya dado origen a la notificación.

De igual manera:

```text
CAMBIO DE CANAL
        ≠
CAMBIO DEL ORIGEN
FUNCIONAL DE LA
NOTIFICACIÓN
```

#### Los canales deberán considerarse mecanismos de comunicación

Los canales deberán utilizarse como mecanismos mediante los cuales Vehículos Services pueda hacer llegar una notificación al destinatario correspondiente.

Conceptualmente:

```text
NOTIFICACIÓN
        ↓
CANAL
        ↓
DESTINATARIO
```

La existencia de un canal deberá mantenerse separada de la notificación y de la información que esta comunica.

Por ejemplo, una misma información funcional:

```text
CAMBIO DE ACEITE
PRÓXIMO A SU
OBJETIVO
```

no deberá cambiar su significado únicamente porque la notificación correspondiente sea transmitida mediante un mecanismo diferente.

Por lo tanto:

```text
MISMA
NOTIFICACIÓN
        +
CANAL DIFERENTE
        ≠
SIGNIFICADO
FUNCIONAL
DIFERENTE
```

El canal deberá afectar la forma mediante la cual la notificación llega al destinatario y no alterar por sí mismo el contenido funcional que originó dicha notificación.

#### Vehículos Services podrá contemplar diferentes canales

La plataforma deberá permitir conceptualmente la existencia de diferentes canales o mecanismos de notificación.

Sin embargo, en esta etapa del proyecto no deberá establecerse de forma definitiva qué tecnologías o proveedores serán utilizados para implementarlos.

Conceptualmente:

```text
NOTIFICACIÓN
        ↓
CANALES O
MECANISMOS
DISPONIBLES
        ↓
CANAL APLICABLE
CUANDO CORRESPONDA
```

La definición de esta capacidad no deberá interpretarse como una selección anticipada de una solución tecnológica específica.

Por lo tanto:

```text
CAPACIDAD DE
NOTIFICAR
        ≠
TECNOLOGÍA DE
NOTIFICACIÓN
YA DEFINIDA
```

La selección de tecnologías, proveedores y mecanismos técnicos deberá realizarse posteriormente dentro de los componentes técnicos correspondientes.

#### La existencia de un canal no deberá significar que siempre deba utilizarse

Que un determinado canal se encuentre disponible no deberá significar que todas las notificaciones deban utilizar dicho canal.

Por lo tanto:

```text
CANAL
DISPONIBLE
        ≠
CANAL UTILIZADO
OBLIGATORIAMENTE
```

La utilización de un canal deberá depender de las reglas funcionales aplicables, del destinatario, de la disponibilidad del mecanismo y de las condiciones que posteriormente se definan para las comunicaciones.

Conceptualmente:

```text
NOTIFICACIÓN
        +
DESTINATARIO
        +
CANALES
DISPONIBLES
        +
REGLAS
APLICABLES
        ↓
CANAL O
MECANISMO
QUE CORRESPONDA
```

No deberá asumirse que todas las notificaciones tengan necesariamente el mismo tratamiento de comunicación.

#### Una notificación podrá utilizar más de un canal cuando corresponda

Vehículos Services deberá permitir conceptualmente que una misma notificación pueda hacerse llegar mediante más de un canal cuando las reglas funcionales así lo determinen.

Por ejemplo:

```text
NOTIFICACIÓN
        │
        ├── CANAL A
        │
        └── CANAL B
```

Sin embargo:

```text
MÚLTIPLES
CANALES
        ≠
MÚLTIPLES
NOTIFICACIONES
FUNCIONALES
OBLIGATORIAS
```

La utilización de varios canales para hacer llegar una misma notificación no deberá crear artificialmente nuevas alertas, recomendaciones o condiciones funcionales.

Conceptualmente:

```text
UNA
NOTIFICACIÓN
        ↓
DOS MECANISMOS
DE COMUNICACIÓN
```

no deberá significar:

```text
DOS ALERTAS
```

ni:

```text
DOS
RECOMENDACIONES
```

ni necesariamente:

```text
DOS SITUACIONES
FUNCIONALES
DIFERENTES
```

La relación entre una notificación y los mecanismos utilizados para hacerla llegar al destinatario deberá mantenerse diferenciada.

#### Un mismo canal podrá comunicar diferentes tipos de notificaciones

La existencia de un canal tampoco deberá limitarse necesariamente a un único tipo de notificación.

Conceptualmente:

```text
CANAL
        │
        ├── NOTIFICACIÓN
        │   DE MANTENIMIENTO
        │
        ├── SOLICITUD DE
        │   ACTUALIZACIÓN
        │   DE KILOMETRAJE
        │
        ├── NOTIFICACIÓN
        │   RELACIONADA CON
        │   DOCUMENTACIÓN
        │
        └── OTRAS
            NOTIFICACIONES
            FUTURAS
```

La utilización del mismo mecanismo no deberá convertir estas notificaciones en el mismo tipo de comunicación funcional.

Por lo tanto:

```text
MISMO CANAL
        ≠
MISMO ORIGEN
FUNCIONAL
```

Cada notificación deberá conservar la relación con la situación que justificó su generación.

#### El canal deberá ser compatible con el destinatario

La selección de un canal deberá considerar que exista un destinatario válido y que dicho mecanismo pueda utilizarse para hacerle llegar la notificación correspondiente.

Conceptualmente:

```text
NOTIFICACIÓN
        ↓
DESTINATARIO
VÁLIDO
        ↓
CANAL
APLICABLE
```

No deberá asumirse que la existencia de un canal disponible para un actor significa automáticamente que dicho actor puede recibir cualquier información mediante ese mecanismo.

Por lo tanto:

```text
CANAL
DISPONIBLE PARA
UN ACTOR
        ≠
AUTORIZACIÓN PARA
RECIBIR CUALQUIER
NOTIFICACIÓN
```

Las condiciones de destinatarios, relaciones y autorizaciones deberán continuar rigiéndose por lo establecido en `63.13.4 Destinatarios y condiciones para recibir notificaciones`.

El canal no deberá utilizarse para evadir dichas condiciones.

#### La indisponibilidad de un canal no deberá modificar la situación funcional de origen

Cuando un canal no pueda utilizarse o no se encuentre disponible, esta situación no deberá modificar automáticamente la condición funcional que originó la notificación.

Por ejemplo:

```text
ALERTA
VIGENTE
        ↓
NOTIFICACIÓN
GENERADA
        ↓
CANAL NO
DISPONIBLE
```

no deberá significar:

```text
ALERTA
RESUELTA
```

ni:

```text
CONDICIÓN
DESAPARECIDA
```

Por lo tanto:

```text
CANAL NO
DISPONIBLE
        ≠
CONDICIÓN
RESUELTA
```

La situación funcional del vehículo deberá continuar evolucionando de acuerdo con sus propias reglas.

De igual manera, la imposibilidad de utilizar un canal no deberá considerarse evidencia de que el Propietario conoce la información.

#### Utilizar un canal no deberá equivaler automáticamente a confirmar conocimiento del Propietario

La utilización de un mecanismo para hacer llegar una notificación deberá mantenerse diferenciada de la confirmación de que el destinatario efectivamente recibió, consultó o comprendió la información.

Conceptualmente:

```text
NOTIFICACIÓN
        ↓
CANAL
        ↓
INTENTO O RESULTADO
DE COMUNICACIÓN
SEGÚN LA INFORMACIÓN
DISPONIBLE
```

no deberá significar automáticamente:

```text
PROPIETARIO
CONSULTÓ LA
INFORMACIÓN
```

Por lo tanto:

```text
UTILIZACIÓN
DEL CANAL
        ≠
CONSULTA
CONFIRMADA
```

y:

```text
NOTIFICACIÓN
GENERADA
        ≠
CONOCIMIENTO
CONFIRMADO DEL
PROPIETARIO
```

La posibilidad de conocer estados o resultados relacionados con el proceso de comunicación podrá depender del mecanismo utilizado y deberá desarrollarse posteriormente en `63.13.7 Estado, vigencia y trazabilidad de las notificaciones`.

#### El canal no deberá determinar por sí mismo la frecuencia de comunicación

La existencia o utilización de un canal no deberá definir automáticamente cuántas veces debe generarse o hacerse llegar una comunicación relacionada con una misma situación.

Por lo tanto:

```text
CANAL
        ≠
FRECUENCIA DE
NOTIFICACIÓN
```

La repetición de una comunicación deberá depender de las reglas funcionales correspondientes y no simplemente de que exista un mecanismo disponible para utilizarlo nuevamente.

Conceptualmente:

```text
CANAL
DISPONIBLE
        ≠
REENVÍO
AUTOMÁTICO
```

Las condiciones de frecuencia, repetición y prevención de comunicaciones innecesarias deberán desarrollarse específicamente en `63.13.6 Frecuencia, repetición y prevención de notificaciones innecesarias`.

#### Los canales deberán mantenerse diferenciados de las preferencias del Propietario

La disponibilidad de un canal dentro de Vehículos Services no deberá significar automáticamente que dicho canal deba utilizarse para todas las comunicaciones dirigidas al Propietario.

Por lo tanto:

```text
CANAL
DISPONIBLE
        ≠
CANAL
PREFERIDO
```

Las preferencias del Propietario podrán influir posteriormente en la utilización de determinados mecanismos cuando las reglas funcionales así lo permitan.

Sin embargo, la definición de dichas preferencias no deberá desarrollarse en este punto.

Las condiciones relacionadas con preferencias y control deberán establecerse en `63.13.8 Preferencias y control de notificaciones por parte del Propietario`.

#### Los canales no deberán definirse todavía mediante una tecnología específica

En esta etapa del proyecto deberá mantenerse abierta la decisión tecnológica relacionada con los mecanismos de notificación.

Por lo tanto, este punto no deberá establecer como solución definitiva tecnologías, plataformas, servicios o proveedores concretos.

Conceptualmente:

```text
NECESIDAD
FUNCIONAL:
GENERAR UNA
NOTIFICACIÓN
        ↓
CAPACIDAD:
UTILIZAR UN
CANAL
        ↓
TECNOLOGÍA:
PENDIENTE DE
DEFINICIÓN
```

La definición funcional deberá permitir posteriormente evaluar alternativas tecnológicas sin modificar las reglas de negocio establecidas.

Por lo tanto:

```text
CANAL
FUNCIONAL
        ≠
PROVEEDOR
TECNOLÓGICO
```

y:

```text
MECANISMO DE
COMUNICACIÓN
        ≠
IMPLEMENTACIÓN
TÉCNICA YA
SELECCIONADA
```

La selección de tecnologías deberá realizarse posteriormente considerando los requerimientos funcionales, técnicos, de seguridad, costos, escalabilidad y demás criterios que correspondan.

#### Alcance futuro

Los mecanismos de comunicación podrán evolucionar a medida que Vehículos Services incorpore nuevas funcionalidades, nuevos actores o nuevas necesidades de comunicación.

La incorporación futura de un nuevo canal no deberá requerir modificar la naturaleza de las alertas, recomendaciones, eventos o solicitudes que puedan originar las notificaciones.

Conceptualmente:

```text
NUEVO CANAL
        ↓
NUEVA FORMA DE
HACER LLEGAR LA
NOTIFICACIÓN
```

no deberá significar:

```text
NUEVA DEFINICIÓN
DE ALERTA
```

ni:

```text
NUEVA DEFINICIÓN
DE RECOMENDACIÓN
```

ni:

```text
NUEVA DEFINICIÓN
DE NOTIFICACIÓN
```

La evolución de los mecanismos de comunicación deberá mantenerse desacoplada de los conceptos funcionales que originan las comunicaciones.

Este punto no deberá definir todavía:

- Los canales definitivos que estarán disponibles.
- La tecnología específica de notificaciones.
- Proveedores tecnológicos.
- Servicios de notificaciones push.
- Servicios de correo electrónico.
- Servicios de mensajería.
- Números telefónicos.
- Direcciones de correo electrónico.
- Tokens de dispositivos.
- Credenciales técnicas.
- Protocolos de comunicación.
- Frecuencias concretas.
- Horarios de envío.
- Cantidad de reintentos.
- Políticas técnicas de reenvío.
- Confirmaciones técnicas de entrega.
- Preferencias definitivas del Propietario.
- Estructuras de almacenamiento.
- APIs o servicios responsables del envío.
- Procesos técnicos en segundo plano.

Estos aspectos deberán definirse posteriormente en los puntos funcionales correspondientes o durante el diseño técnico de Vehículos Services.

Como principio general:

```text
ORIGEN
FUNCIONAL
        ↓
INFORMACIÓN QUE
DEBE COMUNICARSE
        ↓
NOTIFICACIÓN
        ↓
DESTINATARIO
VÁLIDO
        +
REGLAS
APLICABLES
        ↓
CANAL O
MECANISMO
HABILITADO
```

manteniendo siempre:

```text
NOTIFICACIÓN
        ≠
CANAL
```

```text
DESTINATARIO
        ≠
CANAL
```

```text
CANAL
        ≠
FRECUENCIA
```

y:

```text
CANAL
FUNCIONAL
        ≠
TECNOLOGÍA O
PROVEEDOR
ESPECÍFICO
```

Vehículos Services deberá permitir que las notificaciones puedan hacerse llegar mediante canales o mecanismos adecuados al contexto funcional, al destinatario y a las reglas aplicables, manteniendo la notificación diferenciada del medio utilizado y evitando vincular prematuramente esta capacidad a una tecnología o proveedor específico.



---

### 63.13.6 Frecuencia, repetición y prevención de notificaciones innecesarias

Vehículos Services deberá controlar la frecuencia y repetición de las notificaciones con el propósito de comunicar información relevante al Propietario cuando corresponda, evitando generar comunicaciones innecesarias, duplicadas o repetitivas derivadas de una misma situación funcional.

La existencia de una condición que continúa vigente no deberá significar que deba generarse una nueva notificación cada vez que dicha condición sea evaluada.

Conceptualmente:

```text
CONDICIÓN
VIGENTE
        ↓
EVALUACIÓN
        ↓
CONTINÚA
VIGENTE
        ↓
¿CORRESPONDE
VOLVER A
COMUNICAR?
        │
   ┌────┴────┐
   ↓         ↓
  SÍ         NO
   │         │
   ↓         ↓
NUEVA       NO SE GENERA
NOTIFICACIÓN NUEVA
CUANDO       NOTIFICACIÓN
CORRESPONDA
```

Por lo tanto:

```text
CONDICIÓN
VIGENTE
        ≠
NOTIFICACIÓN
CONTINUA
```

y:

```text
NUEVA
EVALUACIÓN
        ≠
NUEVA
NOTIFICACIÓN
AUTOMÁTICA
```

La repetición de una comunicación deberá responder a una condición funcional que justifique volver a poner determinada información en conocimiento del Propietario.

#### La reevaluación de una situación no deberá generar automáticamente una nueva notificación

Vehículos Services podrá reevaluar una misma condición múltiples veces como consecuencia del paso del tiempo, la actualización del kilometraje, la incorporación de nueva información o la ejecución de otros procesos funcionales.

Por ejemplo:

```text
ALERTA:
CAMBIO DE ACEITE
PRÓXIMO AL OBJETIVO
        ↓
NOTIFICACIÓN
CUANDO CORRESPONDA
        ↓
NUEVA ACTUALIZACIÓN
DE KILOMETRAJE
        ↓
REEVALUACIÓN
        ↓
LA CONDICIÓN
CONTINÚA SIENDO
PRÓXIMA AL OBJETIVO
```

Esta nueva evaluación no deberá significar automáticamente:

```text
NUEVA
NOTIFICACIÓN
```

Por lo tanto:

```text
REEVALUACIÓN
        ≠
REENVÍO
AUTOMÁTICO
```

La plataforma deberá distinguir entre volver a evaluar una situación y volver a comunicarla.

Conceptualmente:

```text
EVALUAR
        ≠
NOTIFICAR
```

Una condición podrá ser evaluada tantas veces como sea necesario para mantener actualizado su estado funcional sin que cada evaluación produzca una nueva comunicación.

#### La persistencia de una condición no deberá producir comunicaciones indefinidas

Una condición podrá permanecer vigente durante determinado período sin que esto signifique que Vehículos Services deba comunicarla repetidamente de forma indefinida.

Por ejemplo:

```text
ALERTA
VIGENTE
        ↓
DÍA 1
        ↓
DÍA 2
        ↓
DÍA 3
        ↓
DÍA 4
```

no deberá significar automáticamente:

```text
DÍA 1:
NOTIFICACIÓN

DÍA 2:
NOTIFICACIÓN

DÍA 3:
NOTIFICACIÓN

DÍA 4:
NOTIFICACIÓN
```

Por lo tanto:

```text
PERSISTENCIA DE
UNA CONDICIÓN
        ≠
REPETICIÓN
INDEFINIDA DE
NOTIFICACIONES
```

La continuidad de una situación podrá ser considerada dentro de las reglas de comunicación, pero no deberá utilizarse por sí sola como justificación universal para generar comunicaciones repetidas.

#### Los recordatorios deberán responder a reglas funcionales

Vehículos Services podrá generar recordatorios cuando una situación previamente comunicada continúe siendo relevante y exista una regla funcional que determine que corresponde volver a comunicarla.

Conceptualmente:

```text
SITUACIÓN
COMUNICADA
        ↓
CONTINÚA
VIGENTE
        ↓
SE CUMPLE UNA
CONDICIÓN DE
RECORDATORIO
        ↓
NUEVA
NOTIFICACIÓN
CUANDO CORRESPONDA
```

Por ejemplo:

```text
ALERTA
        ↓
NOTIFICACIÓN
INICIAL
        ↓
LA CONDICIÓN
CONTINÚA
        ↓
SE CUMPLE UNA
REGLA DE
RECORDATORIO
        ↓
RECORDATORIO
```

Sin embargo:

```text
CONDICIÓN
CONTINÚA
        ≠
RECORDATORIO
AUTOMÁTICO
```

y:

```text
RECORDATORIO
        ≠
NUEVA ALERTA
```

La generación de un recordatorio deberá mantenerse relacionada con la situación previamente comunicada cuando corresponda y no deberá crear artificialmente una nueva alerta, recomendación o condición.

#### La frecuencia podrá depender del tipo y evolución de la situación

La frecuencia con la que una situación pueda volver a comunicarse podrá depender de las características funcionales de dicha situación.

Entre los elementos que podrán ser considerados cuando corresponda se encuentran:

- El tipo de notificación.
- La condición funcional que originó la comunicación.
- La permanencia de dicha condición.
- La evolución de la situación.
- La relevancia de la información.
- La existencia de una alerta relacionada.
- La evolución de una alerta relacionada.
- La existencia de una recomendación relacionada.
- El cumplimiento de una condición de recordatorio.
- El tiempo transcurrido desde una comunicación anterior.
- Las reglas específicas definidas para la funcionalidad correspondiente.
- Las preferencias del Propietario cuando estas resulten aplicables.

Esta enumeración no deberá interpretarse como una fórmula universal ni como la obligación de utilizar todos estos elementos para determinar la frecuencia.

Por lo tanto:

```text
FRECUENCIA
        ≠
VALOR UNIVERSAL
PARA TODAS LAS
NOTIFICACIONES
```

Diferentes tipos de comunicaciones podrán requerir comportamientos diferentes según su naturaleza.

#### No deberá establecerse todavía una frecuencia universal

En esta etapa del proyecto no deberá definirse una frecuencia única aplicable a todas las notificaciones.

Por ejemplo, no deberá establecerse de manera general:

```text
TODAS LAS
NOTIFICACIONES
        ↓
SE REPITEN CADA
24 HORAS
```

ni:

```text
TODAS LAS
NOTIFICACIONES
        ↓
MÁXIMO TRES
RECORDATORIOS
```

ni cualquier otro intervalo o cantidad universal que no haya sido definido funcionalmente.

Por lo tanto:

```text
NOTIFICACIÓN
        ≠
FRECUENCIA
UNIVERSAL
PREDEFINIDA
```

Los valores concretos de frecuencia, intervalos, cantidad de recordatorios y demás parámetros deberán definirse posteriormente para cada caso cuando exista suficiente definición funcional.

#### Una evolución relevante podrá justificar una nueva comunicación

Cuando una situación previamente comunicada evolucione de manera funcionalmente relevante, Vehículos Services podrá determinar que corresponde generar una nueva notificación.

Por ejemplo:

```text
CAMBIO DE ACEITE

CONDICIÓN INICIAL:
PRÓXIMO AL OBJETIVO
        ↓
NOTIFICACIÓN
CUANDO CORRESPONDA

        ↓

NUEVA INFORMACIÓN

        ↓

CONDICIÓN:
OBJETIVO SUPERADO
```

La evolución de:

```text
PRÓXIMO AL
OBJETIVO
```

a:

```text
OBJETIVO
SUPERADO
```

podrá justificar una nueva comunicación cuando las reglas correspondientes así lo determinen.

Sin embargo:

```text
CAMBIO DE
CONDICIÓN
        ≠
NUEVA NOTIFICACIÓN
AUTOMÁTICA
```

Deberá evaluarse si el cambio presenta suficiente relevancia funcional para requerir una nueva comunicación.

Esto permitirá diferenciar entre una simple actualización de información y una evolución que realmente deba ponerse nuevamente en conocimiento del Propietario.

#### Una modificación sin cambio funcional relevante no deberá generar comunicaciones innecesarias

La modificación de información que no produzca un cambio funcional relevante no deberá generar automáticamente una nueva notificación.

Por ejemplo:

```text
INFORMACIÓN
ACTUALIZADA
        ↓
REEVALUACIÓN
        ↓
MISMA CONDICIÓN
FUNCIONAL
```

no deberá significar:

```text
NUEVA
NOTIFICACIÓN
OBLIGATORIA
```

Por lo tanto:

```text
CAMBIO DE
INFORMACIÓN
        ≠
CAMBIO FUNCIONAL
RELEVANTE
```

y:

```text
CAMBIO DE
INFORMACIÓN
        ≠
NUEVA NOTIFICACIÓN
AUTOMÁTICA
```

Vehículos Services deberá evitar utilizar cualquier modificación de datos como motivo suficiente para volver a comunicar una situación que funcionalmente permanece igual.

#### Deberán evitarse notificaciones duplicadas derivadas de una misma situación

Cuando una misma situación produzca diferentes resultados funcionales relacionados, Vehículos Services deberá evitar generar comunicaciones duplicadas innecesarias.

Por ejemplo:

```text
MISMA CONDICIÓN
DE MANTENIMIENTO
        │
        ├── ESTADO
        │
        ├── ALERTA
        │
        └── RECOMENDACIÓN
```

no deberá significar automáticamente:

```text
NOTIFICACIÓN
POR ESTADO
        +
NOTIFICACIÓN
POR ALERTA
        +
NOTIFICACIÓN
POR RECOMENDACIÓN
```

La plataforma deberá evaluar si dichos elementos corresponden a una misma situación comunicable y determinar el tratamiento adecuado conforme a las reglas aplicables.

Por lo tanto:

```text
MÚLTIPLES
RESULTADOS
RELACIONADOS
        ≠
MÚLTIPLES
COMUNICACIONES
OBLIGATORIAS
```

Esto deberá ser coherente con lo establecido en `63.13.2 Condiciones que pueden originar una notificación` y `63.13.3 Relación entre alertas, recomendaciones y notificaciones`.

#### Una comunicación repetida no deberá crear nuevos elementos funcionales

Cuando una misma información deba comunicarse nuevamente, la nueva comunicación no deberá crear artificialmente una nueva alerta, recomendación, intervención o condición.

Conceptualmente:

```text
UNA ALERTA
        ↓
NOTIFICACIÓN
INICIAL
        ↓
POSTERIOR
RECORDATORIO
```

no deberá significar:

```text
DOS ALERTAS
```

Por lo tanto:

```text
NUEVA
NOTIFICACIÓN
        ≠
NUEVA ALERTA
AUTOMÁTICA
```

```text
NUEVA
NOTIFICACIÓN
        ≠
NUEVA RECOMENDACIÓN
AUTOMÁTICA
```

```text
NUEVA
NOTIFICACIÓN
        ≠
NUEVA INTERVENCIÓN
```

Cada elemento deberá conservar su propia identidad y responsabilidad funcional.

#### La utilización de varios canales no deberá confundirse con repetición funcional

Cuando una misma notificación pueda comunicarse mediante más de un canal conforme a `63.13.5 Canales y mecanismos de notificación`, la utilización de dichos canales deberá mantenerse diferenciada de la generación de nuevas notificaciones funcionales.

Conceptualmente:

```text
UNA
NOTIFICACIÓN
        │
        ├── CANAL A
        │
        └── CANAL B
```

no deberá significar automáticamente:

```text
DOS SITUACIONES
FUNCIONALES
```

ni:

```text
DOS ALERTAS
```

La utilización de diferentes mecanismos para comunicar una misma información no deberá utilizarse por sí sola para determinar la cantidad de veces que una situación fue funcionalmente originada.

Por lo tanto:

```text
MÚLTIPLES
CANALES
        ≠
MÚLTIPLES ORÍGENES
FUNCIONALES
```

#### Las preferencias del Propietario podrán influir cuando corresponda

Las preferencias de comunicación del Propietario podrán ser consideradas dentro de las reglas de frecuencia y repetición cuando funcionalmente resulte permitido.

Conceptualmente:

```text
REGLAS DE
COMUNICACIÓN
        +
PREFERENCIAS
APLICABLES
        ↓
TRATAMIENTO DE
LA COMUNICACIÓN
```

Sin embargo:

```text
PREFERENCIA DEL
PROPIETARIO
        ≠
ELIMINACIÓN DE
LA CONDICIÓN
FUNCIONAL
```

Una preferencia relacionada con la forma o frecuencia de comunicación no deberá eliminar la alerta, recomendación, condición o evento que exista dentro de Vehículos Services.

Las reglas detalladas sobre preferencias deberán desarrollarse en `63.13.8 Preferencias y control de notificaciones por parte del Propietario`.

Este punto no deberá determinar todavía qué tipos de comunicaciones podrán ser configurables, obligatorias o exceptuadas de determinadas preferencias.

#### La frecuencia no deberá modificar el origen funcional

Modificar la frecuencia con la que una notificación puede comunicarse no deberá modificar la situación que dio origen a dicha comunicación.

Por ejemplo:

```text
ALERTA
VIGENTE
        ↓
FRECUENCIA DE
COMUNICACIÓN
MODIFICADA
```

no deberá significar:

```text
ALERTA
MODIFICADA
```

Por lo tanto:

```text
CAMBIO DE
FRECUENCIA
        ≠
CAMBIO DE
ALERTA
```

```text
CAMBIO DE
FRECUENCIA
        ≠
CAMBIO DE
RECOMENDACIÓN
```

```text
CAMBIO DE
FRECUENCIA
        ≠
CAMBIO DE
CONDICIÓN
```

La frecuencia deberá afectar únicamente el comportamiento de comunicación cuando corresponda.

#### La resolución de una situación deberá impedir repeticiones injustificadas

Cuando una condición que originó una comunicación deje de aplicar, Vehículos Services deberá reevaluar la necesidad de futuras notificaciones relacionadas con dicha situación.

Conceptualmente:

```text
CONDICIÓN
        ↓
NOTIFICACIÓN
        ↓
POSTERIORMENTE
CONDICIÓN
RESUELTA
        ↓
REEVALUACIÓN DE
FUTURAS
COMUNICACIONES
```

Una situación resuelta no deberá continuar generando recordatorios como si permaneciera vigente, salvo que exista otra razón funcional independiente que justifique una comunicación posterior.

Por lo tanto:

```text
CONDICIÓN
RESUELTA
        ≠
CONTINUAR
RECORDATORIOS
DE LA MISMA
CONDICIÓN
```

Esto no deberá impedir que, cuando corresponda, pueda existir una comunicación relacionada con la resolución de la situación conforme a lo establecido en `63.13.2`.

#### La prevención de comunicaciones innecesarias no deberá ocultar situaciones diferentes

La prevención de duplicaciones no deberá utilizarse para agrupar o suprimir comunicaciones correspondientes a situaciones funcionalmente diferentes.

Por ejemplo:

```text
ALERTA A:
CAMBIO DE ACEITE
VENCIDO

ALERTA B:
DOCUMENTO
PRÓXIMO A VENCER
```

representan situaciones diferentes aunque pertenezcan al mismo vehículo.

Por lo tanto:

```text
MISMO VEHÍCULO
        ≠
MISMA SITUACIÓN
FUNCIONAL
```

La plataforma deberá evitar duplicaciones derivadas de una misma situación sin impedir que situaciones distintas puedan comunicarse independientemente cuando corresponda.

Conceptualmente:

```text
MISMA SITUACIÓN
        ↓
EVITAR
DUPLICACIONES
INNECESARIAS


SITUACIONES
DIFERENTES
        ↓
EVALUAR CADA
COMUNICACIÓN
SEGÚN SUS
PROPIAS REGLAS
```

#### La frecuencia deberá mantenerse como una decisión funcional pendiente de parametrización

En esta etapa deberá definirse el comportamiento conceptual de la frecuencia y repetición sin establecer todavía valores definitivos para cada tipo de notificación.

Vehículos Services deberá permitir que posteriormente puedan definirse reglas específicas para determinar, cuando corresponda:

- Si una comunicación puede repetirse.
- Bajo qué condiciones puede repetirse.
- Cuándo puede generarse un recordatorio.
- Qué evolución funcional puede justificar una nueva comunicación.
- Qué período deberá existir entre comunicaciones cuando aplique.
- Cuántos recordatorios podrán generarse cuando aplique.
- Cuándo deberá dejar de repetirse una comunicación.
- Qué preferencias podrán influir sobre la frecuencia cuando corresponda.

La inclusión de estos criterios no deberá significar que todos deban aplicarse a todas las notificaciones.

Por lo tanto:

```text
CAPACIDAD DE
PARAMETRIZAR
FRECUENCIA
        ≠
FRECUENCIA
DEFINIDA PARA
TODOS LOS CASOS
```

Este punto no deberá definir todavía:

- Intervalos concretos de tiempo.
- Cantidades máximas de recordatorios.
- Horarios específicos.
- Ventanas horarias.
- Frecuencias universales.
- Políticas técnicas de reintento.
- Reintentos por fallos técnicos de entrega.
- Proveedores de comunicación.
- Mecanismos técnicos de programación.
- Procesos en segundo plano.
- Colas de mensajería.
- Tareas programadas.
- Estados técnicos de entrega.
- Estructuras de almacenamiento.
- APIs o servicios responsables de ejecutar los envíos.

Estos aspectos deberán definirse posteriormente cuando exista suficiente detalle funcional o durante el diseño técnico correspondiente.

Como principio general:

```text
SITUACIÓN
FUNCIONAL
        ↓
NOTIFICACIÓN
CUANDO CORRESPONDA
        ↓
LA SITUACIÓN
CONTINÚA O
EVOLUCIONA
        ↓
REEVALUACIÓN
        ↓
¿EXISTE UNA RAZÓN
FUNCIONAL PARA
VOLVER A
COMUNICAR?
        │
   ┌────┴────┐
   ↓         ↓
  SÍ         NO
   │         │
   ↓         ↓
NUEVA       NO SE GENERA
COMUNICACIÓN COMUNICACIÓN
CUANDO       INNECESARIA
CORRESPONDA
```

manteniendo siempre:

```text
REEVALUACIÓN
        ≠
NOTIFICACIÓN
AUTOMÁTICA
```

```text
PERSISTENCIA
        ≠
REPETICIÓN
INDEFINIDA
```

```text
RECORDATORIO
        ≠
NUEVA ALERTA
```

y:

```text
MÚLTIPLES
RESULTADOS
RELACIONADOS
        ≠
MÚLTIPLES
NOTIFICACIONES
OBLIGATORIAS
```

Vehículos Services deberá controlar la frecuencia y repetición de las notificaciones de acuerdo con las condiciones funcionales aplicables, permitiendo volver a comunicar una situación cuando exista una razón que lo justifique y evitando que la reevaluación, persistencia o existencia de múltiples resultados relacionados produzca comunicaciones automáticas, duplicadas o innecesarias para el Propietario.


---

### 63.13.7 Estado, vigencia y trazabilidad de las notificaciones

Vehículos Services deberá mantener información suficiente para conocer la evolución de una notificación desde que se determina funcionalmente que corresponde generarla, conservando su trazabilidad de manera independiente de la condición, alerta, recomendación, evento o solicitud que haya dado origen a la notificación.

El estado de una notificación deberá representar la situación propia de dicha notificación y no deberá utilizarse para representar el estado del elemento funcional que la originó.

Conceptualmente:

```text
ORIGEN
FUNCIONAL
        ↓
NOTIFICACIÓN
        ↓
EVOLUCIÓN DE LA
NOTIFICACIÓN
        ↓
TRAZABILIDAD
```

Por lo tanto:

```text
ESTADO DE
LA NOTIFICACIÓN
        ≠
ESTADO DE
LA ALERTA
```

y:

```text
ESTADO DE
LA NOTIFICACIÓN
        ≠
ESTADO DE LA
CONDICIÓN
COMUNICADA
```

Una alerta podrá continuar vigente aunque una notificación relacionada ya haya sido enviada o puesta a disposición del destinatario mediante el canal correspondiente.

De igual manera, una alerta podrá resolverse posteriormente sin eliminar la existencia histórica de las notificaciones que hayan sido generadas legítimamente mientras dicha situación se encontraba vigente.

#### La generación de una notificación deberá mantenerse diferenciada de su envío o puesta a disposición mediante un canal

Vehículos Services deberá diferenciar conceptualmente el momento en que una notificación es generada del momento en que se utiliza un canal o mecanismo para hacerla llegar o ponerla a disposición del destinatario.

Conceptualmente:

```text
SE DETERMINA QUE
CORRESPONDE
NOTIFICAR
        ↓
NOTIFICACIÓN
GENERADA
        ↓
CANAL O
MECANISMO
        ↓
INTENTO DE ENVÍO
O PUESTA A
DISPOSICIÓN
        ↓
RESULTADO
CUANDO PUEDA
DETERMINARSE
```

Por lo tanto:

```text
NOTIFICACIÓN
GENERADA
        ≠
NOTIFICACIÓN
NECESARIAMENTE
ENVIADA
```

La existencia funcional de una notificación no deberá utilizarse como evidencia suficiente de que esta ya fue enviada o puesta a disposición del destinatario mediante un canal.

Por ejemplo:

```text
NOTIFICACIÓN
GENERADA
        ↓
CANAL NO
DISPONIBLE
```

no deberá registrarse conceptualmente como:

```text
NOTIFICACIÓN
ENVIADA
```

si no existe información que permita sustentarlo.

#### El envío no deberá equivaler automáticamente a entrega

Cuando el mecanismo utilizado permita diferenciar estas situaciones, Vehículos Services deberá mantener conceptualmente separado el envío de la entrega.

Por lo tanto:

```text
NOTIFICACIÓN
ENVIADA
        ≠
NOTIFICACIÓN
NECESARIAMENTE
ENTREGADA
```

Un intento de envío podrá haber sido realizado sin que exista confirmación suficiente de que la notificación llegó efectivamente al destinatario.

Conceptualmente:

```text
NOTIFICACIÓN
        ↓
CANAL O
MECANISMO
        ↓
ENVÍO
        ↓
¿EXISTE INFORMACIÓN
SOBRE EL RESULTADO?
        ↓
RESULTADO
CUANDO PUEDA
DETERMINARSE
```

Vehículos Services no deberá afirmar una entrega cuando el mecanismo utilizado no permita confirmarla.

Por lo tanto:

```text
RESULTADO
DESCONOCIDO
        ≠
ENTREGA
CONFIRMADA
```

#### La entrega no deberá equivaler automáticamente a consulta

Incluso cuando pueda determinarse que una notificación fue entregada mediante determinado mecanismo, esto no deberá significar automáticamente que el Propietario haya consultado su contenido.

Conceptualmente:

```text
NOTIFICACIÓN
ENTREGADA
        ≠
NOTIFICACIÓN
CONSULTADA
```

Por ejemplo:

```text
NOTIFICACIÓN
ENTREGADA
        ↓
PROPIETARIO
NO LA HA
CONSULTADO
```

deberá ser una situación conceptualmente posible cuando el mecanismo utilizado permita diferenciar ambos momentos.

Por lo tanto:

```text
ENTREGAR
        ≠
CONSULTAR
```

La plataforma no deberá asumir que el Propietario conoce la información únicamente porque exista evidencia de entrega.

#### La consulta tampoco deberá equivaler a resolución de la situación comunicada

Cuando Vehículos Services pueda determinar que el Propietario consultó una notificación, este hecho no deberá modificar automáticamente la condición, alerta, recomendación o situación funcional relacionada.

Por ejemplo:

```text
ALERTA
VIGENTE
        ↓
NOTIFICACIÓN
        ↓
PROPIETARIO
CONSULTA LA
NOTIFICACIÓN
```

no deberá significar:

```text
ALERTA
RESUELTA
```

Por lo tanto:

```text
NOTIFICACIÓN
CONSULTADA
        ≠
CONDICIÓN
RESUELTA
```

y:

```text
NOTIFICACIÓN
CONSULTADA
        ≠
ACCIÓN
REALIZADA
```

La resolución de una condición deberá continuar dependiendo de nueva información o de un evento funcional válido que permita determinar que la situación cambió.

#### La vigencia de la notificación deberá mantenerse separada de la vigencia de su origen

Una notificación podrá conservarse como antecedente aunque la situación que la originó posteriormente cambie o deje de estar vigente.

Por ejemplo:

```text
ALERTA
VIGENTE
        ↓
NOTIFICACIÓN
        ↓
POSTERIORMENTE
SE REALIZA LA
INTERVENCIÓN
        ↓
ALERTA
RESUELTA
```

La resolución posterior de la alerta no deberá provocar:

```text
ELIMINACIÓN DE
LA NOTIFICACIÓN
ANTERIOR
```

Por lo tanto:

```text
ORIGEN
RESUELTO
        ≠
NOTIFICACIÓN
HISTÓRICA
INEXISTENTE
```

La notificación deberá poder conservarse como evidencia de que determinada información debía ponerse en conocimiento del destinatario y del resultado que haya podido determinarse respecto de su envío, entrega o consulta.

De igual manera, que una notificación permanezca registrada no deberá significar que la condición que la originó continúa vigente.

Por lo tanto:

```text
NOTIFICACIÓN
HISTÓRICA
EXISTENTE
        ≠
CONDICIÓN
ACTUALMENTE
VIGENTE
```

#### Las notificaciones deberán conservar su propia trazabilidad

Vehículos Services deberá permitir conocer conceptualmente la evolución de cada notificación sin convertirla en parte inseparable del registro de la alerta, recomendación u otro elemento que la haya originado.

Conceptualmente:

```text
ORIGEN
FUNCIONAL
        ↓
NOTIFICACIÓN
        ↓
TRAZABILIDAD
PROPIA
```

Cuando exista relación entre diferentes elementos, deberá ser posible conservar dicha relación sin fusionarlos.

Por ejemplo:

```text
ALERTA
        ↓
NOTIFICACIÓN
```

deberá permitir conocer que ambos elementos se encuentran relacionados, manteniendo:

```text
ALERTA
        ≠
NOTIFICACIÓN
```

y:

```text
TRAZABILIDAD
DE LA ALERTA
        ≠
TRAZABILIDAD DE
LA NOTIFICACIÓN
```

Esto será necesario porque ambos elementos podrán evolucionar de manera diferente.

Por ejemplo:

```text
ALERTA:
VIGENTE

NOTIFICACIÓN:
ENVIADA
```

o posteriormente:

```text
ALERTA:
RESUELTA

NOTIFICACIÓN:
SE CONSERVA COMO
ANTECEDENTE
```

#### La trazabilidad deberá permitir reconstruir la evolución de la notificación

Cuando exista información suficiente, Vehículos Services deberá conservar los elementos necesarios para poder comprender posteriormente qué ocurrió con una notificación.

Conceptualmente, deberá poder reconstruirse información como:

```text
¿QUÉ INFORMACIÓN
SE NOTIFICÓ?

        ↓

¿QUÉ ORIGINÓ LA
NOTIFICACIÓN?

        ↓

¿A QUIÉN
CORRESPONDÍA?

        ↓

¿MEDIANTE QUÉ
CANAL O MECANISMO
SE GESTIONÓ?

        ↓

¿QUÉ RESULTADO
PUDO DETERMINARSE?
```

El nivel exacto de información disponible podrá depender del mecanismo utilizado y de las capacidades técnicas que posteriormente se definan.

Por lo tanto:

```text
TRAZABILIDAD
        ≠
INVENTAR INFORMACIÓN
NO DISPONIBLE
```

Cuando determinado resultado no pueda conocerse, Vehículos Services deberá conservar únicamente aquello que pueda sustentarse.

Por ejemplo:

```text
ENVÍO
CONFIRMADO

ENTREGA:
DESCONOCIDA
```

deberá mantenerse como una situación válida si el mecanismo utilizado no permite conocer la entrega.

No deberá transformarse artificialmente en:

```text
ENTREGA
CONFIRMADA
```

#### Los intentos de envío deberán mantenerse diferenciados de la notificación funcional

Una notificación podrá requerir uno o más intentos de envío o puesta a disposición dependiendo del canal utilizado y de las reglas técnicas o funcionales que posteriormente se definan.

Conceptualmente:

```text
NOTIFICACIÓN
        ↓
INTENTO DE
ENVÍO
        ↓
RESULTADO
```

Podrá existir posteriormente:

```text
MISMA
NOTIFICACIÓN
        ↓
NUEVO INTENTO
DE ENVÍO
```

cuando corresponda.

Esto no deberá significar:

```text
NUEVO INTENTO
        =
NUEVA
NOTIFICACIÓN
FUNCIONAL
```

Por lo tanto:

```text
CANTIDAD DE
INTENTOS
        ≠
CANTIDAD DE
NOTIFICACIONES
```

Esta separación será especialmente importante para evitar que los reintentos técnicos sean interpretados como nuevas situaciones funcionales.

Las políticas concretas de reintento deberán definirse posteriormente durante el diseño funcional o técnico correspondiente.

#### La utilización de múltiples canales deberá conservar trazabilidad sin duplicar el origen funcional

Cuando una misma notificación sea gestionada mediante más de un canal, Vehículos Services deberá poder conservar conceptualmente el resultado correspondiente a cada mecanismo sin interpretar que existen múltiples situaciones funcionales.

Por ejemplo:

```text
UNA
NOTIFICACIÓN
        │
        ├── CANAL A
        │      ↓
        │   RESULTADO A
        │
        └── CANAL B
               ↓
            RESULTADO B
```

Por lo tanto:

```text
DOS CANALES
UTILIZADOS
        ≠
DOS ORÍGENES
FUNCIONALES
```

y:

```text
DOS RESULTADOS
DE LOS CANALES
        ≠
DOS ALERTAS
```

Cada mecanismo podrá producir información diferente sobre el resultado del envío, entrega o consulta, pero todos deberán conservar su relación con la notificación correspondiente.

#### Las notificaciones repetidas deberán poder relacionarse con su situación de origen

Cuando una misma situación pueda notificarse nuevamente conforme a `63.13.6 Frecuencia, repetición y prevención de notificaciones innecesarias`, Vehículos Services deberá conservar la relación entre dichas notificaciones y la situación funcional correspondiente.

Conceptualmente:

```text
ALERTA
        ↓
NOTIFICACIÓN
INICIAL
        ↓
POSTERIORMENTE
RECORDATORIO
```

deberá permitir reconocer que ambas notificaciones pueden encontrarse relacionadas con la misma alerta.

Sin embargo:

```text
NOTIFICACIÓN
INICIAL
        ≠
RECORDATORIO
POSTERIOR
```

como eventos funcionales de notificación.

Cada notificación deberá conservar la trazabilidad necesaria para identificar cuándo ocurrió y cuál fue su relación con la situación funcional.

Por lo tanto:

```text
MISMO ORIGEN
FUNCIONAL
        ≠
MISMA
NOTIFICACIÓN
```

#### Las correcciones no deberán destruir la trazabilidad

Cuando exista la necesidad de corregir información relacionada con una notificación, Vehículos Services no deberá eliminar silenciosamente información histórica relevante que impida comprender qué ocurrió.

Conceptualmente:

```text
INFORMACIÓN
REGISTRADA
        ↓
SE IDENTIFICA
UNA CORRECCIÓN
        ↓
CORRECCIÓN
TRAZABLE
```

no deberá convertirse en:

```text
REEMPLAZO
SILENCIOSO SIN
ANTECEDENTE
```

Las reglas detalladas sobre correcciones, versionamiento, anulaciones o ajustes deberán definirse posteriormente.

Sin embargo, deberá mantenerse el principio general:

```text
CORREGIR
        ≠
BORRAR LA
TRAZABILIDAD
```

Esto deberá ser coherente con los principios generales de integridad y auditoría definidos para Vehículos Services.

#### La trazabilidad deberá diferenciar el origen de la notificación

Cuando una notificación se origine a partir de una alerta, recomendación, solicitud, recordatorio, evento u otra situación funcional, deberá conservarse conceptualmente la posibilidad de conocer dicho origen.

Por ejemplo:

```text
NOTIFICACIÓN A
        ↓
ORIGEN:
ALERTA
```

```text
NOTIFICACIÓN B
        ↓
ORIGEN:
SOLICITUD DE
ACTUALIZACIÓN
DE KILOMETRAJE
```

```text
NOTIFICACIÓN C
        ↓
ORIGEN:
RECORDATORIO
```

Esto no deberá significar que todos los orígenes deban representarse técnicamente de la misma manera.

La estructura técnica correspondiente deberá definirse posteriormente.

El principio funcional deberá ser:

```text
NOTIFICACIÓN
        ↓
ORIGEN
IDENTIFICABLE
CUANDO
CORRESPONDA
```

sin crear relaciones artificiales cuando la notificación no provenga de una alerta o recomendación.

#### Los estados concretos no deberán cerrarse todavía como una enumeración técnica definitiva

En esta etapa del proyecto deberá definirse la necesidad de representar la evolución de las notificaciones sin establecer todavía un catálogo técnico definitivo de estados.

Conceptualmente podrán existir momentos o resultados como:

```text
GENERACIÓN
        ↓
CANAL O
MECANISMO
        ↓
ENVÍO
        ↓
ENTREGA
CUANDO PUEDA
DETERMINARSE
        ↓
CONSULTA
CUANDO PUEDA
DETERMINARSE
```

Sin embargo, este flujo no deberá interpretarse como una secuencia obligatoria disponible para todos los canales.

Por ejemplo, determinado mecanismo podría permitir conocer:

```text
GENERADA
        ↓
ENVIADA
```

pero no necesariamente:

```text
ENTREGADA
        ↓
CONSULTADA
```

Por lo tanto:

```text
CAPACIDAD DE
REPRESENTAR LA
EVOLUCIÓN
        ≠
MISMOS ESTADOS
OBLIGATORIOS PARA
TODOS LOS CANALES
```

La definición definitiva de estados deberá realizarse cuando se conozcan los canales, tecnologías y necesidades funcionales correspondientes.

#### La trazabilidad no deberá modificar la situación notificada

Registrar información sobre la evolución de una notificación deberá servir para conocer qué ocurrió con dicha notificación, pero no deberá modificar por sí mismo la situación funcional de origen.

Por ejemplo:

```text
NOTIFICACIÓN
ENTREGADA
```

no deberá significar:

```text
ALERTA
RESUELTA
```

y:

```text
NOTIFICACIÓN
CONSULTADA
```

no deberá significar:

```text
MANTENIMIENTO
REALIZADO
```

Por lo tanto:

```text
TRAZABILIDAD DE
LA NOTIFICACIÓN
        ≠
EVIDENCIA DE
RESOLUCIÓN
FUNCIONAL
```

La resolución de la situación deberá continuar dependiendo de la información válida correspondiente al dominio que la originó.

#### La información histórica deberá conservarse independientemente de la situación actual

Vehículos Services deberá poder conservar las notificaciones históricas que correspondan aunque actualmente la situación del vehículo sea diferente.

Por ejemplo:

```text
10/09/2026

NOTIFICACIÓN:
CAMBIO DE ACEITE
PRÓXIMO AL OBJETIVO
```

posteriormente:

```text
20/09/2026

INTERVENCIÓN:
CAMBIO DE ACEITE
REALIZADO
```

La existencia de la intervención posterior no deberá eliminar la notificación generada anteriormente.

Conceptualmente:

```text
SITUACIÓN
ANTERIOR
        ↓
NOTIFICACIÓN
HISTÓRICA
        ↓
NUEVA SITUACIÓN
        ↓
SE CONSERVA EL
ANTECEDENTE
```

Esto permitirá reconstruir adecuadamente la evolución de las notificaciones relacionadas con el vehículo.

#### La trazabilidad deberá respetar las reglas de acceso y privacidad

La conservación de información relacionada con las notificaciones no deberá significar que cualquier actor pueda consultar dicha información.

Por lo tanto:

```text
NOTIFICACIÓN
CONSERVADA
        ≠
NOTIFICACIÓN
VISIBLE PARA
CUALQUIER ACTOR
```

La visibilidad deberá continuar dependiendo de las reglas de acceso, privacidad, relación con el vehículo y autorización aplicables.

De igual manera, conservar la identidad del destinatario o información relacionada con la notificación no deberá utilizarse para ampliar automáticamente los permisos de otros actores.

Conceptualmente:

```text
TRAZABILIDAD
        ≠
ACCESO
IRRESTRICTO
```

Este principio deberá mantenerse alineado con `63.13.4 Destinatarios y condiciones para recibir notificaciones` y con las reglas generales de privacidad y acceso de Vehículos Services.

#### Alcance técnico posterior

Este punto deberá establecer la necesidad funcional de conservar el estado, evolución y trazabilidad de las notificaciones sin definir todavía su implementación técnica.

No deberá determinar todavía:

- El catálogo definitivo de estados.
- Los códigos internos de cada estado.
- Las tablas de almacenamiento.
- Las estructuras de base de datos.
- Los identificadores técnicos.
- Los campos definitivos.
- Los formatos de fecha y hora.
- Los mecanismos técnicos de auditoría.
- Los proveedores de comunicación.
- Los códigos de respuesta de proveedores externos.
- Las políticas técnicas de reintento.
- La cantidad máxima de reintentos.
- Las colas de mensajería.
- Los procesos en segundo plano.
- Las APIs de comunicación.
- Los mecanismos de sincronización.
- Los tiempos técnicos de retención.
- La representación visual de cada estado.

Estos elementos deberán definirse posteriormente durante el diseño funcional detallado y el diseño técnico correspondiente.

Como principio general:

```text
ORIGEN
FUNCIONAL
        ↓
NOTIFICACIÓN
GENERADA
        ↓
CANAL O
MECANISMO
CUANDO CORRESPONDA
        ↓
ENVÍO O PUESTA
A DISPOSICIÓN
        ↓
RESULTADO
SEGÚN INFORMACIÓN
DISPONIBLE
        ↓
TRAZABILIDAD
```

manteniendo siempre:

```text
GENERADA
        ≠
NECESARIAMENTE
ENVIADA
```

```text
ENVIADA
        ≠
NECESARIAMENTE
ENTREGADA
```

```text
ENTREGADA
        ≠
NECESARIAMENTE
CONSULTADA
```

```text
CONSULTADA
        ≠
SITUACIÓN
RESUELTA
```

y:

```text
ESTADO DE
LA NOTIFICACIÓN
        ≠
ESTADO DEL
ORIGEN FUNCIONAL
```

Vehículos Services deberá conservar la evolución y trazabilidad de las notificaciones de acuerdo con la información realmente disponible, diferenciando su generación, envío o puesta a disposición, entrega y consulta cuando estos puedan determinarse, sin asumir estados no comprobados y sin interpretar la evolución de una notificación como evidencia automática de que la condición, alerta, recomendación o situación que la originó fue atendida o resuelta.

---

### 63.13.8 Preferencias y control de notificaciones por parte del Propietario

Vehículos Services deberá contemplar que el Propietario pueda disponer de mecanismos de configuración y control sobre determinadas notificaciones cuando las reglas funcionales correspondientes permitan dicha configuración.

Las preferencias deberán permitir adaptar determinados aspectos de la comunicación sin modificar la información, condición, alerta, recomendación, evento o solicitud funcional que exista dentro de la plataforma.

Conceptualmente:

```text
SITUACIÓN
FUNCIONAL
        ↓
¿CORRESPONDE
NOTIFICAR?
        ↓
REGLAS
APLICABLES
        +
PREFERENCIAS DEL
PROPIETARIO
CUANDO APLIQUEN
        ↓
NOTIFICACIÓN
CUANDO
CORRESPONDA
        ↓
CANAL Y
TRATAMIENTO
APLICABLE
```

Por lo tanto:

```text
PREFERENCIA DE
NOTIFICACIÓN
        ≠
REGLA QUE MODIFICA
LA SITUACIÓN DEL
VEHÍCULO
```

Las preferencias deberán actuar sobre los aspectos de comunicación que puedan ser configurables y no sobre la existencia de los hechos o elementos funcionales que puedan originar dicha comunicación.

#### Las preferencias no deberán modificar la información funcional

Una configuración realizada por el Propietario sobre sus notificaciones no deberá modificar el estado real de la información registrada en Vehículos Services.

Por ejemplo:

```text
ALERTA:
CAMBIO DE ACEITE
PRÓXIMO AL OBJETIVO
```

si el Propietario modifica una preferencia relacionada con su comunicación:

```text
PREFERENCIA DE
NOTIFICACIÓN
MODIFICADA
```

esto no deberá significar:

```text
ALERTA
ELIMINADA
```

ni:

```text
ALERTA
RESUELTA
```

ni:

```text
MANTENIMIENTO
REALIZADO
```

Por lo tanto:

```text
MODIFICAR UNA
PREFERENCIA
        ≠
MODIFICAR LA
CONDICIÓN
FUNCIONAL
```

La alerta, recomendación, condición, evento o solicitud deberá continuar evolucionando según sus propias reglas.

#### Desactivar una comunicación no deberá eliminar su origen funcional

Cuando las reglas funcionales permitan que determinada comunicación pueda ser desactivada por el Propietario, esta acción deberá afectar únicamente el comportamiento de comunicación permitido.

Conceptualmente:

```text
ALERTA
        ↓
¿CORRESPONDE
GENERAR UNA
NOTIFICACIÓN?
        ↓
REGLAS
APLICABLES
        +
PREFERENCIAS
PERMITIDAS
```

Una preferencia que limite o desactive determinada comunicación no deberá significar:

```text
ALERTA
INEXISTENTE
```

Por lo tanto:

```text
PREFERENCIA QUE
LIMITA O DESACTIVA
UNA COMUNICACIÓN
        ≠
ALERTA
DESACTIVADA
```

y:

```text
COMUNICACIÓN
DESACTIVADA
        ≠
RECOMENDACIÓN
ELIMINADA
```

La información correspondiente deberá poder continuar existiendo dentro de Vehículos Services aunque determinada comunicación se encuentre desactivada cuando dicha configuración sea permitida.

#### No todas las notificaciones deberán asumirse como configurables

Vehículos Services no deberá establecer en esta etapa que todas las notificaciones podrán ser activadas, desactivadas o modificadas libremente por el Propietario.

Conceptualmente:

```text
EXISTENCIA DE
PREFERENCIAS
        ≠
CONTROL TOTAL SOBRE
TODAS LAS
NOTIFICACIONES
```

La posibilidad de configurar una comunicación deberá depender de las reglas funcionales que posteriormente se definan para cada tipo de notificación.

Por lo tanto, no deberá asumirse todavía:

```text
TODAS LAS
NOTIFICACIONES
        ↓
PUEDEN
DESACTIVARSE
```

ni:

```text
TODAS LAS
NOTIFICACIONES
        ↓
SON OBLIGATORIAS
```

La clasificación de qué comunicaciones podrán ser configurables y cuáles deberán tener un tratamiento diferente deberá definirse posteriormente cuando exista suficiente detalle funcional.

#### Las preferencias podrán aplicarse a diferentes aspectos de la comunicación

Cuando funcionalmente corresponda, las preferencias del Propietario podrán influir sobre determinados aspectos de las notificaciones.

Conceptualmente, estos aspectos podrán incluir:

- Canales habilitados.
- Tipos o categorías de comunicaciones.
- Frecuencia de determinadas comunicaciones.
- Recordatorios.
- Otros comportamientos de comunicación que posteriormente sean definidos.

Esta enumeración deberá considerarse conceptual y no como una definición definitiva de todas las opciones que estarán disponibles.

Por lo tanto:

```text
CAPACIDAD DE
CONFIGURACIÓN
        ≠
TODAS LAS OPCIONES
YA DEFINIDAS
```

Cada preferencia deberá establecerse posteriormente de acuerdo con las necesidades funcionales y las restricciones aplicables.

#### Las preferencias de canal deberán mantenerse separadas de la disponibilidad del canal

Cuando Vehículos Services disponga de diferentes canales de comunicación, el Propietario podrá eventualmente establecer preferencias sobre determinados canales cuando las reglas lo permitan.

Conceptualmente:

```text
CANALES
DISPONIBLES
        +
PREFERENCIAS
APLICABLES
        ↓
CANAL O
MECANISMO
UTILIZABLE
```

Sin embargo:

```text
CANAL
DISPONIBLE
        ≠
CANAL
PREFERIDO
```

y:

```text
CANAL
PREFERIDO
        ≠
CANAL SIEMPRE
UTILIZABLE
```

La utilización efectiva de un canal podrá depender también de su disponibilidad, de la naturaleza de la notificación, de las condiciones del destinatario y de las reglas funcionales aplicables.

Esto deberá mantenerse alineado con `63.13.5 Canales y mecanismos de notificación`.

#### Las preferencias de frecuencia deberán respetar las reglas funcionales

Cuando una determinada comunicación permita configurar aspectos relacionados con su frecuencia, la preferencia del Propietario deberá aplicarse dentro de los límites funcionales que correspondan.

Conceptualmente:

```text
REGLAS DE
FRECUENCIA
        +
PREFERENCIA DEL
PROPIETARIO
CUANDO APLIQUE
        ↓
FRECUENCIA DE
COMUNICACIÓN
```

Por lo tanto:

```text
PREFERENCIA DE
FRECUENCIA
        ≠
ELIMINACIÓN DE
LAS REGLAS DE
COMUNICACIÓN
```

Una preferencia no deberá utilizarse para modificar arbitrariamente la lógica funcional que determina cuándo existe una situación comunicable.

De igual manera:

```text
MENOR FRECUENCIA
DE COMUNICACIÓN
        ≠
MENOR RELEVANCIA
DE LA CONDICIÓN
```

La frecuencia y repetición deberán continuar rigiéndose por los principios establecidos en `63.13.6 Frecuencia, repetición y prevención de notificaciones innecesarias`.

#### Las preferencias sobre categorías no deberán modificar la clasificación funcional de la información

Si posteriormente Vehículos Services permite al Propietario establecer preferencias sobre determinadas categorías o tipos de comunicaciones, dicha configuración deberá afectar el tratamiento de comunicación y no la naturaleza funcional de la información.

Por ejemplo:

```text
CATEGORÍA DE
COMUNICACIÓN
        ↓
PREFERENCIA DEL
PROPIETARIO
```

no deberá modificar:

```text
TIPO DE ALERTA
```

ni:

```text
TIPO DE
RECOMENDACIÓN
```

ni:

```text
NATURALEZA DEL
EVENTO
```

Por lo tanto:

```text
CATEGORÍA DE
NOTIFICACIÓN
        ≠
CLASIFICACIÓN DEL
ORIGEN FUNCIONAL
```

Aunque puedan existir relaciones entre ambos conceptos, deberán mantenerse diferenciados.

#### Las preferencias deberán pertenecer al Propietario correspondiente

Las configuraciones realizadas por un Propietario no deberán aplicarse automáticamente a otros Propietarios.

Conceptualmente:

```text
PROPIETARIO A
        ↓
PREFERENCIAS A


PROPIETARIO B
        ↓
PREFERENCIAS B
```

Por lo tanto:

```text
PREFERENCIAS DEL
PROPIETARIO A
        ≠
PREFERENCIAS DEL
PROPIETARIO B
```

Esto será especialmente importante cuando diferentes Propietarios utilicen Vehículos Services de manera independiente.

Las preferencias deberán relacionarse con quien las configura y no convertirse automáticamente en una característica permanente del vehículo.

Por lo tanto:

```text
PREFERENCIA DEL
PROPIETARIO
        ≠
PREFERENCIA
PERMANENTE DEL
VEHÍCULO
```

#### El cambio de Propietario no deberá transferir automáticamente las preferencias personales

Cuando un vehículo cambie de Propietario, las preferencias de comunicación configuradas por el Propietario anterior no deberán transferirse automáticamente al nuevo Propietario como si fueran configuraciones propias de este.

Conceptualmente:

```text
PROPIETARIO A
        ↓
PREFERENCIAS A
        ↓
CAMBIO DE
PROPIETARIO
        ↓
PROPIETARIO B
```

no deberá significar:

```text
PROPIETARIO B
        ↓
HEREDA
AUTOMÁTICAMENTE
PREFERENCIAS A
```

Por lo tanto:

```text
CAMBIO DE
PROPIETARIO
        ≠
TRANSFERENCIA
AUTOMÁTICA DE
PREFERENCIAS
PERSONALES
```

Esto no deberá afectar la continuidad del historial del vehículo ni la conservación de las notificaciones históricas correspondientes.

#### Las preferencias no deberán modificar permisos ni autorizaciones

La configuración de notificaciones deberá mantenerse separada de los permisos de acceso a la información.

Por lo tanto:

```text
PREFERENCIA DE
NOTIFICACIÓN
        ≠
PERMISO DE
ACCESO
```

Un Propietario no deberá obtener acceso a información adicional únicamente por activar una preferencia de comunicación.

De igual manera, desactivar determinada comunicación no deberá modificar los permisos que el Propietario tenga sobre la información correspondiente.

Conceptualmente:

```text
ACCESO A
INFORMACIÓN
        ↓
REGLAS DE ACCESO
Y AUTORIZACIÓN
```

mientras que:

```text
NOTIFICACIÓN DE
INFORMACIÓN
        ↓
REGLAS DE
NOTIFICACIÓN
        +
PREFERENCIAS
CUANDO APLIQUEN
```

Ambos procesos deberán mantenerse diferenciados.

#### Las preferencias no deberán modificar quién es un destinatario válido

La posibilidad de configurar una notificación deberá aplicarse únicamente después de determinar que el actor correspondiente puede ser destinatario de dicha notificación.

Conceptualmente:

```text
¿ES DESTINATARIO
VÁLIDO?
        ↓
SÍ
        ↓
¿EXISTEN
PREFERENCIAS
APLICABLES?
        ↓
TRATAMIENTO DE
LA NOTIFICACIÓN
```

No deberá ocurrir:

```text
PREFERENCIA
CONFIGURADA
        ↓
SE CONVIERTE EN
DESTINATARIO
AUTORIZADO
```

Por lo tanto:

```text
PREFERENCIA
        ≠
AUTORIZACIÓN
```

La determinación de destinatarios deberá continuar rigiéndose por `63.13.4 Destinatarios y condiciones para recibir notificaciones`.

#### La ausencia de una preferencia explícita deberá tratarse mediante reglas definidas

Cuando el Propietario no haya establecido una preferencia para determinada comunicación, Vehículos Services deberá aplicar el comportamiento funcional que posteriormente se defina para dicho caso.

Conceptualmente:

```text
SITUACIÓN
COMUNICABLE
        ↓
¿EXISTE
PREFERENCIA
APLICABLE?
        │
   ┌────┴────┐
   ↓         ↓
  SÍ         NO
   │         │
   ↓         ↓
APLICAR     APLICAR
PREFERENCIA COMPORTAMIENTO
DENTRO DE   DEFINIDO POR
LAS REGLAS  LAS REGLAS
        │         │
        └────┬────┘
             ↓
       NOTIFICACIÓN
       CUANDO
       CORRESPONDA
```

En esta etapa no deberá definirse todavía cuál será el comportamiento predeterminado para cada tipo de comunicación.

Por lo tanto:

```text
SIN PREFERENCIA
CONFIGURADA
        ≠
NOTIFICACIONES
DESACTIVADAS
AUTOMÁTICAMENTE
```

y tampoco:

```text
SIN PREFERENCIA
CONFIGURADA
        ≠
TODAS LAS
NOTIFICACIONES
ACTIVADAS
AUTOMÁTICAMENTE
```

El comportamiento predeterminado deberá definirse posteriormente para cada caso cuando corresponda.

#### Las modificaciones de preferencias deberán afectar comunicaciones futuras cuando corresponda

Cuando el Propietario modifique una preferencia, dicha modificación deberá aplicarse a las notificaciones futuras de acuerdo con las reglas funcionales correspondientes.

Conceptualmente:

```text
PREFERENCIA
ANTERIOR
        ↓
MODIFICACIÓN
        ↓
NUEVA
PREFERENCIA
        ↓
NOTIFICACIONES
POSTERIORES
CUANDO APLIQUE
```

La modificación de una preferencia no deberá alterar retroactivamente las notificaciones que ya hayan sido generadas ni la evolución que estas hayan tenido respecto de su envío, entrega o consulta cuando dichos resultados puedan determinarse.

Por lo tanto:

```text
CAMBIO DE
PREFERENCIA
        ≠
MODIFICACIÓN
RETROACTIVA DEL
HISTORIAL
```

Las notificaciones históricas deberán conservarse conforme a lo establecido en `63.13.7 Estado, vigencia y trazabilidad de las notificaciones`.

#### La configuración deberá evitar contradicciones con las reglas funcionales

Las preferencias del Propietario deberán aplicarse dentro de las posibilidades permitidas por Vehículos Services.

No deberá asumirse que una preferencia puede invalidar cualquier regla funcional existente.

Conceptualmente:

```text
REGLAS
FUNCIONALES
        +
PREFERENCIAS
PERMITIDAS
        ↓
COMPORTAMIENTO
DE NOTIFICACIÓN
```

Por lo tanto:

```text
PREFERENCIA
        ≠
EXCEPCIÓN
AUTOMÁTICA A
CUALQUIER REGLA
```

Cuando una determinada comunicación no admita cierto tipo de configuración, Vehículos Services deberá respetar la regla correspondiente.

Sin embargo, en esta etapa no deberán inventarse categorías de notificaciones obligatorias, críticas o no configurables sin que exista una definición funcional que las sustente.

#### Las preferencias deberán poder evolucionar con las funcionalidades de la plataforma

A medida que Vehículos Services incorpore nuevas funcionalidades, podrán incorporarse nuevas opciones de configuración relacionadas con las comunicaciones.

Por ejemplo, en el futuro podrán existir preferencias relacionadas con comunicaciones provenientes de:

- Mantenimiento.
- Kilometraje.
- Documentación.
- Abastecimiento y consumo energético.
- Preparación para viajes.
- Información pendiente o inconsistente.
- Otras funcionalidades que posteriormente sean incorporadas.

La existencia de estas áreas funcionales no deberá significar que desde este momento se encuentren definidas todas sus opciones de notificación.

Por lo tanto:

```text
NUEVA
FUNCIONALIDAD
        ≠
PREFERENCIAS DE
NOTIFICACIÓN
AUTOMÁTICAMENTE
DEFINIDAS
```

Cada nueva capacidad deberá determinar posteriormente qué aspectos de comunicación podrán ser configurados.

#### Alcance técnico posterior

Este punto deberá establecer únicamente los principios funcionales relacionados con las preferencias y el control de las notificaciones por parte del Propietario.

No deberá definir todavía:

- La interfaz exacta de configuración.
- Los controles visuales.
- Los valores predeterminados definitivos.
- Las categorías definitivas de notificaciones.
- Qué comunicaciones serán configurables.
- Qué comunicaciones no podrán desactivarse.
- Los canales tecnológicos definitivos.
- Los horarios configurables.
- Los intervalos concretos de frecuencia.
- Los límites mínimos o máximos de repetición.
- La estructura de almacenamiento de preferencias.
- Las tablas de base de datos.
- Los identificadores técnicos.
- Las APIs de configuración.
- La sincronización entre dispositivos.
- La integración con configuraciones del sistema operativo.
- Los mecanismos técnicos de autorización.
- Los proveedores de comunicación.

Estos elementos deberán definirse posteriormente durante el diseño funcional detallado y el diseño técnico correspondiente.

Como principio general:

```text
SITUACIÓN
FUNCIONAL
        ↓
REGLAS DE
COMUNICACIÓN
        ↓
¿CORRESPONDE
NOTIFICAR?
        ↓
DESTINATARIO
VÁLIDO
        ↓
PREFERENCIAS
APLICABLES
CUANDO
CORRESPONDA
        ↓
NOTIFICACIÓN
CUANDO
CORRESPONDA
        ↓
CANAL Y
TRATAMIENTO
APLICABLE
```

manteniendo siempre:

```text
PREFERENCIA
        ≠
AUTORIZACIÓN
```

```text
PREFERENCIA
        ≠
CONDICIÓN
FUNCIONAL
```

```text
DESACTIVAR UNA
COMUNICACIÓN
        ≠
ELIMINAR UNA
ALERTA O
RECOMENDACIÓN
```

y:

```text
CAMBIO DE
PREFERENCIA
        ≠
CAMBIO
RETROACTIVO DEL
HISTORIAL
```

Vehículos Services deberá permitir que el Propietario pueda controlar determinados aspectos de sus notificaciones cuando funcionalmente corresponda, manteniendo dichas preferencias separadas de las reglas de acceso, de la condición del vehículo y de los elementos funcionales que pueden originar las comunicaciones, sin asumir todavía que todas las notificaciones serán configurables ni definir prematuramente cuáles podrán ser activadas, desactivadas o modificadas.


---
# 64. Estado general del documento

| Área | Estado |
|---|---|
| Visión | Definida |
| Contexto | Definido |
| Problema | Definido |
| Necesidad | Definida |
| Propuesta de valor | Definida |
| Objetivos | Definidos |
| Alcance | Definido a nivel general |
| Actores | Definidos a nivel funcional |
| Procesos | Definidos a nivel general |
| Reglas de negocio | Definidas a nivel general / Pendientes de documentación detallada |
| Requerimientos funcionales | Pendientes de levantamiento detallado |
| Requerimientos no funcionales | Definidos inicialmente / Pendientes de detalle |
| Casos de uso | Preliminares / Pendientes de documentación detallada |
| Modelo de datos | Conceptual |
| Arquitectura | Conceptual |
| Tecnología | Pendiente de evaluación |
| Infraestructura | Pendiente de evaluación |
| Seguridad | Conceptual |
| UX/UI | Conceptual / Pendiente de diseño detallado |
| Suscripciones | Conceptual |
| Preparación para viajes | Conceptual |
| Reglas de preparación para viajes | Definidas a nivel general / Pendientes de detalle |
| Checklist de viaje | Conceptual |
| Integración con mapas | Fuera del alcance inicial / Futuro |
| MVP | Pendiente de definición |
| Roadmap | Conceptual / Pendiente de definición detallada |

---

# 65. Criterio para continuar el proyecto

El presente documento será utilizado como documento maestro de definición de Vehículos Services.

Las nuevas decisiones, requerimientos, reglas de negocio, componentes técnicos y cambios de alcance deberán incorporarse en este documento o referenciarse mediante documentos especializados.

No se deberán considerar como definitivas aquellas decisiones marcadas como:

- Pendiente.
- Preliminar.
- Conceptual.
- Por definir.
- Por validar.

Una decisión deberá considerarse definitiva únicamente cuando haya sido analizada, documentada y aprobada.

El proyecto deberá avanzar desde la definición del negocio hacia el diseño funcional y posteriormente hacia el diseño técnico.

La implementación tecnológica no deberá iniciar hasta contar con una definición suficiente del MVP, los requerimientos prioritarios, las reglas de negocio principales y la arquitectura inicial.

La funcionalidad de preparación para viajes deberá seguir el mismo principio.

Inicialmente se define como una capacidad de la plataforma para utilizar la información disponible del vehículo y generar recomendaciones de revisión antes de un viaje.

No deberá asumirse todavía:

- Que la aplicación conoce automáticamente el estado mecánico real del vehículo.
- Que la aplicación puede certificar que el vehículo está en condiciones para viajar.
- Que la aplicación realizará diagnósticos mecánicos.
- Que la aplicación calculará automáticamente rutas.
- Que la aplicación tendrá integración con mapas.
- Que la aplicación conocerá automáticamente la distancia del viaje.

Estas capacidades podrán incorporarse posteriormente mediante nuevas reglas, servicios e integraciones.

La definición técnica, funcional y comercial de estas funcionalidades deberá realizarse antes de incorporarlas al desarrollo.

El objetivo de esta evolución será mantener la misma filosofía central de Vehículos Services:

```text
INFORMACIÓN DEL VEHÍCULO

        ↓

HISTORIAL

        ↓

DATOS ACTUALIZADOS

        ↓

REGLAS

        ↓

EVALUACIÓN

        ↓

RESULTADO FUNCIONAL
CUANDO CORRESPONDA

        ↓

INFORMACIÓN / CONDICIÓN / ESTADO /
ALERTA / RECOMENDACIÓN

        ↓

DECISIÓN DEL PROPIETARIO
CUANDO CORRESPONDA

        ↓

ACCIÓN
CUANDO CORRESPONDA

        ↓

NUEVO REGISTRO

        ↓

ACTUALIZACIÓN DEL CICLO DE VIDA
```

De esta manera, la preparación para viajes no constituye una aplicación diferente dentro de Vehículos Services, sino una nueva capacidad que utiliza el mismo activo principal de la plataforma: el historial y conocimiento acumulado del vehículo.
---
# 66. Estructura documental del proyecto

La documentación del proyecto se organizará mediante un documento maestro y documentos especializados.

El objetivo de esta estructura es separar la definición general del proyecto de los detalles funcionales, de negocio y técnicos, permitiendo que cada aspecto de la solución sea documentado con el nivel de detalle requerido para su posterior análisis, diseño, implementación, mantenimiento y evolución.

La estructura documental propuesta será:

```text
docs/
├── proyecto.md
├── requerimientos-funcionales-propietario.md
├── requerimientos-funcionales-prestador.md
├── requerimientos-no-funcionales.md
├── reglas-negocio.md
├── casos-uso.md
├── arquitectura.md
├── modelo-datos.md
├── seguridad.md
└── ux-ui.md
```

Los requerimientos funcionales se organizarán por módulo en los documentos del Propietario y del Prestador de Servicios Vehiculares. Las capacidades generales compartidas tendrán una única definición principal y se referenciarán desde el otro documento cuando corresponda.

Los requerimientos no funcionales se documentarán en un archivo independiente, indicando los módulos, capacidades y etapas a los que aplican.

Las reglas de negocio se desarrollarán en `reglas-negocio.md`, manteniendo su relación con las definiciones generales de `proyecto.md` y los requerimientos correspondientes.

La separación del contenido actualmente reunido en `requerimientos.md` conservará los identificadores y las definiciones existentes. Las referencias al archivo anterior deberán actualizarse conforme se complete la reorganización.

La inclusión de un documento en esta estructura no implicará que ya esté creado, completo o aprobado. El documento funcional del Prestador se desarrollará en su etapa correspondiente, sin bloquear la primera entrega independiente del Propietario.

---
## 66.1 proyecto.md

proyecto.md será el documento maestro del proyecto.

Contendrá la definición general de la solución, incluyendo:

Información general.

Visión.

Contexto.

Problema.

Necesidad.

Oportunidad.

Objetivos.

Alcance.

Actores.

Procesos.

Reglas de negocio iniciales.

Requerimientos preliminares.

Casos de uso preliminares.

Arquitectura conceptual.

Definición tecnológica conceptual.

Modelo de datos conceptual.

Riesgos.

Decisiones pendientes.

Principios.

Estado general del proyecto.

Este documento deberá proporcionar el contexto necesario para comprender el propósito, alcance y dirección general de Vehículos Services.
---

## 66.2 Documentos de requerimientos

La especificación detallada de los requerimientos funcionales y no funcionales de Vehículos Services se organizará en documentos especializados.

Cada requerimiento deberá tener un identificador único dentro de su nomenclatura.

Los requerimientos funcionales utilizarán RF-001, RF-002 y sucesivas, conforme al punto 27. Su numeración será única para todo el proyecto y no se reiniciará por módulo o documento.

Los requerimientos no funcionales utilizarán RNF-001, RNF-002 y sucesivas. Su numeración será independiente de la funcional y única para todo el proyecto, sin reiniciarse por módulo, documento o categoría de calidad.

Cada requerimiento conservará su identificador cuando cambie de ubicación. Los saltos de numeración no deberán corregirse mediante la renumeración de los requerimientos existentes.

Cada requerimiento deberá documentar, según corresponda:

- ID.
- Nombre.
- Descripción del comportamiento o condición esperada.
- Tipo de requerimiento: funcional o no funcional.
- Actor o actores relacionados, cuando corresponda.
- Módulo o capacidad a la que pertenece.
- Etapa o entrega prevista.
- Estado de la definición.
- Reglas de negocio relacionadas, cuando existan.
- Criterios de aceptación verificables.
- Prioridad.
- Dependencias.
- Validaciones o restricciones, cuando correspondan.
- Decisiones pendientes, cuando existan.

Cada requerimiento tendrá una única especificación principal. Los documentos que necesiten utilizarlo deberán referenciar su identificador y el archivo donde esté definido, evitando duplicar su contenido.

Las propuestas y decisiones pendientes no deberán interpretarse como aprobadas para implementación.

### 66.2.1 requerimientos-funcionales-propietario.md

Este documento contendrá la especificación detallada de los requerimientos funcionales del módulo del Propietario y de las capacidades generales necesarias para su funcionamiento.

También establecerá el alcance funcional de sus entregas, distinguiendo los requerimientos incluidos inicialmente, los previstos para entregas posteriores y los que dependan de la integración con el Prestador de Servicios Vehiculares.

Los requerimientos de la primera entrega deberán permitir que el Propietario gestione sus vehículos y la información asociada sin depender de la implementación del módulo del Prestador.

Las capacidades generales compartidas que tengan su definición principal en este documento deberán identificarse como tales. Su utilización por el Prestador no implicará crear otra especificación del mismo requerimiento.

Las acciones del Propietario que requieran una integración posterior podrán documentarse aquí, indicando expresamente su etapa y dependencias. Su inclusión no implicará que formen parte de la primera entrega.

### 66.2.2 requerimientos-funcionales-prestador.md

Este documento contendrá la especificación detallada de los requerimientos funcionales propios del Prestador de Servicios Vehiculares.

Su desarrollo corresponderá a la etapa de definición de ese módulo. La existencia de este documento dentro de la estructura documental no implicará que sus requerimientos estén completos, aprobados o incluidos en la primera implementación.

Cuando una funcionalidad del Prestador utilice una capacidad general definida en el documento del Propietario, deberá referenciarla mediante su identificador y documento de origen.

Las acciones de cada módulo que intervengan en una integración deberán mantener sus responsabilidades y dependencias explícitas, sin duplicar requerimientos ni establecer comportamientos contradictorios.

### 66.2.3 requerimientos-no-funcionales.md

Este documento contendrá la especificación detallada de los requerimientos no funcionales de Vehículos Services.

Establecerá las condiciones de calidad que deberá cumplir la solución, indicando los módulos, capacidades, componentes y etapas a los que aplica cada requerimiento.

Los requerimientos generales compartidos tendrán una única definición principal. Cuando existan condiciones particulares para un módulo o entrega, deberán identificarse expresamente.

Cada requerimiento deberá establecer criterios de aceptación verificables y las condiciones necesarias para comprobarlos. Los objetivos, límites o escenarios todavía sin definir deberán señalarse como pendientes.

La separación documental no implicará aplazar los requerimientos no funcionales hasta finalizar el desarrollo. Los controles y condiciones aplicables deberán incorporarse durante el diseño, implementación y validación de cada entrega.

### Relación con los demás documentos

Los documentos funcionales establecerán qué debe hacer el sistema. El documento no funcional establecerá qué condiciones de calidad debe cumplir.

Las condiciones, restricciones y cálculos de negocio se desarrollarán en `reglas-negocio.md`.

Los flujos de interacción, precondiciones, postcondiciones, alternativas y excepciones propios de los casos de uso se desarrollarán en `casos-uso.md`.

Las decisiones técnicas y su implementación se desarrollarán en los documentos de arquitectura, modelo de datos, seguridad y UX/UI correspondientes.

La reorganización del contenido existente en `requerimientos.md` deberá conservar los identificadores, definiciones y estados de los requerimientos. Sus referencias deberán actualizarse para señalar el documento que contenga su especificación principal.

---

## 66.3 reglas-negocio.md

reglas-negocio.md contendrá la definición detallada de las reglas que determinan el comportamiento del negocio y de la plataforma.

Las reglas deberán documentar, según corresponda:

- ID.
- Nombre.
- Descripción.
- Condiciones.
- Datos involucrados.
- Cálculos.
- Restricciones.
- Estados.
- Excepciones.
- Resultado esperado.
- Requerimientos relacionados.
- Casos de uso relacionados.
- Módulo o capacidad a la que pertenecen.
- Etapa o entrega prevista.
- Estado de la definición.
- Referencias a las definiciones generales del proyecto.
- Decisiones pendientes, cuando existan.

Este documento deberá establecer bajo qué condiciones y reglas debe comportarse el sistema.

Las reglas utilizarán la nomenclatura RN-001, RN-002 y sucesivas, conforme a los identificadores existentes en el punto 26 de proyecto.md. Su numeración será única para todo el proyecto y no se reiniciará por módulo, documento o entrega.

El desarrollo detallado de las reglas iniciales conservará sus identificadores y su correspondencia con las definiciones del punto 26. Su traslado o ampliación no deberá cambiar silenciosamente el comportamiento aprobado.

Las reglas nuevas deberán utilizar identificadores disponibles, indicar su estado y referenciar las definiciones y requerimientos que las sustentan. Documentar una propuesta no implicará que esté aprobada.

El punto 26 conservará la presentación general de las reglas iniciales. reglas-negocio.md mantendrá su especificación detallada, evitando copiar íntegramente ese detalle en el documento maestro.

Cuando una regla nueva aprobada incorpore o modifique una definición general, un alcance o una decisión del proyecto, deberá ajustarse el punto correspondiente de proyecto.md y conservarse la trazabilidad. No será necesario reproducir en el punto 26 todas las reglas detalladas que se desarrollen posteriormente.

Los requerimientos funcionales y no funcionales conservarán su especificación principal en sus documentos correspondientes. Los casos de uso describirán las interacciones y referenciarán las reglas aplicables.

Las decisiones sobre lenguajes, frameworks, infraestructura y mecanismos técnicos se documentarán en los documentos técnicos correspondientes.

Una regla compartida por varios módulos tendrá una única definición principal. Las condiciones particulares de cada módulo o entrega deberán señalarse expresamente cuando exista una diferencia de comportamiento.


---
## 66.4 casos-uso.md

casos-uso.md contendrá la especificación detallada de los casos de uso de la plataforma.

Deberá documentar las interacciones entre los actores y el sistema, incluyendo:

Actor.

Objetivo.

Precondiciones.

Postcondiciones.

Flujo principal.

Flujos alternativos.

Excepciones.

Reglas de negocio relacionadas.

Requerimientos relacionados.

Datos involucrados.

Este documento deberá establecer cómo interactúan los actores con la solución.
---
## 66.5 arquitectura.md

arquitectura.md contendrá la definición técnica detallada de la arquitectura de la solución.

Podrá incluir, entre otros:

Arquitectura general.

Componentes.

Aplicaciones móviles.

Backend.

APIs.

Servicios.

Base de datos.

Almacenamiento.

Autenticación.

Autorización.

Notificaciones.

Infraestructura.

Cloud.

Ambientes.

Seguridad.

Observabilidad.

Integraciones.

Comunicación entre componentes.

Escalabilidad.

Disponibilidad.

Estrategias de despliegue.

Los registros de decisión técnica (ADR) definidos en el punto 53 deberán documentarse en arquitectura.md. Cada ADR permitirá identificar la decisión, las alternativas consideradas, su justificación, sus consecuencias y su estado.

Este documento deberá establecer cómo estará construida técnicamente la solución.
---
## 66.6 modelo-datos.md

modelo-datos.md contendrá la definición detallada del modelo de datos de la plataforma.

Deberá desarrollarse progresivamente desde el modelo conceptual hasta el modelo físico.

Podrá incluir:

Modelo conceptual.

Modelo lógico.

Modelo relacional.

Modelo físico.

Entidades.

Atributos.

Identificadores.

Claves primarias.

Claves foráneas.

Relaciones.

Cardinalidades.

Restricciones.

Integridad referencial.

Normalización.

Índices.

Auditoría.

Históricos.

Catálogos.

Diccionario de datos.

Tipos de datos.

Reglas relacionadas con persistencia.

Estrategias de almacenamiento.

Scripts de creación o migración, cuando corresponda.

El modelo de datos deberá derivarse de los requerimientos, reglas de negocio y casos de uso previamente definidos y aprobados.

El modelo conceptual incluido en proyecto.md no reemplaza el modelo detallado de modelo-datos.md.

---

## 66.7 Relación entre los documentos

Los documentos deberán complementarse entre sí y mantener trazabilidad.

`proyecto.md` establecerá la visión, el alcance y las definiciones generales que orientan los documentos especializados.

`requerimientos-funcionales-propietario.md` y `requerimientos-funcionales-prestador.md` establecerán los comportamientos esperados de cada módulo y referenciarán las capacidades generales compartidas.

`requerimientos-no-funcionales.md` establecerá las condiciones de calidad aplicables a los módulos, capacidades y entregas correspondientes.

`reglas-negocio.md` desarrollará las condiciones, validaciones, restricciones y cálculos relacionados con los requerimientos.

`casos-uso.md` describirá las interacciones entre actores y sistema, referenciando los requerimientos y las reglas aplicables.

`arquitectura.md` establecerá las decisiones técnicas necesarias para construir la solución conforme a las definiciones funcionales y no funcionales.

`modelo-datos.md` desarrollará las estructuras de información derivadas de los requerimientos, reglas de negocio, casos de uso y decisiones arquitectónicas.

La implementación deberá mantener trazabilidad con las definiciones aprobadas de estos documentos.

`seguridad.md` deberá relacionarse transversalmente con los documentos anteriores, de acuerdo con lo definido en el punto 67.

`ux-ui.md` deberá relacionar los requerimientos funcionales, los requerimientos no funcionales aplicables y los casos de uso con el diseño de la experiencia y la interfaz de la aplicación móvil, de acuerdo con lo definido en los puntos 57 y 66.13.

Esta relación no implica necesariamente que todos los documentos deban ser completados de manera estrictamente secuencial, sino que las definiciones deberán mantener coherencia y trazabilidad entre sí.


---
## 66.8 Fuente de referencia para la implementación

La documentación aprobada constituirá la fuente de referencia para la futura implementación de Vehículos Services.

La implementación deberá basarse en los requerimientos, reglas de negocio, casos de uso, arquitectura, modelo de datos, seguridad y diseño UX/UI documentados.

La solución no deberá desarrollar comportamientos funcionales, reglas de negocio, estructuras de datos o decisiones arquitectónicas relevantes únicamente mediante inferencias no documentadas.

Cuando una definición necesaria para implementar una funcionalidad sea:

Ambigua.

Incompleta.

Contradictoria.

Pendiente.

No definida.

deberá identificarse y resolverse antes de realizar una implementación que pueda comprometer el comportamiento esperado del sistema.
---
## 66.9 Trazabilidad documental

Las definiciones deberán mantener trazabilidad entre los diferentes niveles de la solución.

Conceptualmente:

REQUERIMIENTO
↓
REGLA DE NEGOCIO
↓
CASO DE USO
↓
MODELO DE DATOS
↓
ARQUITECTURA
↓
API / BACKEND
↓
APLICACIÓN
↓
PRUEBAS

El diseño documentado en ux-ui.md deberá mantener trazabilidad con los requerimientos y casos de uso correspondientes y con las pantallas e interacciones implementadas en la aplicación móvil.

Esta relación representa los vínculos que pueden ser necesarios según la naturaleza de cada definición; no implica que todo requerimiento deba tener una regla de negocio, un caso de uso o un cambio en cada componente técnico.

Esta trazabilidad permitirá identificar el origen de cada funcionalidad y facilitará posteriormente el desarrollo, validación, mantenimiento y evolución de la plataforma.

---
## 66.10 Consistencia entre documentos

Los documentos especializados deberán complementar el documento maestro y no deberán contradecir las definiciones aprobadas.

Cuando una decisión posterior modifique una definición existente, deberá actualizarse el documento correspondiente y, cuando sea necesario, también deberá actualizarse proyecto.md para mantener la coherencia de la definición general del proyecto.

---
## 66.11 Estado de las definiciones

Los documentos deberán diferenciar claramente entre:

Definición aprobada.

Definición preliminar.

Definición conceptual.

Definición pendiente.

Definición por validar.

Decisión propuesta.

Una definición que no haya sido aprobada no deberá interpretarse automáticamente como una decisión definitiva de implementación.

---
## 66.12 Propósito de la estructura documental

La estructura documental tiene como propósito proporcionar una especificación suficientemente completa y trazable para que, en una etapa posterior, una IA pueda utilizar la documentación del proyecto como fuente de referencia para desarrollar la aplicación.

La IA deberá poder identificar mediante la documentación:

Qué problema resuelve la plataforma.

Qué objetivos tiene.

Qué funcionalidades debe implementar.

Quiénes son los actores.

Cómo deben funcionar los procesos.

Cómo deben organizarse las pantallas, la navegación y las interacciones de la aplicación móvil.

Qué reglas debe cumplir.

Qué información debe almacenar.

Cómo se relacionan los datos.

Qué arquitectura debe respetar.

Qué restricciones existen.

Qué funcionalidades forman parte del alcance.

Qué funcionalidades están fuera del alcance.

Qué decisiones han sido aprobadas.

Qué decisiones todavía están pendientes.

La documentación deberá evolucionar junto con el proyecto y deberá mantenerse actualizada para conservar su valor como fuente de referencia para la implementación.

---
## 66.13 ux-ui.md

ux-ui.md contendrá el diseño detallado de la experiencia de usuario y de la interfaz de la aplicación móvil Android e iOS.

Deberá desarrollarse a partir de los requerimientos funcionales y casos de uso definidos para cada etapa del proyecto, considerando los requerimientos no funcionales aplicables. Comenzará por el módulo del Propietario y las funcionalidades generales necesarias para su uso; el diseño del módulo del Prestador de Servicios Vehiculares corresponderá a una etapa posterior.

Podrá incluir, según corresponda:

Arquitectura de navegación.

Mapa de pantallas.

Flujos de interacción.

Diseño de pantallas y formularios.

Componentes de interfaz.

Estados de carga, vacío, error y confirmación.

Mensajes y retroalimentación al usuario.

Criterios de usabilidad y accesibilidad.

Diseño adaptable a Android e iOS.

Prototipos y especificaciones visuales.

Este documento deberá establecer cómo se presentarán las funcionalidades y cómo interactuará el usuario con ellas. No deberá sustituir la definición de qué hace el sistema en requerimientos-funcionales-propietario.md y requerimientos-funcionales-prestador.md, las condiciones de calidad en requerimientos-no-funcionales.md, los casos de uso en casos-uso.md ni las decisiones sobre la tecnología móvil en arquitectura.md.

El diseño detallado de UX/UI deberá realizarse después de definir suficientemente los requerimientos y casos de uso de las funcionalidades correspondientes, de acuerdo con el principio establecido en el punto 57.


---

# 67. Seguridad como requisito transversal

La seguridad deberá considerarse un requisito transversal de Vehículos Services y deberá incorporarse desde las etapas de definición, diseño, desarrollo, pruebas, despliegue y operación de la plataforma.

La seguridad no deberá tratarse únicamente como una actividad posterior de auditoría. Las decisiones de seguridad deberán formar parte de los requerimientos, reglas de negocio, casos de uso, arquitectura, modelo de datos, implementación y pruebas correspondientes.

El documento especializado seguridad.md será la fuente de referencia para la definición detallada de los controles y criterios de seguridad de la solución.
---
## 67.1 Objetivo de seguridad

La solución deberá proteger la información de los usuarios, propietarios, talleres y vehículos, garantizando como mínimo:

Confidencialidad.

Integridad.

Disponibilidad.

Autenticidad.

Autorización adecuada.

Trazabilidad.

Protección de datos.
---
## 67.2 Alcance de seguridad

seguridad.md deberá definir, como mínimo, los controles relacionados con:

Autenticación de usuarios.

Verificación de correo electrónico.

Política de contraseñas.

Protección frente al uso de contraseñas comprometidas o filtradas.

Hashing y almacenamiento seguro de contraseñas.

Sesiones y tokens.

Almacenamiento seguro de credenciales y tokens en los clientes.

Autorización en backend.

Roles y permisos.

Control de acceso a nivel de recurso.

Propiedad y autorización sobre vehículos e historial.

Prevención de acceso indebido a recursos mediante identificadores manipulables.

Validación de entradas en servidor.

Prevención de inyección SQL y otras inyecciones.

Prevención de XSS y contenido no confiable.

Protección de APIs.

Rate limiting y protección contra abuso, especialmente en autenticación y recuperación de cuenta.

Configuración de CORS.

Manejo seguro de errores y excepciones.

Protección de rutas administrativas.

Protección frente a asignación masiva de atributos no autorizados.

Validación de webhooks e integraciones externas.

Seguridad de carga de archivos y documentos.

Validación de tipo, tamaño y contenido de archivos.

Gestión de secretos, claves y credenciales.

Prevención de exposición de secretos en código, repositorios y logs.

Logging seguro y protección de información sensible.

Auditoría de operaciones relevantes.

Gestión de dependencias y vulnerabilidades conocidas.

Seguridad de ambientes.

Seguridad de infraestructura y servicios cloud.

Seguridad del proceso CI/CD.

Protección de datos personales.

Pruebas de seguridad.

Gestión y corrección de vulnerabilidades.
---
## 67.3 Principio de seguridad del lado del servidor

Las validaciones relacionadas con autenticación, autorización, permisos, propiedad de recursos, reglas de negocio y protección de datos no deberán depender exclusivamente de la aplicación móvil.

El backend deberá validar las operaciones antes de permitir el acceso, modificación, eliminación o exposición de información.

La aplicación cliente deberá considerarse un entorno no confiable para efectos de seguridad.
---
## 67.4 Control de acceso a recursos

La seguridad deberá contemplar no solamente la autenticación del usuario, sino también la autorización específica sobre cada recurso solicitado.

El sistema deberá validar que el usuario tenga permisos suficientes para acceder o modificar el recurso solicitado.

Deberán contemplarse especialmente los riesgos asociados con:

Identificadores predecibles o manipulables.

Acceso directo a recursos de otros usuarios.

Acceso de un taller a vehículos no autorizados.

Modificación de información perteneciente a otros actores.

Acceso a documentos no autorizados.

Acceso a funciones administrativas sin los permisos correspondientes.
---
## 67.5 Validación y protección de datos de entrada

Toda información recibida desde aplicaciones móviles, APIs, archivos, integraciones o usuarios deberá ser validada y procesada de acuerdo con las reglas de seguridad definidas.

No deberá asumirse que una validación realizada únicamente en el cliente es suficiente para proteger el backend.
---
## 67.6 Seguridad de documentos y archivos

Los archivos almacenados por la plataforma deberán contar con controles que eviten la carga, almacenamiento, acceso o procesamiento de contenido no autorizado o potencialmente malicioso.

Los controles detallados deberán definirse en seguridad.md y relacionarse con la arquitectura de almacenamiento y los requerimientos correspondientes.
---
## 67.7 Secretos, credenciales y configuración sensible

Las claves, contraseñas, tokens, credenciales, certificados y demás secretos no deberán incorporarse directamente al código fuente ni almacenarse en repositorios públicos o mecanismos no autorizados.

Deberá existir una estrategia para su almacenamiento, acceso, rotación y protección según el ambiente correspondiente.
---
## 67.8 Seguridad de APIs y servicios

Las APIs deberán contemplar controles para autenticación, autorización, validación de entradas, limitación de solicitudes, manejo seguro de errores, protección contra abuso y exposición mínima de información.

Los controles específicos dependerán de la arquitectura y tecnologías finalmente aprobadas.
---
## 67.9 Seguridad de logs y auditoría

Los mecanismos de observabilidad y auditoría deberán permitir investigar eventos relevantes sin exponer información sensible innecesariamente.

Los logs no deberán utilizarse como mecanismo para almacenar contraseñas, tokens, secretos u otra información sensible que no sea estrictamente necesaria para la operación.
---
## 67.10 Seguridad durante el desarrollo

La seguridad deberá incorporarse al ciclo de desarrollo mediante revisiones, pruebas automatizadas y verificaciones específicas antes de liberar funcionalidades.

La definición de terminado de una funcionalidad deberá considerar, cuando corresponda:

Validación funcional.

Validación de reglas de negocio.

Validación de permisos.

Validación de controles de seguridad.

Pruebas correspondientes.

Auditoría de cambios relevantes.
---
## 67.11 Auditoría de seguridad

La auditoría de seguridad deberá utilizarse como mecanismo de verificación de la implementación y no como sustituto de la definición de seguridad.

El proyecto deberá contemplar revisiones específicas para detectar vulnerabilidades que puedan no ser identificadas únicamente mediante análisis estático o escáneres automáticos.

Entre los aspectos que deberán verificarse se encuentran, como mínimo:

Secretos o credenciales versionados en el repositorio.

Claves de API expuestas en el cliente.

Autorización implementada únicamente en frontend.

Ausencia de rate limiting en operaciones sensibles.

Construcción insegura de consultas SQL.

Falta de validación de datos en servidor.

XSS y contenido HTML no sanitizado.

Almacenamiento inseguro de contraseñas.

Almacenamiento inseguro de sesiones o tokens.

Rutas administrativas sin autenticación o autorización adecuada.

Configuración insegura de CORS.

Registro de usuarios sin mecanismos adecuados de verificación.

Acceso indebido a recursos mediante identificadores manipulables.

Asignación masiva de atributos no autorizados.

Webhooks sin validación de autenticidad.

Exposición de trazas o errores internos en producción.

Dependencias con vulnerabilidades conocidas.

Ausencia de controles frente a contraseñas comprometidas.

Carga de archivos sin validaciones suficientes.

Exposición de secretos o información sensible mediante logs.

Estos puntos deberán convertirse posteriormente en controles, requerimientos, pruebas o criterios de aceptación concretos dentro de la documentación especializada.
---
## 67.12 Trazabilidad de seguridad

Los controles de seguridad deberán mantener trazabilidad con el resto de la documentación del proyecto.

La relación conceptual será:

REQUERIMIENTO
↓
REGLA DE NEGOCIO
↓
CASO DE USO
↓
CONTROL DE SEGURIDAD
↓
ARQUITECTURA
↓
IMPLEMENTACIÓN
↓
PRUEBA
↓
AUDITORÍA

Esto permitirá determinar por qué existe cada control, qué riesgo pretende mitigar, dónde se implementa y cómo se verifica.
---
## 67.13 Seguridad y futura implementación mediante IA

La documentación deberá permitir que una futura IA utilizada para desarrollar Vehículos Services pueda identificar los controles de seguridad que debe respetar durante la implementación.

La IA no deberá asumir que una funcionalidad es segura únicamente porque funciona correctamente desde el punto de vista funcional.

Cuando una funcionalidad involucre información, permisos, autenticación, autorización, documentos, APIs, datos personales o integraciones externas, deberá consultar las definiciones correspondientes de seguridad.md antes de implementarla.

La IA no deberá inventar controles, permisos, reglas o decisiones técnicas que no estén documentados. Cuando una definición de seguridad sea ambigua, incompleta o pendiente, deberá identificarse como tal y resolverse antes de implementar una decisión que pueda comprometer la seguridad de la solución.
---
## 67.14 Relación con los documentos especializados

seguridad.md deberá trabajar de forma integrada con los demás documentos del proyecto:

proyecto.md: contexto, alcance, principios y definición general.

requerimientos-funcionales-propietario.md: requisitos funcionales del Propietario y capacidades generales compartidas relacionados con seguridad.

requerimientos-funcionales-prestador.md: requisitos funcionales del Prestador de Servicios Vehiculares relacionados con seguridad, correspondientes a su etapa de desarrollo.

requerimientos-no-funcionales.md: requisitos no funcionales relacionados con seguridad, indicando su alcance y condiciones de verificación.

reglas-negocio.md: reglas que afectan permisos, acceso, integridad y comportamiento seguro.

casos-uso.md: controles de seguridad aplicables a cada interacción.

arquitectura.md: mecanismos técnicos mediante los cuales se implementan los controles.

modelo-datos.md: estructuras necesarias para soportar permisos, auditoría, trazabilidad y protección de información.

ux-ui.md: diseño de pantallas e interacciones que deberá respetar los controles de acceso, privacidad y protección de información definidos.

seguridad.md: definición especializada de controles, amenazas, criterios y verificaciones de seguridad.

Ningún documento especializado deberá contradecir una definición de seguridad aprobada.


---
## 67.15 Estado de seguridad

La seguridad definida en este documento es de carácter conceptual y establece el alcance mínimo que deberá desarrollarse posteriormente.

Las tecnologías, mecanismos específicos, proveedores, configuraciones y controles técnicos definitivos deberán documentarse y aprobarse en los documentos especializados y ADR correspondientes antes de considerarse decisiones definitivas.

