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

<div id="refs" class="references csl-bib-body hanging-indent"
line-spacing="2">

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

<div id="ref-Magnotta2006" class="csl-entry">

Magnotta, V. A., & Friedman, L. (2006). Measurement of signal-to-noise
and contrast-to-noise in the fBIRN multicenter imaging study. *Journal
of Digital Imaging*, *19*(2), 140–147.
<https://doi.org/10.1007/s10278-006-0264-x>

</div>

<div id="ref-Mortamet2009" class="csl-entry">

Mortamet, B., Bernstein, M. A., Jack Jr, C. R., Gunter, J. L., Ward, C.,
Britson, P. J., Meuli, R., Thiran, J.-P., & Krueger, G. (2009).
Automatic quality assessment in structural brain magnetic resonance
imaging. *Magnetic Resonance in Medicine: An Official Journal of the
International Society for Magnetic Resonance in Medicine*, *62*(2),
365–372. <https://doi.org/10.1002/mrm.21992>

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
