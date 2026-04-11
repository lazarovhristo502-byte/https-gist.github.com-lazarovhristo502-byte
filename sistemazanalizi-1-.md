# 🟦 БЛОК 0 — ДОПЪЛНИТЕЛНИ RAW ПОЛЕТА (v400 EXTENDED)

## 0.5. REFEREE NORMALIZATION (RAW)
| Поле | Стойност |
|------|----------|
| 0.5.1. Referee Tempo Impact (1–10) | |
| 0.5.2. Referee Aggression Index (1–10) | |
| 0.5.3. Foul-to-Card Ratio | |
| 0.5.4. Penalty Frequency (на мач) | |
| 0.5.5. VAR Overturn Rate (%) | |
| 0.5.6. Home Bias (%) | |
| 0.5.7. Away Bias (%) | |
| 0.5.8. Bias Normalization Formula | x = (HB - AB) / (HB + AB) |

## 0.6. CROSS-SOURCE WEIGHTING (RAW)
| Източник | Тегло | Причина |
|----------|--------|----------|
| Flashscore | 0.50 | Приоритетен източник |
| Sofascore | 0.30 | Детайлни статистики |
| Opta/FBref | 0.20 | Потвърждение и корекции |

## 0.7. DATA CONSISTENCY CHECK (RAW)
- 0.7.1. Проверка за разлика в xG > 0.20 между източници  
- 0.7.2. Проверка за разлика в фалове > 10%  
- 0.7.3. Проверка за разлика в картони > 0.5  
- 0.7.4. Проверка за разлика в possession > 5%  
- 0.7.5. Ако има разминаване → теглово усредняване

## 0.8. REFEREE IMPACT MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 0.8.1. Tempo Modifier | |
| 0.8.2. Card Modifier | |
| 0.8.3. Foul Modifier | |
| 0.8.4. Penalty Modifier | |
| 0.8.5. VAR Modifier | |

## 0.9. OUTPUT → ПОДАВАНЕ КЪМ ДРУГИ БЛОКОВЕ
| Данни | Използва се в |
|-------|----------------|
| Tempo Impact | Block 7 (Tactical Tempo) |
| Aggression Index | Block 11 (Risk Engine) |
| Bias | Block 15 (Simulation) |
| VAR Rate | Block 16 (Validation) |
| Penalty Frequency | Block 17 (Final Model) |






# 🟦 БЛОК 1 — ДОПЪЛНИТЕЛНИ RAW ПОЛЕТА (v400 EXTENDED)

## 1.6. SQUAD STABILITY INDEX (RAW)
| Поле | Стойност |
|------|----------|
| 1.6.1. Среден брой промени в стартовите 11 (последни 5 мача) | |
| 1.6.2. Среден брой контузени титуляри | |
| 1.6.3. Среден брой ротации на мач | |
| 1.6.4. Stability Score (1–10) | |
| 1.6.5. Причина за Stability Score | |

## 1.7. INJURY CLUSTER DETECTION (RAW)
| Показател | Стойност |
|-----------|----------|
| 1.7.1. Брой контузени играчи по позиции | |
| 1.7.2. Клъстер (Да/Не) | |
| 1.7.3. Най-засегната линия (DEF/MID/ATT) | |
| 1.7.4. Injury Severity Index (1–10) | |
| 1.7.5. Очаквано влияние върху състава | |

## 1.8. TRAVEL FATIGUE NORMALIZATION (RAW)
| Поле | Стойност |
|------|----------|
| 1.8.1. Общо изминати километри (последни 30 дни) | |
| 1.8.2. Средно време на пътуване | |
| 1.8.3. Time Zone Changes | |
| 1.8.4. Travel Fatigue Score (1–10) | |
| 1.8.5. Причина за Travel Fatigue Score | |

## 1.9. COACH TACTICAL PROFILE (RAW)
| Показател | Стойност |
|-----------|----------|
| 1.9.1. Основна формация | |
| 1.9.2. Алтернативна формация | |
| 1.9.3. Пресинг интензитет (1–10) | |
| 1.9.4. Темпо на игра (1–10) | |
| 1.9.5. Директност (1–10) | |
| 1.9.6. Ротационна политика (1–10) | |
| 1.9.7. Coach Stability Index (1–10) | |

## 1.10. HOME/AWAY NORMALIZATION (RAW)
| Показател | Домакин | Гост |
|-----------|---------|------|
| 1.10.1. Home xG Boost | | |
| 1.10.2. Away xG Drop | | |
| 1.10.3. Home Momentum Boost | | |
| 1.10.4. Away Fatigue Penalty | | |

## 1.11. OUTPUT → ПОДАВАНЕ КЪМ ДРУГИ БЛОКОВЕ
| Данни | Използва се в |
|-------|----------------|
| Squad Stability | Block 3 (Workload & Fatigue) |
| Injury Clusters | Block 3 (Absences) |
| Travel Fatigue | Block 5 (Form Normalization) |
| Coach Profile | Block 7 (Tactical Shape) |
| Home/Away Factors | Block 5, Block 15 |






# 🟦 БЛОК 2 — ДОПЪЛНИТЕЛНИ RAW ПОЛЕТА (v400 EXTENDED)

## 2.4. METEO IMPACT MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 2.4.1. Wind Impact (1–10) | |
| 2.4.2. Rain Impact (1–10) | |
| 2.4.3. Temperature Impact (1–10) | |
| 2.4.4. Humidity Impact (1–10) | |
| 2.4.5. Pitch Friction Coefficient | |
| 2.4.6. Meteo Composite Score (1–10) | |

### Формули:
- Wind Impact = min(10, (скорост на вятъра / 2))  
- Rain Impact = (mm валежи × 0.8)  
- Pitch Friction = (влажност × 0.01) + (валежи × 0.05)

---

## 2.5. STADIUM PERFORMANCE MODIFIERS (RAW)
| Показател | Стойност |
|-----------|----------|
| 2.5.1. Home Advantage Modifier (1–10) | |
| 2.5.2. Crowd Pressure Index (1–10) | |
| 2.5.3. Pitch Size Effect (1–10) | |
| 2.5.4. Turf Type Modifier (1–10) | |
| 2.5.5. Stadium Noise Level (dB) | |

### Бележки:
- Pitch Size Effect = базирано на площ (дължина × ширина)  
- Turf Modifier = 1–10 според настилката (изкуствен → по-нисък контрол)

---

## 2.6. WEATHER → TACTICAL IMPACT (RAW)
| Тактически елемент | Влияние (1–10) | Бележка |
|--------------------|----------------|---------|
| 2.6.1. Pressing Efficiency | | |
| 2.6.2. Long Ball Efficiency | | |
| 2.6.3. Passing Accuracy | | |
| 2.6.4. Sprint Frequency | | |
| 2.6.5. Defensive Line Height | | |

---

## 2.7. WEATHER → PLAYER IMPACT (RAW)
| Показател | Стойност |
|-----------|----------|
| 2.7.1. Fatigue Increase (%) | |
| 2.7.2. Injury Risk Increase (%) | |
| 2.7.3. Hydration Loss (%) | |
| 2.7.4. Temperature Stress Score (1–10) | |

---

## 2.8. STADIUM → BALL BEHAVIOR MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 2.8.1. Ball Speed Reduction (%) | |
| 2.8.2. Bounce Height Reduction (%) | |
| 2.8.3. Slip Probability (%) | |
| 2.8.4. Control Difficulty Score (1–10) | |

---

## 2.9. OUTPUT → ПОДАВАНЕ КЪМ ДРУГИ БЛОКОВЕ
| Данни | Използва се в |
|-------|----------------|
| Meteo Composite Score | Block 5 (Form Normalization) |
| Wind/Rain Impact | Block 7 (Tactical Shape) |
| Pitch Friction | Block 11 (Risk Engine) |
| Crowd Pressure | Block 15 (Simulation) |
| Ball Behavior Model | Block 17 (Final Model) |




# 🟦 БЛОК 3 — ДОПЪЛНИТЕЛНИ RAW ПОЛЕТА (v400 EXTENDED)

## 3.8. INJURY SEVERITY MODEL (RAW)
| Поле | Стойност |
|------|----------|
| 3.8.1. Тип контузия | |
| 3.8.2. Severity Score (1–10) | |
| 3.8.3. Средно време за възстановяване (дни) | |
| 3.8.4. Риск от рецидив (%) | |
| 3.8.5. Impact on Team (1–10) | |

### Severity Score правила:
- 1–3 → лека травма  
- 4–6 → средна  
- 7–10 → тежка  

---

## 3.9. PLAYER AVAILABILITY PROBABILITY (RAW)
| Показател | Стойност |
|-----------|----------|
| 3.9.1. Медицинска готовност (%) | |
| 3.9.2. Тренировъчна готовност (%) | |
| 3.9.3. Match Fitness (%) | |
| 3.9.4. Availability Probability (%) | |
| 3.9.5. Причина за стойността | |

### Формула:
Availability = (Medical × 0.5) + (Training × 0.3) + (Fitness × 0.2)

---

## 3.10. FATIGUE DECAY MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 3.10.1. Минути последни 7 дни | |
| 3.10.2. Минути последни 14 дни | |
| 3.10.3. Минути последни 30 дни | |
| 3.10.4. Recovery Rate (1–10) | |
| 3.10.5. Fatigue Decay Score (1–10) | |

### Формула:
Fatigue Decay = (Min30 × 0.5) + (Min14 × 0.3) + (Min7 × 0.2)

---

## 3.11. POSITIONAL DEPENDENCY (RAW)
| Позиция | Dependency Score (1–10) | Бележка |
|---------|--------------------------|---------|
| GK | | |
| CB | | |
| FB | | |
| DM | | |
| CM | | |
| AM | | |
| W | | |
| CF | | |

### Бележка:
- GK/CB/DM имат най-висока dependency (структурни позиции)

---

## 3.12. PLAYER IMPACT LOSS (RAW)
| Показател | Стойност |
|-----------|----------|
| 3.12.1. Impact Score (1–10) | |
| 3.12.2. Missing Minutes (последни 5 мача) | |
| 3.12.3. Replacement Quality (1–10) | |
| 3.12.4. Net Impact Loss | |

### Формула:
Net Impact Loss = Impact Score – Replacement Quality

---

## 3.13. WORKLOAD NORMALIZATION (RAW)
| Показател | Стойност |
|-----------|----------|
| 3.13.1. Средни минути на мач | |
| 3.13.2. Средни минути последни 5 мача | |
| 3.13.3. Отклонение (%) | |
| 3.13.4. Workload Stress Score (1–10) | |

---

## 3.14. PLAYER CONSISTENCY INDEX (RAW)
| Показател | Стойност |
|-----------|----------|
| 3.14.1. Последователност на представяне (1–10) | |
| 3.14.2. Отклонение от средното | |
| 3.14.3. Form Stability Score (1–10) | |

---

## 3.15. OUTPUT → ПОДАВАНЕ КЪМ ДРУГИ БЛОКОВЕ
| Данни | Използва се в |
|-------|----------------|
| Injury Severity | Block 11 (Risk Engine) |
| Availability Probability | Block 4, Block 5 |
| Fatigue Decay | Block 6 (Player Impact) |
| Positional Dependency | Block 7 (Tactical Shape) |
| Impact Loss | Block 15 (Simulation) |
| Workload Stress | Block 6, Block 11 |
| Consistency Index | Block 5, Block 7 |






# 🟦 БЛОК 4 — ДОПЪЛНИТЕЛНИ RAW ПОЛЕТА (v400 EXTENDED)

## 4.12. TACTICAL ROLE WEIGHTS (RAW)
| Роля | Weight (1–10) | Бележка |
|------|----------------|----------|
| GK | | |
| FB | | |
| CB | | |
| DM | | |
| CM | | |
| AM | | |
| W | | |
| CF | | |

### Бележки:
- CB/DM имат най-висок структурен weight  
- W/CF имат най-висок атакуващ weight  

---

## 4.13. POSITIONAL DEPENDENCY (RAW)
| Позиция | Dependency Score (1–10) | Бележка |
|---------|--------------------------|---------|
| GK | | |
| CB | | |
| FB | | |
| DM | | |
| CM | | |
| AM | | |
| W | | |
| CF | | |

### Бележка:
- Dependency Score идва от Block 3 → 3.11  

---

## 4.14. SUBSTITUTION IMPACT MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 4.14.1. Средна минута на първа смяна | |
| 4.14.2. Среден брой смени | |
| 4.14.3. Impact Score на смени (1–10) | |
| 4.14.4. Quality Drop-Off (1–10) | |
| 4.14.5. Replacement Efficiency (%) | |

### Формула:
Replacement Efficiency = (Средно представяне на резервите / титулярите) × 100

---

## 4.15. SQUAD DEPTH NORMALIZATION (RAW)
| Линия | Depth Score (1–10) | Качествени резерви | Normalized Depth |
|--------|----------------------|----------------------|--------------------|
| Вратар | | | |
| Защита | | | |
| Халфове | | | |
| Нападение | | | |

### Формула:
Normalized Depth = Depth Score × (1 + (бр. резерви × 0.1))

---

## 4.16. ROTATION LOGIC (RAW)
| Показател | Стойност |
|-----------|----------|
| 4.16.1. Rotation Probability (%) | |
| 4.16.2. Причина | |
| 4.16.3. Minutes Threshold | |
| 4.16.4. Fatigue Trigger | |
| 4.16.5. Tactical Rotation Trigger | |

### Бележки:
- Rotation Probability се влияе от Block 3 (fatigue + availability)  
- Tactical Trigger идва от Block 7  

---

## 4.17. PLAYER AVAILABILITY INTEGRATION (RAW)
| Играч | Availability (%) | Impact Score | Final Availability Weight |
|--------|-------------------|--------------|----------------------------|
|        |                   |              |                            |
|        |                   |              |                            |
|        |                   |              |                            |

### Формула:
Final Availability Weight = Availability × (Impact Score / 10)

---

## 4.18. STARTING XI RELIABILITY INDEX (RAW)
| Показател | Стойност |
|-----------|----------|
| 4.18.1. Среден брой промени последни 5 мача | |
| 4.18.2. Injury Influence (1–10) | |
| 4.18.3. Fatigue Influence (1–10) | |
| 4.18.4. Tactical Influence (1–10) | |
| 4.18.5. Reliability Index (1–10) | |

### Формула:
Reliability = 10 – (Injury + Fatigue + Tactical) / 3

---

## 4.19. OUTPUT → ПОДАВАНЕ КЪМ ДРУГИ БЛОКОВЕ
| Данни | Използва се в |
|-------|----------------|
| Tactical Role Weights | Block 7 (Tactical Shape) |
| Positional Dependency | Block 7, Block 11 |
| Substitution Impact | Block 13 (Micro-Phases) |
| Depth Normalization | Block 15 (Simulation) |
| Rotation Logic | Block 15, Block 17 |
| Availability Weight | Block 6, Block 11 |
| Reliability Index | Block 5, Block 7 |








# 🟦 БЛОК 5 — ДОПЪЛНИТЕЛНИ RAW ПОЛЕТА (v400 EXTENDED)

## 5.11. OPPONENT STRENGTH ADJUSTMENT (RAW)
| Показател | Стойност |
|-----------|----------|
| 5.11.1. Strength Index на съперника (1–10) | |
| 5.11.2. Adjustment Factor | |
| 5.11.3. Коригиран xG | |
| 5.11.4. Коригиран xGA | |

### Формула:
Adjustment Factor = (Opponent Strength / 10)

Коригиран xG = xG × (1 – Adjustment Factor × 0.15)  
Коригиран xGA = xGA × (1 + Adjustment Factor × 0.15)

---

## 5.12. HOME/AWAY FORM NORMALIZATION (RAW)
| Показател | Домакин | Гост |
|-----------|---------|------|
| 5.12.1. Home Boost (%) | | |
| 5.12.2. Away Penalty (%) | | |
| 5.12.3. Коригиран xG | | |
| 5.12.4. Коригиран xGA | | |

### Бележки:
- Home Boost идва от Block 1 → 1.10  
- Away Penalty идва от Block 1 → 1.10  

---

## 5.13. FORM DECAY MODEL (RAW)
| Мач | Decay Weight | Бележка |
|-----|--------------|----------|
| 1 | 1.00 | най-актуален |
| 2 | 0.95 | |
| 3 | 0.90 | |
| 4 | 0.85 | |
| 5 | 0.80 | |
| 6 | 0.75 | |
| 7 | 0.70 | |
| 8 | 0.65 | |
| 9 | 0.60 | |
| 10 | 0.55 | най-стар |

### Формула:
Final Weighted xG = Σ(xG × Decay Weight) / Σ(Decay Weight)

---

## 5.14. MOMENTUM RAW MODEL
| Показател | Стойност |
|-----------|----------|
| 5.14.1. Momentum Peaks | |
| 5.14.2. Momentum Drops | |
| 5.14.3. Net Momentum Score (1–10) | |
| 5.14.4. Momentum Stability (%) | |

### Бележки:
- Взима се от Sofascore Momentum Timeline  
- Няма анализ → само RAW стойности  

---

## 5.15. PPDA RAW MODEL
| Мач | PPDA | Пресинг зона | Бележка |
|-----|------|--------------|----------|
| 1 | | | |
| 2 | | | |
| 3 | | | |
| 4 | | | |
| 5 | | | |

### Допълнителни RAW полета:
- Средно PPDA последни 5 мача  
- PPDA variance  
- PPDA stability score  

---

## 5.16. xT (Expected Threat) RAW
| Мач | xT | xT Against | xT Diff |
|-----|----|------------|----------|
| 1 | | | |
| 2 | | | |
| 3 | | | |
| 4 | | | |
| 5 | | | |

### Бележки:
- xT Diff = xT – xT Against  
- RAW → без интерпретация  

---

## 5.17. POSSESSION ZONES RAW
| Зона | % Време | Бележка |
|------|---------|----------|
| Defensive Third | | |
| Middle Third | | |
| Attacking Third | | |

---

## 5.18. DEFENSIVE ACTIONS RAW
| Показател | Стойност |
|-----------|----------|
| 5.18.1. Interceptions | |
| 5.18.2. Tackles | |
| 5.18.3. Blocks | |
| 5.18.4. Clearances | |
| 5.18.5. Defensive Errors | |

---

## 5.19. PASSING MAP RAW
| Показател | Стойност |
|-----------|----------|
| 5.19.1. Средна дължина на пас | |
| 5.19.2. Progressive Passes | |
| 5.19.3. Key Passes | |
| 5.19.4. Switches of Play | |

---

## 5.20. HEAD-TO-HEAD RAW (последни 2 мача)
| Мач | Резултат | xG | xGA | Бележка |
|-----|----------|-----|------|----------|
| 1 | | | | |
| 2 | | | | |

---

## 5.21. SUPER-OPPONENTS RAW (3 общи силни съперника)
| Съперник | Мач | xG | xGA | Резултат |
|----------|------|-----|------|----------|
| | | | | |
| | | | | |
| | | | | |

---

## 5.22. FORM CONSISTENCY INDEX (RAW)
| Показател | Стойност |
|-----------|----------|
| 5.22.1. xG Variance | |
| 5.22.2. xGA Variance | |
| 5.22.3. Goal Variance | |
| 5.22.4. Consistency Score (1–10) | |

---

## 5.23. OUTPUT → ПОДАВАНЕ КЪМ ДРУГИ БЛОКОВЕ
| Данни | Използва се в |
|-------|----------------|
| Weighted xG/xGA | Block 6 (Player Impact) |
| Momentum | Block 7 (Tactical Shape) |
| PPDA | Block 7, Block 11 |
| xT | Block 7 |
| Possession Zones | Block 7 |
| Defensive Actions | Block 11 |
| H2H | Block 15 |
| Super-Opponents | Block 15 |
| Consistency Index | Block 11, Block 17 |






# 🟦 БЛОК 6 — ДОПЪЛНИТЕЛНИ RAW ПОЛЕТА (v400 EXTENDED)

## 6.1. PLAYER IMPACT BASE MODEL (RAW)
| Играч | Позиция | Impact Score (1–10) | Бележка |
|--------|----------|-----------------------|----------|
|        |          |                       |          |
|        |          |                       |          |
|        |          |                       |          |

### Бележки:
- Impact Score идва от Block 3 → 3.12  
- Няма анализ → само RAW стойности  

---

## 6.2. FATIGUE WEIGHTED IMPACT (RAW)
| Играч | Fatigue Score (1–10) | Impact Score | Weighted Impact |
|--------|------------------------|----------------|------------------|
|        |                        |                |                  |
|        |                        |                |                  |

### Формула:
Weighted Impact = Impact Score × (1 – Fatigue Score × 0.07)

---

## 6.3. AVAILABILITY WEIGHTED IMPACT (RAW)
| Играч | Availability (%) | Weighted Impact | Final Availability Impact |
|--------|-------------------|------------------|----------------------------|
|        |                   |                  |                            |
|        |                   |                  |                            |

### Формула:
Final Availability Impact = Weighted Impact × (Availability / 100)

---

## 6.4. TACTICAL FIT MODEL (RAW)
| Играч | Роля | Role Weight (1–10) | Fit Score (1–10) |
|--------|-------|----------------------|--------------------|
|        |       |                      |                    |
|        |       |                      |                    |

### Бележки:
- Role Weight идва от Block 4 → 4.12  
- Fit Score е RAW оценка от последните 5 мача  

---

## 6.5. MATCHUP DIFFICULTY (RAW)
| Играч | Срещу позиция | Difficulty (1–10) | Бележка |
|--------|----------------|--------------------|----------|
|        |                |                    |          |
|        |                |                    |          |

### Бележки:
- Difficulty се базира на форма на противниковата линия (Block 5)  

---

## 6.6. REPLACEMENT PENALTY (RAW)
| Играч | Replacement Quality (1–10) | Impact Score | Penalty |
|--------|------------------------------|----------------|----------|
|        |                              |                |          |
|        |                              |                |          |

### Формула:
Penalty = Impact Score – Replacement Quality

---

## 6.7. PLAYER SYNERGY MODEL (RAW)
| Играч | Синергия с | Synergy Score (1–10) | Бележка |
|--------|-------------|------------------------|----------|
|        |             |                        |          |
|        |             |                        |          |

### Бележки:
- RAW → без анализ  
- Синергия се базира на общи минути + пасови комбинации  

---

## 6.8. INSTABILITY INDEX (RAW)
| Играч | Form Variance | Minutes Variance | Instability Score (1–10) |
|--------|----------------|--------------------|-----------------------------|
|        |                |                    |                             |
|        |                |                    |                             |

### Формула:
Instability = (FormVar × 0.6) + (MinVar × 0.4)

---

## 6.9. PLAYER RISK MODIFIERS (RAW)
| Играч | Injury Risk (%) | Fatigue Risk (%) | Tactical Risk (1–10) | Total Risk |
|--------|------------------|--------------------|-------------------------|-------------|
|        |                  |                    |                         |             |
|        |                  |                    |                         |             |

### Формула:
Total Risk = (Injury × 0.4) + (Fatigue × 0.4) + (Tactical × 0.2)

---

## 6.10. FINAL PLAYER IMPACT SCORE (RAW)
| Играч | Availability Impact | Tactical Fit | Matchup Difficulty | Risk | Final Impact |
|--------|----------------------|----------------|----------------------|--------|----------------|
|        |                      |                |                      |        |                |
|        |                      |                |                      |        |                |

### Формула:
Final Impact = AvailabilityImpact × TacticalFit × (1 – Risk × 0.05)

---

## 6.11. OUTPUT → ПОДАВАНЕ КЪМ ДРУГИ БЛОКОВЕ
| Данни | Използва се в |
|-------|----------------|
| Final Impact | Block 7 (Tactical Shape) |
| Risk Modifiers | Block 11 (Risk Engine) |
| Replacement Penalty | Block 15 (Simulation) |
| Matchup Difficulty | Block 15 |
| Synergy | Block 13 (Micro-Phases) |
| Instability | Block 17 (Final Model) |






# 🟦 БЛОК 7 — ДОПЪЛНИТЕЛНИ RAW ПОЛЕТА (v400 EXTENDED)

## 7.1. BASE TACTICAL SHAPE (RAW)
| Показател | Стойност |
|-----------|----------|
| 7.1.1. Основна формация | |
| 7.1.2. Средна формация в защита | |
| 7.1.3. Средна формация в атака | |
| 7.1.4. Линии (височина) | |
| 7.1.5. Ширина | |
| 7.1.6. Компактност | |

---

## 7.2. TACTICAL ROLE INTEGRATION (RAW)
| Позиция | Role Weight | Dependency | Combined Tactical Weight |
|---------|--------------|------------|---------------------------|
| GK | | | |
| CB | | | |
| FB | | | |
| DM | | | |
| CM | | | |
| AM | | | |
| W | | | |
| CF | | | |

### Формула:
Combined Tactical Weight = (RoleWeight × 0.6) + (Dependency × 0.4)

---

## 7.3. TEAM TEMPO ENGINE (RAW)
| Показател | Стойност |
|-----------|----------|
| 7.3.1. Tempo Score (1–10) | |
| 7.3.2. Referee Tempo Modifier | |
| 7.3.3. Meteo Tempo Modifier | |
| 7.3.4. Final Tempo | |

### Формула:
Final Tempo = TempoScore × (1 – MeteoImpact × 0.05) × RefereeTempo

---

## 7.4. PRESSING ENGINE (RAW)
| Показател | Стойност |
|-----------|----------|
| 7.4.1. PPDA | |
| 7.4.2. Pressing Intensity (1–10) | |
| 7.4.3. Pressing Height | |
| 7.4.4. Pressing Efficiency (%) | |

### Бележки:
- PPDA идва от Block 5  
- Pressing Height = височина на линията  

---

## 7.5. TRANSITION MODEL (RAW)
| Тип преход | Скорост (1–10) | Ефективност (1–10) | Бележка |
|-------------|----------------|----------------------|----------|
| Defensive → Offensive | | | |
| Offensive → Defensive | | | |

---

## 7.6. BALL PROGRESSION MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 7.6.1. Progressive Passes | |
| 7.6.2. Progressive Runs | |
| 7.6.3. xT Contribution | |
| 7.6.4. Build-Up Efficiency (%) | |

---

## 7.7. RISK ZONES (RAW)
| Зона | Риск (1–10) | Причина |
|------|--------------|----------|
| Лява зона | | |
| Център | | |
| Дясна зона | | |

### Бележки:
- Рискът се влияе от Matchup Difficulty (Block 6)  

---

## 7.8. MATCHUP GEOMETRY (RAW)
| Линия | Предимство (1–10) | Недостатък (1–10) | Net Geometry |
|--------|---------------------|----------------------|----------------|
| Защита | | | |
| Халфове | | | |
| Атака | | | |

### Формула:
Net Geometry = Advantage – Disadvantage

---

## 7.9. TACTICAL STABILITY INDEX (RAW)
| Показател | Стойност |
|-----------|----------|
| 7.9.1. Form Stability | |
| 7.9.2. Player Instability | |
| 7.9.3. Tactical Variance | |
| 7.9.4. Stability Index (1–10) | |

### Формула:
Stability = 10 – (Instability × 0.7 + Variance × 0.3)

---

## 7.10. TACTICAL VOLATILITY (RAW)
| Показател | Стойност |
|-----------|----------|
| 7.10.1. Промени във формацията | |
| 7.10.2. Промени в ролите | |
| 7.10.3. Промени в линиите | |
| 7.10.4. Volatility Score (1–10) | |

---

## 7.11. FINAL TACTICAL SHAPE SCORE (RAW)
| Показател | Стойност |
|-----------|----------|
| 7.11.1. Tempo | |
| 7.11.2. Pressing | |
| 7.11.3. Transitions | |
| 7.11.4. Geometry | |
| 7.11.5. Stability | |
| 7.11.6. Volatility | |
| 7.11.7. Final Tactical Score | |

### Формула:
Final Tactical Score = (Tempo + Pressing + Geometry + Stability – Volatility) / 4

---

## 7.12. OUTPUT → ПОДАВАНЕ КЪМ ДРУГИ БЛОКОВЕ
| Данни | Използва се в |
|-------|----------------|
| Final Tactical Score | Block 11 (Risk Engine) |
| Tempo | Block 15 (Simulation) |
| Pressing | Block 15 |
| Geometry | Block 15 |
| Stability | Block 17 |
| Volatility | Block 17 |







# 🟦 БЛОК 8 — ДОПЪЛНИТЕЛНИ RAW ПОЛЕТА (v400 EXTENDED)

## 8.1. CHANCE CREATION ZONES (RAW)
| Зона | % Атаки | % Удари | Danger Score (1–10) |
|------|----------|----------|-----------------------|
| Лява зона | | | |
| Център | | | |
| Дясна зона | | | |

### Бележки:
- Danger Score = базирано на xT + shot quality  

---

## 8.2. CHANCE TYPES (RAW)
| Тип шанс | Брой | % от всички | Среден xG | Бележка |
|----------|-------|--------------|------------|----------|
| 8.2.1. Пробив | | | | |
| 8.2.2. Центриране | | | | |
| 8.2.3. Комбинация | | | | |
| 8.2.4. Далечен удар | | | | |
| 8.2.5. Статично положение | | | | |

---

## 8.3. SHOT QUALITY MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 8.3.1. Средна дистанция на удар | |
| 8.3.2. Среден xG на удар | |
| 8.3.3. Blocked Shots (%) | |
| 8.3.4. Big Chances | |
| 8.3.5. Shot Quality Score (1–10) | |

---

## 8.4. BUILD-UP PATTERNS (RAW)
| Тип | Брой | % | Efficiency (1–10) |
|------|-------|-----|--------------------|
| 8.4.1. Къс билд-ъп | | | |
| 8.4.2. Среден билд-ъп | | | |
| 8.4.3. Директна атака | | | |

---

## 8.5. TRANSITION CHANCES (RAW)
| Тип преход | Брой | Среден xG | Efficiency (1–10) |
|-------------|--------|------------|--------------------|
| Defensive → Offensive | | | |
| Offensive → Defensive | | | |

---

## 8.6. CROSSING MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 8.6.1. Брой центрирания | |
| 8.6.2. Успешни центрирания (%) | |
| 8.6.3. Cross xT | |
| 8.6.4. Cross Danger Score (1–10) | |

---

## 8.7. CUTBACK MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 8.7.1. Брой cutbacks | |
| 8.7.2. Успеваемост (%) | |
| 8.7.3. Cutback xG | |
| 8.7.4. Cutback Efficiency (1–10) | |

---

## 8.8. OVERLOAD / UNDERLOAD MODEL (RAW)
| Зона | Overload (%) | Underload (%) | Net Advantage |
|------|----------------|------------------|----------------|
| Лява | | | |
| Център | | | |
| Дясна | | | |

### Формула:
Net Advantage = Overload – Underload

---

## 8.9. PLAYER IMPACT → CHANCE CREATION (RAW)
| Играч | Final Impact | Contribution (%) | Chance Weight |
|--------|----------------|--------------------|----------------|
|        |                |                    |                |
|        |                |                    |                |

### Формула:
Chance Weight = FinalImpact × Contribution

---

## 8.10. xG CHAIN (RAW)
| Атака | Играч 1 | Играч 2 | Играч 3 | xG Chain |
|--------|----------|----------|----------|-----------|
| 1 | | | | |
| 2 | | | | |

---

## 8.11. xT CHAIN (RAW)
| Атака | Играч 1 | Играч 2 | Играч 3 | xT Chain |
|--------|----------|----------|----------|-----------|
| 1 | | | | |
| 2 | | | | |

---

## 8.12. CHANCE VOLATILITY (RAW)
| Показател | Стойност |
|-----------|----------|
| 8.12.1. Variance в xG | |
| 8.12.2. Variance в xT | |
| 8.12.3. Variance в Danger Score | |
| 8.12.4. Volatility Score (1–10) | |

---

## 8.13. FINAL CHANCE CREATION SCORE (RAW)
| Показател | Стойност |
|-----------|----------|
| 8.13.1. Shot Quality | |
| 8.13.2. Build-Up | |
| 8.13.3. Transitions | |
| 8.13.4. Crosses | |
| 8.13.5. Cutbacks | |
| 8.13.6. Geometry | |
| 8.13.7. Volatility | |
| 8.13.8. Final Chance Score | |

### Формула:
Final Chance Score = (ShotQ + BuildUp + Transitions + Crosses + Cutbacks + Geometry – Volatility) / 5

---

## 8.14. OUTPUT → ПОДАВАНЕ КЪМ ДРУГИ БЛОКОВЕ
| Данни | Използва се в |
|-------|----------------|
| Final Chance Score | Block 9 (Chance Conversion) |
| Shot Quality | Block 11 (Risk Engine) |
| Volatility | Block 17 (Final Model) |
| xG/xT Chains | Block 15 (Simulation) |
| Overload/Underload | Block 15 |







# 🟦 БЛОК 9 — ДОПЪЛНИТЕЛНИ RAW ПОЛЕТА (v400 EXTENDED)

## 9.1. FINISHING QUALITY MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 9.1.1. Среден xG на удар | |
| 9.1.2. Реални голове | |
| 9.1.3. Очаквани голове (xG) | |
| 9.1.4. Overperformance (Голове – xG) | |
| 9.1.5. Finishing Quality Score (1–10) | |

---

## 9.2. SHOT PLACEMENT MODEL (RAW)
| Зона | % Удари | % Голове | Placement Score (1–10) |
|------|----------|-----------|--------------------------|
| Лява част | | | |
| Център | | | |
| Дясна част | | | |

---

## 9.3. GOALKEEPER DIFFICULTY MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 9.3.1. Save Difficulty (1–10) | |
| 9.3.2. Keeper Form (1–10) | |
| 9.3.3. Keeper xG Saved | |
| 9.3.4. Keeper Overperformance | |
| 9.3.5. GK Difficulty Score (1–10) | |

---

## 9.4. CHANCE → GOAL CONVERSION (RAW)
| Тип шанс | Брой | Голове | Conversion (%) |
|----------|-------|---------|----------------|
| Пробив | | | |
| Центриране | | | |
| Комбинация | | | |
| Далечен удар | | | |
| Статично положение | | | |

---

## 9.5. TRANSITION FINISHING (RAW)
| Тип преход | Удари | Голове | Conversion (%) |
|-------------|--------|---------|----------------|
| Defensive → Offensive | | | |
| Offensive → Defensive | | | |

---

## 9.6. SET-PIECE CONVERSION (RAW)
| Тип | Удари | Голове | Conversion (%) |
|------|--------|---------|----------------|
| Корнери | | | |
| Преки свободни | | | |
| Непреки свободни | | | |
| Дузпи | | | |

---

## 9.7. PRESSURE FINISHING (RAW)
| Показател | Стойност |
|-----------|----------|
| 9.7.1. Удари под пресинг | |
| 9.7.2. Conversion под пресинг (%) | |
| 9.7.3. Pressure Finishing Score (1–10) | |

---

## 9.8. PLAYER FINISHING IMPACT (RAW)
| Играч | Final Impact | Shots | Goals | Finishing Impact |
|--------|----------------|--------|--------|-------------------|
|        |                |        |        |                   |
|        |                |        |        |                   |

### Формула:
Finishing Impact = FinalImpact × (Goals / Shots)

---

## 9.9. xG OVER/UNDERPERFORMANCE (RAW)
| Мач | xG | Голове | Δ (Голове – xG) |
|-----|-----|---------|------------------|
| 1 | | | |
| 2 | | | |
| 3 | | | |
| 4 | | | |
| 5 | | | |

---

## 9.10. FINISHING STABILITY (RAW)
| Показател | Стойност |
|-----------|----------|
| 9.10.1. Variance в conversion | |
| 9.10.2. Variance в shot quality | |
| 9.10.3. Stability Score (1–10) | |

---

## 9.11. FINISHING VOLATILITY (RAW)
| Показател | Стойност |
|-----------|----------|
| 9.11.1. Δ conversion между мачове | |
| 9.11.2. Δ shot quality | |
| 9.11.3. Δ xG overperformance | |
| 9.11.4. Volatility Score (1–10) | |

---

## 9.12. FINAL CHANCE CONVERSION SCORE (RAW)
| Показател | Стойност |
|-----------|----------|
| 9.12.1. Finishing Quality | |
| 9.12.2. Shot Placement | |
| 9.12.3. GK Difficulty | |
| 9.12.4. Pressure Finishing | |
| 9.12.5. Stability | |
| 9.12.6. Volatility | |
| 9.12.7. Final Conversion Score | |

### Формула:
Final Conversion Score = (FinQ + Placement + Pressure + Stability – Volatility – GKDiff) / 4

---

## 9.13. OUTPUT → ПОДАВАНЕ КЪМ ДРУГИ БЛОКОВЕ
| Данни | Използва се в |
|-------|----------------|
| Final Conversion Score | Block 10 (Goal Probability) |
| Finishing Volatility | Block 17 (Final Model) |
| GK Difficulty | Block 15 (Simulation) |
| xG Overperformance | Block 11 (Risk Engine) |
| Pressure Finishing | Block 15 |






# 🟦 БЛОК 10 — ДОПЪЛНИТЕЛНИ RAW ПОЛЕТА (v400 EXTENDED)

## 10.1. BASE GOAL PROBABILITY MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 10.1.1. Среден xG на мач | |
| 10.1.2. Среден xGA на мач | |
| 10.1.3. Weighted xG (от Block 5) | |
| 10.1.4. Weighted xGA | |
| 10.1.5. Base Goal Probability (%) | |

### Формула:
BaseGoalProb = Weighted xG × 0.85

---

## 10.2. CHANCE → GOAL PROBABILITY (RAW)
| Показател | Стойност |
|-----------|----------|
| 10.2.1. Final Chance Score | |
| 10.2.2. Final Conversion Score | |
| 10.2.3. Chance-to-Goal Probability (%) | |

### Формула:
ChanceToGoal = (ChanceScore × ConversionScore) / 10

---

## 10.3. SHOT → GOAL PROBABILITY (RAW)
| Показател | Стойност |
|-----------|----------|
| 10.3.1. Shot Quality Score | |
| 10.3.2. Shot Placement Score | |
| 10.3.3. Pressure Finishing Score | |
| 10.3.4. Shot-to-Goal Probability (%) | |

### Формула:
ShotToGoal = (ShotQuality × Placement × (PressureFinishing / 10)) / 10

---

## 10.4. GK SUPPRESSION MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 10.4.1. GK Difficulty Score | |
| 10.4.2. Keeper Form | |
| 10.4.3. Keeper Overperformance | |
| 10.4.4. GK Suppression (%) | |

### Формула:
GK Suppression = GK Difficulty × 3

---

## 10.5. TACTICAL SUPPRESSION MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 10.5.1. Final Tactical Score | |
| 10.5.2. Pressing Intensity | |
| 10.5.3. Defensive Geometry | |
| 10.5.4. Tactical Suppression (%) | |

### Формула:
TacticalSupp = (Pressing + Geometry) × 2

---

## 10.6. METEO SUPPRESSION MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 10.6.1. Meteo Composite Score | |
| 10.6.2. Wind Impact | |
| 10.6.3. Rain Impact | |
| 10.6.4. Meteo Suppression (%) | |

### Формула:
MeteoSupp = (Wind + Rain) × 1.5

---

## 10.7. FINAL GOAL PROBABILITY (RAW)
| Показател | Стойност |
|-----------|----------|
| 10.7.1. Base Goal Probability | |
| 10.7.2. Chance-to-Goal Probability | |
| 10.7.3. Shot-to-Goal Probability | |
| 10.7.4. Total Suppression (%) | |
| 10.7.5. Final Goal Probability (%) | |

### Формула:
TotalSupp = GK Supp + Tactical Supp + Meteo Supp  
FinalGoalProb = (Base + ChanceToGoal + ShotToGoal) × (1 – TotalSupp / 100)

---

## 10.8. SCORING ZONES (RAW)
| Зона | Удари | Голове | Conversion (%) |
|------|--------|---------|----------------|
| Лява | | | |
| Център | | | |
| Дясна | | | |

---

## 10.9. SCORING PATTERNS (RAW)
| Тип | Брой голове | % | Бележка |
|------|--------------|-----|----------|
| Build-Up | | | |
| Transition | | | |
| Set-Piece | | | |
| Individual Action | | | |

---

## 10.10. SCORING CHAINS (RAW)
| Гол | Играч 1 | Играч 2 | Играч 3 | xG Chain |
|------|----------|----------|----------|-----------|
| 1 | | | | |
| 2 | | | | |

---

## 10.11. PRESSURE SCORING (RAW)
| Показател | Стойност |
|-----------|----------|
| 10.11.1. Голове под пресинг | |
| 10.11.2. Conversion под пресинг (%) | |
| 10.11.3. Pressure Scoring Score (1–10) | |

---

## 10.12. GOAL VOLATILITY (RAW)
| Показател | Стойност |
|-----------|----------|
| 10.12.1. Δ голове между мачове | |
| 10.12.2. Δ conversion | |
| 10.12.3. Δ xG overperformance | |
| 10.12.4. Volatility Score (1–10) | |

---

## 10.13. OUTPUT → ПОДАВАНЕ КЪМ ДРУГИ БЛОКОВЕ
| Данни | Използва се в |
|-------|----------------|
| Final Goal Probability | Block 11 (Risk Engine) |
| Goal Volatility | Block 17 (Final Model) |
| Scoring Patterns | Block 15 (Simulation) |
| GK Suppression | Block 15 |
| Tactical Suppression | Block 15 |
| Meteo Suppression | Block 15 |







# 🟦 БЛОК 11 — ДОПЪЛНИТЕЛНИ RAW ПОЛЕТА (v400 EXTENDED)

## 11.1. INJURY RISK MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 11.1.1. Injury Severity Index | |
| 11.1.2. Availability Probability | |
| 11.1.3. Recurrence Risk (%) | |
| 11.1.4. Injury Risk Score (1–10) | |

---

## 11.2. FATIGUE RISK MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 11.2.1. Fatigue Score | |
| 11.2.2. Fatigue Decay | |
| 11.2.3. Workload Stress | |
| 11.2.4. Fatigue Risk Score (1–10) | |

---

## 11.3. TACTICAL RISK MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 11.3.1. Final Tactical Score | |
| 11.3.2. Tactical Volatility | |
| 11.3.3. Tactical Suppression | |
| 11.3.4. Tactical Risk Score (1–10) | |

---

## 11.4. MOMENTUM RISK MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 11.4.1. Momentum Drops | |
| 11.4.2. Momentum Variance | |
| 11.4.3. Momentum Stability | |
| 11.4.4. Momentum Risk Score (1–10) | |

---

## 11.5. VOLATILITY RISK MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 11.5.1. Finishing Volatility | |
| 11.5.2. Chance Volatility | |
| 11.5.3. Goal Volatility | |
| 11.5.4. Volatility Risk Score (1–10) | |

---

## 11.6. REFEREE RISK MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 11.6.1. Aggression Index | |
| 11.6.2. Foul-to-Card Ratio | |
| 11.6.3. Penalty Frequency | |
| 11.6.4. VAR Overturn Rate | |
| 11.6.5. Referee Risk Score (1–10) | |

---

## 11.7. METEO RISK MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 11.7.1. Meteo Composite Score | |
| 11.7.2. Wind Impact | |
| 11.7.3. Rain Impact | |
| 11.7.4. Temperature Stress | |
| 11.7.5. Meteo Risk Score (1–10) | |

---

## 11.8. DEFENSIVE RISK MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 11.8.1. Defensive Errors | |
| 11.8.2. PPDA Allowed | |
| 11.8.3. xGA Trend | |
| 11.8.4. Defensive Risk Score (1–10) | |

---

## 11.9. TRANSITION RISK MODEL (RAW)
| Тип преход | Риск (1–10) | Бележка |
|-------------|--------------|----------|
| Def → Off | | |
| Off → Def | | |

---

## 11.10. GEOMETRY RISK MODEL (RAW)
| Линия | Net Geometry | Risk (1–10) |
|--------|----------------|--------------|
| Защита | | |
| Халфове | | |
| Атака | | |

---

## 11.11. GK RISK MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 11.11.1. GK Difficulty | |
| 11.11.2. GK Overperformance | |
| 11.11.3. GK Volatility | |
| 11.11.4. GK Risk Score (1–10) | |

---

## 11.12. PLAYER INSTABILITY RISK (RAW)
| Играч | Instability Score | Risk Weight |
|--------|---------------------|--------------|
|        |                     |              |
|        |                     |              |

---

## 11.13. TEAM INSTABILITY RISK (RAW)
| Показател | Стойност |
|-----------|----------|
| 11.13.1. Tactical Instability | |
| 11.13.2. Player Instability | |
| 11.13.3. Form Instability | |
| 11.13.4. Instability Risk Score (1–10) | |

---

## 11.14. COMPOSITE RISK SCORE (RAW)
| Показател | Стойност |
|-----------|----------|
| 11.14.1. Injury Risk | |
| 11.14.2. Fatigue Risk | |
| 11.14.3. Tactical Risk | |
| 11.14.4. Momentum Risk | |
| 11.14.5. Volatility Risk | |
| 11.14.6. Referee Risk | |
| 11.14.7. Meteo Risk | |
| 11.14.8. Defensive Risk | |
| 11.14.9. Transition Risk | |
| 11.14.10. GK Risk | |
| 11.14.11. Instability Risk | |
| 11.14.12. FINAL RISK SCORE (1–10) | |

### Формула:
FinalRisk = Average(всички рискови фактори)

---

## 11.15. OUTPUT → ПОДАВАНЕ КЪМ ДРУГИ БЛОКОВЕ
| Данни | Използва се в |
|-------|----------------|
| Final Risk Score | Block 15 (Simulation) |
| Volatility Risk | Block 17 (Final Model) |
| Defensive Risk | Block 15 |
| GK Risk | Block 15 |
| Tactical Risk | Block 15 |
| Meteo Risk | Block 15 |
| Referee Risk | Block 15 |







# 🟦 БЛОК 12 — ДОПЪЛНИТЕЛНИ RAW ПОЛЕТА (v400 EXTENDED)

## 12.1. FLOW ZONES (RAW)
| Зона | % Време | Flow Score (1–10) | Бележка |
|------|----------|----------------------|----------|
| Лява зона | | | |
| Център | | | |
| Дясна зона | | | |

---

## 12.2. FLOW MOMENTUM (RAW)
| Показател | Стойност |
|-----------|----------|
| 12.2.1. Momentum Peaks | |
| 12.2.2. Momentum Drops | |
| 12.2.3. Net Flow Momentum | |
| 12.2.4. Flow Momentum Score (1–10) | |

---

## 12.3. FLOW ACCELERATION (RAW)
| Показател | Стойност |
|-----------|----------|
| 12.3.1. Progressive Actions | |
| 12.3.2. Tempo Influence | |
| 12.3.3. Transition Speed | |
| 12.3.4. Flow Acceleration Score (1–10) | |

---

## 12.4. FLOW DECAY (RAW)
| Показател | Стойност |
|-----------|----------|
| 12.4.1. Lost Possessions | |
| 12.4.2. Failed Transitions | |
| 12.4.3. Defensive Pressure | |
| 12.4.4. Flow Decay Score (1–10) | |

---

## 12.5. POSSESSION FLOW (RAW)
| Показател | Стойност |
|-----------|----------|
| 12.5.1. Possession % | |
| 12.5.2. Possession Stability | |
| 12.5.3. Possession Progression | |
| 12.5.4. Possession Flow Score (1–10) | |

---

## 12.6. TRANSITION FLOW (RAW)
| Тип преход | Брой | Успеваемост (%) | Flow Score |
|-------------|--------|------------------|-------------|
| Def → Off | | | |
| Off → Def | | | |

---

## 12.7. PRESSURE FLOW (RAW)
| Показател | Стойност |
|-----------|----------|
| 12.7.1. Pressing Intensity | |
| 12.7.2. Pressing Efficiency | |
| 12.7.3. PPDA Influence | |
| 12.7.4. Pressure Flow Score (1–10) | |

---

## 12.8. RISK FLOW (RAW)
| Показател | Стойност |
|-----------|----------|
| 12.8.1. Final Risk Score | |
| 12.8.2. Defensive Errors | |
| 12.8.3. Transition Risk | |
| 12.8.4. Risk Flow Score (1–10) | |

---

## 12.9. TACTICAL FLOW (RAW)
| Показател | Стойност |
|-----------|----------|
| 12.9.1. Final Tactical Score | |
| 12.9.2. Geometry Influence | |
| 12.9.3. Stability Influence | |
| 12.9.4. Tactical Flow Score (1–10) | |

---

## 12.10. SUBSTITUTION FLOW (RAW)
| Играч | Минута | Impact | Flow Change |
|--------|---------|----------|---------------|
|        |         |          |               |
|        |         |          |               |

### Формула:
FlowChange = Impact × (90 – Минута) / 90

---

## 12.11. FLOW GEOMETRY (RAW)
| Линия | Advantage | Disadvantage | Net Flow Geometry |
|--------|------------|----------------|---------------------|
| Защита | | | |
| Халфове | | | |
| Атака | | | |

---

## 12.12. FLOW VOLATILITY (RAW)
| Показател | Стойност |
|-----------|----------|
| 12.12.1. Δ Possession | |
| 12.12.2. Δ Momentum | |
| 12.12.3. Δ Transitions | |
| 12.12.4. Flow Volatility Score (1–10) | |

---

## 12.13. FLOW STABILITY (RAW)
| Показател | Стойност |
|-----------|----------|
| 12.13.1. Possession Stability | |
| 12.13.2. Tactical Stability | |
| 12.13.3. Momentum Stability | |
| 12.13.4. Flow Stability Score (1–10) | |

---

## 12.14. FINAL FLOW SCORE (RAW)
| Показател | Стойност |
|-----------|----------|
| 12.14.1. Momentum | |
| 12.14.2. Acceleration | |
| 12.14.3. Decay | |
| 12.14.4. Tactical Flow | |
| 12.14.5. Risk Flow | |
| 12.14.6. Stability | |
| 12.14.7. Volatility | |
| 12.14.8. Final Flow Score | |

### Формула:
FinalFlow = (Momentum + Accel + TacticalFlow + Stability – Decay – RiskFlow – Volatility) / 5

---

## 12.15. OUTPUT → ПОДАВАНЕ КЪМ ДРУГИ БЛОКОВЕ
| Данни | Използва се в |
|-------|----------------|
| Final Flow Score | Block 13 (Micro-Phases) |
| Flow Volatility | Block 17 (Final Model) |
| Flow Geometry | Block 15 (Simulation) |
| Substitution Flow | Block 15 |







# 🟦 БЛОК 13 — ДОПЪЛНИТЕЛНИ RAW ПОЛЕТА (v400 EXTENDED)

## 13.1. MICRO-PHASE TIMING (RAW)
| Фаза | Минути | Интензитет (1–10) | Бележка |
|------|---------|----------------------|----------|
| Фаза 1 | 0–15 | | |
| Фаза 2 | 15–30 | | |
| Фаза 3 | 30–45 | | |
| Фаза 4 | 45–60 | | |
| Фаза 5 | 60–75 | | |
| Фаза 6 | 75–90 | | |

---

## 13.2. MICRO-PHASE MOMENTUM (RAW)
| Фаза | Momentum | Δ Momentum | Phase Momentum Score |
|------|-----------|-------------|------------------------|
| 1 | | | |
| 2 | | | |
| 3 | | | |
| 4 | | | |
| 5 | | | |
| 6 | | | |

---

## 13.3. MICRO-PHASE FLOW (RAW)
| Фаза | Flow Score | Acceleration | Decay | Net Flow |
|------|-------------|----------------|----------|-----------|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |
| 5 | | | | |
| 6 | | | | |

### Формула:
NetFlow = Flow – Decay + Acceleration

---

## 13.4. MICRO-PHASE RISK (RAW)
| Фаза | Risk Score | Δ Risk | Phase Risk |
|------|-------------|----------|--------------|
| 1 | | | |
| 2 | | | |
| 3 | | | |
| 4 | | | |
| 5 | | | |
| 6 | | | |

---

## 13.5. MICRO-PHASE TACTICAL SHAPE (RAW)
| Фаза | Tactical Score | Geometry | Stability | Phase Tactical |
|------|------------------|------------|-------------|----------------|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |
| 5 | | | | |
| 6 | | | | |

---

## 13.6. MICRO-PHASE CHANCE CREATION (RAW)
| Фаза | Chance Score | Shot Quality | xT | Phase Chance |
|------|----------------|----------------|------|----------------|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |
| 5 | | | | |
| 6 | | | | |

---

## 13.7. MICRO-PHASE CONVERSION (RAW)
| Фаза | Conversion Score | GK Difficulty | Pressure Finishing | Phase Conversion |
|------|--------------------|----------------|----------------------|--------------------|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |
| 5 | | | | |
| 6 | | | | |

---

## 13.8. MICRO-PHASE SUPPRESSION (RAW)
| Фаза | Tactical Suppression | GK Suppression | Meteo Suppression | Total Suppression |
|------|------------------------|------------------|----------------------|---------------------|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |
| 5 | | | | |
| 6 | | | | |

---

## 13.9. MICRO-PHASE xG / xGA (RAW)
| Фаза | micro-xG | micro-xGA | Δ (xG – xGA) |
|------|-----------|-------------|----------------|
| 1 | | | |
| 2 | | | |
| 3 | | | |
| 4 | | | |
| 5 | | | |
| 6 | | | |

---

## 13.10. MICRO-PHASE GEOMETRY (RAW)
| Фаза | Advantage | Disadvantage | Net Geometry |
|------|------------|----------------|----------------|
| 1 | | | |
| 2 | | | |
| 3 | | | |
| 4 | | | |
| 5 | | | |
| 6 | | | |

---

## 13.11. MICRO-PHASE VOLATILITY (RAW)
| Фаза | Δ Flow | Δ Momentum | Δ Chance | Phase Volatility |
|------|---------|--------------|-------------|--------------------|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |
| 5 | | | | |
| 6 | | | | |

---

## 13.12. MICRO-PHASE STABILITY (RAW)
| Фаза | Flow Stability | Tactical Stability | Conversion Stability | Phase Stability |
|------|------------------|----------------------|--------------------------|-------------------|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |
| 5 | | | | |
| 6 | | | | |

---

## 13.13. SUBSTITUTION PHASE SHIFTS (RAW)
| Играч | Минута | Impact | Phase Shift |
|--------|---------|----------|----------------|
|        |         |          |                |
|        |         |          |                |

### Формула:
PhaseShift = Impact × (1 – (Минута / 90))

---

## 13.14. FINAL MICRO-PHASE SCORE (RAW)
| Фаза | Momentum | Flow | Chance | Conversion | Risk | Stability | Volatility | Final Phase Score |
|------|-----------|--------|-----------|--------------|--------|--------------|----------------|----------------------|
| 1 | | | | | | | | |
| 2 | | | | | | | | |
| 3 | | | | | | | | |
| 4 | | | | | | | | |
| 5 | | | | | | | | |
| 6 | | | | | | | | |

### Формула:
FinalPhase = (Momentum + Flow + Chance + Conversion + Stability – Risk – Volatility) / 5

---

## 13.15. OUTPUT → ПОДАВАНЕ КЪМ ДРУГИ БЛОКОВЕ
| Данни | Използва се в |
|-------|----------------|
| Final Phase Scores | Block 14 (Phase Weighting) |
| Phase Volatility | Block 17 |
| Phase Geometry | Block 15 |
| micro-xG / micro-xGA | Block 15 |
| Substitution Phase Shifts | Block 15 |







# 🟦 БЛОК 14 — ДОПЪЛНИТЕЛНИ RAW ПОЛЕТА (v400 EXTENDED)

## 14.1. BASE PHASE WEIGHTS (RAW)
| Фаза | Final Phase Score | Base Weight |
|------|---------------------|--------------|
| 1 | | |
| 2 | | |
| 3 | | |
| 4 | | |
| 5 | | |
| 6 | | |

### Формула:
BaseWeight = FinalPhaseScore / 10

---

## 14.2. MOMENTUM WEIGHTING (RAW)
| Фаза | Momentum | Momentum Weight |
|------|-----------|------------------|
| 1 | | |
| 2 | | |
| 3 | | |
| 4 | | |
| 5 | | |
| 6 | | |

### Формула:
MomentumWeight = Momentum / 10

---

## 14.3. FLOW WEIGHTING (RAW)
| Фаза | Flow Score | Flow Weight |
|------|-------------|--------------|
| 1 | | |
| 2 | | |
| 3 | | |
| 4 | | |
| 5 | | |
| 6 | | |

### Формула:
FlowWeight = FlowScore / 10

---

## 14.4. TACTICAL WEIGHTING (RAW)
| Фаза | Tactical Score | Tactical Weight |
|------|------------------|------------------|
| 1 | | |
| 2 | | |
| 3 | | |
| 4 | | |
| 5 | | |
| 6 | | |

### Формула:
TacticalWeight = TacticalScore / 10

---

## 14.5. CHANCE WEIGHTING (RAW)
| Фаза | Phase Chance | Chance Weight |
|------|----------------|----------------|
| 1 | | |
| 2 | | |
| 3 | | |
| 4 | | |
| 5 | | |
| 6 | | |

### Формула:
ChanceWeight = PhaseChance / 10

---

## 14.6. CONVERSION WEIGHTING (RAW)
| Фаза | Phase Conversion | Conversion Weight |
|------|--------------------|---------------------|
| 1 | | |
| 2 | | |
| 3 | | |
| 4 | | |
| 5 | | |
| 6 | | |

### Формула:
ConversionWeight = PhaseConversion / 10

---

## 14.7. SUPPRESSION WEIGHTING (RAW)
| Фаза | Total Suppression | Suppression Weight |
|------|----------------------|----------------------|
| 1 | | |
| 2 | | |
| 3 | | |
| 4 | | |
| 5 | | |
| 6 | | |

### Формула:
SuppressionWeight = 1 – (TotalSuppression / 100)

---

## 14.8. RISK WEIGHTING (RAW)
| Фаза | Phase Risk | Risk Weight |
|------|--------------|--------------|
| 1 | | |
| 2 | | |
| 3 | | |
| 4 | | |
| 5 | | |
| 6 | | |

### Формула:
RiskWeight = 1 – (PhaseRisk / 10)

---

## 14.9. VOLATILITY WEIGHTING (RAW)
| Фаза | Phase Volatility | Volatility Weight |
|------|--------------------|---------------------|
| 1 | | |
| 2 | | |
| 3 | | |
| 4 | | |
| 5 | | |
| 6 | | |

### Формула:
VolatilityWeight = 1 – (PhaseVolatility / 10)

---

## 14.10. STABILITY WEIGHTING (RAW)
| Фаза | Phase Stability | Stability Weight |
|------|-------------------|--------------------|
| 1 | | |
| 2 | | |
| 3 | | |
| 4 | | |
| 5 | | |
| 6 | | |

### Формула:
StabilityWeight = PhaseStability / 10

---

## 14.11. COMPOSITE PHASE WEIGHT (RAW)
| Фаза | Base | Momentum | Flow | Tactical | Chance | Conversion | Suppression | Risk | Stability | Volatility | Composite Weight |
|------|--------|------------|---------|-----------|-----------|--------------|--------------|--------|--------------|----------------|----------------------|
| 1 | | | | | | | | | | | |
| 2 | | | | | | | | | | | |
| 3 | | | | | | | | | | | |
| 4 | | | | | | | | | | | |
| 5 | | | | | | | | | | | |
| 6 | | | | | | | | | | | |

### Формула:
CompositeWeight = (Base + Momentum + Flow + Tactical + Chance + Conversion + Stability – Volatility – Risk) × Suppression

---

## 14.12. NORMALIZED PHASE WEIGHTS (RAW)
| Фаза | Composite Weight | Normalized Weight |
|------|--------------------|---------------------|
| 1 | | |
| 2 | | |
| 3 | | |
| 4 | | |
| 5 | | |
| 6 | | |

### Формула:
NormalizedWeight = CompositeWeight / Σ(CompositeWeights)

---

## 14.13. FINAL PHASE PROBABILITY (RAW)
| Фаза | Normalized Weight | Final Phase Probability (%) |
|------|---------------------|-------------------------------|
| 1 | | |
| 2 | | |
| 3 | | |
| 4 | | |
| 5 | | |
| 6 | | |

### Формула:
FinalPhaseProb = NormalizedWeight × 100

---

## 14.14. OUTPUT → ПОДАВАНЕ КЪМ ДРУГИ БЛОКОВЕ
| Данни | Използва се в |
|-------|----------------|
| Final Phase Probabilities | Block 15 (Simulation Engine) |
| Phase Weights | Block 15 |
| Suppression Weights | Block 15 |
| Risk Weights | Block 15 |
| Volatility Weights | Block 17 |






# 🟦 БЛОК 15 — SIMULATION ENGINE (RAW EXTENDED v400)

## 15.1. PHASE INPUT MATRIX (RAW)
| Фаза | Phase Prob (%) | micro-xG | micro-xGA | Phase Risk | Phase Volatility |
|------|------------------|-----------|-------------|--------------|--------------------|
| 1 | | | | | |
| 2 | | | | | |
| 3 | | | | | |
| 4 | | | | | |
| 5 | | | | | |
| 6 | | | | | |

---

## 15.2. PHASE GOAL PROBABILITY (RAW)
| Фаза | micro-xG | Suppression | Risk | Final Phase Goal Prob (%) |
|------|-----------|--------------|--------|------------------------------|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |
| 5 | | | | |
| 6 | | | | |

### Формула:
PhaseGoalProb = micro-xG × (1 – Suppression/100) × (1 – Risk/10)

---

## 15.3. PHASE GOAL AGAINST PROBABILITY (RAW)
| Фаза | micro-xGA | Opp Suppression | Opp Risk | Final Phase GA Prob (%) |
|------|-------------|-------------------|------------|----------------------------|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |
| 5 | | | | |
| 6 | | | | |

---

## 15.4. PHASE SIMULATION (RAW)
| Фаза | Phase Prob | Goal Prob | GA Prob | Expected Goals | Expected GA |
|------|--------------|-------------|-----------|------------------|----------------|
| 1 | | | | | |
| 2 | | | | | |
| 3 | | | | | |
| 4 | | | | | |
| 5 | | | | | |
| 6 | | | | | |

### Формула:
ExpectedGoals = PhaseProb × GoalProb  
ExpectedGA = PhaseProb × GAProb

---

## 15.5. TACTICAL SIMULATION (RAW)
| Показател | Стойност |
|-----------|----------|
| 15.5.1. Tactical Score | |
| 15.5.2. Geometry Advantage | |
| 15.5.3. Pressing Influence | |
| 15.5.4. Tactical Simulation Modifier | |

### Формула:
TacticalSim = (TacticalScore + Geometry – Pressing) / 10

---

## 15.6. CHANCE SIMULATION (RAW)
| Показател | Стойност |
|-----------|----------|
| 15.6.1. Final Chance Score | |
| 15.6.2. Shot Quality | |
| 15.6.3. xT | |
| 15.6.4. Chance Simulation Modifier | |

---

## 15.7. CONVERSION SIMULATION (RAW)
| Показател | Стойност |
|-----------|----------|
| 15.7.1. Final Conversion Score | |
| 15.7.2. GK Difficulty | |
| 15.7.3. Pressure Finishing | |
| 15.7.4. Conversion Simulation Modifier | |

---

## 15.8. RISK-ADJUSTED SIMULATION (RAW)
| Показател | Стойност |
|-----------|----------|
| 15.8.1. Final Risk Score | |
| 15.8.2. Defensive Risk | |
| 15.8.3. Transition Risk | |
| 15.8.4. Risk Simulation Modifier | |

### Формула:
RiskSim = 1 – (FinalRisk / 20)

---

## 15.9. VOLATILITY-ADJUSTED SIMULATION (RAW)
| Показател | Стойност |
|-----------|----------|
| 15.9.1. Goal Volatility | |
| 15.9.2. Chance Volatility | |
| 15.9.3. Flow Volatility | |
| 15.9.4. Volatility Simulation Modifier | |

---

## 15.10. SUPPRESSION SIMULATION (RAW)
| Показател | Стойност |
|-----------|----------|
| 15.10.1. Tactical Suppression | |
| 15.10.2. GK Suppression | |
| 15.10.3. Meteo Suppression | |
| 15.10.4. Total Suppression Modifier | |

---

## 15.11. COMPOSITE SIMULATION MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 15.11.1. Phase Simulation Total xG | |
| 15.11.2. Phase Simulation Total xGA | |
| 15.11.3. TacticalSim | |
| 15.11.4. ChanceSim | |
| 15.11.5. ConversionSim | |
| 15.11.6. RiskSim | |
| 15.11.7. VolatilitySim | |
| 15.11.8. SuppressionSim | |
| 15.11.9. Composite Simulation Score | |

### Формула:
CompositeSim = (xG – xGA) × TacticalSim × ChanceSim × ConversionSim × RiskSim × VolatilitySim × SuppressionSim

---

## 15.12. SCENARIO TREE (RAW)
| Сценарий | Описание | Вероятност (%) |
|-----------|-----------|------------------|
| S1 | Ранен гол | |
| S2 | Късен гол | |
| S3 | Доминация | |
| S4 | Контра-атаки | |
| S5 | Висок риск | |
| S6 | Нисък риск | |

---

## 15.13. MATCH RESULT PROBABILITIES (RAW)
| Резултат | Вероятност (%) |
|----------|------------------|
| Победа | |
| Равен | |
| Загуба | |

---

## 15.14. SCORELINE PROBABILITIES (RAW)
| Резултат | Вероятност (%) |
|----------|------------------|
| 0–0 | |
| 1–0 | |
| 0–1 | |
| 1–1 | |
| 2–1 | |
| 1–2 | |
| 2–2 | |
| 3–1 | |
| 1–3 | |

---

## 15.15. SIMULATION UNCERTAINTY (RAW)
| Показател | Стойност |
|-----------|----------|
| 15.15.1. Model Noise | |
| 15.15.2. Data Variance | |
| 15.15.3. Volatility Impact | |
| 15.15.4. Final Uncertainty Score (1–10) | |

---

## 15.16. OUTPUT → ПОДАВАНЕ КЪМ ДРУГИ БЛОКОВЕ
| Данни | Използва се в |
|-------|----------------|
| Composite Simulation Score | Block 16 |
| Match Result Probabilities | Block 17 |
| Scoreline Probabilities | Block 17 |
| Scenario Tree | Block 17 |
| Uncertainty Score | Block 17 |







# 🟦 БЛОК 16 — OUTCOME SYNTHESIS ENGINE (RAW EXTENDED v400)

## 16.1. BASE OUTCOME MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 16.1.1. Composite Simulation Score | |
| 16.1.2. Expected Goals | |
| 16.1.3. Expected GA | |
| 16.1.4. Net Expected (xG – xGA) | |
| 16.1.5. Base Outcome Score | |

### Формула:
BaseOutcome = NetExpected × CompositeSimScore

---

## 16.2. RESULT PROBABILITY NORMALIZATION (RAW)
| Резултат | Raw Prob (%) | Normalized Prob (%) |
|----------|----------------|------------------------|
| Победа | | |
| Равен | | |
| Загуба | | |

### Формула:
Normalized = Raw / Σ(Raw)

---

## 16.3. SCORELINE NORMALIZATION (RAW)
| Резултат | Raw Prob | Normalized Prob |
|----------|-----------|------------------|
| 0–0 | | |
| 1–0 | | |
| 0–1 | | |
| 1–1 | | |
| 2–1 | | |
| 1–2 | | |
| 2–2 | | |
| 3–1 | | |
| 1–3 | | |

---

## 16.4. SCENARIO WEIGHTING (RAW)
| Сценарий | Вероятност | Weight | Weighted Impact |
|-----------|--------------|---------|------------------|
| S1 | | | |
| S2 | | | |
| S3 | | | |
| S4 | | | |
| S5 | | | |
| S6 | | | |

### Формула:
WeightedImpact = Prob × Weight

---

## 16.5. UNCERTAINTY ADJUSTMENT (RAW)
| Показател | Стойност |
|-----------|----------|
| 16.5.1. Uncertainty Score | |
| 16.5.2. Volatility Impact | |
| 16.5.3. Data Variance | |
| 16.5.4. Uncertainty Adjustment Factor | |

### Формула:
UncertaintyAdj = 1 – (UncertaintyScore / 20)

---

## 16.6. TACTICAL ADJUSTMENT (RAW)
| Показател | Стойност |
|-----------|----------|
| 16.6.1. Tactical Score | |
| 16.6.2. Geometry Advantage | |
| 16.6.3. Pressing Influence | |
| 16.6.4. Tactical Adjustment Factor | |

---

## 16.7. FINISHING ADJUSTMENT (RAW)
| Показател | Стойност |
|-----------|----------|
| 16.7.1. Final Conversion Score | |
| 16.7.2. Shot Quality | |
| 16.7.3. Pressure Finishing | |
| 16.7.4. Finishing Adjustment Factor | |

---

## 16.8. DEFENSIVE ADJUSTMENT (RAW)
| Показател | Стойност |
|-----------|----------|
| 16.8.1. Defensive Risk | |
| 16.8.2. GK Risk | |
| 16.8.3. Transition Risk | |
| 16.8.4. Defensive Adjustment Factor | |

---

## 16.9. OUTCOME SMOOTHING (RAW)
| Показател | Стойност |
|-----------|----------|
| 16.9.1. Raw Outcome Score | |
| 16.9.2. Adjustment Factors Combined | |
| 16.9.3. Smoothed Outcome Score | |

### Формула:
SmoothedOutcome = RawOutcome × CombinedAdjustments

---

## 16.10. FINAL OUTCOME PROBABILITIES (RAW)
| Резултат | Smoothed Score | Final Probability (%) |
|----------|------------------|--------------------------|
| Победа | | |
| Равен | | |
| Загуба | | |

### Формула:
FinalProb = Smoothed / Σ(Smoothed)

---

## 16.11. FINAL SCORELINE PROBABILITIES (RAW)
| Резултат | Smoothed Score | Final Probability (%) |
|----------|------------------|--------------------------|
| 0–0 | | |
| 1–0 | | |
| 0–1 | | |
| 1–1 | | |
| 2–1 | | |
| 1–2 | | |
| 2–2 | | |
| 3–1 | | |
| 1–3 | | |

---

## 16.12. OUTCOME CONFIDENCE (RAW)
| Показател | Стойност |
|-----------|----------|
| 16.12.1. Model Stability | |
| 16.12.2. Volatility | |
| 16.12.3. Uncertainty | |
| 16.12.4. Confidence Score (1–10) | |

---

## 16.13. OUTPUT → ПОДАВАНЕ КЪМ ДРУГИ БЛОКОВЕ
| Данни | Използва се в |
|-------|----------------|
| Final Outcome Probabilities | Block 17 |
| Final Scoreline Probabilities | Block 17 |
| Outcome Confidence | Block 17 |
| Scenario Weights | Block 17 |







# 🟦 БЛОК 17 — FINAL MODEL (RAW EXTENDED v400)

## 17.1. FINAL INPUT MATRIX (RAW)
| Показател | Стойност |
|-----------|----------|
| 17.1.1. Composite Simulation Score | |
| 17.1.2. Final Outcome Probabilities | |
| 17.1.3. Final Scoreline Probabilities | |
| 17.1.4. Scenario Weights | |
| 17.1.5. Outcome Confidence | |
| 17.1.6. Final Risk Score | |
| 17.1.7. Final Tactical Score | |
| 17.1.8. Final Chance Score | |
| 17.1.9. Final Conversion Score | |
| 17.1.10. Final Flow Score | |
| 17.1.11. Volatility Scores | |

---

## 17.2. FINAL MATCH PROBABILITY MODEL (RAW)
| Резултат | Вероятност (%) |
|----------|------------------|
| Победа | |
| Равен | |
| Загуба | |

### Формула:
FinalMatchProb = OutcomeProb × Confidence × (1 – Risk/20)

---

## 17.3. FINAL SCORELINE MODEL (RAW)
| Резултат | Вероятност (%) |
|----------|------------------|
| 0–0 | |
| 1–0 | |
| 0–1 | |
| 1–1 | |
| 2–1 | |
| 1–2 | |
| 2–2 | |
| 3–1 | |
| 1–3 | |

---

## 17.4. FINAL xG/xGA MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 17.4.1. Total Simulated xG | |
| 17.4.2. Total Simulated xGA | |
| 17.4.3. Net Expected Goals | |

---

## 17.5. FINAL RISK-ADJUSTED MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 17.5.1. Risk Score | |
| 17.5.2. Volatility Score | |
| 17.5.3. Uncertainty Score | |
| 17.5.4. Risk Adjustment Factor | |

### Формула:
RiskAdj = 1 – (Risk + Volatility + Uncertainty) / 30

---

## 17.6. FINAL TACTICAL MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 17.6.1. Tactical Score | |
| 17.6.2. Geometry | |
| 17.6.3. Stability | |
| 17.6.4. Tactical Adjustment Factor | |

---

## 17.7. FINAL CHANCE MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 17.7.1. Chance Score | |
| 17.7.2. Shot Quality | |
| 17.7.3. xT | |
| 17.7.4. Chance Adjustment Factor | |

---

## 17.8. FINAL CONVERSION MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 17.8.1. Conversion Score | |
| 17.8.2. GK Difficulty | |
| 17.8.3. Pressure Finishing | |
| 17.8.4. Conversion Adjustment Factor | |

---

## 17.9. FINAL FLOW MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 17.9.1. Flow Score | |
| 17.9.2. Flow Stability | |
| 17.9.3. Flow Volatility | |
| 17.9.4. Flow Adjustment Factor | |

---

## 17.10. FINAL COMPOSITE MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 17.10.1. TacticalAdj | |
| 17.10.2. ChanceAdj | |
| 17.10.3. ConversionAdj | |
| 17.10.4. FlowAdj | |
| 17.10.5. RiskAdj | |
| 17.10.6. Composite Final Score | |

### Формула:
CompositeFinal = TacticalAdj × ChanceAdj × ConversionAdj × FlowAdj × RiskAdj

---

## 17.11. FINAL MATCH OUTCOME (RAW)
| Показател | Стойност |
|-----------|----------|
| 17.11.1. Final Win Probability | |
| 17.11.2. Final Draw Probability | |
| 17.11.3. Final Loss Probability | |
| 17.11.4. Highest Probability Outcome | |

---

## 17.12. FINAL SCORELINE OUTPUT (RAW)
| Резултат | Вероятност (%) |
|----------|------------------|
| Най-вероятен резултат | |
| Втори най-вероятен | |
| Трети най-вероятен | |

---

## 17.13. FINAL CONFIDENCE MODEL (RAW)
| Показател | Стойност |
|-----------|----------|
| 17.13.1. Model Stability | |
| 17.13.2. Volatility | |
| 17.13.3. Uncertainty | |
| 17.13.4. Final Confidence Score (1–10) | |

---

## 17.14. FINAL OUTPUT PACKAGE (RAW)
| Компонент | Стойност |
|-----------|----------|
| Final Match Probabilities | |
| Final Scoreline Probabilities | |
| Composite Final Score | |
| Final Confidence Score | |
| Scenario Weights | |
| Risk-Adjusted Output | |
| Tactical-Adjusted Output | |
| Chance-Adjusted Output | |
| Conversion-Adjusted Output | |
| Flow-Adjusted Output | |




# 🟦 БЛОК 18 — ФИНАЛЕН ДАШБОРД (RAW)

## 🔹 18.0. Преглед от 4 агента (0–18)
| Агент | Обхват | Оценка (1–10) | Риск (0–10) | Бележка |
|-------|---------|----------------|--------------|----------|
| Agent 1 | Тактика (0–7) | | | |
| Agent 2 | Шансове (8–10) | | | |
| Agent 3 | Риск (11–14) | | | |
| Agent 4 | Симулация (15–18) | | | |

---

## 🔹 18.1. Мачова статистика (RAW)
| Показател | Домакин | Гост | Бележка |
|-----------|---------|------|----------|
| Владение (%) | | | |
| Общо пасове | | | |
| Точни пасове (%) | | | |
| Удари | | | |
| Точни удари | | | |
| Удари извън | | | |
| Блокирани удари | | | |
| Корнери | | | |
| Фалове | | | |
| Жълти картони | | | |
| Червени картони | | | |
| xG | | | |
| xGA | | | |
| Тежест / Weight (%) | | | |
| Общ риск (0–10) | | | |

---

## 🔹 18.2. Точни резултати и голова информация
| Показател | Стойност |
|-----------|----------|
| Най‑вероятен точен резултат | |
| Втори резултат | |
| Трети резултат | |
| Минута на гол (домакин) | |
| Минута на гол (гост) | |
| Голмайстор (домакин) | |
| Голмайстор (гост) | |
| Риск на играча (0–10) | |

---

## 🔹 18.3. Рискови показатели (RAW)
| Показател | Домакин | Гост |
|-----------|---------|------|
| Тактически риск | | |
| Риск от преходи | | |
| Риск от преса | | |
| Риск от вратар | | |
| Волатилност | | |
| Финална тежест (%) | | |

---

## 🔹 18.4. Гол линии (Over / Under)
| Линия | Over (%) | Under (%) | Риск (0–10) | Сигурност (%) |
|--------|-----------|-------------|--------------|----------------|
| 2.0 | | | | |
| 2.5 | | | | |
| 3.0 | | | | |
| 3.5 | | | | |

---

## 🔹 18.5. Двоен шанс (Double Chance)
| Маркет | Страна | Моделна опора | Риск (0–10) | Сигурност (%) |
|--------|---------|----------------|--------------|----------------|
| 1X | Домакин | | | |
| X2 | Гост | | | |
| 12 | И двата | | | |

---

## 🔹 18.6. Хендикап (Handicap)
| Маркет | Линия | Страна | Покритие (%) | Риск (0–10) | Сигурност (%) |
|--------|--------|---------|----------------|--------------|----------------|
| AH -1.0 | -1.0 | Домакин | | | |
| AH +1.0 | +1.0 | Гост | | | |
| AH -0.5 | -0.5 | Домакин | | | |
| AH +0.5 | +0.5 | Гост | | | |

---

## 🔹 18.7. Финална препоръка (RAW)
| Тип | Маркет | Страна / Линия | Моделна опора | Риск (0–10) | Сигурност (%) |
|-----|--------|------------------|----------------|--------------|----------------|
| Двоен шанс | | | | | |
| Хендикап | | | | | |
| Над/Под | | | | | |
| Алтернативен маркет | | | | | |

---

## 🔹 18.8. Финален Checksum
| Показател | Стойност |
|-----------|----------|
| Σ Match Probabilities = 100% | |
| Σ Scoreline Probabilities ≈ 100% | |
| Съвместимост с xG/xGA | |
| Съвместимост с риск/волатилност | |
| Финална сигурност (%) | |
