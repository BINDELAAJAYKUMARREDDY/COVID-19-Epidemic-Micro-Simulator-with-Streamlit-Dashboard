# COVID-19 Epidemic Micro-Simulation Across Countries

**Author:** BINDELA AJAY KUMAR REDDY  
**November 2025**

A stochastic, agent-based micro-simulation that models the daily spread of COVID-19 in any selected countries using age-stratified Markov chains. The simulator tracks individual transitions between five health states (Healthy, Infected asymptomatic, Symptomatic, Immune, Deceased) and naturally produces realistic epidemic waves.

![Simulation Output](a2-covid-simulation.png)

---

### Features

- Age-specific transition probabilities & holding times
- Realistic population sampling based on actual country demographics and age structures
- Daily individual-level simulation (395 days default period)
- Aggregated time-series per country and date
- Clear stacked bar visualization showing multiple epidemic waves
- Interactive **Streamlit** web dashboard

---

### Project Files
.
├── a2-countries.csv                  # Real demographic & age-group data (153 countries)
├── sim_parameters.py                 # Transition probabilities & holding times
├── helper.py                         # Plotting utility (provided)
├── assignment2.py                    # Core simulation engine
├── streamlit_ui.py                   # Interactive web app
├── test.py                           # Example run / quick test
├── sample_population.csv             # Generated sample (example)
├── a2-covid-simulated-timeseries.csv # Full individual trajectories
├── a2-covid-summary-timeseries.csv   # Daily country-level summary
├── a2-covid-simulation.png           # Final stacked bar chart
└── README.md
text---

### Health States

| State | Meaning                     | Plot Color    |
|-------|-----------------------------|---------------|
| H     | Healthy                     | Green         |
| I     | Infected (no symptoms)      | Orange        |
| S     | Infected (symptomatic)      | Red           |
| M     | Immune / Recovered          | Teal          |
| D     | Deceased                    | Gray          |

---

### How to Run

#### 1. Install dependencies
```bash
pip install pandas matplotlib streamlit numpy
2. Launch the interactive dashboard (recommended)
Bashstreamlit run streamlit_ui.py
→ Opens at http://localhost:8501
Select countries, adjust sample ratio and dates, then click Go.
3. Run directly via Python
Pythonfrom assignment2 import run

run(
    countries_csv_name="a2-countries.csv",
    countries=["Afghanistan", "Sweden", "Japan"],
    sample_ratio=1_000_000,
    start_date="2021-04-01",
    end_date="2022-04-30"
)
Generates all output files including the final plot.

Example Results
Afghanistan · Sweden · Japan
Multiple natural waves emerge from purely individual stochastic transitions — no external forcing required.

Notes

Infection rates are intentionally high for clearer visualization of waves
No vaccination or non-pharmaceutical interventions are modeled
Results vary slightly each run due to randomness
Lower sample_ratio → higher resolution (but slower)


All required outputs are included and verified.
Ready to run, explore, and extend.
Made by BINDELA AJAY KUMAR REDDY
November 2025
