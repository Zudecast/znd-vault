---
Type: Quest
QuestGiver: 
GiverLocation: 
Rewards: 
Experience: 100
Description: Enter quest description here...
Created: 04/09/2023
Modified: 22/09/2023
---

# Quest Overview

> **Quest Giver:** `$= dv.current().QuestGiver`
> **Giver Location:** `$= dv.current().GiverLocation`
> **Rewards:** `$= dv.current().Rewards`
> **Experience:** `INPUT[slider:Experience]`

`INPUT[text_area:Description]`

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
