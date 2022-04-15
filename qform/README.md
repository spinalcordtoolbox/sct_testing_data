qform testing images
====================

* `bad_quaternion.nii.gz`: a made-up image file with a slightly bad qform, used to check that `sct_crop_image` is sufficiently lenient when reading its input (the total norm of `quatern_b` and `quatern_c` and `quatern_d` is a bit more than 1).
  ```python3
  >>> import nibabel as nib
  >>> im = nib.load('bad_quaternion.nii.gz')
  >>> print(im.header)
  <class 'nibabel.nifti1.Nifti1Header'> object, endian='<'
  sizeof_hdr      : 348
  data_type       : b''
  db_name         : b''
  extents         : 16384
  session_error   : 0
  regular         : b'r'
  dim_info        : 57
  dim             : [4 2 3 4 5 1 1 1]
  intent_p1       : 0.0
  intent_p2       : 0.0
  intent_p3       : 0.0
  intent_code     : none
  datatype        : int16
  bitpix          : 16
  slice_start     : 0
  pixdim          : [1.   0.75 0.75 3.   1.5  0.   0.   0.  ]
  vox_offset      : 0.0
  scl_slope       : nan
  scl_inter       : nan
  slice_end       : 0
  slice_code      : sequential increasing
  xyzt_units      : 10
  cal_max         : 0.0
  cal_min         : 0.0
  slice_duration  : 0.0
  toffset         : 0.0
  glmax           : 120
  glmin           : 1
  descrip         : b''
  aux_file        : b''
  qform_code      : scanner
  sform_code      : scanner
  quatern_b       : 1.0
  quatern_c       : 0.0
  quatern_d       : 0.0009765625
  qoffset_x       : 10.0
  qoffset_y       : 20.0
  qoffset_z       : 30.0
  srow_x          : [ 0.75  0.    0.   10.  ]
  srow_y          : [ 0.   -0.75  0.   20.  ]
  srow_z          : [ 0.  0. -3. 30.]
  intent_name     : b''
  magic           : b'n+1'
  ```
