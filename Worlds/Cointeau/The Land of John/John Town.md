---
Type: Settlement
World: ["[[Worlds/Cointeau/Cointeau.md|Cointeau]]"]
Region: "[[The Land of John]]"
mapmarker: Settlement
location:
  - -105.9688
  - 614.5
Created: 2023-09-03
Modified: 2023-09-28
---

> **World:** `$= dv.current().World`
> **Region:** `$= dv.current().Region`

# Map

![[Cointeau#^f8025d]]

# Quests

```dataviewjs
const {fieldModifier: f} = this.app.plugins.plugins["metadata-menu"].api;

dv.table(["Quests ", "Quest Giver"],
	await Promise.all(dv.pages()
	.where(p => !p.file.path.includes("Backend"))
	.where(p => p.Type == "Quest")
	.where(p => p.GiverLocation == dv.current().file.link.toString())
	.sort(p => p.file.name, "asc")
	.map(async p => [
		p.file.link,
		await f(dv,p, "QuestGiver")
		])
	)
)
```

# Local

```dataviewjs
const {fieldModifier: f} = this.app.plugins.plugins["metadata-menu"].api;

dv.table(["Factions ", "Leader"],
	await Promise.all(dv.pages()
	.where(p => !p.file.path.includes("Backend"))
	.where(p => p.Type == "Faction")
	.where(p => p.Location == dv.current().file.link.toString())
	.sort(p => p.file.name, "asc")
	.map(async p => [
		p.file.link,
		await f(dv,p, "Leader")
		])
	)
)
```

---

```dataviewjs
const {fieldModifier: f} = this.app.plugins.plugins["metadata-menu"].api;

dv.table(["Characters ", "Race", "Faction"],
	await Promise.all(dv.pages()
	.where(p => !p.file.path.includes("Backend"))
	.where(p => p.Type == "Character")
	.where(p => p.Location == dv.current().file.link.toString())
	.sort(p => p.file.name, "asc")
	.map(async p => [
		p.file.link,
		await f(dv, p, "Race"),
		await f(dv, p, "Faction")
		])
	)
)
```

---
