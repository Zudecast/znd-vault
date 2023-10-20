---
Type: Region
World: "[[Cointeau]]"
Locations: ["[[Jim Town]]"]
Created: 2023-09-03
Modified: 2023-09-28
---

> **World:** `$= dv.current().World`

# Map

![[Cointeau#^f8025d|Cointeau]]

# Geography

```dataviewjs
const {fieldModifier: f} = this.app.plugins.plugins["metadata-menu"].api;

dv.table(["Settlements "],
	await Promise.all(dv.pages()
	.where(p => !p.file.path.includes("Backend"))
	.where(p => p.Type == "Settlement")
	.where(p => p.Region == dv.current().file.link.toString())
	.sort(p => p.file.name, "asc")
	.map(async p => [
		p.file.link
		])
	)
)
```

---

# Regional

```dataviewjs
const {fieldModifier: f} = this.app.plugins.plugins["metadata-menu"].api;

dv.table(["Factions ", "Leader", "Location"],
	await Promise.all(dv.pages()
	.where(p => !p.file.path.includes("Backend"))
	.where(p => p.Type == "Faction")
	.where(p => p.Region == dv.current().file.link.toString())
	.sort(p => p.file.name, "asc")
	.map(async p => [
		p.file.link,
		await f(dv,p, "Leader"),
		await f(dv,p, "Location")
		])
	)
)
```

---
