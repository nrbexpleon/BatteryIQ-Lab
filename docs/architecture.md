# Architecture

## Layers

1. **Domain:** pack and telemetry validation, estimators, diagnostics, gates, fleet aggregation, comparison and evidence.
2. **Application:** bounded report retention and campaign coordination.
3. **Delivery:** loopback REST API and browser dashboard.
4. **Future adapters:** CAN/UDS, SmartVehicle, VSS, time-series stores, HIL and fleet platforms.

## Data conventions

- Current is positive during discharge and negative during charge.
- Voltage is volts, current amperes, capacity ampere-hours, energy kilowatt-hours, temperature degrees Celsius and distance kilometres.
- Timestamps are strictly increasing integer milliseconds.
- Cell arrays must equal the declared pack cell count.

## Decisions

Automated gates identify obvious engineering concerns. A passing run is only eligible for human review. No result authorizes a BMS calibration change, charging action, service intervention or vehicle operation.
