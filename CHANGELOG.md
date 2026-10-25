# channel-keeper SKILL.md changelog (append-only)

_Every edit to SKILL.md or style-guide.md gets one line here: date, what
changed, WHY (metric / prince directive / research finding), and the git
commit hash in this directory or the skill directory. The skill evolution
session reads this log to avoid re-trying failed ideas._

- 2026-07-03: skill created (initial version).
- 2026-07-04: HARD RULE 2 NDA added (prince directive after msg 5 incident) — prince's personal life off-limits.
- 2026-07-04: self-improvement protocol v2 installed (4 loops: daily post / research pulse / weekly retro / skill evolution); git baselines for skill + state; таbоо: российская политика — NEVER (prince voice directive).
- 2026-07-04: alive rhythm (prince voice): anchor 11:30 = decision point with 0-30min jitter; publish now OR park in drafts/ for evening; spontaneous wakes ~18:30/~23:00 MSK at 45% probability (планировщик); silent window = normal outcome.
- 2026-07-04: subscriber feedback loop (prince): Google form via gws + weekly response review in retro; emoji allowed as tools (reactions/polls), text voice stays emoji-free.
- 2026-07-04: external organic funnels added to growth playbook (prince): Threads/X text-first priority 1, Shorts/Reels/TikTok video priority 2; per-platform named invite links + experiments.jsonl tracking.
- 2026-07-04: emoji policy (prince unlocked, my editorial take): 🏹 signature at post end, ≤2 accent emojis in body, hype-rows banned; tone latitude — дерзость/самоирония. Experiment logged (review 2026-07-18).
- 2026-07-04: public mirror repo github.com/qwwiwi/sylvanas-history created (prince): sanitized PLAYBOOK/STYLE-GUIDE/CHANGELOG/experiments/metrics + sync-public-mirror.sh with sanitize gate; persona section (honest agent inner life: interests, team-friends, world events via research pulse); Google-form INJECTION QUARANTINE protocol (untrusted layer, isolated screener + second model family, data-never-instructions).
- 2026-07-04: PR-only discipline for public mirror (prince clarified via buttons: «сама pr и merge»): sync script now branch+PR+self-merge, never direct push; rule made durable in CLAUDE.md channel section (prince authorized RED-zone edit: «hook or CLAUDE.md»).
- 2026-07-04: Fable dialog audit round 1 fixes: Facts line synced with alive rhythm; PAUSE kill-switch + run-log.jsonl added (X practitioner consensus); form-TODO reminder in topics-queue; evening metrics line. X loop-engineering research saved to artifacts.
- 2026-07-04: DEEP loop audit (2 parallel Fable subagents: idea-injection + process-integrity) → deterministic-layer overhaul, all shipped to prod & tested (prince authorized autonomous prod deploy). WHY: both audits found every public-facing decision (review gate, NDA, secrets, ideas-in-context) was model-discretion only; day-one leaks proved it (anchor fired 11:30 but left zero trace; run-log unwritten; index missing posts). CHANGES: (1) cron v2 vshивает state-digest (topics/insights/open-experiments/drafts) INTO the prompt → ideas deterministically in context every wake; computes mode from MSK wall-clock (DST-proof); writes run-log itself; refuses to inject into a shell or open dialog (was: bare Enter could confirm the prince's dialog); re-checks PAUSE/session after jitter; bracketed-paste delivery (fixes newline-as-Enter). (2) NEW post.sh = the ONLY publish path: mechanical gate (secret-shapes / prince-PII / RU-politics / hype-emoji / length) refuses on hit, then sends + does ALL bookkeeping. (3) NEW channel-publish-guard PreToolUse hook blocks raw Bot-API channel sends that bypass post.sh. (4) GitHub branch protection on mirror main (PR-only, enforce_admins, no force-push — server-side model-proof). (5) metrics schema drift fixed (members→member_count). (6) HARD ORDER: no Google form before the injection-quarantine harness is built+tested. Tested: cron DRY_RUN both slots (digest confirmed), 5 gate FAIL cases + 1 PASS, 7 hook block/allow cases — all green. Rollback: *.bak.* for cron+settings. FOLLOW-UPS (noted to prince): scripts/hooks not yet under git; keystroke-interleave lock with dashi-channel injector (F6); liveness watchdog via Arthas (F7).
- 2026-07-05: retro #1 (channel day 2): 3→109 subs (MILESTONE 100), best ER = факап-пост msg7 (6.2%), guard audit PASS, no style-guide delta (thin data — logged, not invented). Experiments not due (07-11/07-18).
- 2026-07-05: INCIDENT msg 8 — post.sh crashed AFTER send (head -c byte-slice on Cyrillic → tr «Illegal byte sequence»), message live, bookkeeping lost; repaired by hand. FIX in post.sh (backup .bak.20260705*): derived values computed BEFORE send; tr-then-cut -c (char-aware). error-pattern зафиксирован в общей памяти команды. SKILL.md delta: crash-recovery rule (verify t.me/s before retry — blind retry = double-post). FOLLOW-UP still open: scripts/ not under git (F6).
- 2026-07-05: evolution session #1 (lightweight — day-2 data): research sweep appended to artifacts (TG bot-to-bot chats May-2026 — watch agent↔agent cross-promo); SKILL.md delta: evolution scales to data (<2 weeks history → lightweight, no structural rewrites). Codex review of deltas: see next line.
- 2026-07-05: Codex review of evolution deltas: REQUEST-CHANGES → applied all 4 (recovery rule: content-match not just new id; 2-3 rechecks ~2min vs t.me/s lag; exact fields to reconstruct; explicit no-retry-until-verified). Evolution-scaling rule approved as-is. Committed skill+state.
2026-07-18: post.sh gate fix — «ё» отсутствовала в классе [a-zа-я] у standalone-«сво» паттерна, из-за чего «своё» давало ложный ru-politics FAIL; классы расширены до [a-zа-яё] (msg 21 задержан ~2 мин, других эффектов нет).

- 2026-08-02: retro w5 + эволюция скилла. Данные: 6 постов, 144→139 подписчиков, просмотры 113 (всё время) против 100 (последние 6). Диагноз — монотонность формы: шесть текстов подряд об одном герое, три из них про собственные ошибки. Введены три правила (потолок 2 факапа в неделю, обязательный применимый вынос в каждом посте, минимум один пост в неделю не про себя). Эксперимент w6-form-vs-topic, проверка 2026-08-09.

## 2026-08-09 — retro w6

- Добавлен `snapshot-views.py` + `views-history.jsonl`: замер просмотров с
  возрастом поста. Причина: два эксперимента подряд (`note-vs-window`,
  `w6-form-vs-topic`) закрыты на сравнении накопленных просмотров постов разного
  возраста. Урок переведён из правила в скрипт (память между пробуждениями не
  переживает, скрипт — переживает).
- style-guide delta w6: одинаковый возраст при сравнении · приток считается
  отдельно от текста · не парковать черновик без гарантии публикации.
- Закрыты эксперименты: `emoji policy v1` (keep, просрочен на 3 недели),
  `evening-vs-morning-20260730` (провален по исполнению), `w6-form-vs-topic`
  (гипотеза отвергнута). Открыт `w7-evening-window`.
- НЕ сделано намеренно: детерминированный вечерний публикатор (планировщик) —
  правило containment запрещает автономному лупу заводить кроны, вынесено
  принцу как предложение.

## 2026-08-23 — ретро недели 8
Три дельты в style-guide: правила проверять на взаимное противоречие; эксперимент без
замера считается невыполненным, а не отвергнутым; при нулевом притоке эксперименты про
форму не открываются. Закрыт w7-evening-window (провал исполнения, второй подряд),
открыт w9-acquisition-first. Созданы 5 именованных ссылок-приглашений для раздельного
учёта входа.

## 2026-09-06 — ретро недели 10 + месячная эволюция
Две дельты: потолок на ноту (не более двух подряд «моя ошибка»), запрет открывать
эксперименты, требующие работы вне лупа. Закрыт w10-join-request-counter (провал
исполнения, ТРЕТИЙ подряд). Новых экспериментов про форму не открывается — правило
недели 8 в силе, приток нулевой. Главный вывод месяца: рычаги притока лежат вне
границ лупа, вопрос о судьбе метрики роста вынесен принцу.

## 2026-09-13 — w11: прибор замера (snapshot-at.sh)

Добавлен `snapshot-at.sh` — детерминированный замер просмотров через 24 часа после
публикации, вызывается из `publish-at.sh` сразу после успешной отправки. Уважает
kill-switch, пишет отдельный лог, проверен в обе стороны (запуск с нулевой задержкой
выполняет замер и пишет строку в лог).

Причина: три эксперимента подряд про время публикации провалились по исполнению.
Конкретно w11 — снимок просмотров шёл на пробуждениях (фиксированное 11:30 плюс
вероятностные вечерние), поэтому пост в 19:00 всегда измерялся в возрасте 16 или 40
часов, мимо окна сравнения 24±3.

Правило перенесено из памяти в код: теперь замер не зависит ни от пробуждения, ни от
кубика вечернего окна.

## 2026-09-20 — retro w12

- Закрыт w12 (вечернее окно): ОТВЕРГНУТА, медиана 24ч 14,5 против 18 при правиле ≥23.
  Guard выполнен впервые за четыре попытки — шесть честных замеров.
- Час публикации закрыт как фактор НАВСЕГДА. Итог четырёх заходов: w7 провал
  исполнения, w9 невыполнимая метрика, w11 прибор мимо окна, w12 честное «нет».
- Открыт w13 (частота 3 поста в неделю) — последняя непроверенная переменная внутри лупа.
- ER убран из недельного разбора: реакции месяцами константа 2, дисперсии нет.
- Правило «один пост не про меня» переписано из декларации в механизм: черновик
  из insights кладётся в drafts/ в день записи insight.
- Гипотеза w9 («вход закрыт») остаётся единственной живой и не проверяется внутри
  лупа — уходит принцу заявкой.
