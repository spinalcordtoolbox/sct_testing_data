t2 data
=======

~~~~
#!/bin/bash
# reg to template
sct_register_to_template -i $SCT_TESTING_DATA_DIR/t2/t2.nii.gz -l $SCT_TESTING_DATA_DIR/t2/labels.nii.gz -m $SCT_TESTING_DATA_DIR/t2/t2_seg.nii.gz -r 0 -s superfast -o 1 -p $SCT_TESTING_DATA_DIR/template/
# warp template
sct_warp_template -d $SCT_TESTING_DATA_DIR/t2/t2.nii.gz -w $SCT_TESTING_DATA_DIR/t2/warp_template2anat.nii.gz -a 0
~~~~
