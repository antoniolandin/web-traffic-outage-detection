# Outage Detection in Web Traffic Using Statistical Models and Neural Networks

Bachelor's thesis in Software Engineering, U-tad (Madrid), 2026.
Author: Antonio Cabrera Landín · Supervisor: Stanislav Vakaruk

- [English translation (PDF)](thesis-en.pdf)
- [Original in Spanish (PDF)](thesis-es.pdf)

## Abstract

Development of an application-outage alerting system based on anomaly detection over traffic time series. Real production data from 2023 to 2025 are used, belonging to a nationwide application whose existing rule-based alarm system generates an excessive number of false positives. After a manual selection, 355 incidents covering total and partial outages were labeled and used as the ground truth on which the models are evaluated.

Four detectors are implemented under identical conditions: a heuristic baseline, a SARIMAX model, the DeepAnT convolutional network and an LSTM recurrent network. The comparison over the test set places the LSTM as the most accurate detector (F1 = 0.675 and NAB score of 65.53), closely followed by DeepAnT. The final deliverable integrates the three best-performing models (baseline, DeepAnT and LSTM) into a real-time monitoring system with a dashboard interface, applying a consensus criterion among detectors that reduces individual false positives.

## Results on the test set

| Detector | Event-based F1 | NAB score | Median detection latency | Total false-alarm time |
|---|---:|---:|---:|---:|
| LSTM | 0.675 | 65.53 | 22 min | 6 h 55 min |
| DeepAnT (CNN) | 0.640 | 61.11 | 21 min | 11 h 25 min |
| Heuristic baseline | 0.530 | 15.03 | 32 min | 13 h 10 min |
| SARIMAX | 0.272 | −78.01 | 26 min | 442 h 30 min |

The monitoring dashboard is a prototype that replays the test set; it was not deployed in production.

## Data

The data come from a company that wishes to remain anonymous. They are not published, and the documents leave out any detail that could identify it.

## Tools

Python, pandas, NumPy, Statsmodels, Statsforecast, Keras/TensorFlow, Optuna, Matplotlib, Plotly and Dash.

## About the translation

The English version was translated from the Spanish original with the help of an AI model. The abstract is the author's own English text, and the figures keep their original Spanish labels. In case of any discrepancy, the Spanish original prevails.
