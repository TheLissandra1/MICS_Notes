### Author: Zongwei Zhou
##### 1. Dataset: use machine learning models to filter out the most significant medical images; compute consistency loss, histogram distributions among data augmented image pieces; Human-in-the-loop: put the doctors into an annotation loop to mark those specifically-picked, typical images that can symbolize disease/disorder areas in human body.
##### 2. UNet++: a full-dimension net based on UNet structure. Zhou trained a huge model and than use pruning to throw unimportant parameters away to lighten the model size and its capacity in mobile devices.
 DiNTS 2021 (SOTA temporarily) surpasses UNet++ 2018 in multiple dimensions. 
##### 3. Extracting generic knowledge directly from unannotated images
Annotated images are not compulsorily required for deep learning techniques in medical image processing: use transfer learning as a solution.
X (original image) --> deformation to X' --> Encoder + Decoder --> X'', calculate the loss among this to obtain a pretrained model; the deformation process requires medical-based features, including learning organ appearance via non-linear transformation, learning organ texture and local boundaries via local pixel shuffling, learning organ spatial layout and global geometry via outer-cutout and learning local continuities of organs via inner-cutout.

2D images apply ImageNet, but when ImageNet applies in 3D images, its performance decreases because its spatial structure will have a loss to some degree.
3D needs a pretrainded model. E.g. Google deepmind: kinetics-i3d, NifTK: NiftyNet, Tencent: MedicalNet--1638 annotated subjects. 
