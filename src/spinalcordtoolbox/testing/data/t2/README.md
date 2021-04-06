t2 data
=======

~~~~
#!/bin/bash
# reg to template
sct_register_to_template -i t2.nii.gz -s t2_seg.nii.gz -l labels.nii.gz -t ../PAM50_small/ -param step=1,type=seg,algo=centermassrot,smooth=1:step=2,type=im,algo=syn,iter=3
# warp template
sct_warp_template -d t2.nii.gz -w warp_template2anat.nii.gz -a 0
~~~~
