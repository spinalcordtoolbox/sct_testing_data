template
========

This is a downsampled version of the PAM50 template used for rapid testing.

~~~
#!/bin/bash
# declare env
source sct_env
# downsample template
sct_resample -i $SCT_DIR/data/PAM50/template/PAM50_t2.nii.gz -mm 1x1x2 -x spline -o template/PAM50_small_t2.nii.gz 
sct_resample -i $SCT_DIR/data/PAM50/template/PAM50_cord.nii.gz -mm 1x1x2 -x nn -o template/PAM50_small_cord.nii.gz
sct_resample -i $SCT_DIR/data/PAM50/template/PAM50_levels.nii.gz -mm 1x1x2 -x nn -o template/PAM50_small_levels.nii.gz
~~~

OLD CODE:
~~~
sct_resample -i $SCT_DIR/data/PAM50/template/PAM50_label_body.nii.gz -mm 1x1x2 -x nn -o PAM50_label_body.nii.gz 
sct_label_utils -i PAM50_t2.nii.gz -create 35,35,35,19:35,35,50,18:35,35,65,17:35,35,79,16:35,35,93,15:35,35,106,14:35,35,119,13:35,35,132,12:35,35,145,11:35,35,157,10:35,35,168,9:35,35,179,8:35,35,188,7:35,35,197,6:35,35,205,5:35,35,214,4:35,35,223,3:35,35,232,2:35,35,239,1 -o PAM50_label_body.nii.gz
~~~