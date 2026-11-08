\# Premier League Match Outcome Predictor



Predicts home win, draw or away win probabilities for Premier League matches using each team's recent form. Built with pandas and scikit-learn.



\## Data

Match results and bookmaker odds from football-data.co.uk, seasons 2016/17 to 2025/26 (3,800 matches).



\## Method

\- Rolling average of each team's last 5 matches (goals scored, goals conceded, points), computed from past games only to avoid data leakage.

\- Time-based split: trained on 2016/17 to 2023/24, tested on 2024/25 and 2025/26.

\- Models: logistic regression and random forest, compared with a baseline and with bookmaker odds.



\## Results



| Model | Accuracy | Log loss |

|---|---|---|

| Always predict home win | 41.9% | |

| Class frequencies only | | 1.082 |

| Random forest | 46.9% | 1.073 |

| Logistic regression | 48.6% | 1.049 |

| Bookmakers (Bet365 odds) | 51.7% | 0.995 |



!\[Log loss comparison](images/log\_loss\_comparison.png)

!\[Confusion matrix](images/confusion\_matrix.png)

!\[Calibration](images/calibration.png)



\## Example prediction

Newcastle vs Arsenal (21 Nov 2026): Newcastle win 38.2%, draw 25.8%, Arsenal win 36.0%.



\## Limitations

\- Draws are never predicted.

\- Only 6 form features: no team strength, injuries or lineups.

\- The model does not beat the bookmakers.



\## Next steps

Add team strength ratings, home and away form separately, and expected goals data.



\## How to run

1\. Create a virtual environment and run `pip install -r requirements.txt`.

2\. Open `pl\_match\_predictor.ipynb` and run all cells.

