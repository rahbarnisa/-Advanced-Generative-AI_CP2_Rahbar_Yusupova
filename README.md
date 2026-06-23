# -Advanced-Generative-AI_CP2_Rahbar_Yusupova
Designing new cover for the media piece. The goal is to create alternative variation of some iconic media, like a book, cd album, vinyl album or DVD box with movie.
Introduction

The objective of this project was to create alternative media cover designs using a self-hosted generative AI solution. The project required generating redesigned versions of existing media covers while documenting the complete workflow, generation parameters, prompts, and technical environment.

For this project, ComfyUI was deployed locally on a Windows machine and used as the image generation platform. Stable Diffusion v1.5 was selected as the underlying image generation model.

1. Original Media Works

1.1 Book Cover

Original Work: Lord of the Rings
 

1.2 DVD Cover

Original Work: Star Wars

 

1.3 Album / Vinyl Cover

Original Work: Michael Jackson - Thriller

 

2. AI-Generated Variations
2.1 AI-Generated Book Cover
Positive Prompt
alternative fantasy book cover inspired by The Lord of the Rings,
epic medieval fantasy landscape,
ancient mountains,
mystical ring glowing with golden light,
heroic traveler standing on a cliff,
dramatic clouds,
legendary adventure atmosphere,
professional book cover design,
publisher quality artwork,
professional typography space at top,
author name placement area at bottom,
award winning fantasy illustration,
high detail,
cinematic lighting
Negative Prompt
blurry, low quality, watermark, logo, text,
letters,  words, cropped, duplicate characters,
deformed anatomy, bad hands,
oversaturated colors, pixelated, low resolution,
messy composition, cartoon style

Generated Result
 



2.2 AI-Generated DVD Cover
Positive Prompt
alternative DVD cover inspired by Star Wars,
epic space battle,
heroic young space warrior, glowing energy sword,
large futuristic starships, planet in the background,
cinematic movie poster composition, collector edition DVD cover,
professional typography space, movie title area at top,
credits area at bottom,
award winning science fiction artwork, high detail,
dramatic lighting
Negative Prompt
blurry, low quality, watermark,
logo, text, letters,
words, duplicate objects,
deformed anatomy, cropped,
bad composition, oversaturated,
low resolution, messy background

Generated Result
 
2.3 AI-Generated Album/Vinyl Cover
Positive Prompt
alternative vinyl album cover inspired by Michael Jackson Thriller,
1980s luxury aesthetic, dramatic spotlight,
retro music atmosphere, elegant performer silhouette,
premium album artwork, professional vinyl sleeve design,
professional typography space, album title placement area,
artist name placement area, award winning graphic design,
high detail, commercial music packaging

Negative Prompt
blurry, low quality, watermark, logo,
text, letters, words, duplicate figures,
deformed face, bad anatomy,
cropped, pixelated,
messy composition, oversaturated, low resolution

Generated Result

 

3. Workflow
The image generation process was implemented using ComfyUI and the Stable Diffusion v1.5 model. The workflow consisted of the following nodes:
1. Load Checkpoint
2. CLIP Text Encode (Positive Prompt)
3. CLIP Text Encode (Negative Prompt)
4. Empty Latent Image
5. KSampler
6. VAE Decode
7. Save Image

The prompts were encoded using CLIP text encoders and supplied to the diffusion model. The KSampler generated latent representations based on the prompts and configured sampling parameters. The latent output was decoded into an image through the VAE decoder and saved using the Save Image node.

 Workflow Screenshot
 
4. Image Generation Model

 

Model Used: Stable Diffusion v1.5
Checkpoint: v1-5-pruned-emaonly.safetensors

Model Type: Latent Diffusion Model

Model Source: https://huggingface.co/runwayml/stable-diffusion-v1-5

 LoRAs, Adapters, and Extensions: No LoRAs, adapters, ControlNet modules, or additional extensions were used during image generation.

5. Generation Parameters

The following generation parameters were used:
Parameter	Value
Sampler	Euler
Steps	20
CFG Scale	7
Batch Size	1
Seed	Random
Model 	Stable Diffusion v1.5



Book Cover Resolution: 512 × 768

DVD Cover Resolution: 768 × 1024

Album/Vinyl Cover Resolution: 768 × 768

  

6. Resources Used

Software: ComfyUI (Local Installation)
Python Embedded Runtime
Stable Diffusion v1.5

Hardware
Operating System: Windows 11
GPU: NVIDIA GeForce RTX 3050 4GB
CPU: Intel Core i7
RAM: 16 GB
Execution Environment:
Localhost (Self-Hosted)

8. Results and Discussion
The generated covers successfully demonstrated the ability of generative AI models to create alternative interpretations of existing media covers. Stable Diffusion v1.5 produced visually appealing results while maintaining thematic consistency with the selected original media works.
The inclusion of professional typography space in the prompts allowed the generated designs to resemble realistic commercial packaging. The local ComfyUI deployment satisfied the requirement of using a self-hosted image generation solution.

Conclusion
This project demonstrated the use of a self-hosted generative AI workflow for media cover redesign. ComfyUI and Stable Diffusion v1.5 were successfully used to generate alternative book, DVD, and album cover designs. The generated outputs fulfilled the project requirements while providing insight into modern diffusion-based image generation pipelines.
