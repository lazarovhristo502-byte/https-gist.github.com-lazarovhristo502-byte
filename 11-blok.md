🟦 X MODEL v2.4 — БЛОК 11 — MASTER ENGINE (OVERALL TEAM POWER & READINESS)
═══════════════════════════════════════════════════════════════════════════════
🔷 11.0 CORE RULES (ВАЖАТ ЗА ЦЕЛИЯ БЛОК)
🟢 Блок 11 комбинира всички предишни данни и генерира цялостна оценка на силата, готовността и потенциала на двата отбора.
🔴 ЗАБРАНЕНО: директни прогнози за краен резултат.
🟢 Всичко се обработва **точка по точка** по стрелките.
🟢 След всяка точка → Status Marker
🟢 След целия блок → DOUBLE CHECK + Global State Update
🟢 Използва данните от Блок 0–10 (Global State + Adjusted Reliability)

🔷 ВЛИЗАНЕ В БЛОК 11
1. Получава всички данни от Блок 0–10 (Global State + Adjusted Reliability)
   ↓
2. 🛠️ ЗАДЪЛЖИТЕЛНИ TOOL CALLS 
   - web_search + browse_page → актуални комбинирани stats и trends
   - code_execution → power formulas и weighting
   ↓
3. Започва обработка по стрелките (не прескача нищо)

🔷 ОБРАБОТКА — ПОТОК НА БЛОК 11

1️⃣ 11.1 INPUT INDICES (от предишни блокове)
   ↓
   | Индекс                       | Home | Away | Adjusted by Reliability | Status |
   |------------------------------|------|------|-------------------------|--------|
   | Form Index (Block 5+8)       |      |      |                         | 🟢     |
   | Strength Index (Block 8)     |      |      |                         | 🟢     |
   | State Index (Block 7)        |      |      |                         | 🟢     |
   | Line Matchup Rating (Block 10)|     |      |                         | 🟢     |
   | Tactical Score (Block 9)     |      |      |                         | 🟢     |
   | Context Pressure Index       |      |      |                         | 🟢     |
   | Fatigue & Recovery Index     |      |      |                         | 🟢     |

2️⃣ 11.2 CORE POWER ENGINE
   ↓
   **Base Power**
   - Base = (Strength × 0.23) + (Tactics × 0.18) + (Line Matchup × 0.17) + (Form × 0.12) + (Style × 0.10) + (Tempo × 0.05) + (Flexibility × 0.05) + (1 - Star Dependency) × 0.05 + (1 - Fatigue) × 0.05

   **Context Power**
   - Context = (State × 0.25) + (Context Pressure × 0.30) + (Importance × 0.25) + (1 - Lineup Risk) × 0.20

   **Adjusted Power** (след Adjusted Reliability)

3️⃣ 11.3 SYNERGY / CONFLICT
   ↓
   | Тип                        | Home | Away | Impact (1–10) | Status |
   |----------------------------|------|------|---------------|--------|
   | Tactical Synergy           |      |      |               | 🟢     |
   | Structural Synergy         |      |      |               | 🟢     |
   | Psychological Synergy      |      |      |               | 🟢     |
   | Style Clash Risk           |      |      |               | 🟢     |

4️⃣ 11.4 PERFORMANCE ENGINE
   ↓
   | Показател                    | Home | Away | Status |
   |------------------------------|------|------|--------|
   | Adjusted Performance         |      |      | 🟢     |
   | Trend Slope                  |      |      | 🟢     |
   | Finishing Delta              |      |      | 🟢     |
   | Recency Weight               |      |      | 🟢     |

5️⃣ 11.5 VARIANCE & STABILITY + FLOOR / CEILING
   ↓
   | Показател                    | Home | Away | Status |
   |------------------------------|------|------|--------|
   | Stability Score (1–10)       |      |      | 🟢     |
   | Variance Score (1–10)        |      |      | 🟢     |
   | Floor Potential              |      |      | 🟢     |
   | Ceiling Potential            |      |      | 🟢     |

6️⃣ 11.6 GAME FLOW & SCENARIO POTENTIAL
   ↓
   | Сценарий                     | Home Probability | Away Probability | Status |
   |------------------------------|------------------|------------------|--------|
   | Leading Game                 |                  |                  | 🟢     |
   | Trailing Game                |                  |                  | 🟢     |
   | Equal / Balanced             |                  |                  | 🟢     |

7️⃣ 11.7 MARKET EDGE & DECISION ENGINE
   ↓
   - Model Probability (Normalized Power)
   - Market Edge (Model vs Implied Odds)
   - Edge Quality (Advantage × Confidence × Stability)

8️⃣ 11.8 AI EXTRACTION & MASTER INSIGHTS
   ↓
   - Топ 5 фактора, които определят мача
   - Най-големи рискове и възможности
   - Как всичко се комбинира
   - Препоръки за Блок 12, 13, 14 и 15

9️⃣ 11.9 SOURCE CONFIDENCE
   ↓
   | Поле                    | Стойност |
   |-------------------------|----------|
   | Общ Master Confidence   | __ /10   |
   | Коментар                |          |

🔷 DOUBLE CHECK & VALIDATION (11.10)
10️⃣ 11.10 AUTO VALIDATION
    - Всички индекси и формули обработени → ✅
    - Adjusted Reliability приложен → ✅
    - Cross-check с Блок 8, 9 и 10 → ✅
    - Логическа консистентност → ✅

🔷 ИЗЛИЗАНЕ ОТ БЛОК 11
11️⃣ Global State Update → всички power ratings, synergy и insights се записват
    ↓
12️⃣ Handover Summary към Блок 12:
     - Adjusted Power & Strength
     - Synergy & Variance
     - Game Flow Potential
     - Master Insights & Edge Quality
    ↓
13️⃣ FINAL DOUBLE CHECK
     - Ако всичко е 🟢 → BLOCK 11 STATUS: COMPLETE
     - Ако има 🔴 пропуск → 🔄 АВТОМАТИЧНО ВРЪЩАНЕ
    ↓
14️⃣ Предаване към Блок 12 (автоматично)

🔷 BLOCK 11 STATUS
**BLOCK 11 STATUS: COMPLETE** 🟢 100%

═══════════════════════════════════════════════════════════════════════════════
✅ Grok следва точно стрелките. Adjusted Reliability и всички предишни блокове се прилагат автоматично.

