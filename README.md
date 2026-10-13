Purpose: Link prediction in graph-based systems is highly sensitive to the
evaluation regime under which candidate links are constructed and assessed.
In particular, transductive structural exposure should not be conflated with
data leakage, whereas the use of future or test-dependent information can
produce genuinely optimistic estimates of predictive performance. This study
examines how temporal information availability and evaluation design affect
scientific collaboration prediction.

Methods: A leakage-aware temporal evaluation framework was applied to an
academic collaboration network constructed from Universidad Nacional Autónoma
de México (UNAM) bibliographic data. Historical information from 2000--2020
was used for development on collaborations formed during 2021--2022, and
information from 2000--2022 was used for final prediction of collaborations
formed during 2023--2024. Structural features and GNN message passing were
restricted to historical information. Sensitivity analyses examined
coauthorship thresholds of 1, 2, 3, and 5 publications, positive-to-negative
ratios of 1:1, 1:5, and 1:10, and random versus matched hard-negative sampling.
Classical classifiers and four GNN architectures (GCN, GAT, GraphSAGE, and GIN)
were evaluated. GNN comparisons used 32 stochastic repetitions with distinct
random seeds, paired Wilcoxon signed-rank tests, and Holm correction.

Results: Increasing the coauthorship threshold sharply reduced the number of
available future positive links, making thresholds above one publication
unsuitable for reliable supervised evaluation in the present dataset.
For classical models, the best AUC-PR decreased from 0.777 under a 1:1 class
ratio to 0.431 under 1:5 and 0.297 under 1:10. Changing from random to matched
hard negatives reduced the best AUC-PR from 0.787 to 0.533. Among GNNs, GIN
obtained the highest mean AUC-PR (0.584), whereas GraphSAGE achieved the
highest mean AUC-ROC (0.551) and F1 score (0.438). After Holm correction,
GraphSAGE significantly outperformed GAT in AUC-ROC, AUC-PR, and F1, whereas
no uniform superiority was established among GIN, GraphSAGE, and GCN.

Conclusion: Link-prediction performance should be interpreted as a property
of the complete evaluation regime rather than of model architecture alone.
Temporal information availability, class prevalence, collaboration definition,
negative-sample difficulty, and stochastic variation materially affect measured
performance. Leakage-aware evaluation therefore requires explicit control of
the information available at prediction time and alignment between the
evaluation protocol and the intended deployment setting.
