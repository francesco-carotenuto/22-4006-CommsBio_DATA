# DATA
Data and scripts for submitted papers

derived from the Habitat Suitability Index maps computed for the past, the present and the future temporal intervals. In order to properly
load the data, at the beginning of each script the user have to set the path to the folder "DATA". This path must include the folder DATA. For example,
if you unzipped the folder "Script_and_data" in the main folder "C:/", the path must be ""C:/Script_and_data/DATA/". Notice that the path must end with "/"


#### About the scripts ####

# The script ARIMA_regression.R #
This script executes some statistics describing the frequency of the suitable climatic conditions to the
species in the past temporal intervals and compare them to the conditions the Ethiopian wolf is experiencing
now. The main part of this script runs the ARIMA regressions described in the material and methods section
of the manuscript to test the relationship between the species' geographic range, the temperature and altitude 
at which the species lived through time. Since this regression include a "time" component, it has to take
into account the issue of the temporal autocorrelation, which depends on the fact that values measured 
at consecutive time bin are more similar than values measured at distant temporal intervals. This issue 
can lead to an imperfect detection of the regression parameters (see metarial and methods for details),
thus masking true relationships.


# The script PerMANOVA_OLS_GLM.R #
This script executes the analyses to test the differences between the considered future
climatic projections provided by the CMIP6 Project and related shared socio-economic pathways (SSPs) in terms 
measured landscape metrics for the habitat of Canis simensis, and the analyses to test the relationships between
Canis simensis Habitat Suitability Index classes (HSI classes) and the landscape metrics and their temporal evolution.
The future scenarios rely on hypotheses about different strategies mitigating or not mitigating at all the current 
global warming trend. It is important to investigate the fate of Canis simensis under these different future climatic
projections and to understand if even under more optimistic scenarios the species will be threatened in the next future.
The first analysis is a complication of the common MANOVA but able to deal with skewed data distributions and is named 
PerMANOVA, since it relies on permutations to produce p values. This analysis is used to test if the different future 
scenarios may lead to the same degree of the species' habitat fragmentation degree by considering some metrics of the 
landscape computed under these future conditions. In the case statistically differences have been detected, then a second
similar test, the Pairwise PerMANOVA, is used to specifically identify the future climate projections yielding results
(i.e. species' faith) different from all the other models.
The second set of analyses focuses on detecting the future temporal trend of the surface area of the different HSI classes
to identify which class will increase its geographic extension through time. This test is performed via Ordinary Least
Square regression (OLS). Then, a set of Generalized Linear Models (GLMs) is performed to test which of the landscape metrics 
is a statistically better descriptor of the HSI classes by taking into account the temporal variation of all these variables.
