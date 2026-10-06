# Field-Derived Duty Cycles for Fuel Cell Heavy-Duty Truck Capacity Sizing

This repository contains the three power-demand cycles used in the study
"Bilevel Capacity Sizing of Multi-Stack Fuel Cell Heavy-Duty Trucks Using Field Data and Health-Aware Dispatch".

The research team conducted a 306-day field measurement campaign involving three identical heavy-duty logistics trucks operating between Fujian Province and the Chaoshan region of eastern Guangdong Province, China. The retained records comprise 19.518 million 1-Hz samples and a combined distance of 212,117 km. After preprocessing, 7602 valid micro-trips were described by 13 power-domain features. Principal-component analysis and fuzzy C-means clustering were then used to construct two cluster-specific typical cycles and the global representative cycle used for capacity sizing.

Only the reduced, anonymised time--power cycles are included. The repository does not contain raw vehicle identifiers, geographic coordinates, route timestamps, or fleet account information.

The uploaded files are representative cycles rather than the complete 19.518-million-sample field record. Their substantially smaller file size and sample count therefore reflect duty-cycle reduction, not an additional power scaling or a loss of units.

## Files

| File | Description | Samples | Duration |
| --- | --- | ---: | ---: |
| `data/global_representative_cycle.csv` | Global representative cycle used by the capacity-sizing model | 4602 | 4602 s |
| `data/typical_cycle_1.csv` | Cluster-1 typical cycle | 3907 | 3907 s |
| `data/typical_cycle_2.csv` | Cluster-2 typical cycle | 695 | 695 s |
| `data/cluster_summary.csv` | Cluster time weights, micro-trip counts, and representative-cycle lengths | 2 clusters | -- |

## Data format

The three cycle files contain:

- `Time_s`: elapsed time in seconds, sampled at 1 Hz;
- `Power_kW`: traction-system electrical demand in kW. Positive values denote propulsion demand, and negative values denote power available from regenerative braking.

The global cycle concatenates the complete cluster-1 and cluster-2 typical cycles without multiplying their power values by the cluster weights. Cluster 1 accounts for 82.9946% of measured operating time, and cluster 2 accounts for 17.0054%. Because complete micro-trips are retained, their reconstructed shares in the 4602-s global sequence are 84.90% and 15.10%, respectively (3907 and 695 samples).

## Suggested citation

Please cite the associated paper when using these data:

J. Mei, C. Sun, X. Meng, H. M. Hasanien, M. Zadeh, and Z. Li, "Bilevel Capacity Sizing of Multi-Stack Fuel Cell Heavy-Duty Trucks Using Field Data and Health-Aware Dispatch," manuscript.

## Contact

For questions about the data-processing procedure, please contact the corresponding author through the contact information provided in the paper.
