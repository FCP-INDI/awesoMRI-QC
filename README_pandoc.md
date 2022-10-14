# Awesome MRI QC

A curated list of tools, measures, and references for MRI quality control (QC).

> Quality Control (QC) refers to “a real-time prospective process to ensure imaging quality is maintained by comparing it regularly to a defined set of criteria or industry standards” [@Sreedher2021] via [@Das2022].

Inspired by [awesome-python](https://github.com/vinta/awesome-python) and other [awesome lists](https://github.com/sindresorhus/awesome).

- [Tools](#tools)
- [Measures](#measures)
  - [Structural T1](#structural-t1)
    - [Image quality](#image-quality)
    - [Spatial normalization](#spatial-normalization)
    - [Surface reconstruction](#surface-reconstruction)
    - [Segmentation](#segmentation)
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

[MRIQC]: <https://mriqc.readthedocs.io/>

#### Spatial normalization

#### Surface reconstruction

#### Segmentation


### Functional BOLD

#### Image quality

#### Motion correction

#### Co-registration

#### Functional connectivity

### Diffusion weighted imaging (DWI)

#### Image quality

#### Diffusion tensor modeling

#### Tractography

#### Structural connectivity

## References