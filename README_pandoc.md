# Awesome MRI QC

A curated list of tools, measures, and references for MRI quality control (QC).

> Quality Control (QC) refers to “a real-time prospective process to ensure imaging quality is maintained by comparing it regularly to a defined set of criteria or industry standards” [@Sreedher2021] via [@Das2022].

Inspired by [awesome-python](https://github.com/vinta/awesome-python) and other [awesome lists](https://github.com/sindresorhus/awesome).

- [Tools](#tools)
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

- [MRIQC]: extracts no-reference image quality metrics from structural and functional MRI data.

[MRIQC]: <https://mriqc.readthedocs.io/>
[AFNI]: <https://afni.nimh.nih.gov/>
[NiPype]: <https://nipype.readthedocs.io/>
[Freesurfer]: <https://surfer.nmr.mgh.harvard.edu/fswiki>
[`fsl_motion_outliers`]: <https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FSLMotionOutliers>
[XCP]: <https://xcpengine.readthedocs.io/index.html>

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

#### Cortical/subcortical segmentation


### Functional BOLD

#### Image quality

| Measure | Summary | Interpretation | References |
|---|---|---|---|
| EFC | Shannon entropy as indicator of ghosting due to head motion | lower better | [MRIQC], [@Atkinson1997] |
| FBER | Ratio of "mean energy" within head vs air | higher better | [MRIQC], [@Shehzad2015] |
| FWHM | Estimation of image smoothness. Higher values mean blurry. |  | [MRIQC] |
| SNR | SNR within brain mask. | higher better | [MRIQC]  |
| BOLD summary stats | BOLD intensity summary stats (mean, stdev, p95, p05) |  | [MRIQC] |
| Global correlation (GCor) | Energy of average of all voxels' normalized time series |  | [AFNI], [MRIQC], [@Saad2013] |
| Temporal standard deviation (tSD) | Map of temporal standard deviation | lower better | [MRIQC], [@Marcus2013] |
| Temporal SNR (tSNR) | Map of temporal mean divided by standard deviation | higher better | [MRIQC] |
| Ghost to signal ratio (GSR) | Measures amount of signal in regions prone to ghosting | lower better | [MRIQC] |
| AFNI outlier ratio (AOR) | Mean fraction of "outliers" per fMRI volume using AFNI `3dToutcount` | lower better | [AFNI], [MRIQC] |
| AFNI quality index (aqi) | Mean "quality index", which for each volume is 1 - correlation to median volume | lower better | [AFNI], [MRIQC] |
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