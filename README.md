**Network-Based Drug Repurposing for Rheumatoid Arthritis**
This project implements a Systems Biology approach to identify potential drug repurposing candidates using thehuman protein-protein interactome and network medicine principles. 
Network pharmacology pipeline that screens existing drugs for repurposing potential in rheumatoid arthritis, using the network proximity framework 
from Guney et al. (2016, *Nature Communications*). 
The core idea is that a drug is a repurposing candidate if its protein targets sits close to the RA disease module 
in a human protein-protein interaction (PPI) network — closer than would be expected by chance. There is a chance of repurposing the drug or drug combinations to RA then.

Data Sources 
  Disease genes: Open Targets (EFO_0000685, score ≥ 0.30)
  PPI network: STRING v12.0 (combined score ≥ 700)
  Drug-target interactions: DGIdb 
Raw Data 
Large files not tracked by git. Download from: - 
  STRING: https://stringdb-downloads.org/download
  protein.links.detailed.v12.0/ and protein.info.v12.0/ -> DGIdb: https://dgidb.org/download

Pipeline

1. **Disease gene collection** — RA-associated genes pulled from Open Targets (EFO_0000685), filtered to association score ≥ 0.30 (330 genes).
2. **PPI network construction** — human interactome from STRING v12.0, filtered to combined_score ≥ 700 (~16,000 proteins, ~237,000 interactions).
3. **Disease module construction** — RA gene set expanded into a connected module via linker-node expansion.
4. **Drug-target data** — drug-target interactions pulled from DGIdb.
5. **Network proximity calculation** (current stage) — proximity between each drug's target set and the RA disease module, benchmarked against a degree-preserving random reference to get a z-score per drug.
