## Final Project For Machine Learning
William Haufrect and Toby Draper

# NBA Playoff Success Prediction — The Championship Contender Detector

# Question & Background

**Primary question:** *Can regular-season statistics predict how far an NBA team will advance in the playoffs well enough to outperform the naive "trust the top seeds" baseline?*

This addresses the question asked at the beginning of every playoffs: is a team a true contender, or just a pretender? Our model maps each team's regular-season profile to a predicted playoff depth, and derives a champion pick. The goal is to beat the simple "trust the higher seed" baseline.

**Ladder framing.** We treat playoff success as an ordinal outcome (0 = missed playoffs, 1 = lost 1st round, 2 = lost 2nd round, 3 = lost Conf Finals, 4 = lost Finals, 5 = won championship). A team that loses in the Finals is closer to a champion than a team that loses in the 1st round — the ladder captures that ordering.

**What this is and isn't.** This is not a perfect predictor of every team's exit round. Playoff series have high variance, and matchups and injuries cause randomness the model can't see. What this model is trained to do is sort teams into tiers; the model's high-confidence contenders should advance further on average than its low-confidence picks, and further than the seed-based baseline predicts.

**Data.** The Kaggle [NBA Database (`wyattowalsh/basketball`)](https://www.kaggle.com/datasets/wyattowalsh/basketball) — CSV files covering NBA games from 1946 to 2023. We narrow to 2002-2003 season onward so every season uses best-of-7 first round (champions need 16 wins, keeping the ladder labels clean).

**Why this topic.** It sits at the intersection of sports analysis and data science. As basketball fans, we thought it would be especially interesting to build this while the actual NBA playoffs are happening.
