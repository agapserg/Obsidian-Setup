---
obsidianUIMode: preview
---
> [!info] Месяцы
> Месяцы: [01](Date_Notes/Monthly_Notes/<% tp.file.title %>-01) - [02](Date_Notes/Monthly_Notes/<% tp.file.title %>-02) - [03](Date_Notes/Monthly_Notes/<% tp.file.title %>-03) - [04](Date_Notes/Monthly_Notes/<% tp.file.title %>-04) - [05](Date_Notes/Monthly_Notes/<% tp.file.title %>-05) - [06](Date_Notes/Monthly_Notes/<% tp.file.title %>-06) - [07](Date_Notes/Monthly_Notes/<% tp.file.title %>-07) - [08](Date_Notes/Monthly_Notes/<% tp.file.title %>-08) - [09](Date_Notes/Monthly_Notes/<% tp.file.title %>-09) - [10](Date_Notes/Monthly_Notes/<% tp.file.title %>-10) - [11](Date_Notes/Monthly_Notes/<% tp.file.title %>-11) - [12](Date_Notes/Monthly_Notes/<% tp.file.title %>-12)

> [!todo]- Одна задача на год
> ```tasks
> not done 
> due 4<% tp.file.title.slice(1,8) %>
> sort by created
> short mode
> limit 1
> ```

> [!success]+ Уже сделано
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
> FROM "Projects"
> WHERE !contains(file.folder,"Template") = true
> WHERE contains(Status,"#tasks/40DON") = true
> WHERE contains(Date, "<% tp.file.title %>") = true
> SORT
> 	choice(contains(Status, "NEW"), " 🆕 ", "") DESC,
> 	choice(contains(Status, "WIP"), " ⌛ ", "") DESC,
> 	choice(contains(Status, "REC"), " ♻️ ", "") DESC,
> 	choice(contains(Status, "SEL"), " 💤 ", "") DESC,
> 	choice(contains(Status, "DON"), " ✅ ", "") DESC,
> 	choice(contains(Status, "CAN"), " ❌ ", "") DESC,
> 	Date DESC
> ```

> [!tip]+ В процессе - Есть запланированные понятные следующие действия
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
> FROM "Projects"
> WHERE !contains(file.folder,"Template") = true
> WHERE contains(Status,"#tasks/20WIP") = true
> WHERE contains(Date, "<% tp.file.title %>") = true
> SORT
> 	choice(contains(Status, "NEW"), " 🆕 ", "") DESC,
> 	choice(contains(Status, "WIP"), " ⌛ ", "") DESC,
> 	choice(contains(Status, "REC"), " ♻️ ", "") DESC,
> 	choice(contains(Status, "SEL"), " 💤 ", "") DESC,
> 	choice(contains(Status, "DON"), " ✅ ", "") DESC,
> 	choice(contains(Status, "CAN"), " ❌ ", "") DESC,
> 	Date DESC
> ```

> [!quote]+ Саморассосы
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
> FROM "Projects"
> WHERE !contains(file.folder,"Template") = true
> WHERE contains(Status,"#tasks/60SEL") = true
> WHERE contains(Date, "<% tp.file.title %>") = true
> SORT
> 	choice(contains(Status, "NEW"), " 🆕 ", "") DESC,
> 	choice(contains(Status, "WIP"), " ⌛ ", "") DESC,
> 	choice(contains(Status, "REC"), " ♻️ ", "") DESC,
> 	choice(contains(Status, "SEL"), " 💤 ", "") DESC,
> 	choice(contains(Status, "DON"), " ✅ ", "") DESC,
> 	choice(contains(Status, "CAN"), " ❌ ", "") DESC,
> 	Date DESC
> ```

> [!failure]+ Отменённые
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
> FROM "Projects"
> WHERE !contains(file.folder,"Template") = true
> WHERE contains(Status,"#tasks/50CAN") = true
> WHERE contains(Date, "<% tp.file.title %>") = true
> SORT
> 	choice(contains(Status, "NEW"), " 🆕 ", "") DESC,
> 	choice(contains(Status, "WIP"), " ⌛ ", "") DESC,
> 	choice(contains(Status, "REC"), " ♻️ ", "") DESC,
> 	choice(contains(Status, "SEL"), " 💤 ", "") DESC,
> 	choice(contains(Status, "DON"), " ✅ ", "") DESC,
> 	choice(contains(Status, "CAN"), " ❌ ", "") DESC,
> 	Date DESC
> ```

> [!example]+ Определить след действие
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
> FROM "Projects"
> WHERE !contains(file.folder,"Template") = true
> WHERE contains(Status,"#tasks/10NEW") = true
> WHERE contains(Date, "<% tp.file.title %>") = true
> SORT
> 	choice(contains(Status, "NEW"), " 🆕 ", "") DESC,
> 	choice(contains(Status, "WIP"), " ⌛ ", "") DESC,
> 	choice(contains(Status, "REC"), " ♻️ ", "") DESC,
> 	choice(contains(Status, "SEL"), " 💤 ", "") DESC,
> 	choice(contains(Status, "DON"), " ✅ ", "") DESC,
> 	choice(contains(Status, "CAN"), " ❌ ", "") DESC,
> 	Date DESC
> ```

> [!note]+ Периодические задачи
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
> FROM "Projects"
> WHERE !contains(file.folder,"Template") = true
> WHERE contains(Status,"#tasks/30REC") = true
> WHERE contains(Date, "<% tp.file.title %>") = true
> SORT
> 	choice(contains(Status, "NEW"), " 🆕 ", "") DESC,
> 	choice(contains(Status, "WIP"), " ⌛ ", "") DESC,
> 	choice(contains(Status, "REC"), " ♻️ ", "") DESC,
> 	choice(contains(Status, "SEL"), " 💤 ", "") DESC,
> 	choice(contains(Status, "DON"), " ✅ ", "") DESC,
> 	choice(contains(Status, "CAN"), " ❌ ", "") DESC,
> 	Date DESC
> ```