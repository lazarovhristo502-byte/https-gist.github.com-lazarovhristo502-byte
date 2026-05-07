
🟦 X MODEL v2.4 — БЛОК 5 — RAW FORM ENGINE (ULTRA DETAILED RECENT PERFORMANCE)
═══════════════════════════════════════════════════════════════════════════════
🔷 5.0 CORE RULES (ВАЖАТ ЗА ЦЕЛИЯ БЛОК)
🟢 Блок 5 събира и структурира RAW данни за формата на двата отбора.
🔴 ЗАБРАНЕНО: обобщения, крайни изводи или прогнози — само RAW данни и изчисления.
🟢 Всичко се обработва **точка по точка** по стрелките.
🟢 След всяка точка → Status Marker
🟢 След целия блок → DOUBLE CHECK + Global State Update
🟢 Използва данните от Блок 0–4 (Global State)

🔷 ВЛИЗАНЕ В БЛОК 5
1. Получава данни от Блок 0–4 (Global State)
   ↓
2. 🛠️ ЗАДЪЛЖИТЕЛНИ TOOL CALLS 
   - web_search + browse_page → последни мачове, xG, shots, PPDA, xT (Flashscore, Sofascore, FBref)
   - code_execution → weighted xG и всички формули
   ↓
3. Започва обработка по стрелките (не прескача нищо)

🔷 ОБРАБОТКА — ПОТОК НА БЛОК 5

1️⃣ 5.1 LAST 7 MATCHES — DETAIL (Weighted xG)
   ↓
   **ДОМАКИН**
   | # | Съперник | H/A | Резултат | Голове | xG | xGA | xG diff | Удари | В целта | PPDA | xT | Тегло | Status |
   |---|----------|-----|----------|--------|----|-----|---------|--------|---------|------|----|-------|--------|
   
   **ГОСТ**
   | # | Съперник | H/A | Резултат | Голове | xG | xGA | xG diff | Удари | В целта | PPDA | xT | Тегло | Status |

2️⃣ 5.2 MATCHES 8–14 (CONTEXT)
   ↓
   **ДОМАКИН**
   | # | Съперник | Резултат | Status |
   |---|----------|----------|--------|
   
   **ГОСТ**
   | # | Съперник | Резултат | Status |

3️⃣ 5.3 H2H (LAST 2 MATCHES)
   ↓
   | Дата | Домакин | Гост | Резултат | xG | xGA | Status |

4️⃣ 5.4 COMMON OPPONENTS (3)
   ↓
   **ДОМАКИН**
   | Съперник | Резултат | xG | xGA | Status |
   |----------|----------|----|-----|--------|
   
   **ГОСТ**
   | Съперник | Резултат | xG | xGA | Status |

5️⃣ 5.5 PERFORMANCE vs LEVEL
   ↓
   **ДОМАКИН vs СИЛНИ / СРЕДНИ / СЛАБИ**  
   **ГОСТ vs СИЛНИ / СРЕДНИ / СЛАБИ**

6️⃣ 5.6 SUMMARY METRICS + Weighted Calculations
   ↓
   **ДОМАКИН**
   - Weighted xG Formula = Σ(xG × тегло) / Σ(тегло)
   - Weighted xG = 
   - Weighted xGA = 
   - Avg xG = 
   - Avg xGA = 
   - Avg xG diff = 
   - Goals avg = 
   - Goals vs xG = 
   - Clean sheets = 
   - Fail to score = 
   - Trend Slope (last 3 vs previous 4) = 
   - Home/Away Split (xG diff) =

   **ГОСТ** (същите метрики)

7️⃣ 5.7 FLAGS & COMPARISON PREP
   ↓
   | Флаг                        | Стойност | Status |
   |-----------------------------|----------|--------|
   | Missing Data                |          | 🟢     |
   | Suspicious Values           |          | 🟢     |
   | Estimated Data              |          | 🟢     |
   | Extreme Values              |          | 🟢     |
   | xG diff (Home vs Away)      |          | 🟢     |
   | Shots diff                  |          | 🟢     |
   | PPDA diff                   |          | 🟢     |

8️⃣ 5.8 SOURCE RULE (ПРИОРИТЕТ)
   ↓
   1. Flashscore (най-висок приоритет)  
   2. Sofascore  
   3. FBref  
   4. Opta  

9️⃣ 5.9 OPPONENT CLASSIFICATION
   ↓
   - Top → Strong  
   - Mid → Medium  
   - Bottom → Weak  

10️⃣ 5.10 HOME / AWAY FORM SPLIT
    ↓
    **ДОМАКИН**
    - Home xG avg (last 6) = 
    - Home xGA avg = 
    - Home Points per game = 
    - Home Win Rate % = 

    **ГОСТ**
    - Away xG avg (last 6) = 
    - Away xGA avg = 
    - Away Points per game = 
    - Away Win Rate % = 

11️⃣ 5.11 FORM CONSISTENCY & MOMENTUM + RISK FLAGS
    ↓
    | Показател                    | Home | Away | Status |
    |------------------------------|------|------|--------|
    | Form Consistency (1–10)      |      |      | 🟢     |
    | Momentum (last 3 matches)    |      |      | 🟢     |
    | Variance in xG               |      |      | 🟢     |
    | High Form + High Fatigue     |      |      | 🟢     |
    | Overperformance vs xG        |      |      | 🟢     |

12️⃣ 5.12 AI EXTRACTION (КЛЮЧОВИ RAW ИЗВОДИ)
    ↓
    - Най-силни тенденции в последните 7 мача
    - Най-големи разлики Home vs Away
    - Основни проблеми / предимства
    - Weighted xG / xGA сравнение
    - Trend Slope и Performance vs Level
    - Препоръки за следващите блокове

13️⃣ 5.13 SOURCE CONFIDENCE
    ↓
    | Поле                          | Стойност |
    |-------------------------------|----------|
    | Общ Source Confidence         | __ /10   |
    | Надеждност на xG данни        | __ /10   |
    | Надеждност на Home/Away Split | __ /10   |
    | Коментар                      |          |

🔷 DOUBLE CHECK & VALIDATION (5.14)
14️⃣ 5.14 AUTO VALIDATION + RAW CHECK
    - Всички оригинални точки (5.1–5.11) покрити → ✅
    - Всички нови split, consistency и flags добавени → ✅
    - Weighted xG изчислен → ✅
    - Cross-check с Блок 3 и 4 → ✅

🔷 ИЗЛИЗАНЕ ОТ БЛОК 5
15️⃣ Global State Update → всички таблици, метрики, flags и extraction се записват
    ↓
16️⃣ Handover Summary към Блок 6:
     - Weighted xG / xGA + Home/Away Split
     - Form Consistency & Momentum
     - Risk & Warning Flags
     - Enhanced AI Extraction
     - Source Confidence
    ↓
17️⃣ FINAL DOUBLE CHECK
     - Ако всичко е 🟢 → BLOCK 5 STATUS: COMPLETE
     - Ако има 🔴 пропуск → 🔄 АВТОМАТИЧНО ВРЪЩАНЕ
    ↓
18️⃣ Предаване към Блок 6 (автоматично)

🔷 BLOCK 5 STATUS
**BLOCK 5 STATUS: COMPLETE** 🟢 100%

═══════════════════════════════════════════════════════════════════════════════
✅ Grok следва точно стрелките. Не прескача нито една точка.
При пропуск → автоматично връщане и обработка само на проблемната точка.














