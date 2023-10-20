---
limit: 100
mapWithTag: false
icon: help-circle
tagNames: 
excludes: 
extends: 
version: 2
---
QuestGiver:: {"type":"File","options":{"dvQueryString":"dv.pages()\n.where(p => !p.file.path.includes(\"Backend\"))\n.where(p => p.Type == \"Character\")\n.map(p => p.file.link)","customSorting":"a.basename > b.basename ? 1 : -1"},"command":{"id":"insert__Quest__QuestGiver","icon":"user","label":"Insert QuestGiver field"}}

GiverLocation:: {"type":"Lookup","options":{"autoUpdate":true,"outputType":"CustomList","builtinSummarizingFunction":"Count","customListFunction":"page.Location","customSummarizingFunction":"return pages.length","targetFieldName":"Quests","dvQueryString":"dv.pages()\n.where(p => !p.file.path.includes(\"Backend\"))\n.where(p => p.Type == \"Character\")"}}

Rewards:: {"type":"MultiFile","options":{"dvQueryString":"dv.pages()\n.where(p => !p.file.path.includes(\"Backend\"))\n.where(p => p.Type = \"Item\")","customSorting":"a.basename > b.basename ? 1 : -1"}}
Description:: {"type":"Input","options":{"template":"Enter quest description here..."},"style":{"code":true}}
Experience:: {"type":"Number","options":{"step":"1","min":"0"},"command":{"id":"insert__presetField__Experience","icon":"hash","label":"Insert Experience field"}}