---
Name: Rowen Sedano
Edge: 2
Heart: 2
Iron: 3
Shadow: 1
Wits: 1
Health: 5
Spirit: 5
Supply: 4
Momentum: 10
Wealth: 0
Wounded: ⬡
Shaken: ⬡
Unprepared: ⬡
Harmed: ⬡
Traumatized: ⬡
Doomed: ⬡
Tormented: ⬡
Indebted: ⬡
XPSpent: 0
Bonds_Progress: 0
Bonds_TrackImage: "[[progress-track-0.svg]]"
Bonds_XPEarned: 0
Discoveries_Progress: 3
Discoveries_TrackImage: "[[progress-track-3.svg]]"
Discoveries_XPEarned: 0
Quests_Progress: 0
Quests_TrackImage: "[[progress-track-0.svg]]"
Quests_XPEarned: 0
Label: rowen
Callsign: Shutdown
---
# `=this.Name`

#### (_`=this.Callsign`_)

![[RowenSedano.jpg|200]]

Haunted by past actions or failure - was part of outpost wiped out by a monster. Tried to fight back in exosuit (which is why he lived); he failed and exosuit was destroyed (but he survived).

-- TODO add this as progress
Vow: Track down why AI things are letting in monsters (or something).

Stuff:
* Beam Gun (named weapon)
* Greatsword
* Broken exosuit glove with icon (from trying to repel monster attack)
* Paring knife

## Stats
| Edge | Heart | Iron | Shadow | Wits |
| --- | --- | --- | --- | --- |
| `=this.Edge` | `=this.Heart` | `=this.Iron` | `=this.Shadow` | `=this.Wits` |

## Meters
| Health | Spirit | Supply | Wealth | Momentum |
| --- | --- | --- | --- | --- |
| `=this.Health` | `=this.Spirit` | `=this.Supply` | `=this.Wealth` | `=this.Momentum` |

## Impacts
| Misfortunes | Lasting Effects | Burdens |
| --- | --- | --- |
| `=this.Wounded` Wounded | `=this.Harmed` Permanently Harmed | `=this.Doomed` Doomed |
| `=this.Shaken` Shaken | `=this.Traumatized` Traumatized | `=this.Tormented` Tormented |
| `=this.Unprepared` Unprepared |  | `=this.Indebted` Indebted |

## Legacies
| XP Earned | XP Spent |
| --- | --- |
| `=this.Bonds_XPEarned+this.Discoveries_XPEarned+this.Quests_XPEarned` | `=this.XPSpent` |
### Bonds (Rolled Over? `=choice(this.Bonds_Progress > 40, "Yes", "No")`)
```dataview
LIST without id embed(link(meta(Bonds_TrackImage).path, "350"))
WHERE contains(file.path, this.file.path)
```
### Discoveries (Rolled Over? `=choice(this.Discoveries_Progress > 40, "Yes", "No")`)
```dataview
LIST without id embed(link(meta(Discoveries_TrackImage).path, "350"))
WHERE contains(file.path, this.file.path)
```
### Quests (Rolled Over? `=choice(this.Quests_Progress > 40, "Yes", "No")`)
```dataview
LIST without id embed(link(meta(Quests_TrackImage).path, "350"))
WHERE contains(file.path, this.file.path)
```

## Background Vow
```dataview
TABLE WITHOUT ID Name, Character, embed(link(meta(TrackImage).path, "150")) AS Progress
FROM #incomplete 
WHERE file.name != "Progress_Template"
AND contains(file.tags, "background")
AND contains(file.tags, this.Label)
```


## Vows / Progress Tracks
```dataview
TABLE WITHOUT ID Name, embed(link(meta(TrackImage).path, "150")) AS Progress
FROM #incomplete and !#background
WHERE file.name != "Progress_Template" 
```


## Assets

![[Gunner]]

![[Slayer]]

![[Rockhorn]]


