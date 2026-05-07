🟦 X MODEL v2.2 — БЛОК 2 — STADIUM + WEATHER + REFEREE (MASTER FULL SCORING)
═══════════════════════════════════════════════════════════════════════════════
🔷 2.0 CORE RULES (ВАЖАТ ЗА ЦЕЛИЯ БЛОК)
🟢 Блок 2 определя условията на мача (стадион, време, съдия) и измерва влиянието им.
🔴 ЗАБРАНЕНО: прогнози за резултат, форма или тактика.
🟢 Всичко се обработва **точка по точка** по стрелките.
🟢 След всяка точка → Status Marker
🟢 След целия блок → DOUBLE CHECK + Global State Update
🟢 Използва данните от Блок 0 и Блок 1 (Global State)

🔷 ВЛИЗАНЕ В БЛОК 2
1. Получава данни от Блок 0 и Блок 1 (Global State)
   ↓
2. 🛠️ ЗАДЪЛЖИТЕЛНИ TOOL CALLS 
   - browse_page → AccuWeather / Windy (метео за точния стадион + дата + час)
   - web_search + browse_page → referee stats и история
   - code_execution → ако трябва за изчисления на impact
   ↓
3. Започва обработка по стрелките (не прескача нищо)

🔷 ОБРАБОТКА — ПОТОК НА БЛОК 2

1️⃣ 2.1 STADIUM DATA (RAW + SCORES)
   ↓
   | Поле                    | Стойност                          | Status |
   |-------------------------|-----------------------------------|--------|
   | Stadium Name            |                                   | 🟢     |
   | Capacity                |                                   | 🟢     |
   | Avg Attendance (2025/26)|                                   | 🟢     |
   | Home Crowd (%)          |                                   | 🟢     |
   | Away Crowd (%)          |                                   | 🟢     |
   | Pitch Size (L×W meters) |                                   | 🟢     |
   | Surface Type            | Natural / Artificial              | 🟢     |

   **STADIUM SCORES (1–10)**
   | Фактор                  | Score | Status |
   |-------------------------|-------|--------|
   | Pitch Quality           |       | 🟢     |
   | Pitch Wetness           |       | 🟢     |
   | Pitch Speed             |       | 🟢     |
   | Pitch Familiarity (Home)|       | 🟢     |
   | Pitch Familiarity (Away)|       | 🟢     |
   | Crowd Pressure          |       | 🟢     |
   | Stadium Intensity       |       | 🟢     |

2️⃣ 2.2 WEATHER DATA (RAW + SCORES)
   ↓
   | Поле                  | Стойност                  | Status |
   |-----------------------|---------------------------|--------|
   | Temperature (°C)      |                           | 🟢     |
   | Wind Speed (km/h)     |                           | 🟢     |
   | Wind Direction (°)    |                           | 🟢     |
   | Rain Probability (%)  |                           | 🟢     |
   | Rain Volume (mm)      |                           | 🟢     |
   | Humidity (%)          |                           | 🟢     |
   | Pressure (hPa)        |                           | 🟢     |
   | Cloud Cover (%)       |                           | 🟢     |
   | Visibility (km)       |                           | 🟢     |
   | UV Index              |                           | 🟢     |

   **WEATHER IMPACT SCORES (1–10) + Real-Time Adjustment**
   | Фактор                | Score | Real-Time Adjustment (ако Rain >40%) | Status |
   |-----------------------|-------|--------------------------------------|--------|
   | Temperature Impact    |       |                                      | 🟢     |
   | Wind Impact           |       |                                      | 🟢     |
   | Rain Impact           |       | -2 точки                             | 🟢     |
   | Humidity Impact       |       |                                      | 🟢     |
   | Visibility Impact     |       |                                      | 🟢     |
   | Overall Weather Impact|       |                                      | 🟢     |

3️⃣ 2.3 REFEREE DATA (RAW + SCORES)
   ↓
   | Поле                    | Стойност                  | Status |
   |-------------------------|---------------------------|--------|
   | Referee Name            |                           | 🟢     |
   | Fouls per Match         |                           | 🟢     |
   | Yellow Cards per Match  |                           | 🟢     |
   | Red Cards per Match     |                           | 🟢     |
   | Penalties per Match     |                           | 🟢     |

   **REFEREE SCORES (1–10)**
   | Фактор                  | Score | Status |
   |-------------------------|-------|--------|
   | Strictness              |       | 🟢     |
   | Flow (game continuity)  |       | 🟢     |
   | Control Level           |       | 🟢     |
   | Card Frequency Impact   |       | 🟢     |
   | Penalty Tendency Impact |       | 🟢     |

4️⃣ 2.4 CONDITION FLAGS
   ↓
   | Фактор                        | Score (1–10) | Status |
   |-------------------------------|--------------|--------|
   | Weather Severity              |              | 🟢     |
   | Pitch Condition Severity      |              | 🟢     |
   | Combined Condition Difficulty |              | 🟢     |
   | Match Disruption Level        |              | 🟢     |
   | Extreme Condition Flag        | (0/1)        | 🟢     |

5️⃣ 2.5 ENVIRONMENT IMPACT (LIGHT ANALYSIS)
   ↓
   | Фактор                          | Score (1–10) | Влияние (Home/Away/Neutral) | Кратко обяснение | Status |
   |---------------------------------|--------------|-----------------------------|------------------|--------|
   | Home Advantage                  |              |                             |                  | 🟢     |
   | Pitch Compatibility (Home)      |              |                             |                  | 🟢     |
   | Pitch Compatibility (Away)      |              |                             |                  | 🟢     |
   | Weather Effect                  |              |                             |                  | 🟢     |
   | Weather Advantage               |              |                             |                  | 🟢     |
   | Referee Impact                  |              |                             |                  | 🟢     |
   | Referee Advantage               |              |                             |                  | 🟢     |
   | Crowd Influence                 |              |                             |                  | 🟢     |
   | Overall Environmental Advantage |              |                             |                  | 🟢     |

🔷 DOUBLE CHECK & VALIDATION (2.6)
6️⃣ 2.6 AUTO VALIDATION
   - Всички RAW полета попълнени → ✅
   - Всички Scores (1–10) попълнени → ✅
   - Real-Time Adjustment приложен (при дъжд) → ✅
   - Advantage определен навсякъде → ✅
   - Логическа връзка с Блок 0 (стадион и дата) → ✅
   - Extreme Condition Flag проверен → ✅

🔷 ИЗЛИЗАНЕ ОТ БЛОК 2
7️⃣ Global State Update → всички таблици, scores, flags и impact се записват
   ↓
8️⃣ Handover Summary към Блок 3:
    - Stadium Scores + Pitch conditions
    - Weather Impact Scores + Real-Time Adjustment
    - Referee Scores + Tendencies
    - Overall Environmental Advantage
    - Condition Flags + Extreme Flag
    - Adjusted Reliability (обновен)
   ↓
9️⃣ FINAL DOUBLE CHECK
    - Ако всичко е 🟢 → BLOCK 2 STATUS: COMPLETE
    - Ако има 🔴 пропуск → 🔄 АВТОМАТИЧНО ВРЪЩАНЕ само към пропуснатата точка
   ↓
10️⃣ Предаване към Блок 3 (автоматично)

🔷 BLOCK 2 STATUS
**BLOCK 2 STATUS: COMPLETE** 🟢 100%

═══════════════════════════════════════════════════════════════════════════════
✅ Grok следва точно стрелките. Не прескача нито една точка.
При пропуск → автоматично връщане и обработка само на проблемната точка.


 🚀
