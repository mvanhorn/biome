---
"@biomejs/biome": patch
---

Fixed [#10547](https://github.com/biomejs/biome/issues/10547): Biome no longer reports a parse error for a `<!doctype html>` directive that appears after other top-level nodes in an Astro file. Astro layouts place the doctype after the frontmatter and an inline `<script>`, so the following now parses correctly:

```astro
---
const title = "Hello";
---
<script is:inline></script>
<!doctype html>
<html lang="en"></html>
```
