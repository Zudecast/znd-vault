---
Type: 
Aliases: 
excludes: [Locations]
extends: Region
icon: landmark
limit: 100
mapWithTag: true
Name: Location
tagNames: 
version: 12
---

Region:: {"type":"File","options":{"dvQueryString":"dv.pages()\n.where(p => !p.file.path.includes(\"Backend\"))\n.where(p => p.Type == \"Region\")\n.map(p => p.file.link)","customSorting":"a.basename > b.basename ? 1 : -1"},"command":{"id":"insert__presetField__Region","icon":"map","label":"Insert Region field"},"style":{"code":true}}

location:: {"type":"Input","options":{"template":"[\"[0, 0]\"]"},"command":{"id":"insert__presetField__location","icon":"pin","label":"Insert location field"}}

mapmarker:: {"type":"Formula","options":{"autoUpdate":true,"formula":"current.Type"}}

World:: {"type":"Lookup","options":{"autoUpdate":true,"outputType":"CustomList","builtinSummarizingFunction":"Count","customListFunction":"page.World","customSummarizingFunction":"return pages.length","dvQueryString":"dv.pages()\n.where(p => !p.file.path.includes(\"Backend\"))\n.where(p => p.Type == \"Region\")","targetFieldName":"Locations"}}
