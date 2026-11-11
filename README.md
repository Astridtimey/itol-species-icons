# itol-species-icons

Line-art species icons used to annotate a plant–animal phylogenetic tree in [iTOL](https://itol.embl.de/) (Interactive Tree of Life).

## Purpose

iTOL can only display images that are reachable through a public URL.
This repository hosts one icon per species so the tree can show a picture next to each tip,
via an iTOL `DATASET_IMAGE` annotation file.

## Icon format

- PNG, **256 × 256 px**, transparent background
- Black line-art style, consistent across all species
- Empty margins trimmed and the drawing centred, so every icon displays at the same size in iTOL
- File name = tree leaf ID (e.g. `Zea_mays.png`)

## Species

| File | Species | Common name |
|---|---|---|
| `Gallus_gallus.png` | *Gallus gallus* | chicken |
| `Mus_musculus.png` | *Mus musculus* | house mouse |
| `Macaca_mulatta.png` | *Macaca mulatta* | rhesus macaque |
| `Homo_sapiens.png` | *Homo sapiens* | human |
| `Phalaenopsis_aphrodite.png` | *Phalaenopsis aphrodite* subsp. *formosana* | moth orchid |
| `Zea_mays.png` | *Zea mays* | maize |
| `Oryza_sativa.png` | *Oryza sativa* | rice |
| `Triticum_aestivum.png` | *Triticum aestivum* | bread wheat |
| `Hordeum_vulgare.png` | *Hordeum vulgare* | barley |
| `Arabidopsis_thaliana.png` | *Arabidopsis thaliana* | thale cress |
| `Cucumis_sativus.png` | *Cucumis sativus* | cucumber |
| `Glycine_max.png` | *Glycine max* | soybean |
| `Lactuca_sativa.png` | *Lactuca sativa* | lettuce |
| `Solanum_tuberosum.png` | *Solanum tuberosum* | potato |
| `Solanum_lycopersicum.png` | *Solanum lycopersicum* | tomato |

## Using the icons in iTOL

Raw image URL pattern:

```
https://raw.githubusercontent.com/Astridtimey/itol-species-icons/main/<File>
```

Example line in an iTOL `DATASET_IMAGE` file:

```
#ID,position,size_factor,rotation,horizontal_shift,vertical_shift,image_url
Zea_mays,-1,1,0,0,0,https://raw.githubusercontent.com/Astridtimey/itol-species-icons/main/Zea_mays.png?v=2
```

Notes:
- `ID` must match the **node ID** in the tree file, not the display label edited in iTOL
  (e.g. the orchid's ID is `Phalaenopsis_aphrodite_subsp._formosana`).
- iTOL caches images. After replacing an icon, change the `?v=` suffix (e.g. `?v=3`) so iTOL fetches the new version.

## Source
All drawings were generated with ChatGPT (OpenAI image generation) using text prompts
asking for simple black line-art illustrations in a consistent style.

Post-processing (Python, Pillow): white background removed (made transparent),
empty margins trimmed, drawing centred on a square canvas, and resized to 256 × 256 px.

These are illustrative icons, not scientifically accurate botanical or zoological drawings.
