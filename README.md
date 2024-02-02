# LSUN-Bedroom-Latent-Diffusion-Unet-Model
My personal practice, reproduce LSUN Bedroom Latent Diffusion Unet Model result from fastai course (Part 2, Lesson 25)

# Main Objective  
Reproduce LSUN Bedroom Latent Diffusion Unet Model result from fastai course (Part 2, Lesson 25), by training it from scratch.  

# What to expect  
1. Full general Pipeline Latent Diffusion.  
2. Details abstracted to simplify the pipeline.  
3. Visualized result (in notebooks).  

# Result
For practicing and learning purpose only, the model is trained less (on a smaller part of the dataset, and fewer epochs).  
Therefore, the result is not the same as the original result. However, training longer will result in better result.  

# Prequisite  
1. Know how Deep Learning works.  
2. Know how Hook Callback works.  
3. Know Pytorch.  
4. Know Fastai.  

# Pipeline (General)
## Train  
Dataset -> VAE -> Latents -> Noisify -> DataLoader -> Unet -> Noise.  

In training process, we will Noisify the Latents. 
Then input noisified Latents + Timestep to the Unet.  
Then we train the Unet to predict the ***original noise***, which is added to Latents in Noisify step.  

## Sampling  
Init noise + reversed Timestep -> Unet -> Noise -> subtract from Init noise.  

In sampling process, we input Init noise + reversed Timestep into the Unet.  
Then, the Unet will predict noise.  
After that, we will subtract predicted noise gradually from the Init noise.   

# Dataset  
LSUN Bedroom, auto downloaded in notebooks. (from [Dataset link](https://s3.amazonaws.com/fast-ai-imageclas/bedroom.tgz))

# Setup  
## Train  
Dataset -> Subset -> Transform -> VAE -> Latents -> Noisify -> Train/Valid set -> DataLoader -> Unet -> Noise.   

## Sampling  
Init noise + reversed Timestep -> Unet -> Noise -> subtract from Init noise.  

# Bonus Evaluation  
- Activation Stats  
- KID (Kernel Inception Distance)

# Files
1. Original files from Fastai Course Part 2 (from [Course link](https://course.fast.ai/)):   
- 30_lsun_diffusion-latents.ipynb (~300k images, 25 epochs, Miniai Unet, Miniai Noisify)
2. Reproduction files:
- image_generator_nonorm_miniai_100k_20e.ipynb (100k images, 20 epochs, Miniai Unet, Miniai Noisify)
- image_generator_nonorm_miniai_10k_60e.ipynb (10k images, 60 epochs, Miniai Unet, Diffusers Noisify)
- image_generator_nonorm_miniai_10k_60e_Ver2.ipynb (10k images. 60 epochs, Diffusers Unet, Diffuser Noisify)
