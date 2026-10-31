# Cibergüenzas

El muro de la vergüenza de la ciberseguridad: fallos reales, ridículos y evitables, con la lección detrás.

Hugo (extended) + tema [hello-friend-ng](https://github.com/rhazdon/hugo-theme-hello-friend-ng) como submódulo + GitHub Pages.

## Clonar

```bash
git clone --recurse-submodules <url-del-repo>
```

## Trabajar en local

```bash
hugo server -D
```

Sirve en `http://localhost:1313/` con los borradores incluidos.

## Nuevo post

```bash
hugo new posts/nombre-del-caso/index.md
```

Usa la plantilla de `archetypes/posts.md`: front matter (`title`, `date`, `description`, `tags`, `categorias`, `toc`, `draft`), el vergüenzómetro y las secciones fijas:

1. **El caso**: qué se vio.
2. **Qué pasó de verdad**: la causa real, sin mitos.
3. **La lección**: qué falló de fondo y qué revisar mañana.
4. **Qué habría costado evitarlo**.
5. **Referencias**: si no hay fuente, no hay post.

El post es una carpeta (page bundle): las imágenes van dentro y se referencian por nombre.

### Vergüenzómetro

```
{{< verguenzometro 4 >}}
```

| Nivel | Significado |
|:-----:|-------------|
| 1 | Un despiste. Le pasa a cualquiera. |
| 2 | Mal, pero se entiende. |
| 3 | Vergüenza ajena. Alguien debió avisar. |
| 4 | Tierra, trágame. |
| 5 | Cibergüenza histórica. Sale en los libros. |

## Despliegue

Push a `main` → [.github/workflows/hugo.yml](.github/workflows/hugo.yml) construye y publica en GitHub Pages. En el repo: Settings → Pages → Source: **GitHub Actions**. El workflow fija el `baseURL` automáticamente según dónde se publique (sitio de usuario o de proyecto).
