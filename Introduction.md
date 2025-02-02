# Background 

The CEOS-ARD Surface Reflectance Product Family Specification (PFS)  provides a strong basis for interoperability. The CEOS-ARD Surface Reflectance Product Family Specification includes:

* General metadata requirements ensure traceability, machine readability, and accurate data collection times.  
* Per-pixel metadata addresses flags for no data, saturation, cloud presence, and other critical indicators.  
* Radiometric and atmospheric corrections focus on providing valid surface reflectance measurements and associated uncertainties.

Geometric corrections emphasize achieving sub-pixel accuracy for consistent geolocation across time.   However its non-prescriptive nature tolerates different approaches to the derivation of the ARD Surface Reflectance .

Every dataset producer has their own constraints, priorities and approaches when it comes to defining a Surface Reflectance processing chain, however studies (Claverie et al 2016 ,Main-Knorn et al. 2017 and Saunier et al. 2022\) have shown that using equivalent processing steps and model inputs results in surface reflectance products that are more consistent and able to be used for multi-provider analyses of various indices (Samain et al. 2006). Consistent Surface Reflectance measurements are crucial to optimizing results from multi-provider data integration and analysis.

Inconsistency in surface reflectance quantities and their impact on analyses are well documented (Claverie et al 2016, De Keukelaere et al 2018\)  and have also been expressed anecdotally by industry contacts, who have noted the need to independently reprocess data  to address  incompatibility of surface reflectance datasets for multi-sensor analyses from CEOS Agencies. This is something that CEOS should seek to resolve in service of its stated mission to promote the exchange of data. CEOS Agencies’ own efforts in producing NASA HLS (Claverie et al 2018\) and ESA Sen2Like (Saunier et al 2022\) demonstrate the need to improve the compatibility of measurements across providers to enable homogenisation and fusion.

# 1 Introduction 

## 1.1 Purpose  

This work seeks to describe a surface reflectance (Passive Satellite Viewed Bottom of Atmosphere Surface Reflectance) measurand (quantity), applicable steps, model parameters and their tolerance, required to achieve \-comparability between like bands from different sensors. The intent of this work is not to dictate a common process or toolset for the generation of consistent surface reflectance quantities. 

This paper serves as a reference for organizations considering reprocessing of Earth observation Collections of moderate resolution (1 m \- 100 m) passive optical satellite data collections (300-2500 nm) who are aiming to contribute to a virtual constellation of interoperable surface reflectance measurements.  It can also guide the processing of ARD products for higher-resolution passive optical data sets if they have comparable spectral and radiometric properties of reference moderate-resolution systems. This document emphasizes the reference missions from NASA and ESA, which have GSDs 10 m or coarser. However, a well-designed high-resolution system with the proper specifications (radiometric and spectral) should produce good surface reflectance data. 

Surface reflectance consistency provides for measurement level interoperability of  surface reflectance data products from multiple data providers for similar classes of sensor. If consistency is achieved, surface reflectance data products from multiple sensors, can be used together harmoniously in applications requiring a dense time-series of observations and enable meaningful interpretation of results. This work aims to uplift CEOS-ARD with a core focus on enabling consistent surface reflectance time-series from different sources. The authors recognize that not all applications of surface reflectance require the step indicated in the document, and its aim is to serve a general, rather than specialised use case where the proposed corrections obscure the phenomena under investigation.

## 1.2 Contributors 

| Eric Vermote | NASA | eric.f.vermote@nasa.gov |
| :---- | :---- | :---- |
| Martin Bachmann | DLR | martin.bachmann@dlr.de |
| Peter Strobl | EC | Peter.STROBL@ec.europa.eu |
| Robert (Bob) Ryan | I2R | rryan@i2rcorp.com |
| Mary Pagnutti | I2R | mpagnutti@i2rcorp.com |
| Raquel delos Reyes | DLR | Raquel.delosReyes@dlr.de |
| Simon Oliver | GA | Simon.Oliver@ga.gov.au |
| Medhavy Thankappan | GA | medhavy.thankappan@ga.gov.au |
| Dani Schläpfer | ReSe | daniel@rese.ch |
| Rudolf Richter | DLR | Rudolf.Richter@dlr.de |
| Fuqin Li | GA | Fuqin.Li@ga.gov.au |
| David Jupp | CSIRO | David.Jupp@csiro.au |
| Cody Anderson | USGS | chanderson@usgs.gov |
| Sebastien Saunier | Telespazio | sebastien.saunier@telespazio.com |
| Ake Rosenqvist | JAXA | ake.rosenqvist@soloeo.com |
| Steve Covington | USGS | sjcovington@contractor.usgs.gov |
| Sabrina Pinori | Serco | sabrina.pinori@serco.com |
| Danika Wellington | USGS | dwellington@usgs.gov |
| Matthew Steventon | Symbios | matthew@symbios.space |
| Harvey Jones | Symbios | harvey@symbios.space |
| Nigel Fox | NPL | nigel.fox@npl.co.uk |

*Table 1\. Contributors to this manuscript*

