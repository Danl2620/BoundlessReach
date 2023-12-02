---
Name: Keeper Arrives
Segments: 4
Progress: 3
tags: incomplete
ClockImage: "[[progress-clock-4-3.svg]]"
---

# `=this.Name`
**Progress:** `=this.Progress` out of `=this.Segments` segments filled

```dataview
LIST without id embed(link(meta(ClockImage).path, "100"))
WHERE contains(file.path, this.file.path)
```

## Notes
