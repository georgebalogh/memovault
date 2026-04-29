# MemoVault — Struktúra & Bővítési Útmutató

## Fájlstruktúra

```
C:\Work\Memo\
├── index.html              ← Főoldal (sidebar + iframe)
├── memos\
│   ├── gpu-optimization.html   ← Gaming: GPU Max
│   └── [új-memo].html          ← Ide kerülnek az új memo-k
└── README.md
```

## Új memo hozzáadása — 2 lépés

### 1. Hozd létre a memo HTML fájlt

Másold le az egyik meglévő memo fájlt (`memos\gpu-optimization.html`),
módosítsd a tartalmat, mentsd el `memos\[egyedi-id].html` névvel.

### 2. Regisztráld az index.html-ben

Az `index.html`-ben keresd meg a `MEMOS` tömböt (~30. sor),
és adj hozzá egy új bejegyzést:

```javascript
const MEMOS = [
  {
    id: "gpu-optimization",
    title: "GPU Teljesítmény Optimalizálás",
    category: "Gaming",
    categoryIcon: "🎮",
    file: "memos/gpu-optimization.html",
    tags: ["nvidia", "windows", "performance"]
  },
  // ── ÚJ MEMO ──
  {
    id: "egyedi-azonosito",        // pl. "docker-setup"
    title: "Memo Neve",            // pl. "Docker Dev Setup"
    category: "Kategória Neve",    // pl. "Dev / Code"
    categoryIcon: "💻",            // emoji
    file: "memos/egyedi-id.html",  // fájl elérési út
    tags: ["kulcsszó1", "kulcsszó2"]
  }
];
```

A kategória automatikusan megjelenik a sidebarban accordion-ként, ha új nevet adsz.

## Lokális megnyitás

FONTOS: az iframe-es betöltés miatt file:// protokollon nem működik.
Lokális teszteléshez futtasd a mappában:

  npx serve .
  -- vagy --
  python -m http.server 8080

Majd: http://localhost:8080

## Tárhely kirakás (saját domain)

Az egész mappa statikus — FTP-vel vagy hosting panel file managerével tölthető fel.

Ajánlott hosting opciók:
- GitHub Pages (ingyenes, privát repo-hoz Pro kell)
- Netlify / Vercel (ingyenes, drag-and-drop deploy)
- Saját tárhely — FTP upload, semmi szerver-oldali config nem kell

## Kategória ikonok (javaslatok)

| Kategória     | Icon |
|---------------|------|
| Gaming        | 🎮   |
| Dev / Code    | 💻   |
| Szoftver      | 🛠️   |
| Hálózat       | 🌐   |
| AI / Tools    | 🤖   |
| Vegyes        | 📋   |
