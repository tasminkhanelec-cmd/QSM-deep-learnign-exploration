# Deep Learning for MRI Quantitative Susceptibility Mapping (QSM)

## Overview

This repository contains the research documentation for an undergraduate thesis project exploring deep learning approaches to MRI Quantitative Susceptibility Mapping (QSM) reconstruction. The work investigates data-driven solutions to address the ill-posed nature of dipole inversion in QSM, with particular attention to magnetic anisotropy effects.

## Background

Quantitative Susceptibility Mapping is an MRI technique that visualizes magnetic susceptibility distributions in biological tissues. It plays a crucial role in neurological diagnosis by:
- Detecting iron accumulation in brain tissues
- Identifying myelin damage patterns
- Assisting in diagnosis of conditions like Multiple Sclerosis, Alzheimer's, and Parkinson's disease

The traditional QSM reconstruction process involves solving an inverse problem that is mathematically ill-posed, typically requiring iterative methods with manual parameter tuning.

## Research Objectives

This study aimed to:
1. Process raw MRI scans and prepare 3D QSM datasets with anisotropy considerations
2. Evaluate deep learning feasibility for QSM reconstruction using 3D approaches
3. Develop clinically relevant 2D datasets for efficient processing
4. Compare 3D and 2D model performance while addressing computational constraints

## Methodology

### Data Processing
- **Dataset**: Multi-orientation gradient echo MRI scans from 8 subjects
- **Preprocessing**: Phase unwrapping, background field removal, brain mask extraction
- **Anisotropy Handling**: Susceptibility tensor imaging (STI) with χ33 component extraction
- **Registration**: Spatial alignment across different head orientations

### Model Architectures
1. **MoDL-QSM (3D)**: Physics-informed model with iterative CNN blocks
2. **SwinUNet2D**: Transformer-based architecture for 2D slice processing

### Training Environment
- Platform: Kaggle distributed GPU environment
- Constraints: 12-hour runtime limitations, memory restrictions
- Strategy: Checkpoint-based training with patch processing

## Key Findings

### MoDL-QSM Performance
- **RMSE**: 68.42 (vs. 67.91 published benchmark)
- **SSIM**: 0.8306 (vs. 0.8446 published benchmark)
- Successfully achieved near-benchmark performance despite resource constraints

### SwinUNet2D Challenges
- Experienced overfitting with limited dataset diversity
- Model complexity exceeded available data characteristics
- Highlighted importance of data-model complexity balance

## Limitations and Lessons Learned

- **Computational Constraints**: Hardware limitations affected training depth
- **Dataset Size**: Limited subject diversity impacted transformer model performance
- **Anisotropy Complexity**: Fine-grained magnetic anisotropy effects proved challenging for long range attention mechanisms
- **Resource Management**: Balancing model sophistication with available computational resources

## Future Directions

1. **GAN Integration**: Post-processing enhancement for artifact reduction
2. **Data Augmentation**: Advanced techniques for clinical scenario diversity
3. **Clinical Integration**: Real-world workflow validation and testing


**Note**: This repository contains research documentation only. Code implementations and datasets are not publicly available.


## Acknowledgments

This research was conducted under the supervision of Dr. Maruf Ahmed at the Department of Electrical and Electronic Engineering, Bangladesh University of Engineering and Technology (BUET). Special thanks to Ms. Ruimin Feng (Shanghai Jiao Tong University) for technical guidance on processing methodologies.

