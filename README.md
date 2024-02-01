# LSUN-Bedroom-Latent-Diffusion-Unet-Model
My personal practice, reproduce LSUN Bedroom Latent Diffusion Unet Model result from fastai course (Part 2, Lesson 25)

# Main Objective  
Reproduce LSUN Bedroom Latent Diffusion Unet Model result from fastai course (Part 2, Lesson 25), by training it from scratch.  

# What to expect  
1. Full general Pipeline Latent Diffusion.  
2. Details abstracted to simplify the pipeline.  
3. Visualized result.  

# Result
For practicing and learning purpose only, the model is trained less (on a smaller part of the dataset, and fewer epochs).  
Therefore, the result is not the same as the original result. However, training longer will result in better result.  

# Prequisite  
1. Know how Deep Learning works.
2. Know how Hook Callback works.
3. Know Pytorch.

# Pipeline
General:  
Train: Dataset -> VAE -> Latents -> Noisify -> UNet -> Noise -> ...  
Sampling: Init noise + timestep -> Unet -> Noise -> subtract from Init noise  

Experiment:  
Train:  Dataset -> Subset -> VAE -> Latents -> Train/Valid -> Noisify -> Unet -> Noise -> ...  
Sampling:  Init noise + timestep -> Unet -> Noise -> subtract from Init noise  
-> Setup section.  

Plus: Activation Stats, KID.  

# Dataset
LSUN Bedroom, auto downloaded, ...  

# Setup
