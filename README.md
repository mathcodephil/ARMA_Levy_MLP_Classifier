# ARMA_Levy_MLP_Classifier
Heavy-tailed ARMA Time Series Classification Using MLP

__The synthetic dataset is modeled after the following assumptions.__
1. _"The Process" follows ARMA(p,q) model:_
    - 1 <= p <= 3;
    - 1 <= q <= 3;
    - AR coefficients are > -1 and < 1;
    - MA coefficients are >= 0 and < 1;
    - the random variables in MA part are taken from a standard Levy distribution with alpha in [0.25, 1];
    - 80 time points;
    - for each set __(__ (p,q), AR coefficients, MA coefficients, alpha __)__ we generate one instance of "the Process";
    - we don't care about any other assumptions / limitations.
>
2. _Correlation Functions:_
    - maximum lag is 19;
    - for each instance of "the Process" we compute ACF and PACF.

__CONCLUSION__

_In the configurations used_

   - there is evidence to use MLP Classifier with ACF and PACF data to produce only _tentative_ estimates of the orders of ARMA model;
   - there is no reason to build MLP Classifier upon raw Time Series data even for this kind of estimates.
