# Healthcare Zero-Shot Forecasting

A Python-based forecasting system for modeling healthcare customer journeys without historical data.

## Overview

This project implements a 24-month rolling forecast model for healthcare customer journey analysis, focusing on:
- Customer progression: signup → appointment → prescription → delivery → refill
- Seasonality patterns and daily variations
- Confidence intervals with time-based uncertainty growth
- Configurable conversion rates and delays

## Requirements

- Python 3.13
- Required packages: numpy, pandas, matplotlib
- Development environment: Windows, VS Code, Jupyter Notebook

## Project Structure

```
├── lab-01_v0.2.ipynb       # Latest implementation
├── lab-01_v0.2_001.ipynb   # Code-only version of latest implementation
├── lab-01_v0.1.ipynb       # Initial implementation
└── initial-assumptions.md   # Business requirements
```

## Core Components

1. BaseParameters
   - Configurable conversion rates
   - Stage-specific delays
   - Seasonality patterns
   - Daily patterns

2. VolumeForecaster
   - Daily signup generation
   - Stage transition calculations

3. ConfidenceIntervals
   - Time-based uncertainty modeling
   - Upper/lower bound calculations

4. RetentionCalculator
   - Linear retention decay
   - Refill pattern modeling

## Usage

```python
from datetime import datetime
forecaster = HealthcareForecaster(base_daily_signups=100)
forecast = forecaster.generate_forecast(datetime(2024, 1, 1))
```

## Configuration

Default parameters:
- Base daily signups: 100
- Monthly churn rate: 15%
- Base uncertainty: 10%
- Uncertainty growth: 1% per day

## Future Enhancements

Planned features:
- Geographic distribution
- Marketing campaign effects
- Capacity constraints
- Multiple customer journeys
- Customer segmentation

## Development Guidelines

- Follow Google-style docstrings
- Maintain Python naming conventions
- Optimize for performance
- Minimize try/except blocks
- No type hints or assertions


## Acknowledgments
This project uses [TimesFM](https://github.com/google-research/timesfm), an open-source time series forecasting framework.