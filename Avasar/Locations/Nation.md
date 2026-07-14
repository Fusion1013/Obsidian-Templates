---
tags:
  - nation
meta-links:
  - "[[Nations]]"
---
> [!infobox|right]
> # NATION NAME
> ![[placeholder.png]]
> ###### Geography
> | **Aliases** |  |
> | - | - |
> | **Region** | [[REGION LINK]] |
> | **Capital** | [[CAPITAL LINK]] |
> ###### Society
> | **Demonym** |  |
> | - | - |
> | **Races** | |
> | **Languages** | [[LANGUAGE LINK]] |
> | **Religions** | [[RELIGIONS LINK]] |
> | **Estimated Population** | 00 |
> ###### Politics
> | **Type** |  |
> | - | - |
> | **Ruler** |  |
> | **Allegiances** |  |

*"QUOTE"*
# Overview
# History
# Culture
# Cities
```dataview
TABLE 
population AS "Population",
choice(population <= 80, "Thorp", choice(population <= 400, "Hamlet", choice(population <= 900, "Village", choice(population <= 2000, "Small Town", choice(population <= 5000, "Large Town", choice(population <= 12000, "Small City", choice(population <= 25000, "Large City", choice(population > 25000, "Metropolis", "Unknown")))))))) AS "Size"
FROM #city
WHERE nation = "NATION NAME"
SORT file.name ASC
```
# People
```dataview
TABLE description AS "Description", race AS "Race", (age + " years") AS "Age" FROM #major_person AND #NATION AND #alive
```
# Organization
```dataview
TABLE description AS "Description" FROM #organization/major WHERE contains(nation, "NATION")
```
# Economy

## Currency

# Language

# Timeline
```dataview
TABLE WITHOUT ID "[[" + file.name + "]]" + choice(contains(file.etags, "#city_founding"), " `far:Flag`", "") + choice(contains(file.etags, "#discovery"), " `far:Lightbulb`", "") + choice(contains(file.etags, "#nation_founding"), " `ris:Flag`", "") + choice(contains(file.etags, "#law"), " `ris:Book2`", "") AS "Event", description AS "Description" FROM #timeline_event WHERE contains(nation, "NATION") SORT date DESC
```
