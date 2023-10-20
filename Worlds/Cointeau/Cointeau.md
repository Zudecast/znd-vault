---
Type: World
Description: Input world description here...
Map: "[[Cointeau.jpeg]]"
Created: 2023-09-03
Modified: 2023-09-29
---

# Map

```leaflet
id: cointeau
image: ""[[Cointeau.jpeg]]""
markerFolder: Worlds/Cointeau
recenter: true
height: 480px
bounds:
    - [-270, -480]
    - [270, 480]
coordinates [0, 0]
defaultZoom: 0
minZoom: 0
maxZoom: 2
zoomDelta: 0.5
```

^f8025d

---

# Sessions

`button-new-session`

```dataviewjs
const {fieldModifier: f} = this.app.plugins.plugins["metadata-menu"].api;

dv.table(["Sessions ", "Date"],
	await Promise.all(dv.pages()
	.where(p => !p.file.path.includes("Backend"))
	.where(p => p.Type == "Session")
	.where(p => p.World == dv.current().file.link.toString())
	.sort(p => p.file.ctime, "desc")
	.map(async p => [
		p.file.link, 
		p.file.cday
		])
	)
)
```

---

# Geography

`button-new-region`

```dataviewjs
const {fieldModifier: f} = this.app.plugins.plugins["metadata-menu"].api;

dv.table(["Regions "],
	await Promise.all(dv.pages()
	.where(p => !p.file.path.includes("Backend"))
	.where(p => p.Type == "Region")
	.where(p => p.World == dv.current().file.link.toString())
	.sort(p => p.file.name, "asc")
	.map(async p => [
		p.file.link
		])
	)
)
```

---

# Global

`button-new-faction`

```dataviewjs
const {fieldModifier: f} = this.app.plugins.plugins["metadata-menu"].api;

dv.table(["Factions ", "Leader", "Region"],
	await Promise.all(dv.pages()
	.where(p => !p.file.path.includes("Backend"))
	.where(p => p.Type == "Faction")
	.where(p => p.World == dv.current().file.link.toString())
	.sort(p => p.file.name, "asc")
	.map(async p => [
		p.file.link,
		await f(dv,p, "Leader"),
		await f(dv,p, "Region")
		])
	)
)
```

---
