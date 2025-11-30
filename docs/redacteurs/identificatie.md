---
title: Identificatie
parent: Redacteurs
nav_exclude: true
---

# Identificatie
Conceptversie
{: .label .label-yellow }

Ieder begrip krijgt een betekenisloze, stabiele UUID (versie 4) toegekend. Deze wordt als identificerend kenmerk vastgelegd met [`dct:identifier`](http://purl.org/dc/terms/identifier).

<details closed markdown="block">
  <summary>
    Voorbeeldcode
  </summary>
  {: .text-delta }
  <pre>
  <11358ed2-de31-455e-8f72-f7f0d8adaa29> a skos:Concept ;
      dct:identifier "11358ed2-de31-455e-8f72-f7f0d8adaa29" ;
      skos:prefLabel "aansluiting"@nl .
  </pre>
</details>

{: .note-title }
> TIP
>
> UUID’s kunnen eenvoudig worden gegenereerd met hulpmiddelen in bijvoorbeeld Visual Studio Code of via diverse websites.