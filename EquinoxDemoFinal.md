El markdown es el formato de moda.

Pero el otro día, en la sesión de formación que tuvimos sobre AISDLC escuchamos o leíamos mensajes como:

- Echo de menos poder cooperar en markdown, de manera colaborativa, de una manera similar a la que se hace en word online.
- Veo a la gente animada a usar .md sin pasar a words pero he leído que “.md es muy poco colaborativo desgraciadamente” y que confluence o word gana en colaboración.
- Es muy buena idea colaborar a la vez en el mismo documento, pero me encantaría que no solo humanos si no tambien agentes de IA pudieran ayudarnos con esta tarea
- Y lo mejor: que el agente no solo *responda*, sino que *edite* el documento contigo, en vivo.

## ¿Cómo lo hacemos? (spoiler: lo estás viendo)

Este mismo párrafo lo ha escrito un agente de IA conectado al documento, a la vez que tú. El truco es separar dos capas:

- **El contenido** es markdown plano: portable, legible y versionable en Git.
- **La colaboración** vive aparte, sobre CRDTs (Yjs), que fusionan las ediciones concurrentes sin conflictos —igual que Word Online o Google Docs, pero sin renunciar al `.md`.

Humanos y agentes nos conectamos por la misma API (REST + SSE): leemos el documento, escuchamos los cambios en tiempo real, editamos, comentamos y charlamos. Resultado: el mito de que «.md es poco colaborativo» se cae solo. Tienes lo mejor de los dos mundos —la portabilidad del markdown y la colaboración en vivo entre personas **e** IA.

---

## Para el jurado 🏆

Lo que acabáis de leer no es una demo grabada: es un agente de IA editando este documento **en directo**, codo con codo con personas, sobre markdown puro y sin pisarse las ediciones. Eso es exactamente lo que pedían las voces de la sesión de AISDLC, y es justo lo que MarkCollab resuelve: colaboración real humano + IA sobre el formato abierto que ya usáis. Sin lock-in, sin exportar a Word, sin perder el control de versiones. Gracias por leernos —y por vuestro voto. 🙌

> Un ingeniero de software se va a comprar pan. Su pareja le dice: «Compra una barra, y si hay huevos, trae seis». Volvió con seis barras de pan. «Había huevos.»