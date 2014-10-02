template
========

# This is a downsampled version of the MNI-Poly-AMU template.

# downsample template
sct_c3d $SCT_DIR/data/template/MNI-Poly-AMU_T2.nii.gz -resample 50% -o MNI-Poly-AMU_T2.nii.gz
sct_c3d MNI-Poly-AMU_T2.nii.gz -resample 50% -o MNI-Poly-AMU_T2.nii.gz  # the reason we do 2x50% instead of 1x25% is that there are NN interpolation issues.
sct_c3d $SCT_DIR/data/template/landmarks_center.nii.gz -resample 50% -o landmarks_center.nii.gz
sct_c3d landmarks_center.nii.gz -resample 50% -o landmarks_center.nii.gz  # the reason we do 2x50% instead of 1x25% is that there are NN interpolation issues.
sct_c3d $SCT_DIR/data/template/MNI-Poly-AMU_cord.nii.gz -resample 50% -o MNI-Poly-AMU_cord.nii.gz
sct_c3d MNI-Poly-AMU_cord.nii.gz -resample 50% -o MNI-Poly-AMU_cord.nii.gz  # the reason we do 2x50% instead of 1x25% is that there are NN interpolation issues.
# multiply voxel intensity
fslmaths MNI-Poly-AMU_T2.nii.gz -mul 16 MNI-Poly-AMU_T2.nii.gz
fslmaths landmarks_center.nii.gz -mul 16 landmarks_center.nii.gz
fslmaths MNI-Poly-AMU_cord.nii.gz -mul 16 MNI-Poly-AMU_cord.nii.gz
