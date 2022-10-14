# Awesome MRI QC

A curated list of tools, measures, and references for MRI quality control (QC).

> Quality Control (QC) refers to “a real-time prospective process to ensure imaging quality is maintained by comparing it regularly to a defined set of criteria or industry standards” [@Sreedher2021] via [@Das2022].

Inspired by [awesome-python](https://github.com/vinta/awesome-python) and other [awesome lists](https://github.com/sindresorhus/awesome).

- [Tools](#tools)
  - [QC metric and report generation](#qc-metric-and-report-generation)
  - [MRI analysis packages with built-in QC](#mri-analysis-packages-with-built-in-qc)
  - [QC at scale](#qc-at-scale)
  - [QC web platforms](#qc-web-platforms)
  - [Automated QC with machine learning](#automated-qc-with-machine-learning)
  - [General-purpose image quality estimation](#general-purpose-image-quality-estimation)
- [Measures](#measures)
  - [Structural T1](#structural-t1)
    - [Image quality](#image-quality)
    - [Tissue segmentation](#tissue-segmentation)
    - [Brain extraction](#brain-extraction)
    - [Spatial normalization](#spatial-normalization)
    - [Surface reconstruction](#surface-reconstruction)
    - [Cortical/subcortical segmentation](#corticalsubcortical-segmentation)
  - [Functional BOLD](#functional-bold)
    - [Image quality](#image-quality-1)
    - [Motion correction](#motion-correction)
    - [Co-registration](#co-registration)
    - [Functional connectivity](#functional-connectivity)
  - [Diffusion weighted imaging (DWI)](#diffusion-weighted-imaging-dwi)
    - [Image quality](#image-quality-2)
    - [Diffusion tensor modeling](#diffusion-tensor-modeling)
    - [Tractography](#tractography)
    - [Structural connectivity](#structural-connectivity)
- [References](#references)

## Tools

### QC metric and report generation

- [MRIQC][]: extracts no-reference image quality metrics from structural and functional MRI data.
- [QAP](http://preprocessed-connectomes-project.org/quality-assessment-protocol/): The QAP package allows you to obtain spatial and anatomical data quality measures for your own data. (Precursor to MRIQC.)
- [fBIRN QA tools](https://www.nitrc.org/projects/bxh_xcede_tools): These tools form the basis of the fBIRN QA procedures [@Glover2012].
- [MRQy](https://github.com/ccipd/MRQy): A quality assurance and checking tool for quantitative assessment of MRI data

### MRI analysis packages with built-in QC

- [AFNI][]: A suite of programs for looking at and analyzing MRI brain images at all stages of analysis.
  - [`3dToutcount`](https://afni.nimh.nih.gov/pub/dist/doc/program_help/3dToutcount.html): Calculates number of "outliers" a 3D+time dataset, at each
time point.
  - [`3dTqual`](https://afni.nimh.nih.gov/pub/dist/doc/program_help/3dTqual.html): Computes a "quality index" for each sub-brick in a 3D+time dataset.
- [FSL][]: A comprehensive library of analysis tools for FMRI, MRI and DTI brain imaging data.
  - [EDDY QC tools](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/eddyqc/UsersGuide#The_EDDY_QC_tools) : Generates single-subject and group QC reports for diffusion MRI.
  - [FEAT report](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FEAT/UserGuide): HTML report for single-subject and group fMRI analysis.
  - [`fsl_motion_outliers`][]: command-line tool for analyzing single-subject motion.
- [NiPype][]: Provides a uniform interface to existing neuroimaging software and facilitates interaction between these packages within a single workflow
- [C-PAC][]: A configurable, open-source, Nipype-based, automated processing pipeline for resting state functional MRI data
  - [C-PAC QC](https://fcp-indi.github.io/docs/latest/user/pipelines/quality.html): QC metrics and reports extending [XCP].
- [XCP][]: A free, open-source software package for processing of multimodal neuroimages with extensive QC metrics for T1w and BOLD MRI images.
- [DPABI](http://rfmri.org/dpabi): A toolbox for Data Processing & Analysis for Brain Imaging including GUI-based QC reports

### QC at scale

- [NiRV](https://github.com/ni-report-viewer/nirv): A modern neuroimaging report viewer that aggregates participant level HTML reports for datasets, small and large.
- [NiReports](https://github.com/nipreps/nireports): The NiPreps' Reporting and Visualization system - report templates and "reportlets"
- [SQAN](https://github.com/IUSCA/SQAN): Scalable Quality Assurance for Neuroimaging. A full-stack system for extracting, translating, logging, and visualizing DICOM-formatted medical imaging data.

### QC web platforms

- [MIQA](https://miqa.kitware.com/): Efficient and accurate QC processing by leveraging modern UI/UX and deep learning techniques
- [MindControl](https://github.com/akeshavan/mindcontrol): An app for quality control of neuroimaging pipeline outputs, especially anatomical segmentations
- [Braindr](https://github.com/OpenNeuroLab/braindr): a firebase app for braindr: Tinder for brains

### Automated QC with machine learning

- [Qoala-T](https://github.com/Qoala-T/QC): Qoala-T is a supervised-learning tool for quality control of FreeSurfer segmented MRI data
- [mriqc-learn](https://github.com/nipreps/mriqc-learn): Learning on MRIQC-generated image quality metrics (IQMs)

### General-purpose image quality estimation

- [sewar](https://github.com/andrewekhalel/sewar): All image quality metrics you need in one package.
- [MATLAB IQMs](https://www.mathworks.com/help/images/image-quality-metrics.html): Full and no-reference image quality metrics implemented in MATLAB.
- [awesome-image-quality-assessment](https://github.com/chaofengc/Awesome-Image-Quality-Assessment): Awesome list of image quality tools and references.


[MRIQC]: <https://mriqc.readthedocs.io/>
[AFNI]: <https://afni.nimh.nih.gov/>
[NiPype]: <https://nipype.readthedocs.io/>
[Freesurfer]: <https://surfer.nmr.mgh.harvard.edu/fswiki>
[FSL]: <https://fsl.fmrib.ox.ac.uk/fsl/fslwiki>
[`fsl_motion_outliers`]: <https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FSLMotionOutliers>
[XCP]: <https://xcpengine.readthedocs.io/index.html>
[C-PAC]: <https://fcp-indi.github.io/docs/latest/user/index>
[Mindboggle]: <https://mindboggle.info/>
[ANTs]: <https://github.com/ANTsX/ANTs>

## Measures

### Structural T1

#### Image quality

| Measure | Summary | Interpretation | References |
|---|---|---|---|
| Coefficient of joint variation (CJV) | Larger values indicate head motion and INU artifacts | lower better | [MRIQC], [@Ganzetti2016] |
| Contrast-to-noise ratio (CNR) | Larger values indicate more GM to WM contrast | higher better | [MRIQC], [@Magnotta2006] |
| Signal-to-noise ratio (SNR) | SNR within brain mask | higher better | [MRIQC] |
| Dietrich SNR (SNRd) | SNR relative to air background | higher better | [MRIQC], [@Dietrich2007] |
| Mortamet’s quality index 1 (QI1) | Proportion of "corrupted" voxels vs number of background voxels | lower better | [MRIQC], [@Mortamet2009] |
| Mortamet’s quality index 2 (QI2) | Comparison of background noise with $\Chi^2$ distribution after correcting for QI1 | lower better | [MRIQC], [@Mortamet2009] |
| EFC | Shannon entropy as indicator of ghosting due to head motion | lower better | [MRIQC], [@Atkinson1997] |
| FBER | Ratio of "mean energy" within head vs air | higher better | [MRIQC], [@Shehzad2015] |
| INU | Summary stats for INU bias field. Values close to 1 mean less bias. | higher better | [MRIQC], [@Tustison2010] |
| White matter to maximum ratio (WM2max) | Median WM intensity divided by 95 percentile intensity | values in `[0.6, 0.8]` are good. | [MRIQC] |
| FWHM | Estimation of image smoothness. Higher values mean blurry. | lower better | [MRIQC] |

#### Tissue segmentation

| Measure | Summary | Interpretation | References |
|---|---|---|---|
| ICV | Intracranial volume fraction for each tissue type (WM, GM, CSF) | | [MRIQC] |
| rPVe | Residual partial voluming error for each tissue type | lower better | [MRIQC] |
| Tissue summary stats | Summary stats for signal within tissue masks (mean, stdev, p05, p95) | | [MRIQC] |
| Tissue prior overlap | Overlap of estimated tissue probability maps with template priors | higher better | [MRIQC] |
| Tissue skewness/kurtosis | Skewness and kurtosis of intensity distribution for WM, GM, and background |  | [MRIQC], [@Rosen2018] |
| WM hypointensities | Voxel count of white matter hypointensities | lower better | [Freesurfer], [@Klapwijk2019] |
#### Brain extraction

| Measure | Summary | Interpretation | References |
|---|---|---|---|
| Boundary tissue count | Volume of each tissue type lying on brain mask boundary. Large WM values suggest brain extraction failure. | lower WM values better | [@Alfaro-Almagro2018] |

#### Spatial normalization

| Measure | Summary | Interpretation | References |
|---|---|---|---|
| Normalization cost | Cost function between T1 and template under linear and nonlinear alignment | lower better |  |
| Normalization magnitude | Amount of nonlinear warping | lower better | [@Alfaro-Almagro2018] |
| Normalized overlap | Dice or Jaccard overlap coefficient between resampled T1 and template for brain and tissue masks | higher better | [XCP], [@Alfaro-Almagro2018] |

#### Surface reconstruction

| Measure | Summary | Interpretation | References |
|---|---|---|---|
| Euler number | `2 - 2g` where `g` is the number of topological holes in the surface. Computed by the [Euler–Lhulier formula](https://www.quantamagazine.org/topology-101-how-mathematicians-study-holes-20210126/) (`V - E + F`) | higher better | [@Rosen2018], [@Dale1999], [Freesurfer] |
| Local gyrification index (LGI) | Measures degree of cortical folding in neighborhood of each vertex (spatial map). |  | [Freesurfer](https://surfer.nmr.mgh.harvard.edu/fswiki/LGI) |
| BBR criterion | Measures the magnitude of WM/GM contrast across the WM surface boundary | higher better | [@Greve2009], [Freesurfer] |

#### Cortical/subcortical segmentation

| Measure | Summary | Interpretation | References |
|---|---|---|---|
| Subcortical volume | Volume of each subcortical region in a segmentation (vector). |  | [FIRST](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FIRST), [Freesurfer] |
| Cortical volume | Volume of each cortical region in a parcellation (vector). |  | [@Alfaro-Almagro2018], [ANTs] [Freesurfer], [Mindboggle] |
| Cortical thickness | Mean thickness of each region in a parcellation (vector). |  | [@Rosen2018], [ANTs], [Freesurfer] |

### Functional BOLD

#### Image quality

| Measure | Summary | Interpretation | References |
|---|---|---|---|
| EFC | Shannon entropy as indicator of ghosting due to head motion | lower better | [MRIQC], [@Atkinson1997] |
| FBER | Ratio of "mean energy" within head vs air | higher better | [MRIQC], [@Shehzad2015] |
| FWHM | Estimation of image smoothness. Higher values mean blurry. |  | [MRIQC] |
| SNR | SNR within brain mask. | higher better | [MRIQC]  |
| BOLD summary stats | BOLD intensity summary stats (mean, stdev, p95, p05) |  | [MRIQC] |
| Global correlation (GCor) | Average correlation between every voxel and every other voxel |  | [AFNI], [MRIQC], [@Saad2013] |
| Temporal standard deviation (tSD) | Map of temporal standard deviation | lower better | [MRIQC], [@Marcus2013] |
| Temporal SNR (tSNR) | Map of temporal mean divided by standard deviation | higher better | [MRIQC] |
| Ghost to signal ratio (GSR) | Measures amount of signal in regions prone to ghosting | lower better | [MRIQC] |
| AFNI outlier ratio (AOR) | Mean fraction of "outliers" per fMRI volume using AFNI `3dToutcount` | lower better | [AFNI], [MRIQC] |
| AFNI quality index (AQI) | Mean "quality index", which for each volume is 1 - correlation to median volume | lower better | [AFNI], [MRIQC] |
| Number of dummy scans | Number of non-steady state dummy scans |  | [MRIQC] |
| Carpet plot | BOLD time series for a set of ROIs arranged in a matrix |  | [MRIQC], [@Power2017] |
| Air signal | mean BOLD time series for a set of background/air slices |  | [MRIQC] |

#### Motion correction

| Measure | Summary | Interpretation | References |
|---|---|---|---|
| DVARS | Measures amount of signal change between consecutive time points (time series) | spikes indicate significant motion | [MRIQC], [NiPype], [`fsl_motion_outliers`], [@Power2012] |
| Framewise displacement (FD) | Sum of absolute translation and rotation displacements in mm at each time point (time series) | spikes indicate significant motion | [MRIQC], [NiPype], [@Jenkinson2002], [@Power2012]|

#### Co-registration

#### Functional connectivity

### Diffusion weighted imaging (DWI)

#### Image quality

#### Diffusion tensor modeling

#### Tractography

#### Structural connectivity

## References