## SCD_GT_Tool: A tool for annotating images and identifying associated map images from 3D point cloud in automated and consistent way.
This repository provides a tool for annotating images and identifying associated map images from 3D point cloud in automated and consistent way.
In addition, it gives a tool for annotating images, for generating semantic maps for further research studies.. 


# Tool Functionality:

1. Open single image or full directory

2. Switch to Next/Previous images

3. Zoom-Fitting to detect small objects

4. Create Polygons

5. Edit polygons

6. Save polygons as Json & affected images

7. Optional: Create masks, Visualize affected images



# Usage:


1. For annotation only: 

    1.1 For annotation batch of images, use: labelme ./images

    1.2 For annotation single image, use: labelme images/000000000555.jpg -O 000000000555.json

2. For creating affected images labeling, use: images/000000000555.jpg --pc /SCD_GT_Tool/points3D.txt --imf /SCD_GT_Tool/images.txt

    2.1 For affected images visualization, use: labelme ./images --cl ./Examples/change_list.txt

3. For mask visualization, use: labelme_draw_json 000000000555.json
4. For converting annotations to Dataset, use: labelme_json_to_dataset 000000000555.json -o 000000000555_json_dir
    
    It generates standard files from the JSON file, as follows:
    - img.png: Image file.
    - label.png: uint8 label file.
    - label_viz.png: Visualization of label.png.
    - label_names.txt: Label names for values in label.png.
5. For drawing labled image, use: labelme_draw_label_png 000000000555_json_dir/label.png


# Acknowledgement:

1. This repo is the fork of mpitid/pylabelme, whose development has already stopped.
2. @misc{labelme2016,
   author =       {Kentaro Wada},
   title =        {{labelme: Image Polygonal Annotation with Python}},
   howpublished = {\url{https://github.com/wkentaro/labelme}},
   year =         {2016}
   }
