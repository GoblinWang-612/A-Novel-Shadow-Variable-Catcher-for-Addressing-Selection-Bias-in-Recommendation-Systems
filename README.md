# SDR
"A Novel Shadow Variable Catcher for Addressing Selection Bias in Recommendation Systems" published at ICDM 2024 .

# Operating Environment
The experiments were run on NVIDIA GeForce RTX 4060, 12th Gen Intel(R) Core(TM) i5-12400F   2.50 GHz.  
Compiler is Python 3.8.18 and required mainly the following packages:  
* Bottleneck == 1.3.7  
* matplotlib == 3.7.4  
* numpy == 1.22.3  
* pandas == 1.4.2  
* pytorch == 1.13.0

# 如何使用
已經將實做在coat資料集上的weights上傳.
Run ```SDR.py --dataset coat --test``` to test model

如果想要自行手動訓練model

**Step 1:** Run ```SVC.py --dataset coat --tune``` for grid search and run ```SVC.py --dataset coat``` to generate shadow variables for dataset.  
**Step 2:** Run ```EstimateShadowDensity.py --dataset coat --tune``` for grid search and run ```EstimateShadowDensity.py --dataset coat``` to train the density estimation model.  
**Step 3:** Adjust the parameters of the dataset in ```Argparser.py```, mainly ```u_shadow_dim, dense_layer_dim, dense_layer_num```.  
**Step 4:** Run ```SDR.py --dataset coat --tune``` to search for hyperparameters, and run ```SDR.py --dataset coat --test``` to test model.

# Acknowledgment
some code references the following work  
* https://github.com/Dingseewhole/Robust_Deconfounder_master  
* https://github.com/BgmLover/iDCF
* https://github.com/AIflowerQ/InvPref_KDD_2022
* https://github.com/KongXinSAMA/ShadowRecommendation
  
Thanks for their contributions!
