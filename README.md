# coacs — Knowledge Base Simiatug

Base de conocimientos vectorial para el agente de IA de la Cooperativa de Ahorro y Crédito Simiatug Ltda.

---

## Stack técnico

| Componente | Detalle |
|---|---|
| Embeddings | Google `gemini-embedding-001` |
| Dimensiones | 3072 (Cosine similarity) |
| Vector DB | Qdrant |
| Colección | `institucional` |
| LLM respuestas | Gemini 2.0 Flash |
| Orquestación | n8n (webhook → RAG ) |
| Chat | (canal Web Widget) |

---

## Archivo fuente

`knowledge/knowledge-base-simiatug.md`

Cada sección del archivo se convierte en un fragmento vectorizado independiente. Las secciones se delimitan con `---` y deben tener `## Título` como encabezado.

---

## Flujo de actualización

```
Editar .md → push GitHub → ejecutar script en VPS → Qdrant actualizado
```

```bash
# En el VPS
/opt/qdrant/update-knowledge.sh
```

El script:
1. Descarga el `.md` actualizado desde GitHub
2. Elimina y recrea la colección en Qdrant
3. Genera embeddings con Gemini para cada sección
4. Carga los vectores en Qdrant

---

## Archivos en el VPS

```
/opt/qdrant/
├── knowledge/
│   └── knowledge-base-simiatug.md
├── load-knowledge.py         ← genera embeddings y carga en Qdrant
└── update-knowledge.sh       ← script completo de actualización
```

---

## Repositorio

`https://github.com/intiinside/coacs.git`

---

## Cliente

**Cooperativa de Ahorro y Crédito Simiatug Ltda.**
Simiátug, Provincia de Bolívar, Ecuador

---

## Elaborado por

**INTIINSIDE TECH**
Soluciones tecnológicas e inteligencia artificial

| | |
|---|---|
| 🌐 Web | [intiinside.com](https://intiinside.com) |
| 📧 Email | info@intiinside.com |
| 📱 WhatsApp | +593 985 095 122 |
| 👤 Responsable | Inti Poaquiza Azogue |
| 📍 Dirección | Simiátug, Ecuador |

---

*© 2026 INTIINSIDE TECH — Todos los derechos reservados*