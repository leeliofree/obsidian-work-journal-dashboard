# Obsidian Work Journal Dashboard

**Write once. See your priorities automatically.**

A lightweight, priority-driven work journal for [Obsidian](https://obsidian.md/). It is a single Markdown note that keeps your full work log and meeting notes, and shows three live dashboards at the top: your Highest / High priority to-dos, everything else still open, and everything you **completed in the last 7 days** — refreshed automatically by the free **Tasks** community plugin. The third box is built for a Friday manager sync: open the note and your "what I did this week" list is already there.

> **This is an Obsidian template (one `.md` note), not a standalone application and not an Obsidian plugin.**
> The only thing you install is the standard **Tasks** plugin. No Dataview, no JavaScript, no CSS, no build step, no configuration files.

![Dashboard preview](assets/dashboard-preview.png)

*Illustrative preview rendered from the fictional tasks in `Demo_Work_Journal.md`. Obsidian renders the live, interactive dashboard; GitHub shows only the Markdown source. This image is a static illustration, not a screenshot of a real work journal.*

---

## What's in the box

| File | What it is |
|---|---|
| `Work_Journal_Template.md` | The empty template. Copy this one into your vault. |
| `Demo_Work_Journal.md` | The same template with **fictional example tasks**, so you can see it working. |
| `assets/dashboard-preview.png` | Static illustration of the demo note. |
| `assets/priority-split.png` | Illustration of how priorities map to the two boxes. |
| `LICENSE` | MIT License. |

## Install in three steps

1. **Install Obsidian and the Tasks plugin.** Get [Obsidian](https://obsidian.md/) and open your vault. Go to **Settings → Community plugins → Browse**, search for **Tasks** (by *obsidian-tasks-group*), click **Install**, then **Enable**. If community plugins are off, click **Turn on community plugins** first.
2. **Copy the note into your vault.** Click the green **Code** button on this page → **Download ZIP**, unzip it, and move `Work_Journal_Template.md` anywhere into your vault folder. (Or download the ready-made ZIP from the [latest Release](https://github.com/leeliofree/obsidian-work-journal-dashboard/releases/latest).) Open the note in **Reading view** or **Live Preview**.
3. **Write tasks.** Under `📒 RAW RECORDING`, add lines like `- [ ] Finalize the project brief 🔺`. The two to-do boxes at the top fill in immediately. Tick a checkbox in either box to complete the task in the original note — Tasks adds a `✅ YYYY-MM-DD` timestamp, and that task now also appears in the third box (`DONE · LAST 7 DAYS`). Click the small link icon to jump back to its source line.

That's it — no plugin settings to change. Tasks just needs its **emoji priority format** enabled (the default) and an empty **global filter**.

> **Just looking?** Copy `Demo_Work_Journal.md` into your vault instead. It contains only fictional example tasks.

## How the dashboard splits your tasks

| Priority | Marker | Appears in |
|---|---|---|
| Highest | 🔺 | 🔴 KEY TASKS · TO DO |
| High | ⏫ | 🔴 KEY TASKS · TO DO |
| Medium | 🔼 | 📋 NORMAL TASKS · TO DO |
| None | — | 📋 NORMAL TASKS · TO DO |
| Low | 🔽 | 📋 NORMAL TASKS · TO DO |
| Lowest | ⏬ | 📋 NORMAL TASKS · TO DO |

![Priority split](assets/priority-split.png)

*Illustrative diagram built from the same fictional demo tasks.*

Both boxes show **unfinished tasks only**, from **this note only** (`path includes {{query.file.path}}`). The two ranges are `priority is above medium` and `priority is below high` — together they cover every priority exactly once, with no overlap. `short mode` gives you the checkbox and the compact source link; `sort by priority` keeps the most important on top. Completed tasks stay in `📒 RAW RECORDING` as your permanent work history — and the last 7 days of them are also summarised in the third box.

The three query blocks (identical in the template and the demo):

```tasks
not done
path includes {{query.file.path}}
priority is above medium
sort by priority
short mode
```

```tasks
not done
path includes {{query.file.path}}
priority is below high
sort by priority
short mode
```

```tasks
done
path includes {{query.file.path}}
done after 7 days ago
sort by done reverse
```

## Weekly review · DONE · LAST 7 DAYS

The third box is a rolling 7-day "what I finished" list. It reads the `✅ YYYY-MM-DD` completion timestamp that the Tasks plugin appends when you tick a checkbox, so it needs no tags, no metadata and no extra setup.

| Line | What it does |
|---|---|
| `done` | Only completed tasks. |
| `path includes {{query.file.path}}` | Only this note — the same scope as the two to-do boxes. It will not pull in tasks from other notes in your vault. |
| `done after 7 days ago` | Only tasks whose completion date falls in the rolling 7-day window up to and including today. |
| `sort by done reverse` | Newest completion first, so your most recent work sits at the top of the report. |

Unlike the two to-do boxes, this one does **not** use `short mode`. That is deliberate: the default view keeps the completion date and the source link visible, so you can see *when* each item was done and click straight back to the original log entry.

> **One thing to know:** the 7-day box only sees tasks completed **through the Tasks plugin** — ticking a checkbox inside a query result, or using **Tasks: Toggle Task Done**. That is what writes the `✅ YYYY-MM-DD` timestamp. If you manually type `- [x]`, or tick a plain Markdown checkbox without the plugin, there is no done date and that task will not appear here.

**Want a different window?** Replace `done after 7 days ago` with any of these:

| Replace with | Shows |
|---|---|
| `done after 14 days ago` | The last 14 days. |
| `done this week` | Monday to Sunday of the current calendar week — a good fit for a fixed Friday meeting. |
| `done last week` | The previous calendar week. |
| `done this month` | The current calendar month. |

## Good to know

- Tasks must use standard Markdown checkboxes (`- [ ]`). Plain highlighted text is not a task.
- Assign priorities with **Tasks: Create or edit Task**, or by appending the emoji marker (`🔺` / `⏫` / `🔼` / `🔽` / `⏬`).
- This is a **personal, single-note journal**. It does not aggregate tasks from other notes in your vault.
- The dashboard is rendered by Tasks **inside Obsidian**. On GitHub you will see the raw query code, not a live dashboard — that is expected.
- Queries use the Tasks plugin's native `priority is above/below` and `done after … days ago` filters — no Dataview, no JavaScript, no custom CSS. Compatibility with every past or future Tasks release is not guaranteed; if a query looks empty, add `explain` as a line inside the block to see how Tasks parsed it.
- The demo's completion dates are fixed fictional examples (`2026-11-06` … `2026-11-12`). If you open `Demo_Work_Journal.md` much later, some rows will naturally fall outside the 7-day window and the third box will show fewer items — that is the filter working, not a bug. In your own journal the timestamp is written on the day you tick the box, so the window always stays current.
- The three boxes are **views**, not copies. Raw recording remains the single source of truth; nothing is duplicated or moved.

## Privacy

Never publish your real work journal or screenshots of it. This repository contains **only fictional sample tasks** — no company, customer, supplier, personal, or credential data, and no screenshots of any real vault.

## License

MIT — see [LICENSE](LICENSE).
