---
obsidianUIMode: preview
---

> [!danger] [[Личная миссия]]
> ```dataview
> List WITHOUT ID 
> 	Role03
> from #Mission 
> ```

> [!abstract] Ссылки
> - [[Шаблон Role03|Шаблон Role03]]
> ```button
> name Новый проект Role03
> type note(Projects/New Project) template
> action Шаблон Role03
> ```

> [!note]+ Проекты
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
> FROM #Role03 
> WHERE !contains(file.folder,"Template") = true
> SORT
> 	choice(contains(Status, "NEW"), " 🆕 ", "") DESC,
> 	choice(contains(Status, "WIP"), " ⌛ ", "") DESC,
> 	choice(contains(Status, "REC"), " ♻️ ", "") DESC,
> 	choice(contains(Status, "SEL"), " 💤 ", "") DESC,
> 	choice(contains(Status, "DON"), " ✅ ", "") DESC,
> 	choice(contains(Status, "CAN"), " ❌ ", "") DESC,
> 	Date DESC
> ```

> [!success]- Выполненные задачи за последние 3 дня
> ```dataview
> task from #tasks
> WHERE completed
> WHERE completion != empty
> WHERE completion >= date(today) - dur(3 day)
> WHERE contains(Role, "#Role03") = true
> group by list(completion) as abs
> sort abs desc
> ```