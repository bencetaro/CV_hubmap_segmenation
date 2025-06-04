# CV_hubmap_segmenation
Semantic segmenation of kidney tissues to discriminate blood vessels and glomerulus

In this kaggle dataset I made several experiments to achieve the competition goals.
Each notebook differs in the following detials:


1. Model comparison notebook of UNet, UNeXt, Swin (comparison-notebook):
   - Detailed EDA
   - Loss function: Dice loss + CrossEntopyLoss combined
   - Sample weighting, TTA, mixed-sized kernels

2. SSL notebook of UNeXt (ssl-notebook-unext):
   - Continued from the previous notebook
   - Semi-Supervised Learning: Making use of the unlabeled dataset, by predicting on them with a pretrained model and further training for better generalization.
   - CutMix augmentation

3. UNet and Resnet pretrained Unet comparison (hubmap_resnet_plus_unet_hybrid_training):
   - transfer learning: Resnet34 as encoder, UNet decoder part as decoder
   - the hybrid model was not efficient enough though

4. Cyclical training experiment (hubmap-unet-cyclical-training features):
   - Cyclic training approach with LR finder: Repeated trainings with occasional LR search.
   - Gradient accumulation (to handle memory issues)

