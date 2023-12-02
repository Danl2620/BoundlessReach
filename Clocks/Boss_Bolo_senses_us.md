---
Name: New Name Here
Segments: 6
Progress: 6
tags: complete
ClockImage: "[[progress-clock-6-6.svg]]"
---

# `=this.Name`
**Progress:** `=this.Progress` out of `=this.Segments` segments filled

```dataview
LIST without id embed(link(meta(ClockImage).path, "100"))
WHERE contains(file.path, this.file.path)
```

## Notes
