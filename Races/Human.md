---
Created: 2023-09-03
Modified: 2023-09-22
---
# Description

> *You know what the deal is.*

# Players

```dataviewjs
dv.table(["Players "],
	dv.pages()
	.where(p => !p.file.path.includes("Backend"))
	.where(p => p.Type == "Player")
	.where(p => p.Race == dv.current().file.link.toString())
	.sort(p => p.file.name, "asc")
	.map(p => [p.file.link])
)
```

---

# Characters

```dataviewjs
dv.table(["Characters "],
	dv.pages()
	.where(p => !p.file.path.includes("Backend"))
	.where(p => p.Type == "Character")
	.where(p => p.Race == dv.current().file.link.toString())
	.sort(p => p.file.name, "asc")
	.map(p => [p.file.link])
)
```
