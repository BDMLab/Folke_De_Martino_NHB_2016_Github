This is the data and code required to obtain the analysis results presented in Folke et al. (2016) Explicit representation of confidence informs future value-based decisions. Nature Human Behaviour.  DOI:10.1038/s41562-016-0002.
http://www.nature.com/articles/s41562-016-0002
    
The code is written by Tomas Folke.

The code is a mixture of python 2.7 and r 3.2, presented in a Jupyter Notebook (http://jupyter.org/). The easiest way to run the code if you are unfamiliar with Jupyter is to download Anaconda’s build for python (https://www.continuum.io/downloads) and then install and implement rpy2 implement (http://rpy.sourceforge.net/)

If you want to see the code and the output without running it yourself you can do so here: (http://nbviewer.jupyter.org/gist/Sjnjerak/307631db250dbb9014f6a92d503d760d)  

There are some minor differences in the estimates from the hierarchical models in this notebook compared to those presented in the paper. There are two reasons for this:

1) We changed optimising function for lme4, from ‘L-BFGS-B’ to "nlminb”, because the latter showed better convergence properties. If you want to recreate the exact results from the paper just use ‘L-BFGS-B’.
2) Since the publication of the paper we realised that the confidence model was overparameterised, we tried to predict a z-scored confidence from a number of z-scored predictors, which made it impossible for lme4 to fit an intercept. We have since then removed the intercept term and the model estimates are more stable. If you want to replicate the results in the paper simple re-add the intercept term and replace the zAbsDV variable with zAbsDV_sqrt.

Please note that none of these changes influence the conclusions we draw in the paper in any way.

If you have any questions about the code feel free to contact me on tomas.folke@gmail.com.