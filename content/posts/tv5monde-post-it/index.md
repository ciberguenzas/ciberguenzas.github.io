---
title: "TV5Monde: hackeados por la noche, contraseñas en el telediario a la hora de comer"
date: 2026-10-31
description: "En 2015 un ataque deja a negro una televisión internacional. Al día siguiente, el reportaje sobre el ataque emite las contraseñas de la cadena escritas en post-its. Nivel 5."
tags: ["Contraseñas", "Post-it", "TV5Monde", "APT28", "OPSEC", "Gestión de credenciales"]
categorias: ["Clásicos"]
toc: true
draft: false
---

El miércoles 8 de abril de 2015, a las 20:40, TV5Monde, la televisión pública internacional francesa, se quedó a negro. Sus doce canales (once, según otras fuentes; cuando te hackean ni eso queda claro) dejaron de emitir, su web y sus cuentas de Twitter y Facebook aparecieron empapeladas con propaganda de un supuesto "CyberCaliphate", y los sistemas que controlaban la emisión se iban corrompiendo minuto a minuto. El primer canal volvió a las 05:25 de la madrugada; el resto, a lo largo de la mañana. La investigación acabó atribuyendo el ataque a APT28, el grupo que se suele asociar con la inteligencia militar rusa (Rusia lo niega), y la pista yihadista resultó ser una cortina de humo.

Hasta aquí, una desgracia. La cibergüenza viene después.

## El caso

Al día siguiente, el informativo de las 13:00 de France 2 (*13 Heures*) entrevista a David Delos, periodista de TV5Monde, para contar la catástrofe. Plano medio en la redacción. Detrás de él, una mesa empapelada de post-its y fichas pegadas con celo con los usuarios y contraseñas de las cuentas de la cadena en Twitter, Instagram y YouTube. Las dos primeras no se leían bien en el vídeo. La de YouTube, sí: `lemotdepassedeyoutube`. "Lacontraseñadeyoutube", en francés. Emitida en abierto, en el telediario, dentro del reportaje sobre cómo les habían hackeado.

Internet hizo lo que hace internet: capturas, zooms, memes. Y en otro reportaje de otra cadena apareció otro post-it, este con el usuario y la contraseña genéricos de un empleado. TV5Monde reconoció la "metedura de pata" y explicó que, con los sistemas caídos, las credenciales se estaban repartiendo a mano, en papel. Lo cual, bien pensado, lo explica todo y no arregla nada.

{{< verguenzometro 5 >}}

## Qué pasó de verdad

Importante, porque aquí está la trampa de esta historia: **los post-its no fueron la causa del ataque**. Los atacantes llevaban dentro de la red desde el 23 de enero: dos meses y medio haciendo reconocimiento con calma para entender cómo emitía la cadena, y fabricando malware a medida para destruir el hardware que controlaba la emisión (los codificadores que transmiten los programas). Entraron por siete puntos distintos, y uno de ellos ni siquiera era TV5Monde: un proveedor holandés de las cámaras robotizadas del estudio. Ninguna contraseña de YouTube te lleva a eso.

Lo que les salvó fue un técnico que localizó la máquina desde la que se lanzaba el ataque y la desconectó de internet. Estaba en la oficina a esas horas porque ese mismo día habían estrenado un canal nuevo. Según Yves Bigot, director general de la cadena, con un par de horas más los distribuidores por satélite habrían cancelado los contratos y la empresa habría desaparecido.

Entonces, ¿por qué es una cibergüenza de nivel 5 si no causó la brecha? Porque enseña la cultura de seguridad de la organización mejor que cualquier auditoría. Si las credenciales de redes sociales están en la mesa a la vista, ¿dónde están las del CMS? ¿Y las de los codificadores? Que el fondo de plano de la recuperación fuera un post-it no es casualidad: es síntoma. La factura, según el propio Bigot: cinco millones de euros el primer año y más de tres millones cada año desde entonces en protección. Y meses sin internet en la redacción, enviando faxes.

## La lección

1. **Si una credencial cabe en un post-it, cabe en un gestor de contraseñas.** Las cuentas compartidas (redes sociales, el usuario genérico del CMS, el buzón de `marketing@`) son las primeras que acaban en papel, porque hay que pasárselas a varias personas y nadie quiere montar nada. Un gestor con bóvedas compartidas resuelve exactamente ese problema, rota la contraseña cuando alguien se va y, cuando los sistemas se caen, sigue funcionando desde el móvil. El post-it también, pero sale en la tele.

2. **MFA en todo lo que tenga cara pública.** La cuenta de YouTube, Twitter o Instagram de una televisión es un altavoz nacional. Con un segundo factor, la contraseña de la mesa sigue siendo una vergüenza, pero deja de ser un incidente.

3. **El fondo del plano es superficie de ataque.** Cámaras, visitas, videollamadas, la foto para LinkedIn: pizarras, monitores y mesas salen en la imagen. "Mesa limpia" no es burocracia, es OPSEC básica. Y TV5Monde no fue la única: en enero de 2018, tras la falsa alerta de misil en Hawái, alguien se fijó en una foto de AP de julio de 2017 del centro de emergencias del estado. Un post-it con una contraseña pegado al monitor. La agencia admitió que era real. Habrá post.

4. **La lección gorda no sale en el post-it.** Lo que de verdad tumbó a TV5Monde fue una red donde desde la ofimática se llegaba a los codificadores de emisión, un proveedor de cámaras convertido en puerta de entrada y dos meses y medio de intrusión sin que nadie la viera. Segmentar la producción de la IT corporativa, vigilar lo que conectan los proveedores y tener capacidad de detección es lo que separa "nos han pintado la web" de "nos han dejado a negro". Y tener a alguien capaz de tirar del cable a tiempo: aquella noche, la diferencia entre "a negro" y "ya no existimos" fue un técnico desenchufando una máquina.

## Qué habría costado evitarlo

- Gestor de contraseñas para toda la redacción: unos pocos euros por persona al mes.
- Activar MFA en las cuentas de redes: cero euros, una tarde.
- Mirar el fondo antes de rodar: cero euros, cinco segundos.

Lo de los post-its no costó dinero, solo vergüenza; lo que costó cinco millones fue lo otro. Pero las dos cosas salen de la misma cultura, y arreglar la primera es la parte barata.

## Referencias

- Gordon Corera, BBC News, *How France's TV5 was almost destroyed by 'Russian hackers'* (10 de octubre de 2016): <https://www.bbc.com/news/technology-37590375>. Cronología, canales, puntos de entrada, atribución y coste, en palabras del director general.
- Sam Machkovech, Ars Technica, *Hacked French network exposed its own passwords during TV interview* (10 de abril de 2015): <https://arstechnica.com/information-technology/2015/04/hacked-french-network-exposed-its-own-passwords-during-tv-interview/>. El reportaje de *13 Heures*, David Delos y `lemotdepassedeyoutube`.
- Quartz (enero de 2018), sobre la foto de AP con la contraseña en el centro de emergencias de Hawái: <https://qz.com/1181763/hawaiis-emergency-management-agency-accidentally-revealed-an-internal-password>
