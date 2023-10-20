---
Type: Character
Race: "[[Human]]"
Faction: "[[The Cult of Johnny]]"
Rank: Leader
Location: "[[John Town]]"
Created: 2023-09-03
Modified: 2023-09-22
---

> **Location:** `$= dv.current().Location`
> **Race:** `$= dv.current().Race`
> **Faction:** `$= dv.current().Faction`
> **Rank:** `$= dv.current().Rank`

# Quests

```dataviewjs
const {fieldModifier: f} = this.app.plugins.plugins["metadata-menu"].api;

dv.table(["Quests ", "Exp", "Rewards"],
	await Promise.all(dv.pages()
	.where(p => !p.file.path.includes("Backend"))
	.where(p => p.Type == "Quest")
	.where(p => p.QuestGiver == dv.current().file.link.toString())
	.sort(p => p.file.name, "asc")
	.map(async p => [
		p.file.link,
		await f(dv,p, "Experience"),
		await f(dv,p, "Rewards")
		])
	)
)
```

---
