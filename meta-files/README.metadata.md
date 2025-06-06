# Adapted Metadata from External Datasets

In addition to our LVVO dataset, we also incorporated two external datasets: the **Lecture Design Dataset (LDD)** ([source](https://github.com/imurs34/lecture-design-dataset/tree/main)), designed for layout adaptation in online courses, and the **Lecture Presentations Multimodal (LPM)** dataset ([source](https://github.com/dondongwon/LPMDataset)), developed for training vision-language models to interpret and retrieve slide content. Both datasets include bounding box annotations and were adapted for the object detection task.

To ensure consistency with our preprocessing pipeline, we applied the same filtering criteria across all datasets:
- Removed frames lacking image-like visual elements
- Removed near-duplicates
- Excluded slides with only textual content
- Discarded objects with disjoint text components

A **`selected`** column was added to each metadata file to indicate which frames were retained after filtering.

---

## 1. Lecture Design Dataset (LDD)  
📁 [Source Repository](https://github.com/imurs34/lecture-design-dataset/tree/main)

- **Total frames**: 5,527 (with 12 annotated categories)  
- **Frames retained after filtering**: 4,387  
- **Changes applied**:
  - Excluded textual categories ((including *Equation*))
  - Applied consistent filtering rules provided above
- **Updated metadata file**: `ldd_filename_selected.csv`  
- **Added column**:
  - `selected`: Binary flag (`1` = retained, `0` = excluded)

---

## 2. Lecture Presentations Multimodal (LPM) Dataset  
📁 [Source Repository](https://github.com/dondongwon/LPMDataset)

- **Total slides**: 9,031 (5,959 with bounding boxes)  
- **Frames retained after filtering**: 3,981  
- **Changes applied**:
  - Removed *Equation* category
  - Applied consistent filtering rules provided above
- **Updated metadata file**: `lpm_filename_selected.csv`  
- **Added columns**:
  - `video_id`: Source video ID (from `raw_video_links.csv`)
  - `filename`: Unique image identifier based on `video_id` and `Input.save_dir`  
  - `selected`: Binary flag (`1` = retained, `0` = excluded)
  - `image_height`, `image_width`: Dimensions of the selected image


