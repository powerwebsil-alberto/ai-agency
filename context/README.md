# context/ — Documentos de referencia

Aquí van los documentos **estables** que Claude (y cualquier persona nueva) debe
poder leer para entender el proyecto sin preguntar.

## Qué va aquí
- Briefs y descripciones de clientes o del producto
- Investigación: competencia, mercado, herramientas evaluadas
- Especificaciones y requisitos
- Material de marca: tono, posicionamiento, propuesta de valor
- Resúmenes de documentos externos largos (el PDF va fuera; el resumen, aquí)

## Qué NO va aquí
- Apuntes en crudo de una conversación → van a `notas/`
- Una decisión tomada y su razonamiento → va a `decisiones/`
- Credenciales, claves, datos personales de clientes → **nunca en el repo**
- Binarios pesados (vídeos, datasets, PDFs grandes) → súbelos a Drive y enlázalos aquí

## Formato
Un archivo `.md` por tema. Nombre en minúsculas con guiones:

```
investigacion-competencia.md
brief-cliente-acme.md
herramientas-evaluadas.md
```

Empieza cada documento con un encabezado y la fecha de última actualización:

```markdown
# Investigación de competencia

_Última actualización: 2026-09-29_
```

## Regla de mantenimiento
Un documento de `context/` que ya no es cierto es peor que no tenerlo: Claude lo va
a leer y actuar en consecuencia. Si algo deja de ser válido, **actualízalo o bórralo**.
