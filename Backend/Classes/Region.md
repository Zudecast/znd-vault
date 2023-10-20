---
Type: 
Aliases: 
excludes: [Regions]
extends: World
icon: mountain
limit: 100
mapWithTag: true
Name: Region
tagNames: 
version: 9
---

World:: {"type":"File","options":{"dvQueryString":"dv.pages()\n.where(p => !p.file.path.includes(\"Backend\"))\n.where(p => p.Type == \"World\")\n.map(p => p.file.link)","customRendering":"","customSorting":"a.basename > b.basename ? 1 : -1"},"command":{"id":"insert__presetField__World","icon":"globe","label":"Insert World field"},"style":{"code":false,"bold":false}}

Locations:: {"type":"Lookup","options":{"autoUpdate":true,"outputType":"LinksList","builtinSummarizingFunction":"Count","customListFunction":"page.file.name","customSummarizingFunction":"return pages.length","dvQueryString":"dv.pages()\n.where(p => !p.file.path.includes(\"Backend\"))\n.where(p => p.Type == \"Settlement\")","targetFieldName":"Region"}}
