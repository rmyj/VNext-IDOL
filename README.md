# VNext IDOL

A Google Colab implementation of ![VNext IDOL](https://github.com/wjf5203/VNext/blob/main/projects/IDOL/IDOL.md).

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/rmyj/VNext-IDOL/blob/main/VNext-IDOL.ipynb)

## Links

- https://github.com/rmyj/VNext-IDOL/-/raw/main/rgbd_dataset_freiburg3_walking_xyz_rgb_only.zip
- https://github.com/rmyj/VNext-IDOL/-/raw/main/tokyostones.zip
- https://github.com/rmyj/VNext-IDOL/-/raw/main/cocopretrain_R50.zip
- https://github.com/rmyj/VNext-IDOL/-/raw/main/valid.zip.001

## Code

```python
# to download rgbd_dataset_freiburg3_walking_xyz_rgb_only - designed for Google Colab
%cd /content/
!wget https://github.com/rmyj/VNext-IDOL/-/raw/main/rgbd_dataset_freiburg3_walking_xyz_rgb_only.zip
!unzip /content/rgbd_dataset_freiburg3_walking_xyz_rgb_only.zip
!rm /content/rgbd_dataset_freiburg3_walking_xyz_rgb_only.zip
```

```python
# to download tokyostones.zip - designed for Google Colab
%cd /content/
!wget https://github.com/rmyj/VNext-IDOL/-/raw/main/tokyostones.zip
!unzip /content/tokyostones.zip
!rm /content/tokyostones.zip
```

```python
# to download cocopretrain_R50.pth - designed for Google Colab
%cd /content/
!wget https://github.com/rmyj/VNext-IDOL/-/raw/main/cocopretrain_R50.zip
!unzip /content/cocopretrain_R50.zip
!rm /content/cocopretrain_R50.zip
```

```python
# to download valid.zip - designed for Google Colab
%cd /content/
for i in range(15):
  i = i + 1
  url = f"https://github.com/rmyj/VNext-IDOL/-/raw/main/valid.zip.{i:03}"
  !wget $url # shows error but works 

# concatenate all part files to one zip
!cat /content/valid.zip* > /content/valid.zip
!rm /content/valid.zip.*

# repair combination
!zip -FF /content/valid.zip --out /content/valid-full.zip
!rm /content/valid.zip

# unzip combination
!apt-get install -y unzip
!unzip /content/valid-full.zip
!rm /content/valid-full.zip
```
