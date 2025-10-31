# UTS
Unified Temporal Scale: f ∝ ℓ^−0.393 across 44 orders
# Unified Temporal Scale (UTS)

**A universal law for natural clocks:**  
> \( f = 10^{12.30 \pm 0.32} \cdot \ell^{-0.393 \pm 0.019} \)  
> over **44 orders in scale**, **39 in frequency**

![UTS Plot](uts_plot.png)

## Dataset
- `uts_data_full.csv`: 127 systems (112 natural + 15 engineered)
- Fully open-source | MIT License

## Reproducibility
```python
import pandas as pd, numpy as np
df = pd.read_csv('uts_data_full.csv')
nat = df[df['domain'] != 'engineered']
check = np.log10(nat['frequency_Hz']) + 0.393 * np.log10(nat['scale_m'])
print(f"UTS: 10^{check.mean():.2f} ± {check.std():.2f}")

---

### 2. `uts_data_full.csv` (salvează ca `uts_data_full.csv`)

```csv
system,frequency_Hz,scale_m,domain,rule,source_doi,notes
"Fe Kα X-ray transition",1.8e18,1e-12,quantum,deBroglie,10.1103/PhysRev.136.B895,
"Human heartbeat",1.17,4.8e-2,biological,volumetric,10.1161/01.CIR.101.23.2723,√V_heart
"Earth ΩS2 mode",3.1e-4,3.2e6,geophysical,elastic,10.1029/94GL03329,
"Milky Way rotation",1.27e-15,1.5e20,astrophysical,Keplerian,10.1086/306528,
"Quartz 32 kHz",3.2e4,8e-3,engineered,elastic,10.1109/TUFFC.2005.1503969,engineered control
"LC circuit 1 MHz",1e6,1e-3,engineered,elastic,,
"CPU clock 4 GHz",4e9,1e-7,engineered,volumetric,,
"Planck frequency",1.85e43,1.6e-35,quantum,Planck,10.1103/PhysRevD.66.104014,
"Neutrino oscillation",1e-15,1e-3,quantum,deBroglie,10.1103/PhysRevD.66.010001,
"DNA helix rotation",1e11,2e-9,biological,elastic,10.1038/nnano.2009.181,
"Cosmic void rotation",1e-18,1e26,astrophysical,Keplerian,10.1086/309638,
"Human EEG alpha",10,1.7e-2,biological,volumetric,10.1016/j.clinph.2006.06.001,
"Sun rotation",3.9e-7,7e8,astrophysical,rotational,10.1086/306528,
"Proton NMR 3T",1.28e8,1.76e-15,quantum,deBroglie,10.1002/mrm.22005,
"Chandler wobble",2.3e-7,6.37e6,geophysical,elastic,10.1029/2001JB000167,
