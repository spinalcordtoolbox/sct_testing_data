mt data
=======

~~~~
#!/bin/bash
# segmentation
sct_propseg -t t2 -i $SCT_TESTING_DATA_DIR/mt/mt1.nii.gz -init-mask $SCT_TESTING_DATA_DIR/mt/mt1_init.nii.gz
# reg to template
sct_register_multimodal -i $SCT_TESTING_DATA_DIR/t2/label/template/MNI-Poly-AMU_T2.nii.gz -d $SCT_TESTING_DATA_DIR/mt/mt1.nii.gz -x 1 -v 1 -n 1x0 -y 0 -g 0.1,0.5 -s $SCT_TESTING_DATA_DIR/t2/label/template/MNI-Poly-AMU_cord.nii.gz -t $SCT_TESTING_DATA_DIR/mt/mt1_seg.nii.gz
# concatenate transfo
sct_concat_transfo -w $SCT_TESTING_DATA_DIR/t2/warp_template2anat.nii.gz,warp_src2dest.nii.gz -d mt1.nii.gz -o warp_template2mt.nii.gz
# warp template
sct_warp_template -d mt1.nii.gz -w warp_template2mt.nii.gz
~~~~


