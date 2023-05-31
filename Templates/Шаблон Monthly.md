---
obsidianUIMode: preview
---

> [!warning]+ Мысли на месяц
> ```tasks
> done
> tags include #мысли 
> done <% tp.file.title %>
> short mode
> ```

> [!todo]- Одна задача на месяц
> ```tasks
> not done 
> due 3<% tp.file.title.slice(1,8) %>
> sort by created
> short mode
> limit 1
> ```

> [!tip] Проекты на месяц
> ```dataview
> LIST WITHOUT ID 
> 	Date +
> 	choice(contains(Status, "NEW"), " 🆕 ", "") +
> 	choice(contains(Status, "WIP"), " ⌛ ", "") +
> 	choice(contains(Status, "REC"), " ♻️ ", "") +
> 	choice(contains(Status, "SEL"), " 💤 ", "") +
> 	choice(contains(Status, "DON"), " ✅ ", "") +
> 	choice(contains(Status, "CAN"), " ❌ ", "") +
> 	file.link
> FROM #<% tp.file.title %>
> WHERE !contains(file.folder,"Template") = true
> WHERE !contains(Status,"#tasks/40DON") = true
> WHERE !contains(Status,"#tasks/50CAN") = true
> SORT
> 	choice(contains(Status, "NEW"), " 🆕 ", "") DESC,
> 	choice(contains(Status, "WIP"), " ⌛ ", "") DESC,
> 	choice(contains(Status, "REC"), " ♻️ ", "") DESC,
> 	choice(contains(Status, "SEL"), " 💤 ", "") DESC,
> 	choice(contains(Status, "DON"), " ✅ ", "") DESC,
> 	choice(contains(Status, "CAN"), " ❌ ", "") DESC,
> 	Date DESC
> ```

> [!success] Сделано/Отменено
> ```dataview
> LIST WITHOUT ID 
> 	Date +
> 	choice(contains(Status, "NEW"), " 🆕 ", "") +
> 	choice(contains(Status, "WIP"), " ⌛ ", "") +
> 	choice(contains(Status, "REC"), " ♻️ ", "") +
> 	choice(contains(Status, "SEL"), " 💤 ", "") +
> 	choice(contains(Status, "DON"), " ✅ ", "") +
> 	choice(contains(Status, "CAN"), " ❌ ", "") +
> 	file.link
> FROM #<% tp.file.title %>
> WHERE !contains(file.folder,"Template") = true
> WHERE contains(Status,"#tasks/40DON") = true OR contains(Status,"#tasks/50CAN") = true
> SORT
> 	choice(contains(Status, "NEW"), " 🆕 ", "") DESC,
> 	choice(contains(Status, "WIP"), " ⌛ ", "") DESC,
> 	choice(contains(Status, "REC"), " ♻️ ", "") DESC,
> 	choice(contains(Status, "SEL"), " 💤 ", "") DESC,
> 	choice(contains(Status, "DON"), " ✅ ", "") DESC,
> 	choice(contains(Status, "CAN"), " ❌ ", "") DESC,
> 	Date DESC
> ```

> [!example]- Стата за месяц
> ```dataviewjs
> let Role01_1 = dv.pages("#Role01").file.tasks.where(t => t.text.includes("✅ <% tp.file.title %>") && t.text.includes("🟩")).length
> let Role01_2 = dv.pages("#Role01").file.tasks.where(t => t.text.includes("✅ <% tp.file.title %>") && t.text.includes("🟨")).length
> let Role01_3 = dv.pages("#Role01").file.tasks.where(t => t.text.includes("✅ <% tp.file.title %>") && t.text.includes("🟥")).length
> let Role01 = Role01_1 + (Role01_2 * 5) + (Role01_3 * 10)
> dv.paragraph("Р1 = " + Role01)
> 
> let Role02_1 = dv.pages("#Role02").file.tasks.where(t => t.text.includes("✅ <% tp.file.title %>") && t.text.includes("🟩")).length
> let Role02_2 = dv.pages("#Role02").file.tasks.where(t => t.text.includes("✅ <% tp.file.title %>") && t.text.includes("🟨")).length
> let Role02_3 = dv.pages("#Role02").file.tasks.where(t => t.text.includes("✅ <% tp.file.title %>") && t.text.includes("🟥")).length
> let Role02 = Role02_1 + (Role02_2 * 5) + (Role02_3 * 10)
> dv.paragraph(" Р2 = " + Role02)
> 
> let Role03_1 = dv.pages("#Role03").file.tasks.where(t => t.text.includes("✅ <% tp.file.title %>") && t.text.includes("🟩")).length
> let Role03_2 = dv.pages("#Role03").file.tasks.where(t => t.text.includes("✅ <% tp.file.title %>") && t.text.includes("🟨")).length
> let Role03_3 = dv.pages("#Role03").file.tasks.where(t => t.text.includes("✅ <% tp.file.title %>") && t.text.includes("🟥")).length
> let Role03 = Role03_1 + (Role03_2 * 5) + (Role03_3 * 10)
> dv.paragraph(" Р3 = " + Role03)
> 
> let Role04_1 = dv.pages("#Role04").file.tasks.where(t => t.text.includes("✅ <% tp.file.title %>") && t.text.includes("🟩")).length
> let Role04_2 = dv.pages("#Role04").file.tasks.where(t => t.text.includes("✅ <% tp.file.title %>") && t.text.includes("🟨")).length
> let Role04_3 = dv.pages("#Role04").file.tasks.where(t => t.text.includes("✅ <% tp.file.title %>") && t.text.includes("🟥")).length
> let Role04 = Role04_1 + (Role04_2 * 5) + (Role04_3 * 10)
> dv.paragraph(" Р4 = " + Role04)
> 
> let sum = Role01 + Role02 + Role03 + Role04
> dv.paragraph(" ΣР = " + sum)
> ```