# Grimório de Drinks

Catálogo pessoal de drinks clássicos e descobertas modernas, com versões de cada fonte lado a lado.

## Estrutura

```
grimorio/
  data/
    drinks.json   ← fonte da verdade (17 drinks, 61 versões)
  index.html      ← interface
  README.md
```

## Rodar localmente

```bash
npx serve .
```

Abrir `http://localhost:3000`. O `fetch("data/drinks.json")` não funciona via `file://` — sempre use um servidor local ou o preview do Vercel.

## Adicionar um drink

O arquivo `data/drinks.json` segue este formato:

```json
{
  "id": "slug-do-drink",
  "n": "Nome do Drink",
  "base": "Gin",
  "m": "Batido",
  "s": "Descrição de uma linha.",
  "versions": [
    {
      "b": "DG",
      "t": "Título da versão",
      "m": "Batido",
      "ingredients": [
        { "q": 45, "u": "ml", "i": "Gin London Dry" },
        { "q": 22.5, "u": "ml", "i": "Suco de limão" }
      ],
      "prep": "Shake → coar em coupe → garnish.",
      "source_url": "https://..."
    }
  ]
}
```

**Chaves de livros** disponíveis: `LAS` · `AoM` · `HW` · `BU` · `CyB` · `DG` (Difford's Guide). Novos livros são adicionados em `books` no JSON.

**Unidades aceitas:** `ml` · `p` (partes) · `oz` · `jig` · `pony` · `med` · `tsp` · `tbsp` · `dash` · `drop` · `gl` · `vl` · `wg` · `j` (suco de fruta) · `un` (unidade) · `qs` (a gosto)

## Deploy (Vercel)

1. Conectar o repo no [vercel.com](https://vercel.com)
2. Framework: **Other** (site estático)
3. Cada push na `main` deploya automaticamente
