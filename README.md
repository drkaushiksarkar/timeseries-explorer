# Timeseries Explorer

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)](https://python.org)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.x-FF4B4B?logo=streamlit)](https://streamlit.io)
[![Time Series](https://img.shields.io/badge/Focus-Time%20Series%20EDA-lightblue)](https://github.com/drkaushiksarkar/timeseries-explorer)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

Interactive exploratory data analysis (EDA) tool for time-series datasets. Upload a file, select columns, and immediately get decomposition plots, stationarity tests, autocorrelation analysis, and summary statistics -- no coding required.

## Overview

Time-series EDA typically requires writing the same boilerplate analysis code for every new dataset. Timeseries Explorer wraps that workflow into a browser-based interface built with Streamlit, making it accessible to analysts and domain experts who need fast insight without a development environment.

## Features

- **Upload and preview**: CSV, Excel, and Parquet file support with automatic datetime column detection
- **Trend and seasonality decomposition**: STL and classical additive/multiplicative decomposition with configurable period
- **Stationarity testing**: ADF and KPSS tests with plain-language interpretation of results
- **Autocorrelation plots**: ACF and PACF correlograms with confidence bands for ARIMA order selection
- **Missing value audit**: Gap detection, interpolation preview, and fill-forward/backward options
- **Outlier flagging**: IQR and z-score based flagging with interactive threshold slider
- **Export**: Download any chart as PNG or the cleaned series as CSV

## Architecture

```
Browser (Streamlit UI)
  |-- Upload widget     Accepts CSV / Excel / Parquet
  |-- Column selector   Datetime index + value columns
  |-- Analysis tabs     Decomposition | Stationarity | ACF | Outliers
  |-- Export panel      PNG / CSV download
        |
        v
Python backend
  statsmodels (decomposition, ADF/KPSS, ACF/PACF)
  pandas (parsing, resampling, gap detection)
  matplotlib / Plotly (charts)
```

## Supported Formats

| Format | Notes |
|---|---|
| CSV | Auto-detects separator; supports ISO 8601 and common date formats |
| Excel (.xlsx) | Reads first sheet by default; sheet selector available |
| Parquet | Preferred for large files; preserves dtype metadata |

Recommended maximum file size: 200 MB. Series longer than 500 K rows are downsampled for display but analysed in full.

## Usage

```bash
pip install -r requirements.txt
streamlit run app.py
# Opens on http://localhost:8501
```

To deploy on Streamlit Community Cloud, fork the repo and connect it via share.streamlit.io. No additional configuration required.

## Tech Stack

Python 3.10, Streamlit, pandas, statsmodels, NumPy, Plotly, openpyxl, pyarrow
