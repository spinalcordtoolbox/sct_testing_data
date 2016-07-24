mt data
=======

~~~~
#!/bin/bash
# segmentation
sct_propseg -t t2 -i $SCT_TESTING_DATA_DIR/mt/mt1.nii.gz -init-mask $SCT_TESTING_DATA_DIR/mt/mt1_init.nii.gz
# register anat to mt
sct_register_multimodal -i ../t2/t2.nii.gz -d mt1.nii.gz -iseg ../t2/t2_seg.nii.gz -dseg mt1_seg.nii.gz -param step=1,type=seg,algo=centermass:step=2,type=seg,algo=bsplinesyn,metric=MeanSquares,iter=5
# compute mtr
sct_compute_mtr -mt0 mt0_reg_slicereg_goldstandard.nii.gz -mt1 mt1.nii.gz
# concatenate transfo
sct_concat_transfo -w ../t2/warp_template2anat.nii.gz,warp_t22mt1.nii.gz -d mt1.nii.gz -o warp_template2mt.nii.gz
# warp template
sct_warp_template -d mt1.nii.gz -w warp_template2mt.nii.gz
# segment gray matter
sct_segment_graymatter -i mt1.nii.gz -s mt1_seg.nii.gz -vertfile label/template/PAM50_levels.nii.gz
# binarize segmentation
sct_maths -i mt1_gmseg_manual.nii.gz -thr 0.5 -o mt1_gmseg_goldstandard.nii.gz 
sct_maths -i mt1_gmseg_goldstandard.nii.gz -bin -o mt1_gmseg_goldstandard.nii.gz 
~~~~


