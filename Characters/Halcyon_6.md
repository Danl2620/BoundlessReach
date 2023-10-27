---
Name: Halcyon 6
Edge: 1
Heart: 3
Iron: 1
Shadow: 2
Wits: 2
Health: 5
Spirit: 5
Supply: 5
Momentum: 2
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
Discoveries_Progress: 0
Discoveries_TrackImage: "[[progress-track-0.svg]]"
Discoveries_XPEarned: 0
Quests_Progress: 0
Quests_TrackImage: "[[progress-track-0.svg]]"
Quests_XPEarned: 0
Label: halcyon
---
# `=this.Name`

![[Halcyon 6.png|200]]![[Tron-Identity.png|320]]

I was created to end the Al wars but I was a child and I was scared. I ran away and my
people paid the ultimate price enslavement to cruel and powerful. But after the years of
isolation and observation of the suffering I caused by not ending the Exodus/Al War. I
now I swear I will not rest till until freedom is the right of all sentient beings is a reality.

Looks like a human/humanoid with odd precise "like Data" when stressed you can see
the seams of his nanites - bald no hair - male

Very Curious, courageous, hopeful, likes sentients, hates oppression.

Wears cool spacer gear.

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

![[Vestige]]


![[Kinetic]]
