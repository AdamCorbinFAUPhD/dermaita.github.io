# Strategies for computing Fitzpatrick skin type to evaluate fairness in dermoscopic datasets

## Abstract

### Introduction

Artificial Intelligence (AI) and Machine learning (ML) are playing a significant role in dermatology to help improve detection of malignant skin conditions. Most AI/ML solutions, however, are trained on public datasets that contain limited or no metadata, and might be biased towards lighter skin tones. This work demonstrates how the Fitzpatrick skin type information can be automatically extracted directly from pixel values of skin lesion images without any annotation. 

### Hypothesis

The patient’s Fitzpatrick skin type can be obtained with reasonable accuracy from dermoscopic images of skin lesions even in the absence of masks delimiting the lesion area.
Methods
We used three publicly available skin lesion datasets with pixel-level annotation (segmentation masks) of the lesion areas. It can be assumed that the area not covered by those masks is healthy and can be used to assess skin tone, which might not always be true, due to the presence of artifacts such as stickers and ink marks.

We use unlabeled images and assume that segmentation masks are not available. We convert each image to a suitable color model (La*b*), compute the individual typology angle (ITA) using four different strategies, and convert the ITA value to the Fitzpatrick skin type. The proposed strategies are: (i) Full image; (ii) Center cropped; (iii) Structured patches; and (iv) Random patches (Figure 1).




Figure 1: Examples of the four proposed approaches (images are from the ISIC 2016 dataset): (a) original image; (b) masked image (used as ground truth for computation of performance metrics); (c) center cropped; (d) structured patches; and (e) random patches. Each blue square in parts (c)-(e) is considered a patch of fixed size. 
Results
Table 1 shows experimental results. The Center Cropped and Structured Patches were the top performers across all datasets. They have both performed better than the baseline (full image) or random patches, as desired. 

Table 1: Experimental results using Root Mean Squared Error (RMSE) and Mean Absolute Error (MAE) as error metrics: lower values mean better performance. The Center Cropped strategy performed best for the ISIC 2016 dataset whereas Structured Patches performed best for ISIC 2017. For the ISIC 2018 dataset both Center Copped and Structure Patches performed well, depending on the performance metric used. 

### Conclusion

The proposed strategies for automatically computing skin tone from dermoscopic images of skin lesions in the absence of masks delimiting the lesion area can provide a reliable estimate of the patient’s Fitzpatrick type. Such information can then be used for: (i) augmenting any metadata already available for the dataset; (ii) assessing dataset imbalance relative to skin color; and (iii)  evaluating fairness and bias in datasets and AI/ML models used in dermatology. 

### Keywords
Fairness, Machine Learning, Artificial Intelligence, Dermatology, Image Analysis.


## Poster

### References

## Source code

## Contact info

- Adam Corbin acorbin3@fau.edu  
- Dr. Oge Marques 
