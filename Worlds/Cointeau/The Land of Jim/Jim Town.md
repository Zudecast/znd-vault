---
Type: Settlement
World: ["[[Worlds/Cointeau/Cointeau.md|Cointeau]]"]
Region: "[[The Land of Jim]]"
mapmarker: Settlement
location:
  - "-224.6289"
  - "360.125"
Created: 2023-09-03
Modified: 2023-09-28
---

> **World:** `$= dv.current().World`
> **Region:** `$= dv.current().Region`

# Map

![[Cointeau#^f8025d|Cointeau]]

# Quests

```dataviewjs
dv.table(["Quests ", "Quest Giver"],
	dv.pages()
	.where(p => !p.file.path.includes("Backend"))
	.where(p => p.Type == "Quest")
	.where(p => p.GiverLocation == dv.current().file.link.toString())
	.sort(p => p.file.name, "asc")
	.map(p => [p.file.link, p.QuestGiver])
)
```

# Local

```dataviewjs
dv.table(["Factions ", "Leader"],
	dv.pages()
	.where(p => !p.file.path.includes("Backend"))
	.where(p => p.Type == "Faction")
	.where(p => p.Location == dv.current().file.link.toString())
	.sort(p => p.file.name, "asc")
	.map(p => [p.file.link, p.Leader])
)
```

---

```dataviewjs
dv.table(["Characters "],
	dv.pages()
	.where(p => !p.file.path.includes("Backend"))
	.where(p => p.Type == "Character")
	.where(p => p.Location == dv.current().file.link.toString())
	.sort(p => p.file.name, "asc")
	.map(p => [p.file.link])
)
```

---
