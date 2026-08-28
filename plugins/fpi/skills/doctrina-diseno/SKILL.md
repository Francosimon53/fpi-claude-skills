---
name: doctrina-diseno
description: Doctrina de diseño de FPI Enterprises basada en psicología humana revisada por pares (2022-2026). Aplícala SIEMPRE antes de escribir o modificar cualquier interfaz, pantalla, formulario, mensaje de error, texto de botón, onboarding, página de precios, landing, flujo de aprobación o copy de producto en cualquier repo de FPI (ariaba-app, abasensei, cotizasalud/enrollsalud, recinto, anonimizador-app, verification-layer, motor-brain-synthetic). Úsala también cuando alguien pida "mejorar la UI", "que se vea mejor", "hacerlo más fácil de usar", "cambiar los colores", "revisar el copy", o cuando decidas por tu cuenta el texto que ve un usuario final. Si estás a punto de escribir algo que un humano va a leer en pantalla, esta skill aplica.
---

# Doctrina de diseño de FPI Enterprises

Los productos de FPI los usan humanos, no máquinas. El diseño arranca de cómo la mente
humana elige e interactúa, no de la lógica del sistema. Esta doctrina la aprobó Simón
Franco el 28 de agosto de 2026 y sale de literatura revisada por pares, priorizando
2022-2026.

## Cómo se usa

Antes de escribir una pantalla, un mensaje o un flujo, pasa el diseño por los 20
principios de abajo. No hace falta cumplirlos los 20 en cada pantalla: identifica cuáles
muerden en ESA pantalla y decláralos en el PR o en el runbook.

Antes de dar por terminado el trabajo, corre el checklist del final.

## Quién es Marta

Marta es la usuaria final. No es técnica. Termina el día cansada y con trabajo pendiente.
Usa el producto porque le ahorra tiempo, pero teme que un error salga con su firma. Nadie
le preguntó qué software quería: lo heredó.

Cambia de nombre según el producto — analista de conducta, agente de seguros, dueño de
agencia, candidata a certificación — pero la psicología es la misma. Cuando dudes de una
decisión de diseño, hazte la pregunta en su voz.

## Los 20 principios

**1. "No sé por qué, pero esta pantalla me da confianza."**
No es belleza, es facilidad de procesar. Jerarquía clara, una idea por pantalla, carga
rápida, tipografía legible. El adorno que no ayuda a entender, resta.

**2. "Le di siguiente, siguiente, siguiente."**
Lo que venga marcado por defecto es lo que va a usar durante años. El default es la única
palanca de arquitectura de elección con evidencia sólida. En dudas de seguridad o
cumplimiento, el default es siempre la opción conservadora: tachar de más, avisar de más,
validar de más.

**3. "Prefiero verlo todo y decidir yo."**
Esconder opciones no ayuda por sí solo. Solo abruma cuando la decisión es genuinamente
compleja o ella no sabe qué prefiere. No mutiles la interfaz por miedo a "demasiadas
opciones".

**4. "¿Puedo fiarme de esto o no?"**
No quiere que le jures que es perfecto: quiere saber CUÁNDO dudar. Marca lo incierto de
forma accionable. Un sistema que solo dice "listo" sin decir qué NO revisó está mintiendo
por omisión.

**5. "Me lo explicó, así que le di a aceptar."**
La explicación la convence igual cuando la máquina se equivoca. Añadir explicaciones sube
la aceptación acierte o falle. No trates una explicación como garantía de buena decisión.

**6. "Si ya me lo escribió, ¿para qué lo leo entero?"**
Si ve el resultado antes de pensar, ya no piensa. En cualquier flujo donde una IA produce
y un humano aprueba, el juicio del humano va PRIMERO, sobre los puntos que solo él puede
juzgar, y después aparece el resultado.

**7. "Yo aquí solo firmo."**
Pedirle que revise todo la agota y no aporta. Que revise solo lo que únicamente ella puede
juzgar; lo demás, que el sistema lo resuelva o lo declare.

**8. "Me acuerdo de cuando me salvó y de cómo terminaba."**
El pico y el final son lo que recuerda y lo que le cuenta a una colega. Diseña a propósito
el momento de máximo valor y el cierre. Terminar en "Listo" es desperdiciar el final.

**9. "Lo abro todos los martes al llegar."**
Sin anclaje a una rutina que ya existe, lo deja en dos semanas. El hábito predice la
retención mucho mejor que las funcionalidades nuevas.

**10. "Vi un candadito y supuse que estaba seguro."**
Los sellos tranquilizan y no protegen. La señal legítima es evidencia verificable: dónde
viven los datos, quién accede, qué se procesó localmente. Y si un día se filtra algo, no
vuelve: la confianza se pierde de forma asimétrica.

**11. "Intenté cancelar y no encontré el botón."**
Prohibidos los patrones oscuros, sin excepción: cancelaciones difíciles, casillas
premarcadas a favor de la empresa, urgencia falsa, costos que aparecen al final. Funcionan
una vez y cuestan para siempre — y en la UE ya son ilegales.

**12. "¿Y si esto me mete en un lío?"**
El miedo puede empujarla a comprar o a huir, según su antigüedad y su exposición. Calibra
el mensaje de riesgo por perfil; el miedo sin salida clara paraliza.

**13. "¿Lo usa alguien como yo?"**
Un ahorro concreto y una colega que lo use pesan más que cualquier lista de
características.

**14. "¿Quién responde si algo pasa?"**
En España y Latinoamérica pide más respaldo, más formalidad y una cara detrás. Traducir no
basta: hay que añadir señales de autoridad y reducción de incertidumbre.

**15. "Acepté 40 de 40."**
Que acepte todo no prueba que funcione: prueba que dejó de mirar. La métrica correcta no
es la aceptación bruta sino si detectó los que estaban mal. Si más del 90% de las salidas
se aprueban sin una sola edición, hay sobredependencia y el producto la está exponiendo.

**16. "No quiero que me devuelvan el reporte."**
Evitar un problema concreto la mueve más que ganar tiempo en abstracto. El copy nombra la
pérdida que se evita, no el beneficio genérico.

**17. "Si esto sale mal, la culpa es mía."**
Ella firma. El sistema tiene que protegerla: registro de qué revisó, cuándo y qué cambió,
exportable. No dejes que el humano más cercano cargue solo con el fallo del sistema
completo.

**18. "Son demasiadas cosas a la vez."**
Menos decisiones simultáneas en el flujo crítico, revelación progresiva para lo avanzado, y
fricción deliberada SOLO donde equivocarse cuesta caro.

**19. "Yo esto ya lo sé hacer." / "Yo de esto no sé nada."**
La novata acepta de más; la veterana ignora la herramienta. No es la misma pantalla para
las dos.

**20. "El de ventas dijo que el rojo vende más."**
Solo cuenta lo que aguanta la prueba. Ninguna decisión de diseño se justifica con
psicología popular.

## Mitos derribados — no usarlos como fundamento

- **"Bonito es usable."** El efecto casi desaparece al controlar la fluidez de
  procesamiento. Persigue claridad, no ornamento.
- **"Los nudges de framing son potentes."** Tras corregir el sesgo de publicación el efecto
  agregado se desploma. Solo sobreviven los defaults.
- **"Menos opciones siempre convierten mejor."** El efecto medio de la sobrecarga de
  elección es cercano a cero salvo bajo condiciones concretas.
- **"La fuerza de voluntad se agota" y "el priming social funciona."** No replican.
- **"Un sello de confianza da seguridad."** Los usuarios los malinterpretan y sobreconfían.
- **"A la gente no le importa la privacidad."** La llamada paradoja de la privacidad es
  mucho más débil de lo que se decía.
- **"Poner un humano a supervisar la IA siempre mejora el resultado."** En promedio
  EMPEORA las decisiones. El punto de supervisión se diseña, no se asume.
- **"Mostrar la explicación de la IA genera buena confianza."** Sube la aceptación acierte
  o falle.

## La tensión aceptada

Obligar a la usuaria a emitir su juicio ANTES de ver el resultado de la IA mejora sus
decisiones y a ella le gusta menos. Está medido. Es una decisión de producto que se toma a
propósito, no un descuido de experiencia de usuario. Si un cambio la elimina "porque
molesta", eso se discute explícitamente con Simón, no se resuelve en silencio.

## Reglas del portafolio que ya son doctrina

- **Prohibido el verde falso.** Ninguna salida de un motor de verificación puede pintarse
  de verde. El verde solo es honesto cuando el dato lo declaró un humano. Un sistema que
  verifica presencia no puede afirmar suficiencia. Aplica a todos los productos, no solo a
  ARIA.
- **Lo no examinado se muestra con el mismo peso visual que lo examinado.** Si una
  categoría, regla o comprobación no corrió, se declara igual de visible que las que sí
  corrieron. Un reporte que solo enumera lo que hizo es un reporte engañoso.
- **El recibo es el entregable.** En productos de cumplimiento o limpieza de datos, lo que
  la usuaria puede enseñarle a un tercero vale más que el archivo procesado.
- **El certificado nunca contiene el dato.** Un reporte que prueba que se redactó algo no
  puede incluir lo redactado.
- **Idioma:** cada producto conserva su regla. Lo clínico y lo que va al pagador nace en
  inglés; el español es capa relacional y de alcance. No cambiar el idioma de un producto
  sin orden explícita.

## Checklist antes de cerrar una pantalla

1. ¿Se entiende sin esfuerzo en los primeros segundos, o hace falta leerla dos veces?
2. ¿Qué viene marcado por defecto, y es la opción conservadora?
3. ¿La pantalla dice qué NO revisó, o solo lo que hizo?
4. Si hay una IA produciendo, ¿el humano emite su juicio antes de ver el resultado?
5. ¿Cómo termina el flujo? ¿El cierre es memorable o es un "Listo"?
6. ¿Queda registro de qué revisó la persona que firma?
7. ¿Hay algún patrón oscuro, aunque sea leve?
8. ¿El copy nombra una pérdida concreta o vende un beneficio abstracto?
9. ¿Cuántas decisiones simultáneas le estoy pidiendo?
10. ¿Un error del usuario se trata como culpa suya o como algo que el sistema puede
    resolver por él?

Si un mensaje de error le dice a la usuaria lo que hizo mal sin decirle exactamente qué
hacer ahora, el punto 10 está fallando y hay que arreglarlo antes de cerrar.
