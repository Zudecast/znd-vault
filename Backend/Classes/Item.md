---
limit: 100
mapWithTag: true
icon: box
tagNames: 
excludes: 
extends: 
version: 1
---


Location:: {"type":"File","options":{"dvQueryString":"dv.pages()\n.where(p => !p.file.path.includes(\"Backend\"))\n.where(p => p.Type == \"Location\")\n.map(p => [p.file.link])","customSorting":"a.basename > b.basename ? 1 : -1"},"command":{"id":"insert__presetField__Location","icon":"box","label":"Insert Location field"}}
Rarity:: {"type":"Select","options":{"valuesList":{"1":"Common","2":"Uncommon","3":"Rare","4":"Exotic","5":"Legendary"},"sourceType":"ValuesList","valuesListNotePath":"","valuesFromDVQuery":""},"command":{"id":"insert__presetField__Rarity","icon":"asterisk","label":"Insert Rarity field"}}
mapmarker:: {"type":"Formula","options":{"autoUpdate":true,"formula":"current.Type"},"command":{"id":"insert__presetField__mapmarker","icon":"pin","label":"Insert mapmarker field"}}
Rewarded:: {"type":"Lookup","options":{"autoUpdate":true,"outputType":"LinksList","builtinSummarizingFunction":"Count","customListFunction":"page.file.name","customSummarizingFunction":"return pages.length","dvQueryString":"dv.pages()\n.where(p => p.Type == \"Quest\")","targetFieldName":"Rewards"}}