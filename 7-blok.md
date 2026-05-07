🟦 X MODEL v2.4 — БЛОК 7 — TEAM STATE & PLAYER STATE ENGINE
═══════════════════════════════════════════════════════════════════════════════
🔷 7.0 CORE RULES (ВАЖАТ ЗА ЦЕЛИЯ БЛОК)
🟢 Блок 7 определя цялостното състояние на отбора и ключовите играчи (физическо, психическо, тактическо, възстановяване).
🔴 ЗАБРАНЕНО: тактика, matchups, xG или каквито и да е прогнози за резултат.
🟢 Всичко се обработва **точка по точка** по стрелките.
🟢 След всяка точка → Status Marker
🟢 След целия блок → DOUBLE CHECK + Global State Update
🟢 Използва данните от Блок 0–6 (Global State + Adjusted Reliability)

🔷 ВЛИЗАНЕ В БЛОК 7
1. Получава всички данни от Блок 0–6 (Global State + Adjusted Reliability)
   ↓
2. 🛠️ ЗАДЪЛЖИТЕЛНИ TOOL CALLS 
   - web_search + browse_page → актуални новини, training reports, press conferences, player interviews
   - browse_page → recovery и fatigue data
   ↓
3. Започва обработка по стрелките (не прескача нищо)

🔷 ОБРАБОТКА — ПОТОК НА БЛОК 7

1️⃣ 7.1 OVERALL TEAM STATE
   ↓
   | Показател                    | Home | Away | Adjusted by Reliability | Status |
   |------------------------------|------|------|-------------------------|--------|
   | Physical Condition (1–10)    |      |      |                         | 🟢     |
   | Mental Condition (1–10)      |      |      |                         | 🟢     |
   | Tactical Readiness (1–10)    |      |      |                         | 🟢     |
   | Recovery Level (1–10)        |      |      |                         | 🟢     |
   | Overall Team State (1–10)    |      |      |                         | 🟢     |
    ### 🔷 БЛОК 7 — TEAM STATE & PLAYER STATE ENGINE (Домашкин vs Гост)

**7.1 OVERALL TEAM STATE**  
| Показател | Home | Away | Adjusted by Reliability | Status |
|-----------|------|------|-------------------------|--------|
| Physical Condition (1–10) | ... | ... | ... | 🟢 |
| Mental Condition (1–10) | ... | ... | ... | 🟢 |
| Tactical Readiness (1–10) | ... | ... | ... | 🟢 |
| Recovery Level (1–10) | ... | ... | ... | 🟢 |
| Overall Team State (1–10) | ... | ... | ... | 🟢 |

**7.2 KEY PLAYER STATE (ТОП 6–8 ИГРАЧИ)**  
**ДОМАКИН**  
| Играч | Physical | Mental | Form | Fatigue | Role Readiness | Overall State (1–10) | Status |
|-------|----------|--------|------|---------|----------------|----------------------|--------|
| [Име] | ... | ... | ... | ... | ... | ... | 🟢 |
| ... | ... | ... | ... | ... | ... | ... | 🟢 |

**ГОСТ** *(същата таблица)*

**7.3 FATIGUE & RECOVERY MATRIX**  
**ДОМАКИН**  
| Категория | Score (1–10) | Status |
|-----------|--------------|--------|
| Squad Fatigue | ... | 🟢 |
| Key Players Fatigue | ... | 🟢 |
| Recovery Potential | ... | 🟢 |

**ГОСТ** *(аналогично)*

**7.4 MENTAL & PSYCHOLOGICAL STATE**  
| Фактор | Home | Away | Status |
|--------|------|------|--------|
| Team Confidence | ... | ... | 🟢 |
| Pressure Level | ... | ... | 🟢 |
| Motivation | ... | ... | 🟢 |
| Leadership Strength | ... | ... | 🟢 |
| Psychological Edge | ... | ... | 🟢 |

**7.5 STATE SYNERGY & CONFLICTS**  
| Тип | Описание | Impact (1–10) | Status |

**7.6 ADJUSTED STATE BY RELIABILITY**  
- Final Adjusted Team State (Home) = ...  
- Final Adjusted Team State (Away) = ...

**7.7 AI EXTRACTION & KEY INSIGHTS**  
- Най-важните 3 състояния:  
- Най-големите рискове:  
- Как се взаимодейства с Block 2 (стадион/метео):  

**Status:** 🟢 100%
2️⃣ 7.2 KEY PLAYER STATE (ТОП 5–7 ИГРАЧИ)
   ↓
   **ДОМАКИН**
   | Играч | Physical | Mental | Form | Fatigue | Role Readiness | Overall State (1–10) | Status |
   |-------|----------|--------|------|---------|----------------|----------------------|--------|
   
   **ГОСТ**
   | Играч | Physical | Mental | Form | Fatigue | Role Readiness | Overall State (1–10) | Status |

3️⃣ 7.3 FATIGUE & RECOVERY MATRIX
   ↓
   **ДОМАКИН**
   | Категория               | Score (1–10) | Status |
   |-------------------------|--------------|--------|
   | Squad Fatigue           |              | 🟢     |
   | Key Players Fatigue     |              | 🟢     |
   | Recovery Potential      |              | 🟢     |
   | Travel Fatigue Impact   |              | 🟢     |
   
   **ГОСТ** (същата таблица)

4️⃣ 7.4 MENTAL & PSYCHOLOGICAL STATE
   ↓
   | Фактор                     | Home | Away | Status |
   |----------------------------|------|------|--------|
   | Team Confidence            |      |      | 🟢     |
   | Pressure Level             |      |      | 🟢     |
   | Motivation (from Block 1)  |      |      | 🟢     |
   | Leadership Strength        |      |      | 🟢     |
   | Psychological Edge         |      |      | 🟢     |

5️⃣ 7.5 STATE SYNERGY & CONFLICTS
   ↓
   | Тип                        | Описание | Impact (1–10) | Status |
   |----------------------------|----------|---------------|--------|
   | Positive Synergy           |          |               | 🟢     |
   | Potential Conflicts        |          |               | 🟢     |
   | Risk Areas                 |          |               | 🟢     |

6️⃣ 7.6 ADJUSTED STATE BY RELIABILITY (от Блок 6)
   ↓
   - Final Adjusted Team State (Home) = 
   - Final Adjusted Team State (Away) = 

7️⃣ 7.7 AI EXTRACTION & KEY INSIGHTS
   ↓
   - Най-важните 3 състояния, които влияят на мача
   - Най-големите рискове в състава
   - Как състоянието взаимодейства с условията от Блок 2
   - Препоръки за Блок 8, 10, 11 и 15

8️⃣ 7.8 SOURCE CONFIDENCE
   ↓
   | Поле                    | Стойност |
   |-------------------------|----------|
   | Общ State Confidence    | __ /10   |
   | Коментар                |          |

🔷 DOUBLE CHECK & VALIDATION (7.9)
9️⃣ 7.9 AUTO VALIDATION
    - Всички ключови играчи и фактори покрити → ✅
    - Adjusted Reliability приложен → ✅
    - Cross-check с Блок 3 и 4 → ✅
    - Логическа консистентност с предишни блокове → ✅

🔷 ИЗЛИЗАНЕ ОТ БЛОК 7
10️⃣ Global State Update → всички оценки и Adjusted State се записват
    ↓
11️⃣ Handover Summary към Блок 8:
     - Overall Team State
     - Key Player States
     - Fatigue & Mental Matrix
     - Synergy & Conflicts
     - Adjusted State by Reliability
     - AI Extraction & Insights
    ↓
12️⃣ FINAL DOUBLE CHECK
     - Ако всичко е 🟢 → BLOCK 7 STATUS: COMPLETE
     - Ако има 🔴 пропуск → 🔄 АВТОМАТИЧНО ВРЪЩАНЕ
    ↓
13️⃣ Предаване към Блок 8 (автоматично)

🔷 BLOCK 7 STATUS
**BLOCK 7 STATUS: COMPLETE** 🟢 100%

═══════════════════════════════════════════════════════════════════════════════
✅ Grok следва точно стрелките. Adjusted Reliability от Блок 6 се прилага автоматично.

