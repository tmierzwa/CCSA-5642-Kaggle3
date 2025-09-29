# Monet Style Transfer with CycleGAN

This project is part of a Kaggle mini-project where the goal is to transform real photos into **Monet-style paintings** using a **CycleGAN** model.  

- **Competition**: [GAN – Getting Started (Monet Paintings)](https://www.kaggle.com/competitions/gan-getting-started)  
- **Evaluation Metric**: MiFID (Memorization-informed Fréchet Inception Distance)  
- **Deliverables**:  
  1. Jupyter notebook with data exploration, model, results, and discussion  
  2. Public GitHub repository (this one)
  3. Kaggle submission (`images.zip` containing 7k–10k generated Monet-style images, 256×256)  

---

## Dataset
The dataset contains:  
- `monet_tfrec/` – 300 Monet paintings (TFRecords, 256×256)  
- `photo_tfrec/` – 7,028 photos (TFRecords, 256×256)  

Photos are used as input; Monet paintings guide the style transfer.  

---

## Model
- **Architecture**: CycleGAN  
  - Generators: U-Net–style encoder/decoder  
  - Discriminators: PatchGAN classifiers  
- **Losses**:  
  - Adversarial loss  
  - Cycle-consistency loss  
  - Identity loss  
- **Training**: Run for 50–100 epochs for best results (this repo includes shorter runs for demonstration).  

---

## Results
- Generators learn to apply Monet-like brush strokes and pastel color palettes to natural photos.  
- Even after a few epochs, style differences become visible.  
- Longer training → sharper, more consistent Monet-style images.  

---

## Submission
1. Generate Monet-style images for all ~7k photos.  
2. Save them in an `images/` folder as JPEG (256×256).  
3. Zip:  
   ```bash
   zip -r images.zip images/
