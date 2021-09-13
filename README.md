# colmap-sparse-recon
<img src="figure/figure1_sfm.png">

Sturcture-from-Motion using [COLMAP](https://colmap.github.io/index.html)

* input: unordered images
* outputs: the pose estimates for registered images and the reconstructed scene structure as a set of points

## How to use
0. prepare data and build colmap
   + [Download data](https://github.com/YoYo000/MVSNet#download) preprocessed by MVSNet (Yao et al.)
   + Build [colmap](https://github.com/colmap/colmap/tree/3.6) (we use version 3.6)
   + modify the `dataset_path`, `colmap_exe_path` in `colmap_sparse_recon.py` and `colmap_sparse_recon_posed.py`

1. sparse recon using colmap
   + For Tanks and Temples 
     `python colmap_sparse_recon.py`

   + For DTU (images with known camera poses)
     `python colmap_sparse_recon_posed.py`

2. convert sparse points to sparse depth map
   `python colmap_sparse_to_depth.py`

## Visualize
![](https://img2020.cnblogs.com/blog/1511168/202107/1511168-20210719221743917-1046669018.jpg)
<center> Fig 2. predictions result </center>

 <table align="center">
  <tr>
    <td><img src="https://github.com/XYZ-qiyh/colmap-sparse-recon/blob/main/figure/figure3_rgb.jpg" width="400" height="300"></td>
    <td><img src="https://github.com/XYZ-qiyh/colmap-sparse-recon/blob/main/figure/figure4_sparse.png" width="400" height="300"></td>
  </tr>
  <tr>
    <td>RGB image</td>
    <td>sparse depth map</td>
  </tr>
</table>
