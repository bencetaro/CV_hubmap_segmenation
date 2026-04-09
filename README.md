# HuBMAP - Hacking the Human Vasculature
*Semantic segmenation of kidney tissues to discriminate blood vessels and glomerulus.*

*Kaggle source: https://www.kaggle.com/competitions/hubmap-hacking-the-human-vasculature*

---

In this kaggle dataset I made several experiments to achieve the competition goals.
Each notebook differs in the following details:


1. Model comparison notebook of UNet, UNeXt, Swin (comparison-notebook.ipynb):
   - Detailed EDA
   - Loss function: Dice loss + CrossEntopyLoss combined
   - Sample weighting, TTA, mixed-sized kernels

2. SSL notebook of UNeXt (ssl-notebook-unext.ipynb):
   - Continued from the previous notebook
   - Semi-Supervised Learning: Making use of the unlabeled dataset, by predicting on them with a pretrained model and further training for better generalization.
   - CutMix augmentation

3. UNet and Resnet pretrained Unet comparison (hubmap_resnet_plus_unet_hybrid_training.ipynb):
   - transfer learning: Resnet34 as encoder, UNet decoder part as decoder
   - the hybrid model was not efficient enough though

4. Cyclical training experiment (hubmap-unet-cyclical-training features.ipynb):
   - Cyclic training approach with LR finder: Repeated trainings with occasional LR search.
   - Gradient accumulation (to handle memory issues)

