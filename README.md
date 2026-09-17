# Estudio Security+ · SY0-701

**▶ Pruébalo aquí:** https://d-gomez-sec.github.io/confundibles-securityplus/

Entrenador de refuerzo para el examen SY0-701: ataca los pares de conceptos donde CompTIA hace dudar, con repetición espaciada, examen simulado y ejercicios de cálculo de riesgo con números reales.

**¿Para qué sirve?:** el temario completo ya está en Messer y en los objetivos oficiales. Esto no lo sustituye — ataca el punto concreto donde de verdad se pierden puntos: la confusión entre dos o tres términos parecidos, y el cálculo de fórmulas que hay que saber hacer a mano.
**Su ventaja:** no siempre hay a mano un simulador completo tipo ExamCompass. Esta herramienta cabe en el bolsillo, funciona sin conexión, y crece con lo que uno mismo va fallando.

---

## Cuatro modos de estudio

| Modo | Qué hace |
|---|---|
| 🔀 Ronda libre | Preguntas al azar de los dominios elegidos. Sin memoria entre sesiones. |
| 🔁 Repaso inteligente | Prioriza lo fallado o lo que hace tiempo que no se repasa, con repetición espaciada real. |
| ⏱ Examen simulado | 15/30/50 preguntas de todos los dominios, un minuto por pregunta, sin corrección hasta el final. |
| 🧮 Cálculo (5.2) | Ejercicios de SLE/ALE generados al vuelo, con valores distintos cada vez. Hace falta calculadora. |

### Repetición espaciada

Cada confundible vive en una de cinco «cajas» (sistema Leitner simplificado). Fallarlo lo manda a la caja 0 — vence de inmediato —; acertarlo lo sube de caja y espacia el próximo repaso (1, 3, 7, 16 días). El modo **Repaso inteligente** construye la ronda con lo que está vencido, priorizando lo más atrasado, y la rellena con preguntas al azar si no hay suficiente pendiente. Arriba del todo, un panel muestra el % de acierto histórico por dominio y cuántas preguntas están pendientes de repaso.

### Examen simulado

Mezcla los cinco dominios ignorando el filtro, como el examen real. No hay feedback pregunta a pregunta — se corrige todo al final, con revisión completa de cada una. El porcentaje final es orientativo: CompTIA puntúa en una escala propia (100–900, apto desde 750) que no se puede reproducir aquí.

### Cálculo de riesgo (Dominio 5.2)

No es un catálogo fijo: cada ejercicio se **improvisa** con un activo, un incidente y valores de AV, EF y ARO distintos, elegidos al azar. Se resuelve en tres pasos con una calculadora real:

1. **SLE** = AV × EF
2. **ALE** = SLE × ARO (a partir del SLE ya calculado, para que un fallo en el paso 1 no arrastre el paso 2)
3. **Decisión de inversión** — se compara el coste de protegerse frente al ALE, que es para lo que de verdad sirve el número: si proteger algo cuesta más que su ALE, no compensa.

El progreso (aciertos por paso) se guarda en el dispositivo.

### Bilingüe con traducción puntual

El contenido está en inglés, como el examen real y como el material avanzado (BTL1, CySA+). Cada pregunta tiene un botón que la traduce individualmente al español —incluidas sus opciones y el feedback— para la que se atragante. Al pasar a la siguiente, vuelve a inglés: el español es una muleta puntual, no un modo general.

### Tus propios confundibles

Cuando algo se falla en ExamCompass o en otro simulador, se puede añadir aquí con su pista y su distinción. Entra directamente en las rondas y se guarda en el dispositivo.

---

## Contenido: 79 confundibles en los cinco dominios

| Dominio | Confundibles | Incluye |
|---|---|---|
| 1 · Conceptos generales | 10 | Cripto simétrico/asimétrico, hashing, zero trust (plano de control/datos), tecnología de decepción (honeypot/honeynet/honeyfile/honeytoken) |
| 2 · Amenazas y vulnerabilidades | 27 | SQLi/XSS/inyección de comandos/LDAP, ingeniería social, actores de amenaza (estado-nación, crimen organizado, hacktivista, insider, script kiddie), taxonomía de malware (ransomware, rootkit, keylogger, bomba lógica, botnet, gusano, troyano) |
| 3 · Arquitectura de seguridad | 11 | IAM, DMZ/VLAN, SASE, IoT/OT/ICS, fail-open/closed, estados del dato, tokenización/enmascaramiento/ofuscación/cifrado |
| 4 · Operaciones de seguridad | 13 | IDS/IPS, SIEM/SOAR, fases de IR, forense (cadena de custodia/orden de volatilidad/legal hold), PAM, BYOD/COPE/CYOD, NAC/802.1X |
| 5 · Gestión, riesgo y cumplimiento | 18 | RTO/RPO, MTBF/MTTR, tipos de acuerdo (SLA/MOU/MSA/NDA/BPA/SOW), análisis cualitativo/cuantitativo, apetito/tolerancia al riesgo, roles de datos, tipos de pentest |

Las preguntas de 3 y hasta 6 opciones (tipos de acuerdo, técnicas de privacidad, tecnología de decepción) se muestran siempre con todas las alternativas juntas, para forzar la distinción real entre varios términos y no solo entre dos.

---

## Uso

Abre `index.html` en cualquier navegador. Un solo archivo, sin instalación, sin conexión y sin dependencias. Todo el progreso se guarda en el dispositivo.

---

## Advertencia sobre el contenido

**Es refuerzo, no sustituto del temario**, y no pretende cobertura exhaustiva de los objetivos oficiales. Si algo aquí contradice a **Professor Messer** o a los objetivos oficiales de CompTIA, manda Messer.

---

## Qué aprendí construyéndolo

- **El motor de opción múltiple ya soportaba N opciones sin cambios.** Al diseñar el ejercicio de los seis tipos de acuerdo, descubrí que la estructura original (un array de opciones y un índice de la correcta) no estaba limitada a pares — solo la usaba así. Eso permitió añadir preguntas de 3, 4 y 6 opciones sin tocar el motor, reutilizando exactamente el mismo código.
- **Repetición espaciada exige identidad estable.** Sin un id que sobreviva a reordenar o ampliar el catálogo, el sistema de repaso no sabría qué habías fallado ayer. Generar el id a partir de un hash del contenido (no de la posición en el array) resuelve esto sin tener que mantener identificadores a mano en cada una de las 79 entradas.
- **Un ejercicio de cálculo no puede depender de un catálogo fijo.** Memorizar la respuesta a un problema concreto no es lo mismo que saber aplicar la fórmula. Generar los valores al vuelo —con un activo, un incidente y unos números distintos cada vez— obliga a razonar la fórmula en lugar de recordar el resultado.
- **Separar el fallo del paso 1 del paso 2 importa.** En el ejercicio de SLE/ALE, el paso 2 usa el SLE que el usuario acaba de calcular como base, no el valor "oficial" oculto. Así, equivocarse en el primer cálculo no arrastra el segundo como un fallo en cascada — cada paso se evalúa por su propio mérito.
- **Verificar con datos generados, no solo con casos fijos.** Antes de dar por buena esta versión, generé ejercicios de cálculo repetidamente y comprobé por script que SLE y ALE cuadraban matemáticamente en todos los casos — y así apareció un fallo real: la frase generada decía «El valor de el CRM» en lugar de «del CRM» cuando el activo elegido al azar empezaba por «el». Un caso de prueba fijo nunca lo habría encontrado.

---

## Licencia

MIT — ver [LICENSE](LICENSE).
