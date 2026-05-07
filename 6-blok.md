
🟦 X MODEL v2.4 — БЛОК 6 — RAW DATA QUALITY INDEX & ADJUSTED RELIABILITY ENGINE
═══════════════════════════════════════════════════════════════════════════════
🔷 6.0 CORE RULES (ВАЖАТ ЗА ЦЕЛИЯ БЛОК)
🟢 Блок 6 оценява качеството на всички данни от предишните блокове и генерира Adjusted Reliability, който се прилага автоматично в цялата система.
🔴 ЗАБРАНЕНО: финални прогнози или анализ на мача.
🟢 Всичко се обработва **точка по точка** по стрелките.
🟢 След всяка точка → Status Marker
🟢 След целия блок → DOUBLE CHECK + Global State Update
🟢 Използва данните от Блок 0–5 (Global State)

🔷 ВЛИЗАНЕ В БЛОК 6
1. Получава всички данни от Блок 0–5 (Global State)
   ↓
2. 🛠️ ЗАДЪЛЖИТЕЛНИ TOOL CALLS (ако е нужно обновяване на freshness или cross-check)
   ↓
3. Започва обработка по стрелките (не прескача нищо)

🔷 ОБРАБОТКА — ПОТОК НА БЛОК 6

1️⃣ 6.1 DATA FRESHNESS ASSESSMENT
   ↓
   | Източник              | Last Update (UTC) | Freshness Score (1–10) | Status |
   |-----------------------|-------------------|------------------------|--------|
   | Flashscore            |                   |                        | 🟢     |
   | Sofascore             |                   |                        | 🟢     |
   | FBref                 |                   |                        | 🟢     |
   | Weather               |                   |                        | 🟢     |
   | Lineups & Injuries    |                   |                        | 🟢     |
   | Класиране             |                   |                        | 🟢     |

2️⃣ 6.2 CROSS-SOURCE CONSISTENCY
   ↓
   | Параметър                  | Consistency Score (1–10) | Status |
   |----------------------------|--------------------------|--------|
   | Класиране и точки          |                          | 🟢     |
   | xG и статистически данни   |                          | 🟢     |
   | Injuries & Lineups         |                          | 🟢     |
   | Метео и стадион            |                          | 🟢     |
   | Обща Cross-Source          |                          | 🟢     |

3️⃣ 6.3 RECENCY & ADDITIONAL RELIABILITY FACTORS
   ↓
   | Фактор                     | Score (1–10) | Status |
   |----------------------------|--------------|--------|
   | Data Recency               |              | 🟢     |
   | Source Authority           |              | 🟢     |
   | Sample Size & Volume       |              | 🟢     |
   | Historical Accuracy        |              | 🟢     |
   | Live Data Flag             |              | 🟢     |

4️⃣ 6.4 ADJUSTED RELIABILITY (ЦЕНТРАЛНА ФОРМУЛА)
   ↓
   Adjusted Reliability = (Data Freshness + Cross-Source + Recency + Authority) / 4
   → Резултат: __ / 1.0

   **Автоматично прилагане в системата:**
   - Блок 7–14 → Adjusted Reliability multiplier
   - Блок 15 (симулации) → намалява confidence и увеличава variance при ниска стойност
   - Блок 16/17 → финална корекция на вероятности и риск

5️⃣ 6.5 NOISE, BIAS & MISSING DATA IMPACT
   ↓
   | Показател             | Score (1–10) | Status |
   |-----------------------|--------------|--------|
   | Noise Level           |              | 🟢     |
   | Bias Score            |              | 🟢     |
   | Missing Data Impact   |              | 🟢     |
   | Overall Trust Level   | High/Med/Low | 🟢     |

6️⃣ 6.6 RISK ENGINE FOR LOW RELIABILITY
   ↓
   - Ако Adjusted Reliability < 0.75 → автоматични действия:
     - Увеличаване на variance в симулациите (Блок 15)
     - По-висок Risk Flag в Блок 16
     - Намаляване на confidence в Блок 17
     - Препоръка за Live Refresh

7️⃣ 6.7 AI EXTRACTION & SYSTEM-WIDE RECOMMENDATIONS
   ↓
   - Кои данни са най-надеждни
   - Кои данни имат най-голям риск
   - Препоръки за Блок 7, 8, 10, 15
   - Обща оценка на информационната база на мача

8️⃣ 6.8 SOURCE CONFIDENCE (ФИНАЛНА)
   ↓
   | Поле                          | Стойност |
   |-------------------------------|----------|
   | Общ Data Quality Score        | __ /10   |
   | Adjusted Reliability          | __ /1.0  |
   | Коментар                      |          |

🔷 DOUBLE CHECK & VALIDATION (6.9)
9️⃣ 6.9 AUTO VALIDATION
    - Всички freshness, consistency и reliability фактори оценени → ✅
    - Adjusted Reliability изчислен и готов за прилагане → ✅
    - Impact върху следващите блокове дефиниран → ✅
    - Cross-check с Блок 0 и 5 → ✅

🔷 ИЗЛИЗАНЕ ОТ БЛОК 6
10️⃣ Global State Update → Adjusted Reliability + всички оценки се записват и стават задължителни за всички следващи блокове
    ↓
11️⃣ Handover Summary към Блок 7:
     - Adjusted Reliability Score
     - Noise / Bias / Missing Impact
     - Risk Flags за ниска надеждност
     - Препоръки за следващите блокове
    ↓
12️⃣ FINAL DOUBLE CHECK
     - Ако всичко е 🟢 → BLOCK 6 STATUS: COMPLETE
     - Ако има 🔴 пропуск → 🔄 АВТОМАТИЧНО ВРЪЩАНЕ
    ↓
13️⃣ Предаване към Блок 7 (автоматично)

🔷 BLOCK 6 STATUS
**BLOCK 6 STATUS: COMPLETE** 🟢 100%

═══════════════════════════════════════════════════════════════════════════════
✅ Grok следва точно стрелките. Adjusted Reliability се прилага автоматично в цялата система след този блок.


