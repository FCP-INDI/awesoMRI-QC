# Awesome MRI QC

A curated list of tools, measures, and references for MRI quality
control (QC).

> Quality Control (QC) refers to “a real-time prospective process to
> ensure imaging quality is maintained by comparing it regularly to a
> defined set of criteria or industry standards” ([Sreedher et al.,
> 2021](#ref-Sreedher2021)) via ([Das et al., 2022](#ref-Das2022)).

Inspired by [awesome-python](https://github.com/vinta/awesome-python)
and other [awesome lists](https://github.com/sindresorhus/awesome).

- [Tools](#tools)
  - [QC metric and report generation](#qc-metric-and-report-generation)
  - [MRI analysis packages with built-in
    QC](#mri-analysis-packages-with-built-in-qc)
  - [QC at scale](#qc-at-scale)
  - [QC web platforms](#qc-web-platforms)
  - [Automated QC with machine
    learning](#automated-qc-with-machine-learning)
  - [General-purpose image quality
    estimation](#general-purpose-image-quality-estimation)
- [Measures](#measures)
  - [Structural T1](#structural-t1)
    - [Image quality](#image-quality)
    - [Tissue segmentation](#tissue-segmentation)
    - [Brain extraction](#brain-extraction)
    - [Spatial normalization](#spatial-normalization)
    - [Surface reconstruction](#surface-reconstruction)
    - [Cortical/subcortical
      segmentation](#corticalsubcortical-segmentation)
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

- [MRIQC](https://mriqc.readthedocs.io/): extracts no-reference image
  quality metrics from structural and functional MRI data.
- [QAP](http://preprocessed-connectomes-project.org/quality-assessment-protocol/):
  The QAP package allows you to obtain spatial and anatomical data
  quality measures for your own data. (Precursor to MRIQC.)
- [fBIRN QA tools](https://www.nitrc.org/projects/bxh_xcede_tools):
  These tools form the basis of the fBIRN QA procedures ([Glover et al.,
  2012](#ref-Glover2012)).
- [MRQy](https://github.com/ccipd/MRQy): A quality assurance and
  checking tool for quantitative assessment of MRI data

### MRI analysis packages with built-in QC

- [AFNI](https://afni.nimh.nih.gov/): A suite of programs for looking at
  and analyzing MRI brain images at all stages of analysis.
  - [`3dToutcount`](https://afni.nimh.nih.gov/pub/dist/doc/program_help/3dToutcount.html):
    Calculates number of “outliers” a 3D+time dataset, at each time
    point.
  - [`3dTqual`](https://afni.nimh.nih.gov/pub/dist/doc/program_help/3dTqual.html):
    Computes a “quality index” for each sub-brick in a 3D+time dataset.
- [FSL](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki): A comprehensive library
  of analysis tools for FMRI, MRI and DTI brain imaging data.
  - [EDDY QC
    tools](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/eddyqc/UsersGuide#The_EDDY_QC_tools)
    : Generates single-subject and group QC reports for diffusion MRI.
  - [FEAT
    report](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FEAT/UserGuide): HTML
    report for single-subject and group fMRI analysis.
  - [`fsl_motion_outliers`](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FSLMotionOutliers):
    command-line tool for analyzing single-subject motion.
- [NiPype](https://nipype.readthedocs.io/): Provides a uniform interface
  to existing neuroimaging software and facilitates interaction between
  these packages within a single workflow
- [C-PAC](https://fcp-indi.github.io/docs/latest/user/index): A
  configurable, open-source, Nipype-based, automated processing pipeline
  for resting state functional MRI data
  - [C-PAC
    QC](https://fcp-indi.github.io/docs/latest/user/pipelines/quality.html):
    QC metrics and reports extending
    [XCP](https://xcpengine.readthedocs.io/index.html).
- [XCP](https://xcpengine.readthedocs.io/index.html): A free,
  open-source software package for processing of multimodal neuroimages
  with extensive QC metrics for T1w and BOLD MRI images.
- [DPABI](http://rfmri.org/dpabi): A toolbox for Data Processing &
  Analysis for Brain Imaging including GUI-based QC reports

### QC at scale

- [NiRV](https://github.com/ni-report-viewer/nirv): A modern
  neuroimaging report viewer that aggregates participant level HTML
  reports for datasets, small and large.
- [NiReports](https://github.com/nipreps/nireports): The NiPreps’
  Reporting and Visualization system - report templates and “reportlets”
- [SQAN](https://github.com/IUSCA/SQAN): Scalable Quality Assurance for
  Neuroimaging. A full-stack system for extracting, translating,
  logging, and visualizing DICOM-formatted medical imaging data.

### QC web platforms

- [MIQA](https://miqa.kitware.com/): Efficient and accurate QC
  processing by leveraging modern UI/UX and deep learning techniques
- [MindControl](https://github.com/akeshavan/mindcontrol): An app for
  quality control of neuroimaging pipeline outputs, especially
  anatomical segmentations
- [Braindr](https://github.com/OpenNeuroLab/braindr): a firebase app for
  braindr: Tinder for brains

### Automated QC with machine learning

- [Qoala-T](https://github.com/Qoala-T/QC): Qoala-T is a
  supervised-learning tool for quality control of FreeSurfer segmented
  MRI data
- [mriqc-learn](https://github.com/nipreps/mriqc-learn): Learning on
  MRIQC-generated image quality metrics (IQMs)

### General-purpose image quality estimation

- [sewar](https://github.com/andrewekhalel/sewar): All image quality
  metrics you need in one package.
- [MATLAB
  IQMs](https://www.mathworks.com/help/images/image-quality-metrics.html):
  Full and no-reference image quality metrics implemented in MATLAB.
- [awesome-image-quality-assessment](https://github.com/chaofengc/Awesome-Image-Quality-Assessment):
  Awesome list of image quality tools and references.

## Measures

### Structural T1

#### Image quality

| Measure                                | Summary                                                                            | Interpretation                   | References                                                                               |
|----------------------------------------|------------------------------------------------------------------------------------|----------------------------------|------------------------------------------------------------------------------------------|
| Coefficient of joint variation (CJV)   | Larger values indicate head motion and INU artifacts                               | lower better                     | [MRIQC](https://mriqc.readthedocs.io/), ([Ganzetti et al., 2016](#ref-Ganzetti2016))     |
| Contrast-to-noise ratio (CNR)          | Larger values indicate more GM to WM contrast                                      | higher better                    | [MRIQC](https://mriqc.readthedocs.io/), ([Magnotta & Friedman, 2006](#ref-Magnotta2006)) |
| Signal-to-noise ratio (SNR)            | SNR within brain mask                                                              | higher better                    | [MRIQC](https://mriqc.readthedocs.io/)                                                   |
| Dietrich SNR (SNRd)                    | SNR relative to air background                                                     | higher better                    | [MRIQC](https://mriqc.readthedocs.io/), ([Dietrich et al., 2007](#ref-Dietrich2007))     |
| Mortamet’s quality index 1 (QI1)       | Proportion of “corrupted” voxels vs number of background voxels                    | lower better                     | [MRIQC](https://mriqc.readthedocs.io/), ([Mortamet et al., 2009](#ref-Mortamet2009))     |
| Mortamet’s quality index 2 (QI2)       | Comparison of background noise with $\Chi^2$ distribution after correcting for QI1 | lower better                     | [MRIQC](https://mriqc.readthedocs.io/), ([Mortamet et al., 2009](#ref-Mortamet2009))     |
| EFC                                    | Shannon entropy as indicator of ghosting due to head motion                        | lower better                     | [MRIQC](https://mriqc.readthedocs.io/), ([Atkinson et al., 1997](#ref-Atkinson1997))     |
| FBER                                   | Ratio of “mean energy” within head vs air                                          | higher better                    | [MRIQC](https://mriqc.readthedocs.io/), ([Shehzad et al., 2015](#ref-Shehzad2015))       |
| INU                                    | Summary stats for INU bias field. Values close to 1 mean less bias.                | higher better                    | [MRIQC](https://mriqc.readthedocs.io/), ([Tustison et al., 2010](#ref-Tustison2010))     |
| White matter to maximum ratio (WM2max) | Median WM intensity divided by 95 percentile intensity                             | values in `[0.6, 0.8]` are good. | [MRIQC](https://mriqc.readthedocs.io/)                                                   |
| FWHM                                   | Estimation of image smoothness. Higher values mean blurry.                         | lower better                     | [MRIQC](https://mriqc.readthedocs.io/)                                                   |

#### Tissue segmentation

| Measure                  | Summary                                                                    | Interpretation | References                                                                                            |
|--------------------------|----------------------------------------------------------------------------|----------------|-------------------------------------------------------------------------------------------------------|
| ICV                      | Intracranial volume fraction for each tissue type (WM, GM, CSF)            |                | [MRIQC](https://mriqc.readthedocs.io/)                                                                |
| rPVe                     | Residual partial voluming error for each tissue type                       | lower better   | [MRIQC](https://mriqc.readthedocs.io/)                                                                |
| Tissue summary stats     | Summary stats for signal within tissue masks (mean, stdev, p05, p95)       |                | [MRIQC](https://mriqc.readthedocs.io/)                                                                |
| Tissue prior overlap     | Overlap of estimated tissue probability maps with template priors          | higher better  | [MRIQC](https://mriqc.readthedocs.io/)                                                                |
| Tissue skewness/kurtosis | Skewness and kurtosis of intensity distribution for WM, GM, and background |                | [MRIQC](https://mriqc.readthedocs.io/), ([Rosen et al., 2018](#ref-Rosen2018))                        |
| WM hypointensities       | Voxel count of white matter hypointensities                                | lower better   | [Freesurfer](https://surfer.nmr.mgh.harvard.edu/fswiki), ([Klapwijk et al., 2019](#ref-Klapwijk2019)) |

#### Brain extraction

| Measure               | Summary                                                                                                    | Interpretation         | References                                               |
|-----------------------|------------------------------------------------------------------------------------------------------------|------------------------|----------------------------------------------------------|
| Boundary tissue count | Volume of each tissue type lying on brain mask boundary. Large WM values suggest brain extraction failure. | lower WM values better | ([Alfaro-Almagro et al., 2018](#ref-Alfaro-Almagro2018)) |

#### Spatial normalization

| Measure                 | Summary                                                                                          | Interpretation | References                                                                                                   |
|-------------------------|--------------------------------------------------------------------------------------------------|----------------|--------------------------------------------------------------------------------------------------------------|
| Normalization cost      | Cost function between T1 and template under linear and nonlinear alignment                       | lower better   |                                                                                                              |
| Normalization magnitude | Amount of nonlinear warping                                                                      | lower better   | ([Alfaro-Almagro et al., 2018](#ref-Alfaro-Almagro2018))                                                     |
| Normalized overlap      | Dice or Jaccard overlap coefficient between resampled T1 and template for brain and tissue masks | higher better  | [XCP](https://xcpengine.readthedocs.io/index.html), ([Alfaro-Almagro et al., 2018](#ref-Alfaro-Almagro2018)) |

#### Surface reconstruction

#### Cortical/subcortical segmentation

### Functional BOLD

#### Image quality

| Measure                           | Summary                                                                         | Interpretation                                                                                                   | References                                                                           |
|-----------------------------------|---------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|
| EFC                               | Shannon entropy as indicator of ghosting due to head motion                     | lower better                                                                                                     | [MRIQC](https://mriqc.readthedocs.io/), ([Atkinson et al., 1997](#ref-Atkinson1997)) |
| FBER                              | Ratio of “mean energy” within head vs air                                       | higher better                                                                                                    | [MRIQC](https://mriqc.readthedocs.io/), ([Shehzad et al., 2015](#ref-Shehzad2015))   |
| FWHM                              | Estimation of image smoothness. Higher values mean blurry.                      |                                                                                                                  | [MRIQC](https://mriqc.readthedocs.io/)                                               |
| SNR                               | SNR within brain mask.                                                          | higher better                                                                                                    | [MRIQC](https://mriqc.readthedocs.io/)                                               |
| BOLD summary stats                | BOLD intensity summary stats (mean, stdev, p95, p05)                            |                                                                                                                  | [MRIQC](https://mriqc.readthedocs.io/)                                               |
| Global correlation (GCor)         | Average correlation between every voxel                                         |                                                                                                                  |                                                                                      |
| and every other voxel             |                                                                                 | [AFNI](https://afni.nimh.nih.gov/), [MRIQC](https://mriqc.readthedocs.io/), ([Saad et al., 2013](#ref-Saad2013)) |                                                                                      |
| Temporal standard deviation (tSD) | Map of temporal standard deviation                                              | lower better                                                                                                     | [MRIQC](https://mriqc.readthedocs.io/), ([Marcus et al., 2013](#ref-Marcus2013))     |
| Temporal SNR (tSNR)               | Map of temporal mean divided by standard deviation                              | higher better                                                                                                    | [MRIQC](https://mriqc.readthedocs.io/)                                               |
| Ghost to signal ratio (GSR)       | Measures amount of signal in regions prone to ghosting                          | lower better                                                                                                     | [MRIQC](https://mriqc.readthedocs.io/)                                               |
| AFNI outlier ratio (AOR)          | Mean fraction of “outliers” per fMRI volume using AFNI `3dToutcount`            | lower better                                                                                                     | [AFNI](https://afni.nimh.nih.gov/), [MRIQC](https://mriqc.readthedocs.io/)           |
| AFNI quality index (AQI)          | Mean “quality index”, which for each volume is 1 - correlation to median volume | lower better                                                                                                     | [AFNI](https://afni.nimh.nih.gov/), [MRIQC](https://mriqc.readthedocs.io/)           |
| Number of dummy scans             | Number of non-steady state dummy scans                                          |                                                                                                                  | [MRIQC](https://mriqc.readthedocs.io/)                                               |
| Carpet plot                       | BOLD time series for a set of ROIs arranged in a matrix                         |                                                                                                                  | [MRIQC](https://mriqc.readthedocs.io/), ([Power, 2017](#ref-Power2017))              |
| Air signal                        | mean BOLD time series for a set of background/air slices                        |                                                                                                                  | [MRIQC](https://mriqc.readthedocs.io/)                                               |

#### Motion correction

| Measure                     | Summary                                                                                       | Interpretation                     | References                                                                                                                                                                                                  |
|-----------------------------|-----------------------------------------------------------------------------------------------|------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| DVARS                       | Measures amount of signal change between consecutive time points (time series)                | spikes indicate significant motion | [MRIQC](https://mriqc.readthedocs.io/), [NiPype](https://nipype.readthedocs.io/), [`fsl_motion_outliers`](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FSLMotionOutliers), ([Power et al., 2012](#ref-Power2012)) |
| Framewise displacement (FD) | Sum of absolute translation and rotation displacements in mm at each time point (time series) | spikes indicate significant motion | [MRIQC](https://mriqc.readthedocs.io/), [NiPype](https://nipype.readthedocs.io/), ([Jenkinson et al., 2002](#ref-Jenkinson2002)), ([Power et al., 2012](#ref-Power2012))                                    |

#### Co-registration

#### Functional connectivity

### Diffusion weighted imaging (DWI)

#### Image quality

#### Diffusion tensor modeling

#### Tractography

#### Structural connectivity

## References

<div id="refs" class="references csl-bib-body hanging-indent"
line-spacing="2">

<div id="ref-Alfaro-Almagro2018" class="csl-entry">

Alfaro-Almagro, F., Jenkinson, M., Bangerter, N. K., Andersson, J. L.,
Griffanti, L., Douaud, G., Sotiropoulos, S. N., Jbabdi, S.,
Hernandez-Fernandez, M., Vallee, E., et al. (2018). Image processing and
quality control for the first 10,000 brain imaging datasets from UK
biobank. *Neuroimage*, *166*, 400–424.
<https://doi.org/10.1016/j.neuroimage.2017.10.034>

</div>

<div id="ref-Atkinson1997" class="csl-entry">

Atkinson, D., Hill, D. L., Stoyle, P. N., Summers, P. E., & Keevil, S.
F. (1997). Automatic correction of motion artifacts in magnetic
resonance images using an entropy focus criterion. *IEEE Transactions on
Medical Imaging*, *16*(6), 903–910. <https://doi.org/10.1109/42.650886>

</div>

<div id="ref-Das2022" class="csl-entry">

Das, D., Etzel, J., Esteban, O., MacNicol, E., Ghosh, S., &
Alfaro-Almagro, F. (2022). *ISMRM’22 QC book*.
<https://www.nipreps.org/qc-book/welcome.html>.

</div>

<div id="ref-Dietrich2007" class="csl-entry">

Dietrich, O., Raya, J. G., Reeder, S. B., Reiser, M. F., & Schoenberg,
S. O. (2007). Measurement of signal-to-noise ratios in MR images:
Influence of multichannel coils, parallel imaging, and reconstruction
filters. *Journal of Magnetic Resonance Imaging: An Official Journal of
the International Society for Magnetic Resonance in Medicine*, *26*(2),
375–385. <https://doi.org/10.1002/jmri.20969>

</div>

<div id="ref-Ganzetti2016" class="csl-entry">

Ganzetti, M., Wenderoth, N., & Mantini, D. (2016). Intensity
inhomogeneity correction of structural MR images: A data-driven approach
to define input algorithm parameters. *Frontiers in Neuroinformatics*,
*10*, 10. <https://doi.org/10.3389/fninf.2016.00010>

</div>

<div id="ref-Glover2012" class="csl-entry">

Glover, G. H., Mueller, B. A., Turner, J. A., Van Erp, T. G., Liu, T.
T., Greve, D. N., Voyvodic, J. T., Rasmussen, J., Brown, G. G., Keator,
D. B., et al. (2012). Function biomedical informatics research network
recommendations for prospective multicenter functional MRI studies.
*Journal of Magnetic Resonance Imaging*, *36*(1), 39–54.
<https://doi.org/10.1002/jmri.23572>

</div>

<div id="ref-Jenkinson2002" class="csl-entry">

Jenkinson, M., Bannister, P., Brady, M., & Smith, S. (2002). Improved
optimization for the robust and accurate linear registration and motion
correction of brain images. *Neuroimage*, *17*(2), 825–841.
<https://doi.org/10.1006/nimg.2002.1132>

</div>

<div id="ref-Klapwijk2019" class="csl-entry">

Klapwijk, E. T., Van De Kamp, F., Van Der Meulen, M., Peters, S., &
Wierenga, L. M. (2019). Qoala-t: A supervised-learning tool for quality
control of FreeSurfer segmented MRI data. *Neuroimage*, *189*, 116–129.
<https://doi.org/10.1016/j.neuroimage.2019.01.014>

</div>

<div id="ref-Magnotta2006" class="csl-entry">

Magnotta, V. A., & Friedman, L. (2006). Measurement of signal-to-noise
and contrast-to-noise in the fBIRN multicenter imaging study. *Journal
of Digital Imaging*, *19*(2), 140–147.
<https://doi.org/10.1007/s10278-006-0264-x>

</div>

<div id="ref-Marcus2013" class="csl-entry">

Marcus, D. S., Harms, M. P., Snyder, A. Z., Jenkinson, M., Wilson, J.
A., Glasser, M. F., Barch, D. M., Archie, K. A., Burgess, G. C.,
Ramaratnam, M., et al. (2013). Human connectome project informatics:
Quality control, database services, and data visualization.
*Neuroimage*, *80*, 202–219.
<https://doi.org/10.1016/j.neuroimage.2013.05.077>

</div>

<div id="ref-Mortamet2009" class="csl-entry">

Mortamet, B., Bernstein, M. A., Jack Jr, C. R., Gunter, J. L., Ward, C.,
Britson, P. J., Meuli, R., Thiran, J.-P., & Krueger, G. (2009).
Automatic quality assessment in structural brain magnetic resonance
imaging. *Magnetic Resonance in Medicine: An Official Journal of the
International Society for Magnetic Resonance in Medicine*, *62*(2),
365–372. <https://doi.org/10.1002/mrm.21992>

</div>

<div id="ref-Power2017" class="csl-entry">

Power, J. D. (2017). A simple but useful way to assess fMRI scan
qualities. *Neuroimage*, *154*, 150–158.
<https://doi.org/10.1016/j.neuroimage.2016.08.009>

</div>

<div id="ref-Power2012" class="csl-entry">

Power, J. D., Barnes, K. A., Snyder, A. Z., Schlaggar, B. L., &
Petersen, S. E. (2012). Spurious but systematic correlations in
functional connectivity MRI networks arise from subject motion.
*Neuroimage*, *59*(3), 2142–2154.
<https://doi.org/10.1016/j.neuroimage.2011.10.018>

</div>

<div id="ref-Rosen2018" class="csl-entry">

Rosen, A. F., Roalf, D. R., Ruparel, K., Blake, J., Seelaus, K., Villa,
L. P., Ciric, R., Cook, P. A., Davatzikos, C., Elliott, M. A., et al.
(2018). Quantitative assessment of structural image quality.
*Neuroimage*, *169*, 407–418.
<https://doi.org/10.1016/j.neuroimage.2017.12.059>

</div>

<div id="ref-Saad2013" class="csl-entry">

Saad, Z. S., Reynolds, R. C., Jo, H. J., Gotts, S. J., Chen, G., Martin,
A., & Cox, R. W. (2013). Correcting brain-wide correlation differences
in resting-state FMRI. *Brain Connectivity*, *3*(4), 339–352.
<https://doi.org/10.1089/brain.2013.0156>

</div>

<div id="ref-Shehzad2015" class="csl-entry">

Shehzad, Z., Giavasis, S., Li, Q., Benhajali, Y., Yan, C., Yang, Z.,
Milham, M., Bellec, P., & Craddock, C. (2015). The preprocessed
connectomes project quality assessment protocol-a resource for measuring
the quality of MRI data. *Frontiers in Neuroscience*, *47*.
<https://doi.org/10.3389/conf.fnins.2015.91.00047>

</div>

<div id="ref-Sreedher2021" class="csl-entry">

Sreedher, G., Ho, M.-L., Smith, M., Udayasankar, U. K., Risacher, S.,
Rapalino, O., Greer, M.-L. C., Doria, A. S., & Gee, M. S. (2021).
Magnetic resonance imaging quality control, quality assurance and
quality improvement. *Pediatric Radiology*, *51*(5), 698–708.
<https://doi.org/10.1007/s00247-021-05043-6>

</div>

<div id="ref-Tustison2010" class="csl-entry">

Tustison, N. J., Avants, B. B., Cook, P. A., Zheng, Y., Egan, A.,
Yushkevich, P. A., & Gee, J. C. (2010). N4ITK: Improved N3 bias
correction. *IEEE Transactions on Medical Imaging*, *29*(6), 1310–1320.
<https://doi.org/10.1109/TMI.2010.2046908>

</div>

</div>
