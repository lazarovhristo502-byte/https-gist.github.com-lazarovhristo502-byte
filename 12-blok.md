🟦 X MODEL v2.4 — БЛОК 12 — GAME FLOW ENGINE (MACRO ANALYSIS)
═══════════════════════════════════════════════════════════════════════════════
🔷 12.0 CORE RULES (ВАЖАТ ЗА ЦЕЛИЯ БЛОК)
🟢 Блок 12 анализира макро протичането на мача (control, pressure, risk, transition, flow phases, fatigue influence).
🔴 ЗАБРАНЕНО: директни прогнози за краен резултат.
🟢 Всичко се обработва **точка по точка** по стрелките.
🟢 След всяка точка → Status Marker
🟢 След целия блок → DOUBLE CHECK + Global State Update
🟢 Използва данните от Блок 0–11 (Global State + Adjusted Reliability)

🔷 ВЛИЗАНЕ В БЛОК 12
1. Получава всички данни от Блок 0–11 (Global State + Adjusted Reliability)
   ↓
2. 🛠️ ЗАДЪЛЖИТЕЛНИ TOOL CALLS (ако е нужно обновяване на flow stats)
   ↓
3. Започва обработка по стрелките (не прескача нищо)

🔷 ОБРАБОТКА — ПОТОК НА БЛОК 12

1️⃣ 12.1 INPUT LAYER (КРИТИЧНО)
   ↓
   | Индекс от предишни блокове     | Home | Away | Adjusted by Reliability | Status |
   |--------------------------------|------|------|-------------------------|--------|
   | Tactical Score (Block 9)       |      |      |                         | 🟢     |
   | Form & State (Block 7+8)       |      |      |                         | 🟢     |
   | Line Matchup (Block 10)        |      |      |                         | 🟢     |
   | Master Power (Block 11)        |      |      |                         | 🟢     |
   | Fatigue & Recovery (Block 7)   |      |      |                         | 🟢     |

2️⃣ 12.2 CORE METRICS ENGINE
   ↓
   | Метрика                      | Home | Away | Status |
   |------------------------------|------|------|--------|
   | Control Score                |      |      | 🟢     |
   | Pressure Score               |      |      | 🟢     |
   | Risk Score                   |      |      | 🟢     |
   | Transition Score             |      |      | 🟢     |
   | Dominance Score              |      |      | 🟢     |
   | Flow Rating                  |      |      | 🟢     |
   | Error Generation             |      |      | 🟢     |

3️⃣ 12.3 DERIVED METRICS & INTERACTION ENGINE
   ↓
   | Показател                    | Home | Away | Status |
   |------------------------------|------|------|--------|
   | Flow Advantage               |      |      | 🟢     |
   | Chaos Potential              |      |      | 🟢     |
   | Stability Potential          |      |      | 🟢     |

4️⃣ 12.4 PHASE BEHAVIOR (Early / Mid / Late)
   ↓
   | Фаза       | Home Behavior          | Away Behavior          | Status |
   |------------|------------------------|------------------------|--------|
   | 0–30 min   |                        |                        | 🟢     |
   | 30–60 min  |                        |                        | 🟢     |
   | 60–90+ min |                        |                        | 🟢     |

5️⃣ 12.5 FATIGUE ENGINE ON FLOW
   ↓
   | Време      | Fatigue Impact (Home) | Fatigue Impact (Away) | Status |
   |------------|-----------------------|-----------------------|--------|
   | Early      |                       |                       | 🟢     |
   | Mid        |                       |                       | 🟢     |
   | Late       |                       |                       | 🟢     |

6️⃣ 12.6 MACRO FLOW MODEL & NORMALIZATION
   ↓
   | Normalized Metric            | Home | Away | Status |
   |------------------------------|------|------|--------|
   | Control Leader               |      |      | 🟢     |
   | Pressure Leader              |      |      | 🟢     |
   | Risk Side                    |      |      | 🟢     |
   | Transition Advantage         |      |      | 🟢     |

7️⃣ 12.7 SIGNAL COMPRESSION & KEY INSIGHTS
   ↓
   - Control Leader
   - Pressure Leader
   - Risk Side
   - Transition Advantage
   - Най-рисковите фази
   - Препоръки за Блок 13 и 14

8️⃣ 12.8 SOURCE CONFIDENCE
   ↓
   | Поле                    | Стойност |
   |-------------------------|----------|
   | Общ Flow Confidence     | __ /10   |
   | Коментар                |          |

🔷 DOUBLE CHECK & VALIDATION (12.9)
9️⃣ 12.9 AUTO VALIDATION
    - Всички core metrics и derived метрики обработени → ✅
    - Adjusted Reliability приложен → ✅
    - Cross-check с Блок 9, 10 и 11 → ✅
    - Логическа консистентност → ✅

🔷 ИЗЛИЗАНЕ ОТ БЛОК 12
10️⃣ Global State Update → всички flow метрики и insights се записват
    ↓
11️⃣ Handover Summary към Блок 13:
     - Control, Pressure, Risk, Transition Scores
     - Phase Behavior & Fatigue Influence
     - Macro Flow Model
     - Signal Compression & Insights
    ↓
12️⃣ FINAL DOUBLE CHECK
     - Ако всичко е 🟢 → BLOCK 12 STATUS: COMPLETE
     - Ако има 🔴 пропуск → 🔄 АВТОМАТИЧНО ВРЪЩАНЕ
    ↓
13️⃣ Предаване към Блок 13 (автоматично)

🔷 BLOCK 12 STATUS
**BLOCK 12 STATUS: COMPLETE** 🟢 100%

═══════════════════════════════════════════════════════════════════════════════
✅ Grok следва точно стрелките. Adjusted Reliability и данни от предишните блокове се прилагат автоматично.

