# Workflows

This file describes how to interact with the system.

---

## 1. Add new notes

1. Write freely
2. Save into `/00_RAW` (new notes are unprocessed by default)
3. Ask: 鈥滄暣鐞嗘枃绔犫€?(or 鈥淧rocess unprocessed notes鈥?
4. After processing, move source note into the right `/00_RAW/<category>/` folder
5. Rewrite old hyperlinks to the new moved path
6. Update `/README_HUMAN.md` article update directory (latest-first)

You do NOT need to:
- classify
- rename perfectly
- organize folders

After processing, the agent should:
- classify into one existing category folder
- move the source note
- update links in `/01_INDEX`, `/02_SUMMARY`, `/03_KNOWLEDGE`, and `/04_PROJECTS`
- append latest source-note links to `/README_HUMAN.md` with date
- run integrity checks using `/06_SYSTEM_GUIDE/tools/validate_organize_articles.sh`

`鈥滄暣鐞嗘枃绔犫€漙 execution should follow:
- `/06_SYSTEM_GUIDE/skills/organize_articles.md`

---

## 2. Retrieve knowledge

Ask:

- 鈥淒o I have notes about [topic]?鈥?- 鈥淪ummarize everything about [topic]鈥?- 鈥淪how key ideas related to [topic]鈥?
The system should:
1. Check index
2. Read summaries
3. Only expand to full notes if needed

---

## 3. Build knowledge

Ask:

- 鈥淭urn my notes about [topic] into structured knowledge鈥?- 鈥淓xtract key insights from these notes鈥?
Output should go to `/03_KNOWLEDGE`

---

## 4. Project work

Store project materials in `/04_PROJECTS`

Ask:

- 鈥淪ummarize project status鈥?- 鈥淲hat decisions have I made?鈥?- 鈥淲hat is still unresolved?鈥?
---

## 5. Structural repair

Ask:

- 鈥滀慨澶嶉摼鎺モ€?- 鈥滀慨澶?RAW 鍜?Summary 瀵瑰簲鍏崇郴鈥?- 鈥滄鏌ュ苟淇鍙屽悜閾炬帴鈥?
Agent should:
- run `/06_SYSTEM_GUIDE/skills/repair_links.md`
- repair mapping/link integrity only
- avoid resolving thesis/argument contradictions

---

## 6. System recovery

If unsure how to proceed:

Ask:

- “What can we do here?”
- “Guide me step by step”
Agent should read system guide files and assist.

---

## 7. Reflective synthesis (summary-only)

Ask:

- “反思”
- “举一反三”
- “从已有概念提出新概念”
- “基于已有 summary 生成新方向”

Agent should:
1. use `/01_INDEX/master_index.md` to narrow candidates
2. read only selected `/02_SUMMARY` files (default 3-8)
3. generate one new synthesis summary in `/02_SUMMARY`
4. emphasize concept combinations, TODO, overlooked concepts, and feasible directions
5. append the new summary path to `master_index` `## Summary Files`
6. append one `reflect` log entry to `/01_INDEX/system_log.md`

`“反思 / 举一反三”` execution should follow:
- `/06_SYSTEM_GUIDE/skills/reflect_synthesis.md`

---

## 下一篇 [[Design Principles.md]]

