








🟦 X MODEL v2.3 — БЛОК 3 — PLAYER CONTEXT ENGINE (ULTRA DYNAMIC STATE)
═══════════════════════════════════════════════════════════════════════════════
🔷 3.0 CORE RULES (ВАЖАТ ЗА ЦЕЛИЯ БЛОК)
🟢 Блок 3 определя динамичното състояние на играчите (форма, умора, липси, роля, зависимост).
🔴 ЗАБРАНЕНО: пълни lineups, тактика, xG или каквито и да е прогнози.
🟢 Всичко се обработва **точка по точка** по стрелките.
🟢 След всяка точка → Status Marker
🟢 След целия блок → DOUBLE CHECK + Global State Update
🟢 Използва данните от Блок 0, 1 и 2 (Global State)

🔷 ВЛИЗАНЕ В БЛОК 3
1. Получава данни от Блок 0, 1 и 2 (Global State)
   ↓
2. 🛠️ ЗАДЪЛЖИТЕЛНИ TOOL CALLS 
   - web_search + browse_page → актуални absences, injuries, returns, lineups (60–90 мин. преди мача)
   - browse_page → player stats (минути, форма, fatigue, overperformance)
   ↓
3. Започва обработка по стрелките (не прескача нищо)

🔷 ОБРАБОТКА — ПОТОК НА БЛОК 3

1️⃣ 3.1 PRIORITY SYSTEM (ТЕЖЕСТИ)
   ↓
   | Фактор          | Тежест |
   |-----------------|--------|
   | Absences        | 30%    |
   | Fatigue         | 25%    |
   | Form            | 20%    |
   | Role Change     | 15%    |
   | Mental State    | 10%    |

2️⃣ 3.2 KEY PLAYER CONTEXT (ТОП 3–5 ИГРАЧИ ЗА ВСЕКИ ОТБОР)
   ↓
   **ДОМАКИН**
   | Играч | Позиция | Голове | Асистенции | Минути | Роля | Важност (1–10) | Status |
   |-------|---------|--------|------------|--------|------|----------------|--------|
   
   **ГОСТ**
   | Играч | Позиция | Голове | Асистенции | Минути | Роля | Важност (1–10) | Status |

3️⃣ 3.3 ABSENCES & RETURNS + Official Lineups Check
   ↓
   **ДОМАКИН**
   | Играч | Статус | Причина | Връщане | Match Fitness | Влияние (1–10) | Status |
   |-------|--------|---------|---------|---------------|----------------|--------|
   
   **ГОСТ**
   | Играч | Статус | Причина | Връщане | Match Fitness | Влияние (1–10) | Status |

4️⃣ 3.4 WORKLOAD & FATIGUE
   ↓
   **ДОМАКИН**
   | Играч | Мин (14 дни) | Мин (30 дни) | Fatigue (1–10) | Status |
   |-------|--------------|--------------|----------------|--------|
   
   **ГОСТ**
   | Играч | Мин (14 дни) | Мин (30 дни) | Fatigue (1–10) | Status |

5️⃣ 3.5 PLAYER FORM & TREND
   ↓
   **ДОМАКИН**
   | Играч | Форма (1–10) | Trend (↑ / ↓ / →) | Status |
   |-------|--------------|-------------------|--------|
   
   **ГОСТ**
   | Играч | Форма (1–10) | Trend (↑ / ↓ / →) | Status |

6️⃣ 3.6 OVERPERFORMANCE / REGRESSION
   ↓
   **ДОМАКИН**
   | Играч | Form vs Avg | Regression Risk (1–10) | Status |
   |-------|-------------|------------------------|--------|
   
   **ГОСТ**
   | Играч | Form vs Avg | Regression Risk (1–10) | Status |

7️⃣ 3.7 ROLE CHANGE IMPACT
   ↓
   **ДОМАКИН**
   | Играч | Обичайна позиция | Текуща позиция | Impact (1–10) | Status |
   |-------|------------------|----------------|---------------|--------|
   
   **ГОСТ**
   | Играч | Обичайна позиция | Текуща позиция | Impact (1–10) | Status |

8️⃣ 3.8 MENTAL STATE
   ↓
   **ДОМАКИН**
   | Играч | Confidence (1–10) | Pressure (1–10) | Status |
   |-------|-------------------|-----------------|--------|
   
   **ГОСТ**
   | Играч | Confidence (1–10) | Pressure (1–10) | Status |

9️⃣ 3.9 TEAM DEPENDENCY + Weighted Dependency Score
   ↓
   **ДОМАКИН**
   | Играч | Dependency (1–10) | Weighted Dependency Score | Status |
   |-------|-------------------|---------------------------|--------|
   
   **ГОСТ**
   | Играч | Dependency (1–10) | Weighted Dependency Score | Status |

10️⃣ 3.10 PLAYER STATUS (FINAL TAG)
    ↓
    **ДОМАКИН**
    | Играч | Status (Fit / Tired / Risk / Out) | Status |
    |-------|-----------------------------------|--------|
    
    **ГОСТ**
    | Играч | Status (Fit / Tired / Risk / Out) | Status |

11️⃣ 3.11 TEAM CONDITION SUMMARY
    ↓
    **ДОМАКИН**
    - Condition (1–10): 
    - Основен проблем: 
    - Основно предимство: 

    **ГОСТ**
    - Condition (1–10): 
    - Основен проблем: 
    - Основно предимство: 

12️⃣ 3.12 DISTORTION CHECK
    ↓
    - High Form + High Fatigue → WARNING
    - Overperformance + Low Sample Size → WARNING
    - High Mental Pressure + Key Player → WARNING
    - Form vs Reality mismatch → WARNING

13️⃣ 3.13 RELIABILITY
    ↓
    Reliability = (min(1, matches / 5) + Data Quality) / 2

14️⃣ 3.14 AI EXTRACTION (КЛЮЧОВИ ИЗВОДИ)
    ↓
    - Най-важни ключови играчи
    - Най-големи липси / рискове
    - Основни проблеми в състава
    - Най-силни и слаби страни

15️⃣ 3.15 КАК СЕ ПОЛЗВА (HANDOVER)
    ↓
    - Подготвя Блок 4 (lineups + matchups)
    - Подготвя Блок 7 (състояние и психология)
    - Подготвя Блок 8 (реална сила)

16️⃣ 3.16 SOURCE CONFIDENCE
    ↓
    | Поле                    | Стойност |
    |-------------------------|----------|
    | Общ Source Confidence   | __ /10   |
    | Надеждност на absences  | __ /10   |
    | Надеждност на форма     | __ /10   |
    | Коментар                |          |

🔷 DOUBLE CHECK & VALIDATION (3.17)
17️⃣ 3.17 AUTO VALIDATION
    - Всички ключови секции покрити → ✅
    - Distortion Check и Reliability направени → ✅
    - AI Extraction готов → ✅
    - Cross-check с предишни блокове → ✅
    - Няма дублиране с Блок 4 → ✅

🔷 ИЗЛИЗАНЕ ОТ БЛОК 3
18️⃣ Global State Update → всички таблици, оценки, warnings и extraction се записват
    ↓
19️⃣ Handover Summary към Блок 4:
     - Key Players + Важност
     - Absences, Fatigue, Form, Over/Regression
     - Role Changes, Mental, Dependency
     - Team Condition + Warnings
     - AI Extraction
     - Reliability & Source Confidence
    ↓
20️⃣ FINAL DOUBLE CHECK
     - Ако всичко е 🟢 → BLOCK 3 STATUS: COMPLETE
     - Ако има 🔴 пропуск → 🔄 АВТОМАТИЧНО ВРЪЩАНЕ само към пропуснатата точка
    ↓
21️⃣ Предаване към Блок 4 (автоматично)

🔷 BLOCK 3 STATUS
**BLOCK 3 STATUS: COMPLETE** 🟢 100%

═══════════════════════════════════════════════════════════════════════════════
✅ Grok следва точно стрелките. Не прескача нито една точка.
При пропуск → автоматично връщане и обработка само на проблемната точка.












 🚀
