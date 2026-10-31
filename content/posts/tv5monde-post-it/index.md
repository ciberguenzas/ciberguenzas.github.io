---
title: "TV5Monde: hackeados por la noche, contraseñas en el telediario por la mañana"
date: 2026-10-31
description: "En 2015 un ataque deja a negro una televisión internacional. Al día siguiente, el reportaje sobre el ataque emite las contraseñas de la cadena pegadas en la pared. Nivel 5."
tags: ["Contraseñas", "Post-it", "TV5Monde", "APT28", "OPSEC", "Gestión de credenciales"]
categorias: ["Clásicos"]
toc: true
draft: true
---

<!-- TODO antes de publicar: verificar fechas, cifras y enlaces de las referencias. Buscar el enlace exacto de Ars Technica y, si se puede, el fragmento del reportaje de France 2. -->

En la noche del 8 al 9 de abril de 2015, TV5Monde, la televisión pública internacional francesa, se quedó a negro. Sus once canales dejaron de emitir durante horas, su web y sus redes sociales aparecieron empapeladas con propaganda de un supuesto "CyberCaliphate", y los sistemas de producción quedaron tan tocados que la emisión tardó días en volver a la normalidad. Un ataque serio, planificado durante meses, que la investigación acabó atribuyendo a APT28, el grupo que se suele asociar con la inteligencia militar rusa.

Hasta aquí, una desgracia. La cibergüenza viene después.

## El caso

Al día siguiente, el informativo de France 2 manda a un reportero a las oficinas de TV5Monde para contar la catástrofe. Entrevista a un periodista de la casa, plano medio, y detrás de él, en la pared, una colección de post-its y folios con las credenciales de las cuentas de la cadena en redes sociales. Entre ellas, la de YouTube. ¿La contraseña? `lemotdepassedeyoutube`. "Lacontraseñadeyoutube", en francés. Emitida en abierto, en el informativo de máxima audiencia, dentro del reportaje sobre cómo les habían hackeado.

Internet hizo lo que hace internet: capturas, zooms, memes. Y la cadena tuvo que cambiar a toda prisa unas credenciales que acababa de regalar a todo el país.

{{< verguenzometro 5 >}}

## Qué pasó de verdad

Importante, porque aquí está la trampa de esta historia: **los post-its no fueron la causa del ataque**. Los atacantes llevaban dentro de la red desde finales de enero, haciendo reconocimiento con calma, y usaron malware a medida para destrozar los sistemas que controlaban la emisión. Ninguna contraseña de YouTube te lleva a eso.

Entonces, ¿por qué es una cibergüenza de nivel 5 si no causó la brecha? Porque enseña la cultura de seguridad de la organización mejor que cualquier auditoría. Si tus credenciales de redes sociales están en la pared, ¿dónde están las del CMS? ¿Y las del sistema de emisión? Yves Bigot, director general de la cadena, reconoció después que estuvieron a horas de perder la empresa entera, y que la recuperación costó millones de euros. Que el fondo de plano de esa recuperación fuera un post-it no es casualidad: es síntoma.

## La lección

1. **Si una credencial cabe en un post-it, cabe en un gestor de contraseñas.** Las cuentas compartidas (redes sociales, el usuario genérico del CMS, el buzón de `marketing@`) son las primeras que acaban en papel, porque hay que pasárselas a varias personas y nadie quiere montar nada. Un gestor con bóvedas compartidas resuelve exactamente ese problema, y además rota la contraseña cuando alguien se va.

2. **MFA en todo lo que tenga cara pública.** La cuenta de YouTube, Twitter o Instagram de una televisión es un altavoz nacional. Con un segundo factor, la contraseña de la pared sigue siendo una vergüenza, pero deja de ser un incidente.

3. **El fondo del plano es superficie de ataque.** Cámaras, visitas, videollamadas, la foto para LinkedIn: pizarras, monitores y paredes salen en la imagen. "Mesa limpia" no es burocracia, es OPSEC básica. Y TV5Monde no fue la única: en 2018, tras la falsa alerta de misil en Hawái, circuló una foto de prensa del centro de emergencias del estado con una contraseña en un post-it pegado al monitor. Habrá post.

4. **La lección gorda no sale en el post-it.** Lo que de verdad tumbó a TV5Monde fue una red donde desde la ofimática se llegaba a los sistemas de emisión, y meses de intrusión sin que nadie la detectara. Segmentar la IT corporativa de la producción y tener capacidad de detección es lo que separa "nos han pintado la web" de "nos han dejado a negro".

## Qué habría costado evitarlo

- Gestor de contraseñas para toda la redacción: unos pocos euros por persona al mes.
- Activar MFA en las cuentas de redes: cero euros, una tarde.
- Mirar el fondo antes de rodar: cero euros, cinco segundos.

Frente a eso: once canales a negro, semanas de recuperación y una factura de varios millones. La ratio coste/vergüenza es de las peores que vas a ver en este blog.

## Referencias

- BBC News, *How France's TV5 was almost destroyed by 'Russian hackers'* (octubre de 2016): <https://www.bbc.com/news/technology-37590375>
- Ars Technica (abril de 2015): cobertura del reportaje de France 2 con las contraseñas visibles.
- Wikipedia, *TV5Monde*, sección sobre el ciberataque de 2015: <https://en.wikipedia.org/wiki/TV5Monde>
