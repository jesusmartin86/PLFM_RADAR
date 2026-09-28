# Open Risks – Initial Register

| ID | Risk | Severity | Initial disposition |
|---|---|---:|---|
| R-001 | Main-board CAD appears tied to XC7A50T-FTG256 while parts of the repo describe XC7A200T-FBG484 as production | Critical | Reconcile before FPGA or PCB freeze |
| R-002 | Current integrated RTL may exceed XC7A50T DSP/BRAM capacity | Critical | Rebuild locally; evaluate XC7A100T-FTG256 |
| R-003 | Tracked BOM variants may not agree with CAD or each other | Critical | Regenerate master BOM from CAD |
| R-004 | Gerbers may not be provably synchronized to current schematics/board files | Critical | Re-export and binary/geometric compare |
| R-005 | Reported waveform bandwidth differs between documentation and RTL discussions (500 MHz vs 20 MHz) | Critical | Establish waveform source of truth |
| R-006 | Full RF end-to-end performance has insufficient independent hardware validation | High | Build staged 1TX/1RX demonstrator |
| R-007 | Main-board stack-up sources appear inconsistent in outer dielectric thickness/material details | High | Reconcile CAD, stack-up drawing, and fab note |
| R-008 | Some passive MPN/footprint entries have been questioned upstream | High | Full MPN and footprint audit |
| R-009 | ADC SPI is strap-configured rather than fully software-controlled on current hardware | Medium | Decide whether redesign is justified |
| R-010 | Range claims are not yet tied to a frozen RCS/Pd/Pfa design requirement | High | Define target classes and radar equation budget |
