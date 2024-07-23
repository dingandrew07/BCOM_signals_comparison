# momentum_signals_creation-comparison

## Description

In this project I create 3 signals that are based on a momentum based timing strategy similar to the one proposed by Meb Faber. Except for a few differences, the details of each signal are listed below. These momentum signals are backtested across the same time frame for the sake of comparison and they are based off of the underlying security of Bloomberg's Commodities Index (BCOM).

### Momentum signals
1)	If (PRICE > 3M avg, 1, 0) #long-only signal
2)	If (PRICE > 3M avg, 1, -1) #long-short signal
3)	(Price – 3M Avg) / (expanding window 3month vol on log strategy returns) #Z-score version of the momentum signal, to add some continuity besides just 1 and -1.

These signals are then compared with existing signals with real historical data. The details of these signals are also listed below as adaptive signals. The underlying securities that these signals are based upon are also commodities.

### Adaptive signals, ETG expected tail gain and ETL is expected tail loss, ETR = ETG/ETL
1)	L_ETR #attractiveness level
2)	L_ETR – min (L_ETR over the last 60 days) #long-only change in attractiveness signal
3)	L_ETR – 3M avg L_ETR #similar setup to signal above
4)	L_ETR / L_ETL #risk-adjusted attractiveness
5)	L_ETR_Z #attractiveness level in the form of a Z score
6)	L_ETL_Z #downside risk in the form of a Z-score, lower means lower downside risk

Several methods of comparison is used to determine the relationship between the new signals and the existing signals. These methods of comparison allow asset managers to determine whether there are new areas of opportunity in the market that can be captured with the integration of these new signals.

### Methods of Comparison
1. Full period correlation matrix
2. Rolling correlation matrix #the windows with the highest and lowest correlation are shown
3. Single and multiple variable regressions between the signals and future returns (t+1). These regressions are displayed as 2D and 3D graphs, and necessary information such as Betas, T-tests and R/R^2 scores.

## Usage

There is one main source code file, coded on python 3 and ran on Jupyter. It is named "momentum_signals_creation-comparison". The data used are included in seperate excel files and was collected from Bloomberg Terminal. 

## Installation instructions

1. Download all the files
2. Ensure these libraries are installed in the environment: pandas, numpy, matplotlib, sklearn, seaborn, prettytable, and statsmodels
3. Run the main source code on Jupyter Lab or Notebook
4. Restart and run all kernels 

## Extensions

1. Sensitivity analysis
2. Integration into automatic portfolio allocation process (automatic way to determine how much should be allocated to which signal)
