# Skinner39 Battery Accuracy Tuning

This keyboard uses a battery voltage divider in:

- `boards/FindKBtokyoJP/skinner39/skinner39.dtsi`
- Node: `vbatt`
- Current values:
  - `output-ohms = <2000000>;`
  - `full-ohms = <(2000000 + 806000)>;`

## Why battery % can look wrong

Battery percentage is inferred from measured voltage. If the resistor values in firmware do not match real hardware, displayed percentage will drift.

## Calibration procedure

1. Fully charge battery and let it rest 10–15 minutes.
2. Measure battery voltage with a multimeter at the battery terminals.
3. Compare measured voltage with displayed battery percent.
4. Repeat around mid-charge and low-charge.
5. If mismatch is consistent, update divider values in `skinner39.dtsi` to match real resistor values.

## Divider math reminder

If:

- top resistor = $R_{\text{top}}$
- bottom resistor = $R_{\text{bottom}}$

Then set:

- `output-ohms = <R_bottom>;`
- `full-ohms = <(R_top + R_bottom)>;`

Current firmware implies:

- $R_{\text{bottom}} = 2.0\text{ M}\Omega$
- $R_{\text{top}} = 806\text{ k}\Omega$

## Practical notes

- Keep BLE/radio tuning in `skinner39.conf` focused on power/latency balance.
- Battery accuracy is mostly a **measurement calibration** issue, not a BLE issue.
- If your PCB uses different resistor population than the DTS values, correcting DTS is the highest-impact fix.