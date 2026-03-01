# Timeseries Explorer

Interactive time series exploration tool for decomposition, forecasting, anomaly detection, and visualization of health indicators.

## Architecture

```
timeseries-explorer/
  src/           # Core modules
  tests/         # Unit and integration tests
  config/        # Configuration files
  docs/          # Documentation
```

## Modules

- **loader**: Core loader functionality
- **decomposer**: Core decomposer functionality
- **forecaster**: Core forecaster functionality
- **visualizer**: Core visualizer functionality
- **anomaly_finder**: Core anomaly finder functionality

## Quick Start

```bash
pip install -r requirements.txt
python -m timeseries_explorer.main
```

## Testing

```bash
pytest tests/ -v
```

## License

MIT License - see LICENSE for details.
