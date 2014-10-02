mt data
=======

~~~~
#!/bin/bash
# segmentation
sct_propseg -t t2 -i $SCT_TESTING_DATA_DIR/mt/mt1.nii.gz -init 3 -detect-radius 3 -detect-display -detect-gap 4 -detect-n 4
# reg to template
sct_register_multimodal -i $SCT_TESTING_DATA_DIR/t2/t2.nii.gz -l $SCT_TESTING_DATA_DIR/t2/labels.nii.gz -m $SCT_TESTING_DATA_DIR/t2/t2_seg.nii.gz -r 0 -s superfast -o 1 -p $SCT_TESTING_DATA_DIR/template/
~~~~


