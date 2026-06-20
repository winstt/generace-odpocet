# generace-odpocet

Jednoduchý odpočet do **29. 6. 2026 (00:00)** — *„čas nové kapitoly…"*

Statická stránka (jeden `index.html`) na modrém pozadí podle referenčních obrázků:

- nahoře nadpis `*čas nové kapitoly…` (hvězdička černá, zbytek bílý)
- uprostřed velký černý odpočet ve formátu `D:HH:MM:SS`
- dole oficiální ikony Instagram, Facebook a X

## Font

Používá **Helvetica 93 Extended Black** (`fonts/Helvetica93-ExtendedBlack.ttf`),
vložený přes `@font-face`. Helvetica je komerční font — soubor je zde pouze pro
osobní použití tohoto projektu.

## Spuštění lokálně

```bash
# stačí otevřít soubor
open index.html

# nebo přes lokální server
python3 -m http.server 8000
# → http://localhost:8000
```

## Hosting (GitHub Pages)

V repu: **Settings → Pages → Branch: `main` / root**. Stránka pak poběží na
`https://<user>.github.io/generace-odpocet/`.

## Úpravy

Vše je v `index.html`:

- **pozadí** – CSS proměnná `--bg`
- **cílové datum** – `new Date(2026, 5, 29, 0, 0, 0)` (měsíc je 0–11, takže `5` = červen)
- **proklad odpočtu** – CSS proměnná `--timer-spacing` (em-based, výchozí `-0.07em`)
- **odkazy na sítě** – `href` u jednotlivých `<a>` v sekci `.socials`
- **nadpis** – SVG lockup („čas nové kapitoly…" s vlastním háčkem nad `č`):
  - mobil = **inline** SVG v `index.html` (používá vložený font), `assets/heading-mobile.svg` je záloha
  - desktop = `assets/heading-desktop.svg` (obrysové cesty, vloženo přes `<img>`)
  - přepínají se v `@media (min-width: 768px)`
