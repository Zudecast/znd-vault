---
Type: Faction
World: 
Region: 
Location: 
Leader: 
Description: Enter faction description here...
---


# Faction Overview

> **Leader:** `$= dv.current().Leader`
> **Region:** `$= dv.current().Region`
> **Location:** `$= dv.current().Location`

`INPUT[text_area:Description]`

# Faction Members

```dataviewjs
const {fieldModifier: f} = this.app.plugins.plugins["metadata-menu"].api;

dv.table(["Characters ", "Rank", "Race"],
	await Promise.all(dv.pages()
	.where(p => !p.file.path.includes("Backend"))
	.where(p => p.Type == "Character")
	.where(p => p.Faction == dv.current().file.link.toString())
	.sort(p => p.file.name, "asc")
	.map(async p => [
		p.file.link, 
		await f(dv,p, "Rank"), 
		await f(dv,p, "Race")
		])
	)
)
```

---
