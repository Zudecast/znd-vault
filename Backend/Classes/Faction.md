---
excludes: 
extends: 
icon: flag-triangle-right
limit: 100
mapWithTag: true
tagNames: 
version: 4
---

World:: {"type":"File","options":{"customSorting":"a.basename > b.basename ? 1 : -1","dvQueryString":"dv.pages()\n.where(p => !p.file.path.includes(\"Backend\"))\n.where(p => p.Type == \"World\")\n.map(p => p.file.link)"},"command":{"id":"insert__presetField__World","icon":"globe","label":"Insert World field"}}

Region:: {"type":"File","options":{"dvQueryString":"dv.pages()\n.where(p => !p.file.path.includes(\"Backend\"))\n.where(p => p.Type == \"Region\")\n.map(p => p.file.link)","customSorting":"a.basename > b.basename ? 1 : -1"},"command":{"id":"insert__presetField__Region","icon":"map","label":"Insert Region field"}}

Location:: {"type":"File","options":{"dvQueryString":"dv.pages()\n.where(p => !p.file.path.includes(\"Backend\"))\n.where(p => p.Type == \"Location\")\n.map(p => p.file.link)","customSorting":"a.basename > b.basename ? 1 : -1"},"command":{"id":"insert__presetField__Location","icon":"pin","label":"Insert Location field"}}

Leader:: {"type":"File","options":{"dvQueryString":"dv.pages()\n.where(p => !p.file.path.includes(\"Backend\"))\n.where(p => p.Type == \"Character\")\n.map(p => p.file.link)","customSorting":"a.basename > b.basename ? 1 : -1"},"command":{"id":"insert__presetField__Leader","icon":"user","label":"Insert Leader field"}}

Description:: {"type":"Input","options":{"template":"Enter faction description here..."},"command":{"id":"insert__presetField__Description","icon":"list-plus","label":"Insert Description field"},"style":{"code":true}}