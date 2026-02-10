# SNCB_Data_mining
```
├── doc
Slides.pdf
│   ├── Paper Tod et al.pdf
│   ├── Presentation_data_mining_sncb.pdf
│   ├── Slides.pdf
│
├── figures
│   ├── F1_score_AC_DC_speed_events.png
│   ├── incident11_time_vs_AC_DC.png
│   ├── incident_6_time_vs_AC_DC.png
│   ├── incident_7_speed_vs_time.png
│   ├── incident_7_time_vs_events.png
│   ├── round_localization_map.png
│   ├── temporal_speed_AC_DC_distribution.png
├── Data_mining_SNCB.ipynb
├── README.md
```
## Project Overview

This project was carried out in the context of a data mining course and aims to **reproduce and improve the results of an existing research paper** on incident detection and classification in SNCB railway data.

The original paper reports an **F1-score of approximately 85%**. By extending the feature set and refining the modeling strategy, we were able to **improve the performance to around 86–87% F1-score** on the evaluation dataset.

---

## Main Contributions

Our main contributions compared to the original paper are:

- **Extended feature representation**:  
  Instead of relying only on event occurrences before and after an incident, we explicitly incorporate:
  - **AC current**
  - **DC current**
  - **Train speed**
  - **Temporal information**
  
  This allowed us to capture richer dynamics around incidents.

- **Pattern discovery**:  
  We identified **distinct patterns specifically associated with AC, DC, and speed signals**, which provide strong discriminative power for certain incident classes.

- **Event-class specificity after filtering**:  
  After applying event filtering, we observed that:
  - A **small subset of events becomes highly specific to certain classes** in the training set.
  - These events also appear with **high probability in the test set for the same class**.
  
  This insight was leveraged to enhance the classification strategy.

- **Hybrid approach with Naive Bayes**:  
  We combined these observations with the **Naive Bayes model proposed in the original paper**, improving robustness and predictive performance.

- **Critical analysis of Naive Bayes formulation**:  
  We highlighted that the Naive Bayes formulation can be **problematic for this dataset due to counting issues**, especially when dealing with rare or highly specific events. This limitation was explicitly analyzed and discussed.

---

## Results

By integrating signal-based features (AC, DC, speed, time) and class-specific event patterns, our approach achieves a **consistent improvement over the baseline**, reaching an **F1-score of approximately 86–87%**, compared to the 85% reported in the original study.

---

## Repository Structure

- `doc/` — Reference paper, slides, and project presentation  
- `figures/` — Visualizations and performance analysis plots  
- `Data_mining_SNCB.ipynb` — Main notebook containing data processing, modeling, and evaluation  
- `README.md` — Project documentation
