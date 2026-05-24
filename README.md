# scRNA-seq Analysis: GSE279086 (Diabetic vs Healthy Kidney)

## Project Overview
Industry-oriented single-cell RNA-seq analysis of human kidney samples comparing Diabetic and Healthy conditions.

**Dataset:** GSE279086 | 40 samples | 181,842 cells (pre-QC)

**Conditions:** Diabetic (29 samples) vs Healthy (11 samples)

## Pipeline Summary
| Step | Tool | Output |
|------|------|--------|
| Data loading | Seurat | 40 RDS objects |
| QC filtering | Seurat | 25,220 cells retained |
| Normalization | LogNormalize | Normalized counts |
| Dimensionality reduction | PCA (50 PCs) + UMAP | 2D embedding |
| Batch correction | Harmony | 28 clusters |
| Cell type annotation | CellTypist | Immune_All_Low model |
| DEG analysis | MAST | Diabetic vs Healthy per cell type |

## QC Parameters
- Min features: 200, Max features: 7000
- Max mitochondrial %: 20%
- Max ribosomal %: 20%
- Mahalanobis threshold: 0.95

## Results
- Cells after QC: 25,220
- Diabetic: 19,347 | Healthy: 5,873
- Clusters identified: 28 (Harmony-corrected)

## Tools Used
R: Seurat, Harmony, MAST, ggplot2
Python: CellTypist, Scanpy, AnnData
