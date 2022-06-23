## Independent Component Analysis
ICA can solve a problem with PCA, which is basically what happens if the features are independent?

#### ICA, Geometrically

Bellow is illustrated what a dataset where ICA can excel. As can be seen, the two signas are independent. The PCA solution here will be wrong, as it assumes the variables are somehow distributed along orthogonal directions. ICA does not require that the directions are orthogonal, moreover it admits independent signals This data situation is common for sound signals being mixed, as sound signas often have a lot of structure, but are completely independent.

![[multivar_ICA_geometrically.png]]

#### Mathematical Formulation and Assumptions
Here we find a linear model for the data, under the most general assumptions possible. We have that:

$x = A s$

Every row if x is a linear combination of N distinct signals. We are trying to separate the signals, $s_1, s_2 ..s_N$. We assume that the Matrix A is non-singular (assumption on the sensors). We want to estimate W s.t. W A = I, ie W = $A^{-1}$
in the process recovering $s_1, s_2, ... s_N$ under the following assumptions:

1) Statistical Independence - $P(S_1, S_2) = P(S_1) P(S_2)$
2) No more than one of the source signals can follow a Gaussian distribution
3) A has full rank
4) The order of independent components is arbitrary (as oposed to PCA where we had ordered PCs)

Point 4) follows from ICA algorithms being somewhat ... not quite adhoc but deffinetely not as mathematically hallal as the SVD or PCA. ICA can be solved with objective functions based on the following concepts: [[information theory]], [[Negentropy]], [[Mutual Information]], [[Joint Density]], [[Higher Order Moments]] ([[kurtosis]])

Here are some results of ICA recovring mixed signals compared to PCA:
![[multivar_ICA_results.png]]


#### ICA Practically
PCA is often done before ICA, we rotate the data in the direction of the PCs, scale to unit variance and then perform ICA. Use then PCA loadings as a starting point. ICA can be thought of as an oblique rotation of the PCs. We might keep a certain number of PCs only to denoise.

Validation for ICA is more challenging as there is at least some ambiguity wrt different algorithms. Firstly, the number of PCs (PCA first assumed) to retain is important for the results of the ICA. Also for ICA the previous components change when one estimates the next one, unlike PCA. Like with PCA, structure must be preserved under cross validation for most robust and conservative model validation.

ICA can be used for classification with Hotteling's $T^2$ plots. Example is taking hyperspectral data, and considering the signals acros the spectre as independent for the different classes. Then ICA can be used to separate them from the background and also from each other. Based on the plastic, the different areas of the image will have different spectra, meaning we can recover and estimate those from the image and compare with the known specter imprint of specific plastics.




