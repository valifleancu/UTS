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
