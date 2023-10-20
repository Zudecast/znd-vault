---
Created: 2023-09-03
Modified: 2023-09-22
---

```dataviewjs
dv.table(["Characters "],
	dv.pages()
	.where(p => !p.file.path.includes("Backend"))
	.where(p => p.Type == "Character")
	.sort(p => p.file.name, "asc")
	.map(p => [p.file.link])
)
```
