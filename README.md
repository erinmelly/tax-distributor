# tax-distributor

This code runs the distributional and growth analysis in Kallen and Mathur (2018). 

# Current status

The model can be run in full. However, it remains under development. We hope to incorporate the following improvements:
 - Industry detail for investment model:
   - The investment response model uses overall corporate and noncorporate investment shares, but it implicitly assumes these are the same within every sector. 
   - A potential improvement make the corporate and noncorporate investment shares specific to each industry.
 - International provisions for MNEs
   - We would like to incorporate the investment location incentives in GILTI, FDII and the DRD more fully into the EATR. 
   - This should also recognize the different incentives from these for location of IP investment and physical investments. 
 - Equity imputation improvements
   - The current version uses deteministic methods. This should be modified to a pseudorandom imputation using pre-generated random numbers.
   - We will improve the specific details of imputation to more fully utilize comparable measures in the PUF and SCF. 

# Model dependencies:
 - Python language, using Anaconda packages
 - `taxcalc`
   - You can install this using `conda install -c ospc taxcalc`
 - IRS public use file for 2011, with modifications using `taxdata`

# How to use the model

tax-distributor is run from the `main_executor.py` file. Once you open this file, the first changes to make are to correct the paths to the relevant ones on your computer.

The main file defines a Calculator for pre-TCJA law (calc_pre) and a Calculator for post-TCJA law (calc_tcja). It later makes alternative versions of these in different programs, but all such versions use current law for the TCJA and use the policy dictionary `param` for pre-TCJA law. If you wish to use alternative policy comparisons, modify these with care.

You also need to specify the change in corporate tax revenue in each year, also in the main file.

You should specify changes to corporate and noncorporate business tax rules. The baseline (pre-TCJA) is in `policy_corp_base.csv` and `policy_noncorp_base.csv`. The reform (TCJA) is in `policy_corp_ref.csv` and `policy_noncorp_ref.csv`. 

Finally, you can modify the main assumptions we use, in `assumptions.py`. 




