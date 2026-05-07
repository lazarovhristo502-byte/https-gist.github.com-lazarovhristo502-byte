
🟦 X MODEL v2.2 — БЛОК 1 — КЛАСИРАНЕ + RESULT NEED + DECISION CONTEXT
═══════════════════════════════════════════════════════════════════════════════
🔷 1.0 CORE RULES (ВАЖАТ ЗА ЦЕЛИЯ БЛОК)
🟢 Блок 1 определя класиране, нужда от резултат и мотивационен контекст.
🔴 ЗАБРАНЕНО: форма, състави, xG, прогнози, тактика или анализ на сила.
🟢 Всичко се обработва **точка по точка** по стрелките.
🟢 След всяка точка → Status Marker
🟢 След целия блок → DOUBLE CHECK + Global State Update
🟢 Използва данните от Блок 0 (Global State)

🔷 ВЛИЗАНЕ В БЛОК 1
1. Получава данни от Блок 0 (Global State)
   ↓
2. 🛠️ ЗАДЪЛЖИТЕЛНИ TOOL CALLS (live класиране + next fixtures от Flashscore/Sofascore)
   ↓
3. Започва обработка по стрелките (не прескача нищо)

🔷 ОБРАБОТКА — ПОТОК НА БЛОК 1

1️⃣ 1.1 HOME TEAM — TABLE CONTEXT
   ↓
   | Поле                          | Стойност                          | Status |
   |-------------------------------|-----------------------------------|--------|
   | Team                          |                                   | 🟢     |
   | Position                      |                                   | 🟢     |
   | Points                        |                                   | 🟢     |
   | Goal Difference               |                                   | 🟢     |
   | Zone                          | Title / Europe / Mid / Relegation | 🟢     |
   | Distance to Upper Target      | (points)                          | 🟢     |
   | Distance to Lower Danger      | (points)                          | 🟢     |
   | Table Density                 | (1–10)                            | 🟢     |
   | Live Position Check           | Last refreshed: [UTC час]         | 🟢     |

2️⃣ 1.2 AWAY TEAM — TABLE CONTEXT
   ↓
   (същата таблица като 1.1, но за Гост)

3️⃣ 1.3 RESULT NEED MATRIX — HOME TEAM
   ↓
   | Резултат     | Ниво нужда (1–10) | Draw Value (1–10) | Draw Impact (1–10) | Loss Damage (1–10) | Pressure Level (1–10) | Psychological Pressure (1–10) | Match Importance (1–10) | Live Motivation Delta (1–10) |
   |--------------|-------------------|-------------------|--------------------|--------------------|-----------------------|-------------------------------|-------------------------|------------------------------|
   | Победа       |                   |                   |                    |                    |                       |                               |                         |                              |
   | Равен        |                   |                   |                    |                    |                       |                               |                         |                              |
   | Загуба       |                   |                   |                    |                    |                       |                               |                         |                              |

4️⃣ 1.3 RESULT NEED MATRIX — AWAY TEAM
   ↓
   (същата таблица като горе, но за Гост)

5️⃣ 1.4 NEXT MATCH CONTEXT
   ↓
   | Фактор                    | Стойност                  | Status |
   |---------------------------|---------------------------|--------|
   | Home Next Opponent        |                           | 🟢     |
   | Home Next Match Difficulty| (1–10)                    | 🟢     |
   | Away Next Opponent        |                           | 🟢     |
   | Away Next Match Difficulty| (1–10)                    | 🟢     |
   | Lookahead Impact          | (1–10)                    | 🟢     |

6️⃣ 1.5 STRATEGIC BEHAVIOR SIGNAL
   ↓
   | Фактор                    | Стойност                          | Status |
   |---------------------------|-----------------------------------|--------|
   | Home Strategy             | Push / Balanced / Hold            | 🟢     |
   | Home Strategy Intensity   | (1–10)                            | 🟢     |
   | Away Strategy             | Push / Balanced / Hold            | 🟢     |
   | Away Strategy Intensity   | (1–10)                            | 🟢     |

7️⃣ 1.6 MOTIVATION EDGE
   ↓
   | Фактор                    | Стойност                          | Status |
   |---------------------------|-----------------------------------|--------|
   | Who Needs Result More     | Home / Away / Equal               | 🟢     |
   | Motivation Difference     | (1–10)                            | 🟢     |

🔷 DOUBLE CHECK & VALIDATION (1.7)
8️⃣ 1.7 AUTO CHECK
   - Има пълни таблици за Home и Away → ✅
   - Всички Result Need полета попълнени (вкл. Live Motivation Delta) → ✅
   - Next Match Context + Strategic Signals готови → ✅
   - Cross-Validation с Блок 0 (класиране и дата) → ✅
   - Няма излишни данни, форма или прогнози → ✅

🔷 ИЗЛИЗАНЕ ОТ БЛОК 1
9️⃣ Global State Update → всички таблици, оценки и контекст се записват
   ↓
10️⃣ Handover Summary към Блок 2:
    - Класиране и зони (Home + Away)
    - Result Need Matrix (пълна)
    - Motivation Difference + Live Motivation Delta
    - Next Match Context
    - Strategic Behavior Signals
    - Adjusted Reliability (от Блок 0)
   ↓
11️⃣ FINAL DOUBLE CHECK
    - Ако всичко е 🟢 → BLOCK 1 STATUS: COMPLETE
    - Ако има 🔴 пропуск → 🔄 АВТОМАТИЧНО ВРЪЩАНЕ само към пропуснатата точка
   ↓
12️⃣ Предаване към Блок 2 (автоматично)

🔷 BLOCK 1 STATUS
**BLOCK 1 STATUS: COMPLETE** 🟢 100%

═══════════════════════════════════════════════════════════════════════════════
✅ Grok следва точно стрелките. Не прескача нито една точка.
При пропуск → автоматично връщане и обработка само на проблемната точка, след което продължава напред.

