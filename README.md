# TDA breast density

Breast density can be defined as the amount of white and bright regions seen on a mammogram. Knowing that cancer is more likely to develop in women with dense breast tissue, and that it's harder to detect cancer in breasts with denser tissue ('masking' issue), we want to find a way to accurately and objectively measure breast density, in a way that is independent from human evaluation and mammogram machine maker. 

## A 'breast density clock'
we know that breast density decreases with age and is consistent over time.[[1]](#1).
We want to create and algotrithm that predicts the age of a patient from digital mammograms, to then compare the predicted age with the actual age, the rationale being that if the predicted age is lower than the actual age, it would be a sign of higher than average breast density. 

## Method 
We encode the geometry in the texture of a mammogram in persistence diagrams. We vectorize persistent diagrams data and classify the features in three age groups (<55y, 55-65y, >65y).





## References
<a id="1">[1]</a> 
Mokhtary A, Karakatsanis A, Valachis A. Mammographic Density Changes over Time and Breast Cancer Risk: A Systematic Review and Meta-Analysis. Cancers (Basel). 2021;13(19):4805. Published 2021 Sep 25. doi:10.3390/cancers13194805

<a id="2">[2]</a>
Asaad, A., Ali, D., Majeed, T. and Rashid, R., 2022. Persistent Homology for Breast Tumor Classification using Mammogram Scans. arXiv preprint arXiv:2201.02295.
