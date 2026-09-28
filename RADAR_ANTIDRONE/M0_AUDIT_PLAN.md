# M0 – Requirements and Baseline Audit

## Objective
Establish a trustworthy technical baseline before modifying hardware or releasing procurement.

## P0 gates

### 1. Source-of-truth reconciliation
- Identify authoritative schematic and board files for each PCB.
- Regenerate BOM and placement data from CAD where possible.
- Diff regenerated manufacturing outputs against tracked Gerbers/CPL/BOM.
- Record all inconsistencies and unresolved provenance.

### 2. FPGA target reconciliation
- Confirm physical production FPGA/package from CAD.
- Audit compatibility of XC7A50T-FTG256 versus potential XC7A100T-FTG256 upgrade.
- Build current integrated RTL for each realistic FPGA target.
- Record LUT/FF/BRAM/DSP utilization and timing.
- Do not accept a target solely because a documentation page labels it “production”.

### 3. Waveform truth model
Define, from one source of truth:
- carrier frequency
- chirp direction
- sweep start/stop
- RF bandwidth
- chirp duration
- PRF
- CPI
- number of chirps
- ADC sample rate
- digital decimation chain

Derive and test:
- theoretical range resolution
- unambiguous range
- Doppler resolution
- unambiguous radial velocity
- expected data rate

Resolve the reported 20 MHz versus 500 MHz discrepancy before hardware freeze.

### 4. RF chain audit
For TX and RX, create a block-level gain/noise/power budget covering:
- synthesizer
- mixers / LO distribution
- beamformer
- PA
- LNA
- filtering
- ADC input level
- TX/RX leakage

Record absolute maximum ratings and nominal operating points.

### 5. PCB manufacturing audit
- Reconcile stack-up drawings against CAD stack-up.
- Verify controlled-impedance assumptions and laminate Dk.
- Check known component/footprint concerns from upstream issues.
- Confirm current Gerbers include known fixes.
- Generate a fabrication release checklist.

### 6. Software and DSP audit
Independent golden models must be created for:
- DDC
- matched filtering / range processing
- Doppler processing
- CFAR
- frame/USB protocol

RTL tests are necessary but are not accepted as the only correctness oracle.

## M0 outputs
- AUDIT_FINDINGS.md
- HARDWARE_BASELINE.md
- WAVEFORM_BASELINE.md
- FPGA_TARGET_DECISION.md
- BOM_MASTER.csv
- OPEN_RISKS.md

## Exit criteria
M0 is complete only when:
- no unresolved blocker remains for the selected first hardware demonstrator,
- waveform parameters are internally consistent,
- the selected FPGA target fits with margin and timing,
- manufacturing files have a traceable source,
- procurement BOM has validated MPNs or approved alternates.
