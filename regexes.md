Ce tableau comprend une liste d'expressions régulières que vous pouvez récupérer pour vérifier la conformité de certains champs, par exemple si vous créez un schéma pour [schema.data.gouv.fr](schema.data.gouv.fr)

| Champ | Exemple | Regex | Source |
| -- | -- | -- | -- |
| Code INSEE | `75114` | `^([013-9]\\d\|2[AB1-9])\\d{3}$` | 
| Chiffres ou valeur `N/A` | `3` ou `N/A` | `^(\\d+\|N\/A)$` |
| Clé FANTOIR | `94059_0040_00036` | `^[A-Za-z0-9_]+$` |
| Heure et date | `2020-05-11T14:08:32Z` | `\\d{4}-[01]\\d-[0-3]\\d([+-][0-2]\\d:[0-5]\\dZ?)?$` |
| Identifiant de marché public | `2014NNNNNNNNNN00` | `^\\d{4}.{1,10}\\d{2}$`|
| Identifiant de parking (issu du PAN) | `75114-P-001` | `^([013-9]\\d\|2[AB1-9])\\d{3}-P-\\d{3}$` | 
| Identifiant de lieu de covoiturage (issu du PAN) | `35238-C-001` | `^([013-9]\\d\|2[AB1-9])\\d{3}-C-\\d{3}$` |
| Nom de commune | `Le Plessis-Trévise` | `^[A-Za-z\\s\\-\\u00C0-\\u00FF]+$` |
| Nom de personne | |`[A-Za-zÀÂÄÇÉÈÊËÎÏÔÖÙÛÜŸàâäçéèêëîïôöùûüÿÆŒæœ \\-']*` |
| Nom de rue pour une adresse | `Avenue Ardouin` | `^[a-zA-Z0-9\\-\\'\\s\\d\\u00C0-\\u00FF]+$` |
| N° de téléphone |  | `^(\\+33\|0\|\\+262\|\\+269\|\\+508\|\\+590\|\\+594\|\\+596\|\\+681\|\\+687\|\\+689)\[1-9\](\\d\\d){4}$`|
| Opening Hours (format OSM) (proposition IRVE) | `Mo-Fr 08:00-12:00,Mo-Fr 14:00-18:00,Th 08:00-18:00` | `(.*?)((\\d{1,2}:\\d{2})-(\\d{1,2}:\\d{2})\|24/7)` |https://schema.data.gouv.fr/etalab/schema-irve/latest/documentation.html#propri%C3%A9t%C3%A9-horaires |
[Opening Hours (format OSM) (proposition personnelle) _ne couvre que les cas les plus courant_ |`Mo-Fr 08:00-12:00,Mo-Fr 14:00-18:00,Th 08:00-18:00`<br>ou `Mo-Fr 08:00-12:00,13:00-17:30; Sa 08:00-12:00; PH off`<br>ou `Mo,We 08:00-12:00`<br>ou `24/7`<br>ou `Mo-Fr 08:00-12:00,13:00-17:30;sunrise-sunset`|`((?:(?:^\|;\s?)(((((Mo\|Tu\|We\|Th\|Fr\|Sa\|Su\|PH\|SH)\|(?:(?:\|,)(Mo\|Tu\|We\|Th\|Fr\|Sa\|Su))+\|((Mo\|Tu\|We\|Th\|Fr\|Sa\|Su)-(Mo\|Tu\|We\|Th\|Fr\|Sa\|Su))))\s((([0-1][0-9]\|2[0-4]):([0-5][0-9]))-(([0-1][0-9]\|2[0-4]):([0-5][0-9]))(,(([0-1][0-9]\|2[0-4]):([0-5][0-9]))-(([0-1][0-9]\|2[0-4]):([0-5][0-9])))?))\|((Mo\|Tu\|We\|Th\|Fr\|Sa\|Su\|PH\|SH) off)\|(sunrise-sunset)))+$\|(24\/7))`|https://regexr.com/5t6m4|
| SIRET | `22940028800010` |`^\\d{14}$` | 
| URL de photo |  | `^https?://(?:[a-z0-9\\-]+\\.)+[a-z]{2,6}(?:/[^/#?]+)+\\.(?:jpg\|jpeg\|gif\|png)`|
| Valeurs séparées par une `,` (Public cible) | `Tout public,Allocataires,Demandeurs d'emploi` ou `Tout public` | `(?:(?:^\|,)(Tout public\|Allocataires\|Demandeurs d'emploi\|Étrangers\|Familles\|Jeunes\|Personnes en situation de handicap\|Séniors))+$`| https://schema.data.gouv.fr/etalab/schema-inclusion-numerique/latest/documentation.html#propri%C3%A9t%C3%A9-public_cible |
| Valeurs séparées par un `\|` (Jours de disponibilité) _Formulation alternative_ | `lundi\|mercredi\|vendredi` | `^(7j/7\|lundi\|mardi\|mercredi\|jeudi\|vendredi\|samedi\|dimanche\|jours fériés\|événements){1}(\\|(7j/7\|lundi\|mardi\|mercredi\|jeudi\|vendredi\|samedi\|dimanche\|jours fériés\|événements))*$`|
| Valeurs séparées par un `\|` (Heures de disponibilité) _Formulation alternative_ | `heures ouvrables\|heures de nuit` | `(heures ouvrables\|heures de nuit\|24h/24){1}(\\|(heures ouvrables\|heures de nuit\|24h/24))*$`|
| Well Known Text d'une ligne _Proposition personnelle_ | | `(MULTI\|multi)?(LINESTRING\|linestring)\(((\|,\s?)\(((\|,\s?)(-?[0-9](\.[0-9]+)?\s-?[0-9](\.[0-9]+)?))+\))+\)` | https://regexr.com/5tfj7

<!--
| UUID | | `"^\\d{14}\\d{4}.{1,10}\\d{2}$"`|
-->
