---
title: URI-strategie
parent: Redacteurs
nav_exclude: true
---

# URI-strategie
Conceptversie
{: .label .label-yellow }

Met deze URI-strategie borgen we een persistente en webvriendelijke identificatie in lijn met [Linked Data](https://www.w3.org/DesignIssues/LinkedData.html)- en [FAIR-principes](https://www.go-fair.org/fair-principles/), en sluiten we aan bij conventies uit de [Stelselcatalogus](https://www.stelselcatalogus.nl/documenten/linked_data_structuur) en de [PLDN-URI-strategie](https://www.pldn.nl/wiki/Boek/URI-strategie). 

{: .text-delta }
URI-patroon
<dl>
    <dt>Begrippenkader</dt>
    <dd><code>https://begrippen.netbeheernederland.nl</code></dd>
    <dt>Begrip</dt>
    <dd><code>https://begrippen.netbeheernederland.nl/id/{id}</code></dd>
    <dt>Begrip (document)</dt>
    <dd><code>https://begrippen.netbeheernederland.nl/doc/{id}</code></dd>
</dl>

waarbij `{id}` wordt vervangen door de [identifier](/energiesysteembeheer/redacteurs/identificatie) van het begrip.

---

Het begrippenkader is een [information resource](https://www.w3.org/TR/2004/REC-webarch-20041215/#def-information-resource) en wordt daarom met één URI geïdentificeerd.

Voor begrippen volgen we de strategie beschreven in [sectie 4.1 van Cool URIs for the Semantic Web
](https://www.w3.org/TR/cooluris/#r303gendocument). Daarbij wordt onderscheid gemaakt tussen de identiteit van het begrip en het document wat een beschrijving van het begrip geeft. Dit resulteert in een _identification URI_ (`/id/{id}`) en een _document URI_ (`/doc/{id}`), waarbij verzoeken naar de identification URI automatisch worden doorgestuurd naar de documentation URI.[^1]

<details closed markdown="block">
  <summary>
    Voorbeeldcode
  </summary>
  {: .text-delta }
  <pre>
  <https://begrippen.netbeheernederland.nl/id/11358ed2-de31-455e-8f72-f7f0d8adaa29>
      a skos:Concept ;
      dct:identifier "11358ed2-de31-455e-8f72-f7f0d8adaa29" ;
      skos:prefLabel "aansluiting"@nl .
  </pre>
</details>

---

{: .text-delta }
Voetnoten

[^1]: Momenteel is een client-sided redirectmechanisme geïmplementeerd i.p.v. een server-sided 303-redirect.