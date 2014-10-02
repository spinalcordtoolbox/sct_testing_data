mt data
=======

~~~~
#!/bin/bash
# segmentation
sct_propseg -t t2 -i $SCT_TESTING_DATA_DIR/mt/mt1.nii.gz -init-mask $SCT_TESTING_DATA_DIR/mt/mt1_init.nii.gz
# reg to template
sct_register_multimodal -i /Users/julien/data/sct_testing_data/data/t2/template2anat.nii.gz -d $SCT_TESTING_DATA_DIR/mt/mt1.nii.gz -x 1 -v 1 -n 1x0 -y 0 -g 0.1,0.5 -s $SCT_TESTING_DATA_DIR/t2/../t2/label/template/MNI-Poly-AMU_cord.nii.gz -t mt1_seg.nii.gz
~~~~


