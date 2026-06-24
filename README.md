# MR-Linac IVIM: Multi-b-value DWI and PINN-based Parameter Estimation

Code repository for the manuscript: "Optimizing IVIM Measurement on Magnetic Resonance Linear Accelerator Using Multi-b-value Acquisition and Physics-Informed Neural Networks."

## Software Environment

- Python: 3.8.18
- PyTorch: 2.1.1
- NumPy: 1.24.3
- SciPy: 1.10.1
- Scikit-learn: 1.3.2
- Matplotlib: 3.7.4
- Pandas: 2.0.3
- Seaborn: 0.13.1
- Statsmodels: 0.14.1
- SimpleITK: 2.3.1
- NiBabel: 5.1.0
- CUDA version: 12.1
- cuDNN version: 8801

## Repository Structure

├── simulation_datagenerate.ipynb # Generate standard IVIM digital phantom
├── simulation_datagenerate_ADC.ipynb # Generate ADC phantom
├── Segmented analytical.ipynb # Segment fitting for IVIM parameter estimation
├── WLS ADC.ipynb # Weighted least squares (LS) estimation
├── bayesian.ipynb # Bayesian estimation
├── simulation_IVIMnet.ipynb # PINN training and inference
├── simulation_LSQ train.ipynb # LS training (phantom)
├── simulation_LSQ-val.ipynb # LS validation (phantom)
├── simulation_boxplot&RMSE.ipynb # Generate box plots, RMSE tables, and figures
└── README.md


## Execution Order

To reproduce the main results:

1. **`simulation_datagenerate.ipynb`** — Generate the standard biexponential IVIM digital phantom (training and test datasets).
2. **`Segmented analytical.ipynb`** — Run segment fitting on both phantom datasets and output parameter estimates.
2. **`simulation_IVIMnet.ipynb`** — Train the PINN on the standard phantom and evaluate on both standard and IVIM-DKI phantoms.
2. **`simulation_LSQ train.ipynb`** and **`simulation_LSQ-val.ipynb`** — Train and validate the LS model on phantom data.
3. **`bayesian.ipynb`** — Run Bayesian estimation on phantom datasets (based on LS on Train data).
4. **`simulation_boxplot&RMSE.ipynb`** — Generate all box plots and RMSE tables.
  
1. **`simulation_datagenerate_ADC.ipynb`** — Generate the IVIM-DKI digital phantom for model-mismatch testing (K = −0.7).
2. **`WLS ADC.ipynb`** — Run LS estimation on both phantom datasets.


