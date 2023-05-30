# ARMA_Levy_MLP_Classifier
Heavy-tailed ARMA Time Series Classification Using MLP

__The synthetic dataset is modeled after the following assumptions.__
1. _"The Process" follows ARMA(p,q) model:_
    - 1 <= p <= 3;
    - 1 <= q <= 3;
    - AR coefficients are > -1 and < 1;
    - MA coefficients are >= 0 and < 1;
    - the random variables in MA part are taken from a standard Levy distribution with alpha in [0.25, 1, 1.9];
    - 80 time points;
    - for each set __(__ (p,q), AR coefficients, MA coefficients, alpha __)__ we generate several instances of "the Process";
    - we don't care about any other assumptions / limitations.
>
2. _Correlation Functions:_
    - maximum lag is 19;
    - for each instance of "the Process" we compute ACF and PACF.

__CONCLUSION__

__Important :__  All below statements / observations should be read as "... _in the configurations used_".

1. Using ACF and PACF data to feed MLP shows moderate classification ability.
>
2. Using raw Time Series data to feed MLP shows very poor ability to classify.
     - ReLU fails almost totally
>
3. Correlation Functions with MPL Classifier shows __non-uniform__ performance wrt Classes:
     - classes () are captured well;
     - classes () are hard to identify.
>
4. Both ReLU and sigmoid show comparable performance in terms of training time.

__Finally,__ there is evidence to feed MLP Classifier with ACF and PACF data to estimate the orders of ARMA model. There is no reason to build MLP Classifier upon raw Time Series data.
