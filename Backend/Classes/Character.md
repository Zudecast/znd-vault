---
Type: 
excludes: 
extends: 
icon: user
limit: 100
mapWithTag: false
Name: Character
tagNames: 
version: 1
---

Location:: {"type":"File","options":{"dvQueryString":"dv.pages()\n.where(p => !p.file.path.includes(\"Backend\"))\n.where(p => p.Type == \"Location\")\n.map(p => [p.file.link])","customSorting":"a.basename > b.basename ? 1 : -1"}}

Faction:: {"type":"File","options":{"dvQueryString":"dv.pages()\n.where(p => !p.file.path.includes(\"Backend\"))\n.where(p => p.Type == \"Faction\")\n.map(p => [p.file.link])","customSorting":"a.basename > b.basename ? 1 : -1"},"command":{"id":"insert__Character__Faction","icon":"list-plus","label":"Insert Faction field"}}

Rank:: {"type":"Select","options":{"valuesList":{"1":"Leader","2":"Follower"},"sourceType":"ValuesList","valuesListNotePath":"","valuesFromDVQuery":""}}

Race:: {"type":"File","options":{"dvQueryString":"dv.pages()\n.where(p => !p.file.path.includes(\"Backend\"))\n.where(p => p.Type == \"Race\")\n.map(p => [p.file.link])","customSorting":"a.basename > b.basename ? 1 : -1"},"command":{"id":"insert__presetField__Race","icon":"scan-face","label":"Insert Race field"}}

mapmarker:: {"type":"Formula","options":{"autoUpdate":true,"formula":"current.Type"}}

Quests:: {"type":"Lookup","options":{"autoUpdate":true,"outputType":"LinksList","builtinSummarizingFunction":"Count","customListFunction":"page.file.name","customSummarizingFunction":"return pages.length","dvQueryString":"dv.pages()\n.where(p => !p.file.path.includes(\"Backend\"))\n.where(p => p.Type == \"Quest\")","targetFieldName":"QuestGiver"}}
Type:: {"type":"Input","options":{"template":"Character"}}
Type:: {"type":"Input","options":{}}