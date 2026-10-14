# GML files anonymized for reproducibility

These six GML files are one-to-one anonymized versions of the exact graph snapshots used by the temporal link-prediction experiments.

## What was preserved
- Exact graph topology (same nodes/edges up to one-to-one relabeling).
- Node insertion order and edge insertion order.
- Node type (`tipo`).
- Article year (`Year`).
- Equality structure of article areas (`Area`) via anonymized category IDs.
- Equality structure of bibliographic attributes via anonymized IDs.
- Coauthorship topology in all author subgraphs.
- A globally consistent author mapping across all periods.
- Lexicographic author order, so fixed-seed sampling over sorted author lists is preserved.

## What was anonymized
- Author labels.
- Article-title labels.
- Keyword labels.
- Affiliation labels.
- DOI, URL, ISBN, ISSN, Abstract and Area values are replaced by non-identifying IDs while preserving equality relations.
- Affiliation attributes in author subgraphs are replaced by anonymized IDs.

No real-to-anonymous mapping is included.

## Reproducibility conclusion
`audit_exact_anonymization.csv` verifies exact node/edge equivalence under the internal one-to-one relabeling.
`audit_temporal_sampling_equivalence.csv` verifies that the final temporal protocol produces the same eligible-author ordering and the same positive and fixed-seed random-negative pairs under anonymization.

Therefore the deterministic graph-derived inputs used by P4-P8 are preserved exactly. P9 uses the same graph topology, node-type counts, fixed seed values and order-preserving author IDs; its inputs are therefore equivalent. As with any neural training pipeline, tiny numerical differences can still occur across hardware/library versions unless the execution environment is identical, even when deterministic settings are requested.
