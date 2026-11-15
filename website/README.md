# MOOS Agency — statická prezentace

Čistý statický web ve 4 HTML5 dokumentech a modulárním CSS3 bez JavaScriptu a bez externích frameworků.

## Struktura projektu

```text
website/
├── index.html          # Úvodní stránka
├── o-nas.html          # O agentuře a představení týmu
├── nase-prace.html     # Portfolio akcí, archiv událostí, ilustrační galerie a CSS lightbox
├── kontakt.html        # Kontaktní údaje a průvodce poptávkou
├── css/
│   ├── style.css       # Design tokeny (:root), @font-face, reset, typografie, animace
│   ├── components.css  # Hlavička, navigace, mobilní menu, tlačítka, karty, lightbox, patička
│   ├── pages.css       # Specifické rozvržení jednotlivých stránek
│   └── responsive.css  # Responzivní breakpointy, prefers-reduced-motion a print styly
├── assets/
│   ├── fonts/          # Self-hosted písmo Manrope (WOFF2 + WOFF) + licence OFL.txt
│   ├── icons/          # Značka nekonečna (infinity.svg)
│   ├── images/         # Optimalizované responzivní fotografie (WebP + JPEG)
│   └── logos/          # Transparentní logo MOOS Agency (WebP + PNG) a SVG favicon
├── robots.txt
├── sitemap.xml
└── README.md
```

## Technická řešení

- **100 % statický web bez JavaScriptu**: mobilní navigace využívá nativní HTML5 prvek `<details>`, zvětšené náhledy fotografií v portfoliu využívají čistě CSS `:target` lightbox (`#lightbox-*`).
- **Typografie a ikony**: písmo Manrope (řezy 400 a 800) ve formátu WOFF2 se záložním WOFF; veškeré směrové a funkční ikony jsou řešeny jako inline SVG (nezávislé na podpoře systémových Unicode znaků).
- **Přístupnost a pohyb**: splněný kontrast dle WCAG AA, viditelné stavy `:focus-visible`, odkaz pro přeskočení na obsah, podpora `prefers-reduced-motion` i plynulé zobrazení bez podpory scroll-driven animací.

## Nasazení a další úpravy

1. Nahrajte obsah složky `website/` (případně dodaný archiv `moos-agency-website.zip`, kde je `index.html` přímo v kořeni) na statický webhosting nebo do Netlify Drop.
2. Po připojení vlastní domény doplňte absolutní URL do `sitemap.xml`, odkaz `Sitemap:` do `robots.txt` a případně `<link rel="canonical">` do hlaviček HTML stránek.
3. Pokud budete chtít v budoucnu doplnit reálné portréty členů týmu do `o-nas.html`, vložte je do `assets/images/` a použijte prvek `<picture>` se zachováním rámce `.media-frame`.
