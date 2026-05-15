# nfl-monte-carlo

Monte Carlo simulation of the 2026/27 NFL season — predicting Super Bowl odds and playoff probabilities for all 32 teams across 10,000 iterations.

Built as a semester project for a probability theory course at university.

## How it works

Each simulation runs a full 272-game regular season using the official 2026 NFL schedule, then a complete playoff bracket through the Super Bowl. Team strength is derived from Vegas win totals via an Elo rating system. Scoring is modeled with a Poisson distribution, day-to-day variance with a Normal distribution.

After 10,000 iterations, the results converge to stable probability estimates for every team.

## Repository structure

```
nfl-monte-carlo/
├── code/
│   ├── nfl_simulation.qmd       # Full simulation report (Quarto HTML)
│   └── nfl_praesentation.qmd   # Presentation slides (Quarto revealjs)
└── output/
    └── ...                      # Rendered HTML, slides, and charts
```

## Key parameters

| Parameter | Value | Description |
|---|---|---|
| `N_SIM` | 10,000 | Number of simulated seasons |
| `BASE_POINTS` | 23.0 | League-average points per game |
| `HOME_BONUS` | 2.0 | Home-field advantage (in expected points) |
| `FORM_SD` | 8.5 | Day-to-day performance variance |
| `DEF_WEIGHT` | 0.1 | Weight of 2025 defensive ratings |

## Running the simulation

Requires [R](https://www.r-project.org/) and [Quarto](https://quarto.org/).

```bash
quarto render code/nfl_simulation.qmd
quarto render code/nfl_praesentation.qmd
```

## Authors

Silvan Herzig & Jay Bärtschi — FS 2026
