# Site de la chorale — Mariage de Solina & Médéric

Site web (une seule page) pour que les choristes révisent partitions et enregistrements.
Messe du **17 octobre 2026**, église Saint-Pierre-et-Saint-Paul, Le Neubourg.

Même outil que le site de la chorale de Loïc & Lola, en **bleu marine**.

## Contenu du dossier

```
Site chorale/
├── index.html      ← la page (design + code)
├── Partitions/     ← les partitions PDF (une par chant)
├── Audio/          ← les enregistrements MP3
└── README.md
```

> ⚠️ Les dossiers s'appellent **Partitions** et **Audio** (avec majuscule). GitHub
> Pages est sensible à la casse : garde exactement cette orthographe dans `index.html`.

## Ordre des chants (déduit du livret de messe)

| # | Moment | Chant | Base du nom de fichier |
|---|--------|-------|------------------------|
| 1 | Procession d'entrée | L'Angélique (violoncelle & violon) | `01-l-angelique` |
| 2 | Chant d'entrée | Céleste Jérusalem | `02-celeste-jerusalem` |
| 3 | Gloria | Messe de saint Claude de la Colombière | `03-gloria` |
| 4 | Psaume 138 | Seigneur, tu connais si bien mon âme | `04-psaume` ✅ PDF |
| 5 | Alléluia | Taizé | `05-alleluia` |
| 6 | Invocation de l'Esprit Saint | Viens, Esprit très Saint (Ad Dei Gloriam) | `06-viens-esprit-saint` ✅ PDF |
| 7 | Action de grâce | Nouveau Laudate Dominum (Médéric & Solina) | `07-nouveau-laudate-dominum` |
| 8 | Action de grâce | Laudate Dominum | `08-laudate-dominum` |
| 9 | Prière universelle | O Marie, prends nos prières | `09-o-marie` |
| 10 | Offertoire | Hostia Sancta | `10-hostia-sancta` |
| 11 | Sanctus | | `11-sanctus` |
| 12 | Anamnèse | | `12-anamnese` |
| 13 | Notre Père (chanté) | Glorious | `13-notre-pere` |
| 14 | Agnus Dei | Saint Augustin | `14-agnus-dei` |
| 15 | Communion | En Esprit et en Vérité | `15-en-esprit-et-en-verite` |
| 16 | Communion | En toi ma confiance | `16-en-toi-ma-confiance` |
| 17 | Action de grâce | Anima Christi | `17-anima-christi` |
| 18 | Consécration à la Vierge | Ave Maria (Caccini) | `18-ave-maria` |
| 19 | Chant d'envoi | Je veux voir Dieu | `19-je-veux-voir-dieu` |

## Ajouter une partition

1. Dépose le PDF dans `Partitions/` (nom conseillé : la base ci-dessus + `.pdf`,
   ex. `03-gloria.pdf`).
2. Dans `index.html`, sur la ligne du chant, renseigne `sheetMusic` :
   `sheetMusic: "Partitions/03-gloria.pdf",`

## Ajouter les enregistrements

1. Dépose les MP3 dans `Audio/` (ex. `03-gloria-soprano.mp3`, `…-alto`, `…-tenor`,
   `…-basse`, `…-tous`).
2. Dans `index.html`, renseigne le bloc `audio` du chant :
   ```js
   audio: {
     soprano: "Audio/03-gloria-soprano.mp3",
     alto:    "Audio/03-gloria-alto.mp3",
     tenor:   "Audio/03-gloria-tenor.mp3",
     basse:   "Audio/03-gloria-basse.mp3",
     tous:    "Audio/03-gloria-tous.mp3"
   },
   ```
   Laisse `""` pour ce qui manque encore : le bouton reste simplement grisé.

`<voix>` = `soprano`, `alto`, `tenor`, `basse` ou `tous`.

## Mettre à jour le site en ligne

Depuis Git Bash dans ce dossier :

```bash
git add -A && git commit -m "Mise à jour" && git push
```

Le site se met à jour tout seul en ~1 minute.
