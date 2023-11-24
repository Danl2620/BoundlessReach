---
Name: Warp Core Breach
Segments: 8
Progress: 3
tags: complete
ClockImage: "[[progress-clock-8-3.svg]]"
---

# `=this.Name`
**Progress:** `=this.Progress` out of `=this.Segments` segments filled

```dataview
LIST without id embed(link(meta(ClockImage).path, "100"))
WHERE contains(file.path, this.file.path)
```

## Notes
