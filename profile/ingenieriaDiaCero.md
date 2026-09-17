# CódigoLimpio@DíaCero: Ingeniería desde la primera línea

## ¿Por qué?

La educación tradicional en programación establece una secuencia predecible: semanas iniciales dedicadas a sintaxis y estructuras básicas, meses de construcción de lógica con literales directos y nombres genéricos, y finalmente —cuando los estudiantes ya han escrito miles de líneas— la introducción de "buenas prácticas" como tema avanzado.

Esta secuencia genera deuda técnica pedagógica. Para cuando se introduce el concepto de claridad semántica, los estudiantes han automatizado patrones contrarios: `60` en lugar de `SEGUNDOS_POR_MINUTO`, `x` en lugar de `totalSegundos`, `flag` en lugar de `esVálido`. La enseñanza tardía de código limpio no es adición de conocimiento, es desaprendizaje de hábitos consolidados.

El problema se agrava cuando esta secuencia contradice la filosofía declarada del programa. Un grado que proclama "ingeniería desde el día 0" pero permite código sin claridad semántica durante meses comunica implícitamente: la ingeniería es refinamiento posterior, no fundamento inicial.

La incoherencia es visible en el código producido. Estudiantes que dominan estructuras de control complejas pero escriben programas incomprensibles. La funcionalidad está correcta, pero el razonamiento es opaco. El código funciona, pero no comunica.

Esta problemática no es exclusiva de programación. Aparece en cualquier disciplina donde se separa artificialmente "hacer que funcione" de "hacerlo correctamente". La separación temporal entre ambos objetivos implica que el segundo es opcional o secundario.

## ¿Qué?

Código limpio no es estética. Es expresión de pensamiento ingenieril.

Cuando un estudiante escribe `int minutos = segundos / 60;`, está realizando una operación correcta computacionalmente. Cuando escribe `int minutos = segundos / SEGUNDOS_POR_MINUTO;`, está documentando razonamiento. La diferencia no es funcional, es semántica: el segundo formato hace explícito qué representa cada elemento de la operación.

Esta distinción es fundamental para ingeniería de software. Un programa no solo debe producir resultados correctos, debe permitir que otros ingenieros comprendan el razonamiento que conduce a esos resultados. La claridad no es atributo auxiliar del código, es requisito técnico básico.

El concepto abarca múltiples dimensiones:

**Nombrado semántico**: Variables y constantes cuyos nombres revelan propósito y tipo de información que contienen. No `x` sino `totalSegundos`. No `60` sino `SEGUNDOS_POR_MINUTO`.

**Intención explícita**: Código donde cada línea comunica no solo qué hace, sino por qué existe. La operación `segundos % SEGUNDOS_POR_MINUTO` es autodocumentada: obtiene los segundos restantes después de extraer minutos completos.

**Estructura legible**: Organización del código que facilita comprensión progresiva. Indentación consistente, espaciado apropiado, agrupación lógica de operaciones relacionadas.

Esta concepción de código limpio como pensamiento ingenieril visible conecta directamente con los principios establecidos en [Ingeniería Informática](README.md): "El software es sagrado y lo importante requiere de un ritual". El ritual comienza con la primera línea escrita, no después de que el programa funcione.

## ¿Para qué?

La introducción temprana de código limpio persigue múltiples objetivos pedagógicos y profesionales:

### Coherencia filosófica

La filosofía de [Ingeniería desde el primer día](README.md#ingeniería-desde-el-día-0) requiere implementación desde la primera asignatura de programación. Si el estudiante es ingeniero desde el primer día, debe escribir código con estándares ingenieriles desde la primera línea. La coherencia entre declaración y práctica es requisito para credibilidad pedagógica.

### Prevención de automatización de malos hábitos

El cerebro automatiza patrones mediante repetición. Un estudiante que escribe `60` directamente en cien programas diferentes automatiza ese patrón como forma "normal" de programar. Revertir esa automatización requiere esfuerzo significativamente mayor que establecer el patrón correcto inicialmente.

La ventana temporal para prevención es estrecha. Ocurre después de que el estudiante comprende variables y operadores, pero antes de que escriba suficiente código como para consolidar hábitos. Introducir código limpio en esa ventana minimiza fricción de aprendizaje.

### Visibilidad del proceso de razonamiento

Como se establece en [Proceso de Creación](procesoDeCreacion.md), la educación debe hacer visible el proceso, no solo evaluar el producto. Código limpio es mecanismo de visibilidad: nombres descriptivos y constantes semánticas revelan cómo el estudiante conceptualizó el problema.

La claridad semántica permite distinguir entre dos tipos de errores fundamentalmente diferentes:

- Error de razonamiento: el estudiante concibió incorrectamente la solución
- Error de traducción: el estudiante razonó correctamente pero expresó mal en código

Esta distinción es invisible cuando el código carece de claridad. Un programa con variables `x`, `y`, `z` y literales numéricos directos no comunica intención, solo resultado.

### Preparación para colaboración profesional

El código en contextos profesionales es siempre colaborativo. Múltiples ingenieros leen, modifican y mantienen el mismo código durante años. La claridad semántica no es cortesía, es requisito operativo.

Estudiantes que aprenden desde el inicio que el código debe ser legible para otros desarrollan sensibilidad para escribir pensando en el lector. Esta sensibilidad es difícil de adquirir posteriormente cuando se ha automatizado el hábito de escribir solo para uno mismo.

## ¿Cómo?

### Timing estratégico

La secuencia pedagógica tradicional en Programación 1 introduce conceptos en este orden:

1. Sintaxis básica (semanas 1-2)
2. Variables y operadores (semanas 3-4)
3. Estructuras de control (semanas 5-8)
4. Métodos y modularización (semanas 9-12)
5. Código limpio (semana 13+)

La secuencia implementada en [25-26-PRG1](https://github.com/mmasias/25-26-PRG1) modifica este orden:

1. Sintaxis básica (semanas 1-2)
2. Variables y operadores (semanas 3-4)
3. **Código limpio (semana 5)**
4. Estructuras de control (semana 6+)

El cambio no es arbitrario. Código limpio se introduce inmediatamente después de que los estudiantes comprenden variables, pero antes de que comiencen a escribir lógica compleja. En ese punto tienen las herramientas conceptuales necesarias (variables, tipos, operadores) pero no han automatizado patrones de uso.

Esta secuencia evolucionó mediante experimentación documentada. En [24-25-PRG1](https://github.com/mmasias/24-25-PRG1), código limpio apareció después de estructuras de control y métodos estáticos. La observación de esa cohorte reveló resistencia significativa: estudiantes que ya habían escrito docenas de programas con literales directos percibían las constantes semánticas como burocracia innecesaria.

La modificación para [25-26-PRG1](https://github.com/mmasias/25-26-PRG1) anticipa la introducción antes de que se consoliden esos patrones. El costo cognitivo de aprender `final int SEGUNDOS_POR_MINUTO = 60;` en semana 5 es comparable al de aprenderlo en semana 10, pero el beneficio de prevención es significativamente mayor.

### Revisiones Públicas de Retos (RPdR)

La implementación operativa de código limpio temprano requiere mecanismo de validación y aprendizaje colectivo. Las RPdR funcionan como code review profesional adaptado a contexto pedagógico:

**Proceso**:
1. Planteamiento de reto de programación
2. Estudiantes desarrollan solución individualmente
3. Envío mediante pull request al repositorio del curso
4. Sesión de revisión pública de soluciones seleccionadas
5. Análisis colectivo de diferencias de aproximación

**Criterios de selección**:
- Solución técnicamente excelente: establece estándar alcanzable
- Solución con dificultad genuina pero iteración visible: muestra proceso de aprendizaje efectivo
- Solución sin proceso visible: expone ausencia de método sin necesidad de acusación directa

La revisión pública entrena tres roles simultáneamente:

**Como autor**: Defender decisiones técnicas. Articular razonamiento detrás de cada aproximación. Distinguir entre decisión consciente y ausencia de alternativa conocida.

**Como revisor**: Leer código ajeno críticamente. Identificar problemas específicos. Sugerir mejoras concretas sin personalizar críticas.

**Como observador**: Reconocer patrones recurrentes entre soluciones. Identificar qué aproximaciones generan código más limpio. Ver errores propios en código ajeno donde son más visibles.

### Infraestructura tecnológica

La implementación requiere herramientas que hagan visible el proceso de desarrollo:

**Repositorios públicos**: Cada estudiante mantiene repositorio personal donde todo el trabajo del curso queda documentado. El historial de commits es trazabilidad completa del proceso de aprendizaje.

**Sistema de tracking**: Herramientas desarrolladas específicamente para monitorear actividad estudiantil:
- [Tracker de contributors](https://manuel.masiasweb.com/github-stats-page-contributors.html): Visualiza patrones de trabajo por estudiante
- [Navegador de commits](https://manuel.masiasweb.com/gh-history-v0/): Permite análisis temporal de evolución de código

**Documentación de progreso**: El documento ["A día de hoy deberíamos saber"](https://github.com/mmasias/25-26-PRG1/blob/main/temario/aDiaDeHoy.md) actualizado después de cada clase establece expectativas claras y permite autoevaluación estudiantil.

Esta infraestructura convierte el proceso de aprendizaje en artefacto auditable. No solo para evaluación docente, sino para análisis entre pares. Los estudiantes pueden examinar el proceso de trabajo de compañeros exitosos y identificar patrones replicables.

### Evaluación de proceso

La calificación no se basa únicamente en funcionalidad del código final. Se evalúa:

**Claridad semántica**: Uso de nombres descriptivos y constantes apropiadas desde programas iniciales.

**Iteración visible**: Historial de commits que muestra proceso de refinamiento progresivo, no solo entregas de última hora.

**Evolución técnica**: Mejora observable en calidad de código entre ejercicios tempranos y tardíos del semestre.

Este modelo de evaluación requiere que el proceso sea público y verificable. La infraestructura de repositorios no es solo herramienta de entrega, es mecanismo de validación de aprendizaje genuino.

## ¿Cuándo?

El momento de introducción de código limpio es crítico y no arbitrario.

**Demasiado temprano** (semana 1-2): Los estudiantes aún no comprenden variables ni tipos. Introducir constantes semánticas antes de consolidar el concepto de variable genera confusión sobre distinción entre ambos.

**Demasiado tarde** (semana 10+): Los estudiantes ya escribieron cientos de líneas con literales directos. La introducción de código limpio se percibe como burocracia adicional, no como forma correcta de programar. La resistencia es proporcional al volumen de código previamente escrito.

**Momento óptimo** (semana 5): Inmediatamente después de consolidar variables y operadores, pero antes de introducir estructuras de control complejas. Los estudiantes tienen las herramientas conceptuales necesarias pero no han automatizado patrones contrarios.

Esta ventana temporal se validó mediante comparación entre cohortes. La evidencia observable sugiere que anticipar la introducción reduce resistencia y mejora adopción sin incrementar significativamente la carga cognitiva inicial.

## ¿Y ahora qué?

### Medición de resultados

La experimentación pedagógica requiere instrumentación para validar efectividad. Los repositorios públicos de tres cohortes consecutivas ([22-23](https://github.com/mmasias/prg1-22-23), [23-24](https://github.com/mmasias/23-24-prg1), [25-26](https://github.com/mmasias/25-26-PRG1)) permiten análisis comparativo:

- Calidad de código en ejercicios equivalentes entre cohortes
- Patrones de adopción de constantes semánticas según momento de introducción
- Correlación entre claridad de código y desempeño en cursos posteriores

Este análisis aún está en proceso. La cohorte 25-26 recién comenzó implementación del timing modificado. Resultados definitivos requerirán seguimiento hasta finalización del semestre.

### Replicación en otras asignaturas

El modelo de "ingeniería desde día 0" no se limita a programación. Cada asignatura del grado debe implementar la filosofía según su contexto específico:

**Estructura de Datos y Algoritmos**: Análisis de complejidad desde la primera implementación, no como tema posterior. Cada algoritmo se acompaña de análisis de eficiencia desde el inicio.

**Bases de Datos**: Normalización como parte del diseño inicial, no como corrección posterior. Esquemas bien diseñados desde las primeras prácticas.

**Ingeniería de Software**: Análisis y diseño antes que implementación, invirtiendo la secuencia tradicional requisitos→diseño por diseño→requisitos para desarrollar intuición técnica antes de formalización.

La coherencia entre asignaturas refuerza el mensaje: la ingeniería no es refinamiento posterior, es aproximación fundamental desde el inicio de cada disciplina.

### Documentación continua

Este documento forma parte de un sistema de tres artículos complementarios que establecen la filosofía pedagógica del grado:

- [Ingeniería Informática](README.md): Visión general y principios rectores
- [Proceso de Creación](procesoDeCreacion.md): Evaluación de proceso sobre producto
- **Código Limpio desde Día Cero**: Implementación específica en programación

La documentación no es estática. Se actualiza conforme evolucionan los proyectos. Los repositorios públicos garantizan trazabilidad completa de cambios y permiten que otros docentes examinen, critiquen, adapten o refuten el enfoque con evidencia observable.

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
