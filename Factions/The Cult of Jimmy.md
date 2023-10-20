---
Type: Faction
World: "[[Cointeau]]"
Region: "[[The Land of Jim]]"
Location: "[[Jim Town]]"
Created: 2023-09-03
Modified: 2023-09-22
Leader: "[[Jimmy]]"
---

> **Location:** `$= dv.current().Location`
> **Leader:** `$= dv.current().Leader`

# Description

> *They worship [[Jimmy]].*

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
