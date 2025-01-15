# CV_hubmap_segmenation
Semantic segmenation of kidney tissues to discriminate blood vessels and glomerulus

In this kaggle dataset I made several experiments to achieve the competition goals.
Each notebook differs in the following detials:

1. unet-for-multiclass-training features:
   - mask arrays were in integer datatype
   - 'unsure' class was also included along 'blood_vessel' and 'glomerulus'
   - loss function: Dice loss + CrossEntopyLoss combined

2. hubmap_resnet_plus_unet_hybrid_training features:
   - mask arrays were in integer datatype
   - only 'blood_vessel' and 'glomerulus' classes were used
   - loss function: Dice loss + CrossEntopyLoss combined
   - transfer learning: Resnet34 as encoder, UNet decoder part as decoder

3. hubmap-unet-cyclical-training features:
   - mask arrays are in float
   - only 'blood_vessel' and 'glomerulus' classes were used
   - combined loss (BCE + Dice loss)
   - gradient accumulation (to handle memory issues)
   - Cyclic training approach with LR finder

