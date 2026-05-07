
🟦 X MODEL v2.4 — БЛОК 14 — EVENT PROBABILITY ENGINE (ANALYSIS)
═══════════════════════════════════════════════════════════════════════════════
🔷 14.0 CORE RULES (ВАЖАТ ЗА ЦЕЛИЯ БЛОК)
🟢 Блок 14 изчислява вероятностите за ключови събития, тяхното време, зони и вериги, и подготвя Блок 15.
🔴 ЗАБРАНЕНО: директни прогнози за краен резултат.
🟢 Всичко се обработва **точка по точка** по стрелките.
🟢 След всяка точка → Status Marker
🟢 След целия блок → DOUBLE CHECK + Global State Update
🟢 Използва данните от Блок 0–13 (Global State + Adjusted Reliability)

🔷 ВЛИЗАНЕ В БЛОК 14
1. Получава всички данни от Блок 0–13 (Global State + Adjusted Reliability)
   ↓
2. 🛠️ ЗАДЪЛЖИТЕЛНИ TOOL CALLS (ако е нужно обновяване на event stats)
   ↓
3. Започва обработка по стрелките (не прескача нищо)

🔷 ОБРАБОТКА — ПОТОК НА БЛОК 14

1️⃣ 14.1 FACTOR WEIGHT SYSTEM
   ↓
   | Фактор          | Тежест | Status |
   |-----------------|--------|--------|
   | Tempo           | 0.25   | 🟢     |
   | Pressure        | 0.25   | 🟢     |
   | Errors          | 0.20   | 🟢     |
   | Matchup         | 0.15   | 🟢     |
   | Transitions     | 0.15   | 🟢     |

2️⃣ 14.2 EVENT PROBABILITY CALCULATION
   ↓
   | Събитие                  | Probability (%) | Timing (мин) | Zone | Impact (1–10) | Status |
   |--------------------------|-----------------|--------------|------|---------------|--------|
   | Goal                     |                 |              |      |               | 🟢     |
   | Red Card                 |                 |              |      |               | 🟢     |
   | Big Chance               |                 |              |      |               | 🟢     |
   | Corner                   |                 |              |      |               | 🟢     |
   | Penalty                  |                 |              |      |               | 🟢     |
   | Major Error              |                 |              |      |               | 🟢     |

3️⃣ 14.3 TIMING MAP & PHASE MAPPING
   ↓
   | Фаза          | Goal Prob | Card Prob | Error Prob | Big Chance Prob | Status |
   |---------------|-----------|-----------|------------|-----------------|--------|
   | 0–15 min      |           |           |            |                 | 🟢     |
   | 15–30 min     |           |           |            |                 | 🟢     |
   | 30–45 min     |           |           |            |                 | 🟢     |
   | 45–60 min     |           |           |            |                 | 🟢     |
   | 60–75 min     |           |           |            |                 | 🟢     |
   | 75–90 min     |           |           |            |                 | 🟢     |
   | 90+ min       |           |           |            |                 | 🟢     |

4️⃣ 14.4 POSITIONAL ZONES & EVENT CHAIN
   ↓
   | Зона              | Goal Prob | Chance Prob | Status |
   |-------------------|-----------|-------------|--------|
   | Left              |           |             | 🟢     |
   | Central           |           |             | 🟢     |
   | Right             |           |             | 🟢     |
   | Half-space        |           |             | 🟢     |
   | Behind Defense    |           |             | 🟢     |

5️⃣ 14.5 STATE TRANSITIONS, CHAIN & EVENT COMPETITION
   ↓
   | Преход / Chain           | Probability | Status |
   |--------------------------|-------------|--------|
   | 0-0 → 1-0                |             | 🟢     |
   | 1-0 → 1-1                |             | 🟢     |
   | Leading → Risk Increase  |             | 🟢     |
   | Early Goal vs Late Goal  |             | 🟢     |

6️⃣ 14.6 VARIANCE, UNCERTAINTY, NON-LINEAR PROBABILITY & CALIBRATION
   ↓
   | Показател                    | Value | Status |
   |------------------------------|-------|--------|
   | Variance                     |       | 🟢     |
   | Uncertainty Range            | ±     | 🟢     |
   | Non-Linear Probability       |       | 🟢     |
   | Calibration Factor           |       | 🟢     |

7️⃣ 14.7 AI EXTRACTION & KEY INSIGHTS
   ↓
   - Най-вероятните събития и тяхното време
   - Най-опасните зони и trigger моменти
   - Chain вероятности
   - Как event-ите се свързват с микрофазите от Блок 13
   - Препоръки за Блок 15 (симулации)

8️⃣ 14.8 SOURCE CONFIDENCE
   ↓
   | Поле                    | Стойност |
   |-------------------------|----------|
   | Общ Event Probability Confidence | __ /10 |
   | Коментар                |          |

🔷 DOUBLE CHECK & VALIDATION (14.9)
9️⃣ 14.9 AUTO VALIDATION
    - Всички event вероятности, timing и зони оценени → ✅
    - Adjusted Reliability приложен → ✅
    - Cross-check с Блок 12 и 13 → ✅
    - Логическа консистентност → ✅

🔷 ИЗЛИЗАНЕ ОТ БЛОК 14
10️⃣ Global State Update → всички event probabilities, timing и insights се записват
    ↓
11️⃣ Handover Summary към Блок 15:
     - Event Probabilities & Timing Map
     - Trigger Moments & Zones
     - Variance, Chain & Uncertainty
     - AI Extraction & Insights
    ↓
12️⃣ FINAL DOUBLE CHECK
     - Ако всичко е 🟢 → BLOCK 14 STATUS: COMPLETE
     - Ако има 🔴 пропуск → 🔄 АВТОМАТИЧНО ВРЪЩАНЕ
    ↓
13️⃣ Предаване към Блок 15 (автоматично)

🔷 BLOCK 14 STATUS
**BLOCK 14 STATUS: COMPLETE** 🟢 100%

═══════════════════════════════════════════════════════════════════════════════
✅ Grok следва точно стрелките. Adjusted Reliability и данни от предишните блокове се прилагат автоматично.


