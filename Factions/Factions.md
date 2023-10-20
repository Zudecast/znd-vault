```dataviewjs
dv.table(["Factions ", "Leader", "Region"],
	dv.pages()
	.where(p => !p.file.path.includes("Backend"))
	.where(p => p.Type == "Faction")
	.sort(p => p.file.name, "asc")
	.map(p => [p.file.link, p.Leader, p.Region])
)
```
