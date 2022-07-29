# TDA breast density

Breast density can be defined as the amount of white and bright regions seen on a mammogram. Knowing that cancer is more likely to develop in women with dense breast tissue, and that it's harder to detect cancer in breasts with denser tissue ('masking' issue), we want to find a way to accurately and objectively measure breast density, in a way that is independent from human evaluation and mammogram machine maker. 


## A 'breast density clock'
We know that breast density decreases with age and is consistent over time [[1]](#1).
We want to create and algotrithm that predicts the age of a patient from digital mammograms, to then compare the predicted age with the actual age, the rationale being that if the predicted age is lower than the actual age, it would be a sign of higher than average breast density. 


## Data 
We use mammograms from patients who attended the NHS Breast Cancer Screening Program (NHSBSP) at units from two NHS Trusts in England with mammograms collected 2010-19 from the OPTIMAM mammography image database (OMI- DB). Further details on the database are available from Halling-Brown et al. [[3]](#3).

The OMI-DB is a mammography image database comprised of unprocessed and processed full-field digital mammograms. It collects NHS Breast Screening Programme images from multiple breast screening centres across the UK, with the goal of serving as a large repository of medical images for research and training purposes. As part of the data sharing agreement, we obtained a subset of this database composed by data of 18,800 patients, of which (before data cleaning):
- 5500 malignant cases with annotations 
- 600 benign cases with annotations
- 800 malignant cases
- 1000 benign cases
- 900 interval cancer cases
- 10000 normal cases
For most imaging events (for example, a screening is an imaging event) we have processed and unprocessed full-field digital mammograms, and two views of each breast, i.e. medio-lateral oblique (MLO) and cranio-caudal (CC). The database contains images from different manufacturers, particularly Hologic Inc (models Hologic Lorad Selenia and Selenia Dimensions Mammography Systems), and General Electric (GE) Medical Systems (models Senograph DS and Senographe Essential), Siemens and Philips. The images were collected from three sites, and not all manufacturers were only used at each site.

For this project we use normal cases. 
	
## Method 
We encode the geometry in the texture of a mammogram in persistence diagrams. We vectorize persistent diagrams data and classify the features in three age groups (<55y, 55-65y, >65y), in a similar fashion (although different problem) to [[2]](#2)

## Structure
In `Notebooks/selecting_images_and_preprocessing.ipynb` we select images from OMI-DB, and preprocess them (dicom reading, normalisation, resizing TODO: remove background and edge of breast).
In `Notebooks/bd_classification.ipynb` we visualise the feature vectors obtained thorugh [[4]](#4) and classify them with a SVM. 


## References
<a id="1">[1]</a> 
Mokhtary A, Karakatsanis A, Valachis A. Mammographic Density Changes over Time and Breast Cancer Risk: A Systematic Review and Meta-Analysis. Cancers (Basel). 2021;13(19):4805. Published 2021 Sep 25. doi:10.3390/cancers13194805


<a id="2">[2]</a>
Asaad, A., Ali, D., Majeed, T. and Rashid, R., 2022. Persistent Homology for Breast Tumor Classification using Mammogram Scans. arXiv preprint arXiv:2201.02295.


<a id="3">[3]</a>
Halling-Brown MD, Warren LM, Ward D, et al. OPTIMAM Mammography Image Database: A Large-Scale Resource of Mammography Images and Clinical Data. Radiol Artif Intell. 2020;3(1):e200103. Published 2020 Nov 25. doi:10.1148/ryai.2020200103

<a id="4">[4]</a>
D. Ali, A. Asaad (2020). DAAR Topology: A software to build topological features from images. [https://github.com/daartopology/DAAR-Topology](
https://github.com/daartopology/DAAR-Topology)
