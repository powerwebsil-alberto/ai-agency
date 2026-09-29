# decisiones/ — Una decisión por archivo

El historial de **por qué** el proyecto es como es. Sirve para no rediscutir lo mismo
cada dos semanas y para que quien llegue después entienda el razonamiento, no solo
el resultado.

## Cuándo escribir una decisión
Cuando se cierra algo que sería costoso cambiar más adelante:
- Qué construimos y qué no
- Elección de stack, herramienta o proveedor
- Cómo nos repartimos el trabajo
- Modelo de negocio o de precios
- Descartar una línea de trabajo (esto también es una decisión, y de las más útiles)

No hace falta para cosas triviales o fácilmente reversibles.

## Nombre de archivo

```
AAAA-MM-DD-descripcion-corta.md
```

Ejemplos:
```
2026-09-29-usar-git-como-espacio-compartido.md
2026-10-05-stack-tecnico.md
```

La fecha delante hace que el orden alfabético sea el orden cronológico.

## Plantilla

```markdown
# [Título de la decisión]

- **Fecha:** 2026-09-29
- **Decidido por:** [nombres]
- **Estado:** Vigente | Superseded por [archivo]

## Contexto
Qué situación nos obligó a decidir algo. Qué sabíamos en ese momento.

## Opciones consideradas
1. **Opción A** — a favor / en contra
2. **Opción B** — a favor / en contra

## Decisión
Qué elegimos.

## Razonamiento
Por qué. Esta es la parte que importa dentro de seis meses.

## Consecuencias
Qué implica: qué nos obliga a hacer, qué nos cierra, qué revisamos más adelante.
```

## Regla importante
Una decisión que deja de valer **no se borra ni se reescribe**. Se crea una decisión
nueva, y en la antigua se cambia el estado a `Superseded por [archivo-nuevo]`.
El historial de ideas descartadas es parte del valor de esta carpeta.
