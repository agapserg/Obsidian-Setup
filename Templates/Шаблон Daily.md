---
obsidianUIMode: preview
tags:
- daily_notes
---

> [!question] Быстрые доступы
> - [📥](obsidian://open?vault=My%20Setup&file=ReferenceInformation%2FInbox)[📃](obsidian://open?vault=My%20Setup&file=Templates%2F%D0%A8%D0%B0%D0%B1%D0%BB%D0%BE%D0%BD%20Daily)[🏛️](obsidian://open?vault=My%20Setup&file=ReferenceInformation%2F%D0%9D%D0%BE%D0%B2%D1%8B%D0%B5%20%D0%B8%20%D0%B4%D1%80%D0%B5%D0%B2%D0%BD%D0%B8%D0%B5%20%D0%B7%D0%B0%D0%BC%D0%B5%D1%82%D0%BA%D0%B8)[⭐](obsidian://open?vault=My%20Setup&file=ReferenceInformation%2F%D0%98%D0%B7%D0%B1%D1%80%D0%B0%D0%BD%D0%BD%D0%BE%D0%B5)[📗](obsidian://open?vault=My%20Setup&file=Projects%2FRead%20Later)[🎦](obsidian://open?vault=My%20Setup&file=Projects%2FWatch%20Later)
> - Цели на: [Год](Date_Notes/Annual_Notes/{{date:YYYY}}) - [Месяц](Date_Notes/Monthly_Notes/{{date:YYYY-MM}})

> [!note]+ Что сделает этот день [успешным](Date_Notes/Success/{{Title}})
> ```tasks
> path includes Date_Notes/Success/{{Title}}
> short mode
> ```

> [!example]+ ```dataviewjs 
> let Tsk11 = dv.pages("#tasks").file.tasks.where(t => t.text.includes("✅ {{Title}}") && t.text.includes("🟩")).length
> let Tsk22 = dv.pages("#tasks").file.tasks.where(t => t.text.includes("✅ {{Title}}") && t.text.includes("🟨")).length
> let Tsk33 = dv.pages("#tasks").file.tasks.where(t => t.text.includes("✅ {{Title}}") && t.text.includes("🟥")).length
> let TskTtl = (Tsk11 + (Tsk22 * 5) + (Tsk33 * 10))
> dv.span("Очков за день:: " + TskTtl)
> ```

> [!todo] Одна [запланированная](Date_Notes/Planned/{{Title}}) задача на {{Title}}
> ```tasks
> not done
> due {{Title}}
> short mode
> sort by start
> sort by created
> limit 1
> ```

> [!todo]- Одна задача из [накопилось](ReferenceInformation/Накопилось) на {{Title}}
> ```tasks
> not done
> due before {{Title}}
> short mode
> sort by start
> sort by created
> limit 1
> ```

> [!success]- Выполненное за {{Title}}
> ```tasks
> done {{Title}}
> path does not include Tracker/Habit/
> path does not include Tracker/Success/
> short mode
> ```

> [!info]- Созданные за {{Title}}:
> ```tasks
> has created date
> created on {{Title}}
> short mode
> ```