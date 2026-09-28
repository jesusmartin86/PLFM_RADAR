# RADAR ANTIDRONE – PLFM_RADAR Derivative

This directory contains the controlled development baseline for the RADAR ANTIDRONE derivative of PLFM_RADAR.

## Baseline
- Upstream project: NawfalMotii79/PLFM_RADAR
- Fork: jesusmartin86/PLFM_RADAR
- Initial upstream commit: 749bd0f86a07a28a86347d8ce9c141e601057c40
- Working branch: radar-antidrone-m0

## Development policy
The upstream project is treated as a reference implementation, not as a fabrication-ready frozen design. No PCB order or procurement release should be based directly on the inherited production files until the hardware, BOM, stack-up, waveform, FPGA target, and RF performance have been independently reconciled and validated.

## Initial milestones
1. M0 – Requirements and baseline audit
2. M1 – Golden radar simulation and waveform definition
3. M2 – Digital FPGA/host verification against independent golden models
4. M3 – 1TX/1RX bench radar
5. M4 – Multi-channel beamformer demonstrator
6. M5 – Array integration and calibration
7. M6 – Detection, tracking, classification, and system integration

See M0_AUDIT_PLAN.md for the initial audit gates.
