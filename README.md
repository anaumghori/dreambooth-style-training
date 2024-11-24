# Dreambooth Custom Style Training
This repository features an implementation of DreamBooth with Stable Diffusion for training custom art styles. Please refer to the following guide and repo to get more familiar with DreamBooth. 
- [DreamBooth Guide](https://huggingface.co/docs/diffusers/en/training/dreambooth)
- [Diffusers](https://github.com/ShivamShrirao/diffusers/tree/main/examples/dreambooth)

# 💻 Setup and the Dataset
I conducted all my work on Google Colab, which offers free access to a GPU and around 15GB of RAM. During training, my setup used approximately 11.4GB of the available 15GB RAM. I trained four different DreamBooth models, experimenting with various hyperparameters and learning rates to achieve the best results. Out of these, two models stood out:

- Manhwa-Style Model: Focused on character faces, this model was trained using 24 high-quality images of women in a manhwa art style.
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



