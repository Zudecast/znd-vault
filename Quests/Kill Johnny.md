---
Type: Quest
QuestGiver: "[[Jimmy]]"
GiverLocation: ["[[Worlds/Cointeau/The Land of Jim/Jim Town.md|Jim Town]]"]
Rewards: "[[Jimmy's Favorite Gun]]"
Created: 2023-09-04
Modified: 2023-09-22
---

> **Quest Giver:** `$= dv.current().QuestGiver`
> **Giver Location:** `$= dv.current().GiverLocation`
> **Rewards:** `$= dv.current().Rewards`

# Quest Overview

- Fucking kill [[Johnny]].
- Bring me his head.

# Rewards

```dataviewjs
const {fieldModifier: f} = this.app.plugins.plugins["metadata-menu"].api;

dv.table(["Items ", "Rarity"],
	await Promise.all(dv.pages()
	.where(p => !p.file.path.includes("Backend"))
	.where(p => p.Rewarded == dv.current().file.link.toString())
	.sort(p => p.file.name, "asc")
	.map(async p => [
		p.file.link, 
		await f(dv,p, "Rarity")
		])
	)
)
```
