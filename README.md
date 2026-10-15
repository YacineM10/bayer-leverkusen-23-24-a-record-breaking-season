![Bayer Leverkusen Banner](./Images/banner.png)

## Description
This project analyzes Bayer Leverkusen’s 2023/24 Bundesliga season (28 wins, 6 draws, 0 losses) using StatsBomb open event data.
A Python notebook extracts and cleans match events, lineups, passes, shots and minutes played for Bayer's 34 league matches.
A Power BI report then visualizes the season: most used starting XI, top scorers and assisters, and a per-match player view with passing and shooting maps.

## Data Sources
- [StatsBomb Open Data](https://github.com/statsbomb/open-data), 1. Bundesliga 2023/24 (competition 9, season 281)

## Contents
| Path | Description |
|---|---|
| `BayerLeverkusen_EN.ipynb` | Data extraction and cleaning notebook: regenerates every CSV in `Data/` |
| `BayerLeverkusen_report.pdf` | PDF export of the Power BI report |
| `Data/bayer_matches.csv` | The 34 league matches and their scores |
| `Data/bayer_squad.csv` | Players who appeared, with display names, general position and photo URL |
| `Data/passes_bayer.csv` | Every Bayer pass, with start/end coordinates and outcome |
| `Data/shots_bayer.csv` | Every Bayer shot, with coordinates, outcome and StatsBomb xG |
| `Data/starting_bayer.csv` | Most used starting XI, with pitch coordinates for the lineup visual |
| `Data/minutes_bayer.csv` | Minutes played per player and match (stoppage time included) |
| `Data/player_extra_info.csv` | Hand-curated input: general position and photo URL per player |

All CSVs use `;` as separator and UTF-8 with BOM, so they open correctly in Excel and Power BI.

## Usage
```bash
pip install -r requirements.txt
jupyter nbconvert --to notebook --execute --inplace BayerLeverkusen_EN.ipynb
```
(or open the notebook and use *Restart & Run All*). The data is downloaded from StatsBomb Open Data, no account needed.
Then refresh the Power BI report to load the updated CSVs.

To add a player, add a row to `Data/player_extra_info.csv`: the notebook stops with an explicit message if a player is missing.

## Note on Report Format
Due to technical and licensing limitations with Power BI, the interactive version of this report cannot be publicly shared online; the PDF export shows each page.

## Credits
Project by Yacine M.

Data provided by StatsBomb.
