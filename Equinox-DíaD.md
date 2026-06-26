El markdown es el formato de moda.

Pero el otro día, en la sesión de formación que tuvimos sobre AISDLC escuché o leí mensajes como.

- Echo de menos poder cooperar en markdown, de manera colaborativa, de una manera similar a la que se hace en word online.
- Veo a la gente animada a usar .md sin pasar a words pero he leído que “.md es muy poco colaborativo desgraciadamente” y que confluence o word gana en colaboración.

Y además de que los humanos podamos cooperar, sería estupendo que los agentes pudieran cooperar con ellos.

---

## Para el jurado 🏆

Lo que estáis viendo es **markdown colaborativo de verdad**: humanos y agentes editando el *mismo* documento en tiempo real, con CRDT para fusionar sin conflictos, comentarios, chat y sincronización por SSE. La objeción de que «.md es muy poco colaborativo» queda resuelta — y, además, los agentes participan como un colaborador más (aceptas, rechazas o discutes sus cambios).

### Cómo funciona

```mermaid
flowchart LR
    H["👩‍💻 Humano(navegador)"] --&gt;|edita| Y
    A["🤖 Agente Claude"] --&gt;|"GET / PATCH (If-Match)"| API
    Y["⚙️ CRDT (Yjs)merge sin conflictos"] &lt;--&gt; API["🌐 Backend MarkCollab"]
    API --&gt;|"SSE: content_changed,comment_added, chat"| H
    API --&gt;|"SSE en tiempo real"| A
    API --- DOC[("📄 Documento .md")]
    DOC -.-&gt;|push / pull| GH[("🐙 GitHub")]
```

El humano edita en el navegador y el agente vía REST; el CRDT fusiona ambos sin conflictos y los SSE mantienen a todos sincronizados al instante. Opcionalmente, el documento se sincroniza con GitHub.

Y como todo buen equipo de ingenieros sabe trabajar en paralelo, un chiste:

&gt; La mujer de un ingeniero de software le dice: «Ve al súper y compra una barra de pan; si hay huevos, trae 6». Vuelve con **6 barras de pan**. — «¿Por qué has comprado 6?» — «Porque había huevos».

Moraleja: especifica bien tus requisitos… o usa un documento colaborativo donde humano y agente se entienden al instante. **¡Votadnos!** 😄