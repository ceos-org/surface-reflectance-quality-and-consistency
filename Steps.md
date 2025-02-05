# 4 Steps/corrections needed to achieve consistency 

## 4.1 General Steps 

To achieve consistency in satellite-derived surface reflectance measurements, several steps and corrections are needed:

1. **Radiometric calibration**: Ensure the satellite sensors' raw digital numbers (DNs) are accurately converted to physical units of top-of-atmosphere (TOA) radiance or reflectance. This includes development of processing dedicated to relative and absolute calibration (e.g., solar diffuser,  dark frame, flat fielding, linearity, conversion to SI units) with an appropriate assessment of uncertainty. Some missions are using vicarious calibration in order to estimate calibration parameters which are subsequently used as parameters in the radiometric processing.  
2. **Atmospheric correction**: Remove the effects of atmospheric scattering and absorption to estimate bottom-of-atmosphere (BOA) surface reflectance. In this case, we define satellite-derived surface reflectance as measured under natural solar illumination composed of direct and diffuse radiation. Surface reflectance is estimated using a radiative transfer method or empirical line method using TOA radiance or reflectance data \[6, 7\]. Atmospheric correction consists of:  
   1. Aerosol and atmospheric parameter retrieval: Accurately estimate atmospheric properties like aerosol optical thickness (AOT) and water vapor content. Regardless of the source of these parameters (eg. retrieved from auxiliary data (ECMWF) or estimated on a scene basis), it is crucial that these atmospheric properties possess the necessary spatial and temporal characteristics to ensure accurate atmospheric correction.   
   2. Cloud and cloud shadow masking: Implement robust (peer reviewed)  algorithms to detect and mask out clouds and their shadows.  
   3. Haze correction (optional)  
   4. Adjacency correction: Apply correction for adjacency where non-homogeneous surface effects are significant (optional).   
   5. Topographic slope correction: Apply correction for terrain effects, especially in areas with significant relief \[8\].  
3. **Surface Reflectance Validation against reference**: Compare satellite-derived surface reflectance with in-situ measurements or reference data to assess the accuracy. Comparisons should be made over various land covers and atmospheric and sun-sensor-view geometric conditions and care should be taken to ensure that the definition of SR used for the validation is consistent with that used for the satellite product. The accuracy evaluation will determine the need for adjustments. The significance of the differences will require an uncertainty in the in-situ measurements (or reference data) lower than the surface reflectance requirement we intend to validate. From ACIX exercises over land, an uncertainty lower than 5% relative to the reference SR.  
4. **Consistency checks**: Since different radiative transfer models and methods are used, compare results obtained using different atmospheric correction algorithms to ensure consistency. Inter-comparison exercises, that include the uncertainty of both sensors, should be performed throughout the life of a sensor under varying atmospheric conditions, land covers and processing updates. A subset of these intercomparisons should evaluate adjacency, BRDF and terrain effects.   
5. **Traceability to SI units**: Ensure derived surface reflectance values are traceable to the International System of Units for comparability across different sensors and platforms. An initial set of measurements to characterise the instruments characteristics impacting the observation e.g. stray light, linearity etc as well as radiometric gain,  should be made in a laboratory traceable to SI standards prior to launch. Post-launch steps should be made to assess and/or correct the sensor characteristics using on-board facilities if available and/or any associated comparison/vicarious calibration of its Level 1 product using appropriate CEOS recommended methods.  Following this to validate performance and assess consistency/evidence of traceability after launch, a subset of in-situ measurements (described in Step 3\) must be made with SI traceable instrumentation.

## 4.2 Harmonisation Steps 

A harmonised satellite series is one where all the calibrations of the sensors have been done consistently relative to reference datasets which can be traced back to known reference sources, with evidence of associated uncertainty, in an ideal case back to SI. Each sensor is calibrated to the reference in a way that maintains the characteristics of that individual sensor such that the calibrated radiances represent the unique nature of each sensor. This means that two sensors which have been harmonised may see different signals when looking at the same location at the same time, the difference being related to known differences in the responses of each sensor such as differences in the sensor’s spectral response functions etc.(Fiduceo, 2024\). However, after accounting for any differences, the resultant  spectral radiance values will be consistent.   

To generate consistent interoperable data sets from different sensors, in addition to radiometric calibration and atmospheric correction, the following steps are needed.

6. **Geometric correction:** Ensure precise geolocation knowledge and if appropriate re-grid  (e.g., ortho-rectification, however if applied the resultant impact on radiometric uncertainty needs to be reported or assessed) and co-register images from different sensors or acquisition times. Align product pixel grids using similar raster/DEM reference..  
7. **BRDF correction:** Apply bidirectional reflectance distribution function (BRDF) corrections to account for variations in viewing and illumination geometry. A standard reporting geometry (adjusted to nadir view)  for the solar and viewing geometries needs to be defined or the potential variance accounted for and reported in the uncertainties (eg. as per Claverie et al. 2018).

The following additional homogenisation steps assume a reference dataset, and are therefore not considered applicable to the generation of consistent measures across multiple sensors  within this guidance.

## 4.3 Homogenisation Steps 

Unlike harmonisation, homogenisation is where all satellites are forced to look the same such that when looking at the same location simultaneously they would (in theory) give the same signal within uncertainties. In reality the signals from different sensors would be different and homogenisation is adding in corrective terms to each or one satellite to make them look the same and generally requires one sensor to be defined as the reference to which others are corrected to give similar values. It is likely that these corrective terms will not be 100% effective and that the process of homogenisation will add in scene dependent errors to the uncertainty budget which may be difficult to assess (Fiduceo, 2024). 

8. **Spectral band adjustment:** Account for differences in spectral response functions between sensors (if possible) for various landcovers by applying appropriate corrections or band-pass adjustments. The adjustment is often estimated with simulation as it depends on the land cover class. This auxiliary information should be available, and computed, or retrieved from a trusted external source (CLC),  in the harmonisation process.  
9. **Spatial resolution harmonisation:** Account for GSD and spatial resolution differences (e.g. point spread function) if a spatially homogeneous data set is desired. This process may also occur prior to the ortho-rectification process.  
10. **Polarization harmonisation correction (optional):** Account for sensor and scene polarization effects. 

## 4.4 Validation Steps 

11. **Surface Reflectance Harmonisation Validation:** When multiple acquisitions from different sensors are possible over the same site at nearly the same time, comparisons between harmonised surface reflectance products should be made.  Such comparisons should also be made even when non-simultaneous but of course after applying the appropriate corrections associated with atmospheric conditions, view/illumination angles etc.  
    

By applying these steps and corrections, researchers can work towards achieving consistency between surface reflectance measurements from different satellite sensors, enabling more reliable multi-sensor and long-term Earth observation studies.


