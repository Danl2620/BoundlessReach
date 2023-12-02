---
Name: Zoya Wade
Edge: 2
Heart: 1
Iron: 1
Shadow: 2
Wits: 3
Health: 5
Spirit: 5
Supply: 5
Momentum: 5
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
Label: zoya
Callsign: Straggler
---

# `=this.Name`
#### (_`=this.Callsign`_)

![[austriac female solider by Antonio Rizzatti.png|200]]![[Latifa El Hassane by This Northern Boy.png|140]]

Zoya was born and raised on Bulwark (the center of human civilization in The Forge). Her duty and destiny was to become a scion of her powerful clan (one of the five that compose The Founders). During an internecine power struggle she was framed for the murder of one of her family's political foes. Now a fugitive sought by the Keepers, she fled to the outlands and has steadily made a name (callsign) for herself as a vigilante for hire solving crimes, major and minor, in the outlying settlements. She stays one step ahead of any Keepers trying to haul her back to Bulwark.

Zoya acquired her starship the "Luminous Sorrow" in trade for a precious family heirloom -- an antique statuette of her clans founder. The ship is powered by an ancient precursor device.

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
AND file.frontmatter["Character"] = this.Name
```


## Vows / Progress Tracks
```dataview
TABLE WITHOUT ID Name, embed(link(meta(TrackImage).path, "150")) AS Progress
FROM #incomplete and !#background
WHERE file.name != "Progress_Template" 
```


## Assets

![[Fugitive]]

![[Sleuth]]

![[Starship]]
