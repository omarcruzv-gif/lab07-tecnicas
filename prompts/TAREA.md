# TAREA: Diseño de un prompt avanzado

## 1. Descripción de la tarea

La tarea elegida consiste en generar casos de prueba para un sistema de inicio de sesión web (Login), que utiliza correo electrónico y contraseña.

El sistema debe bloquear la cuenta después de tres intentos fallidos.

**Objetivo:** Diseñar un prompt avanzado que permita obtener casos de prueba claros, organizados y útiles para identificar posibles errores en el funcionamiento del login.

---

## 2. Iteración de prompts

### Versión 1 – Prompt básico (Zero-shot)

**Prompt utilizado:**

```text
Genera 6 casos de prueba para un sistema de login web con correo electrónico y contraseña. La cuenta se bloquea después de 3 intentos fallidos.
```

**Técnica agregada:** Zero-shot.

**¿Por qué?**
Se utilizó como punto de partida para comprobar qué podía generar la IA sin instrucciones adicionales ni ejemplos.

**¿Qué mejoró en la respuesta?**
La IA generó casos de prueba generales, pero algunos detalles y formatos no estaban suficientemente definidos.

---

### Versión 2 – Prompt con rol y formato estructurado

**Prompt utilizado:**

```text
<rol>
Actúa como analista de pruebas de software especializado en pruebas funcionales.
</rol>

<contexto>
Login web con correo electrónico y contraseña. La cuenta se bloquea después de 3 intentos fallidos.
</contexto>

<tarea>
Genera 6 casos de prueba para verificar el funcionamiento del inicio de sesión.
</tarea>

<formato>
Presenta una tabla con las columnas:
ID, escenario, datos de entrada y resultado esperado.
</formato>
```

**Técnicas agregadas:** Role prompting y prompt estructurado.

**¿Por qué?**
Se agregó un rol específico para orientar a la IA y una estructura para organizar mejor los resultados.

**¿Qué mejoró en la respuesta?**
Los casos de prueba fueron más organizados, claros y fáciles de revisar.

---

### Versión 3 – Prompt avanzado

**Prompt utilizado:**

```text
<rol>
Actúa como analista de aseguramiento de calidad (QA) especializado en pruebas funcionales de aplicaciones web.
</rol>

<contexto>
Se está probando un sistema de inicio de sesión web que utiliza correo electrónico y contraseña.
La cuenta se bloquea después de 3 intentos fallidos consecutivos.
</contexto>

<tarea>
1. Analiza las condiciones de funcionamiento del login.
2. Divide el proceso en escenarios positivos, negativos y casos límite.
3. Genera 6 casos de prueba diferentes.
4. Incluye pruebas para verificar el bloqueo después de 3 intentos fallidos.
5. Revisa los casos generados e identifica posibles escenarios faltantes.
</tarea>

<formato>
Presenta una tabla con las siguientes columnas:
ID, escenario, tipo de prueba, datos de entrada y resultado esperado.

Después de la tabla, incluye una breve revisión indicando si los casos cubren los principales riesgos del login.
Responde en español.
</formato>
```

**Técnicas agregadas:** Descomposición, Chain of Thought y autocrítica.

**¿Por qué?**
Se dividió el problema en pasos para evitar omisiones, se solicitó analizar los escenarios antes de generar los casos y se incorporó una revisión final.

**¿Qué mejoró en la respuesta?**
La respuesta fue más completa, contempló escenarios positivos, negativos y casos límite, y permitió identificar posibles errores adicionales.

---

## 3. Prompt final

El siguiente prompt combina cinco técnicas: Role prompting, descomposición, Chain of Thought, prompt estructurado y autocrítica.

```text
<rol>
Actúa como analista de aseguramiento de calidad (QA) especializado en pruebas funcionales de aplicaciones web.
</rol>

<contexto>
Se está evaluando un sistema de inicio de sesión web que utiliza correo electrónico y contraseña.
La cuenta se bloquea después de 3 intentos fallidos consecutivos.
</contexto>

<tarea>
1. Identifica los requisitos principales del sistema.
2. Divide las pruebas en escenarios positivos, negativos y casos límite.
3. Analiza paso a paso las condiciones necesarias para cada escenario.
4. Genera 6 casos de prueba diferentes.
5. Verifica que se incluya el bloqueo de cuenta después de 3 intentos fallidos.
6. Realiza una autocrítica e identifica posibles escenarios que no se hayan considerado.
</tarea>

<formato>
Presenta una tabla con las columnas:
ID, escenario, tipo de prueba, datos de entrada y resultado esperado.

Después de la tabla, agrega una sección de observaciones y otra de mejoras sugeridas.

Utiliza un lenguaje técnico, claro y conciso.
Responde en español.
</formato>
```

---

## 4. Relación entre las técnicas utilizadas

| Técnica | Parte del prompt | Función |
|---|---|---|
| Role prompting | Actúa como analista QA. | Define el perfil de la IA. |
| Descomposición | Divide las pruebas en diferentes pasos. | Organiza el problema. |
| Chain of Thought | Analiza paso a paso las condiciones. | Mejora el análisis de los escenarios. |
| Prompt estructurado | Define las columnas de la tabla. | Organiza la respuesta. |
| Autocrítica | Identifica escenarios no considerados. | Permite revisar posibles omisiones. |

---

## 5. Evaluación del resultado

| Criterio de evaluación | Resultado |
|---|---|
| El prompt define un rol específico. | Sí |
| El contexto del sistema está claramente definido. | Sí |
| Se generan 6 casos de prueba. | Sí |
| Se incluyen escenarios positivos y negativos. | Sí |
| Se contempla el bloqueo después de 3 intentos. | Sí |
| La respuesta utiliza una tabla organizada. | Sí |
| Se realiza una revisión de posibles omisiones. | Sí |

---

## 6. ¿Por qué elegí estas técnicas?

Elegí estas técnicas porque permiten obtener casos de prueba más completos y organizados. El Role prompting establece el perfil del analista QA, la descomposición divide el problema en pasos, Chain of Thought ayuda a analizar las condiciones y la autocrítica permite identificar posibles omisiones. Finalmente, el prompt estructurado garantiza que los resultados tengan un formato claro y fácil de evaluar.

No utilicé few-shot porque la tarea no necesitaba ejemplos previos para establecer un formato, ya que podía definirlo directamente mediante instrucciones.

---
