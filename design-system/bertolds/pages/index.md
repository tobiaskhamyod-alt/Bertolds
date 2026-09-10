# index.html - Overrides zum MASTER

> Diese Datei überschreibt `../MASTER.md` für die Startseite.
> Grund: Der Suchlauf liefert eine generische Luxus-Vorlage. Marke, Fotos und
> Auftrag des Kunden gehen vor.

## Was aus MASTER.md nicht übernommen wird

| MASTER sagt | Hier stattdessen | Warum |
|---|---|---|
| Style "Liquid Glass" | Editorial Grid, Bogenrahmen aus dem Regal hinter der Bar | Glassmorphism ist im Briefing ausgeschlossen, und Apples Material passt nicht zu einem Café in der Bertoldstraße |
| Typo Cormorant + Montserrat | Archivo (variabel, Breite 75-125) + Karla | Cormorant war die Schrift der alten Seite. Der Leuchtschriftzug im Laden ist eine breit laufende Grotesk, Archivo bildet das ab |
| Akzent `#A16207` | `#B48515` | Exakt aus `assets/logo/original_logo.png` gemessen, nicht geschätzt |
| Hintergrund `#FAFAF9`, Primär `#1C1917` | Papier `#FBF8F3`, Tinte `#12262F` | Warme Fläche laut Briefing, Tinte aus den petrolfarbenen Samtbänken im Raum |
| Google-Fonts-Import per URL | woff2 in `assets/fonts/`, `font-display: swap` | DSGVO, kein CDN |
| Karten mit Schatten und 12px Radius | Flächen kantig (3px), Fotos im Hochformat mit Bogen, Buttons als Pille | Schattenkarten sind der Vorlagenlook, den die Seite gerade loswerden soll |
| Motion-Snippet mit GSAP | IntersectionObserver plus CSS-Übergänge | Kein CDN, kein Build, GSAP wäre 70 KB für vier Effekte |

Übernommen wurde das Muster **Scroll-Triggered Storytelling**: Die Seite läuft als
Tageslauf von 08:00 bis 02:00, mit Zeitmarken als Kapitelköpfen.

## Tokens

```
--paper #FBF8F3   Grundfläche, warm und hell
--oat   #EFE7DA   zweite Fläche (Über uns, Footer)
--ink   #12262F   Text, aus den Samtbänken abgeleitet
--ink-60 #4B6470  Nebentext, 5.9:1 auf Papier
--gold  #B48515   Linie, Kontur, Zeitmarke. Nie als Fläche
--gold-ink #7A5A0E Gold als Textfarbe auf hell, 6.0:1
--night #0E2027   der eine dunkle Block (ab 17 Uhr)
--gold-light #D9AE3C Gold auf dunkel
```

Kaiserstuhl-Chrome (`#0f1628`, `#C9A84C`) steht ausschließlich im Demo-Badge und
in der Footer-Credit-Zeile.

## Dials

`DESIGN_VARIANCE 7` · `MOTION_INTENSITY 6` · `VISUAL_DENSITY 3`

## Regeln, die beim Weiterbauen gelten

- Ein Akzent. Gold bleibt Linie und Kontur, keine gefüllten goldenen Flächen.
- Ein Themenwechsel pro Seite: hell, ein dunkler Block ab 17 Uhr, danach wieder hell.
- Radien: Hochformat bekommt den Bogen (`--arch`), Flächen 3px, interaktive Elemente Pille.
- Kein Layout-Muster zweimal. Aktuell: Foto-Hero, Zeitkapitel mit Bild rechts,
  dunkler Block mit versetztem Bildpaar, Zeitentabelle, Kontaktbogen quer,
  Bild-Text-Block, Adressblock mit Linkliste.
- Bewegung nur, wo sie etwas erklärt. Keine Endlosschleifen.
- Jeder sichtbare Satz läuft vorher durch `stop-slop`.
