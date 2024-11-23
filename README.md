# Dreambooth Custom Style Training
This repository features an implementation of DreamBooth with Stable Diffusion for training custom art styles. Please start by exploring the official documentation and paper to get familiar with DreamBooth.

- [DreamBooth Paper](https://huggingface.co/papers/2208.12242)
- [DreamBooth Guide](https://huggingface.co/docs/diffusers/en/training/dreambooth)
### Repos that I recommend
- [Diffusers](https://github.com/ShivamShrirao/diffusers/tree/main/examples/dreambooth)
- [sd-dreambooth-extension](https://github.com/d8ahazard/sd_dreambooth_extension)


# 💻 Setup and the Dataset
I ran everything on Google Colab, which is awesome because they give you free access to a Tesla T4 GPU and about 15GB of RAM. For reference, my training utilized about 11.4GB of RAM out of the 15GB available. I trained four different DreamBooth models, tweaking hyperparameters and learning rates to experiment with results. Out of them, two models stood out:
- Manhwa-Style Model: Trained on 24 high-quality women manhwa images, focused on character faces.
- Custom Fox Character Model: Trained with 15 hand-drawn images of a stylized fox character. 
## For Datasets
`- High-Volume (100–200 Images):` Requires more training steps and time but offers greater versatility in generating a variety of poses, expressions, and details, especially for specific character styles.

`- Low-Volume (25–30 Images):` Faster to train (6,000–8,000 steps) and produces good results but may limit variety, such as in poses or expressions.

To get the best results, avoid using blurry or low-resolution images and make sure to remove watermarks, text, or graininess, as these can mess up the model’s training. Crop them to the same size to maintain uniformity. If you’re training to copy a specific art style, make sure the style is consistent across all images. Mixing styles or having varied lighting on the subject increases the chances of incorrect outputs. 
> If your dataset includes art directly taken from an artist, always seek their permission to avoid getting into future troubles. Alternatively, you can generate datasets using AI tools like DALL-E or Stable Diffusion, use images of well-known anime/cartoon/comic characters, or create custom designs yourself.


# Training Parameters
Following are the main hyperparameters to focus on for training. The table shows the best values for each hyperparameter that worked for me without running into Colab’s out-of-memory errors. However, it's important to note that these values may not be optimal for every use case. The effectiveness of these parameters depends heavily on the type of dataset and model you're using.
| **Parameter**                  | **Value**       |  
|---------------------------------|-----------------|  
| **Resolution**                 | `512`           |  
| **Learning Rate**              | `3e-7`          |  
| **Learning Rate Scheduler**    | `constant`      |  
| **Validation Steps**           | `100`           |  
| **Batch Size**                 | `2`             |  
| **Gradient Accumulation Steps**| `4`             |  

# Results


https://github.com/user-attachments/assets/d44b0497-8cea-4659-8260-f3844e5fd62f



