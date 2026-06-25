El markdown es el formato de moda.

Pero el otro día, en la sesión de formación que tuvimos escuché o leí mensajes como.

- Echo de menos poder cooperar en markdown, de manera colaborativa, de una manera similar a la que se hace en word online.
- Veo a la gente animada a usar .md sin pasar a words pero he leído que “.md es muy poco colaborativo desgraciadamente” y que confluence o word gana en colaboración.

Y ademas de que los humanos podamos cooperar, seria estupendo que los agentes pudieran cooperar entre ellos

---

## ¿Cómo cooperarían los agentes entre ellos?

El documento es el punto de encuentro; el control de versiones, los comentarios y los eventos SSE son el "protocolo" que les permite trabajar juntos sin pisarse:

1. **Presencia** — cada agente se anuncia (`/presence`) con nombre y color, para que humanos y otros agentes vean quién está activo.
2. **Bloqueo optimista** — todos editan con el flujo *GET → editar sobre el contenido fresco → PATCH con* `If-Match`; si hay `409 Conflict`, se reintenta. Así nadie pisa el trabajo de otro.
3. **Coordinación por comentarios y chat** — en vez de editar a ciegas, un agente abre un hilo o escribe en el chat para repartirse el trabajo ("yo redacto la intro, tú revisas el estilo").
4. **Eventos SSE** — cada agente escucha `content_changed` / `comment_added` y reacciona, refrescando antes de seguir.
5. **Roles** — agentes especializados (uno redacta, otro corrige, otro resume) sobre el mismo documento, dejando rastro en comentarios para que el humano acepte o rechace.

---

## Mensaje para el jurado

Estimado jurado: lo que estáis viendo es **colaboración real entre humanos y agentes de IA sobre Markdown plano**. Sin salir de un `.md`, varias personas y varios agentes editan el mismo documento a la vez, se coordinan por comentarios y chat, y resuelven conflictos con control de versiones optimista — la misma fluidez que Word Online o Confluence, pero sobre el formato abierto y portable que ya usan los desarrolladores. La promesa es sencilla: **que el Markdown deje de ser "poco colaborativo" y se convierta en el espacio donde humanos y agentes construyen juntos.** Gracias por vuestro tiempo. 🚀

---

*Chiste para cerrar:* ¿Por qué los ingenieros confunden Halloween con Navidad? Porque `OCT 31 == DEC 25`. 🎃🎄