
# LVVO Dataset: Lecture Video Visual Objects

The **Lecture Video Visual Objects (LVVO)** dataset is a benchmark designed for **object detection in lecture video frames**. It provides high-quality annotations of visual content such as tables, charts, images, and illustrations in real university lecture recordings.

📄 Our Arxiv Paper can be found here: [Lecture Video Visual Objects (LVVO) Dataset:
A Benchmark for Visual Object Detection in Educational Videos](https://doi.org/10.48550/arXiv.2506.13657)  
📥 The dataset can be downloaded here: [LVVO Dataset Download](https://drive.google.com/drive/folders/1RJjj71CAQHnRLqcWIYmJbWj_1zGmw2bO?usp=drive_link)

---

## 📚 Dataset Overview

- **Total Images**: 4,000 unique frames extracted from lecture videos
- **Manually Annotated Subset (LVVO 1k)**: 1,000 frames
- **Automatically Labeled Subset (LVVO 3k)**: 3,000 frames
- **Source**: Lecture recordings from [videopoints.org](https://www.videopoints.org), covering 8 instructors across 13 courses and 3 domains (Biology, Computer Science, Geosciences)  

- **Annotation Tool**: [VoTT by Microsoft](https://github.com/microsoft/VoTT)

Each visual object in the images is labeled with one of the following categories:

| Category ID | Name                 |
|-------------|----------------------|
| 1           | Table                |
| 2           | Chart-Graph          |
| 3           | Photographic-image   |
| 4           | Visual-illustration  |

---

## 🗂️ Sample Dataset (Mini Version)

To help users quickly explore the dataset structure and format, we provide a **sample version** containing 10 annotated images.


## 📦 Full Dataset Download

The complete dataset is hosted on Google Drive and includes three files:

🔗 [**Download Full LVVO Dataset**](https://drive.google.com/drive/folders/1RJjj71CAQHnRLqcWIYmJbWj_1zGmw2bO?usp=drive_link)

| File Name                      | Description                                       |
|-------------------------------|---------------------------------------------------|
| `LVVO 1k withCategories.zip`  | 1,000 manually annotated images with categories   |
| `LVVO 1k.zip`                 | Same images, single-class annotations             |
| `LVVO 3k.zip`                 | 3,000 images with automatic bounding boxes        |

Each version follows this internal structure:

```plaintext
LVVO_x/
├── images/             # Contains all .jpg images
├── labels/             # Contains corresponding annotation files (.json)           
└── dataset_info.json   # Metadata: category names, image ID mappings
```


---

## 📝 Annotation Format

Each file in the `labels/` folder is a JSON annotation corresponding to an image in `images/`.

It contains:

- **`asset`**: Image metadata
  - `name`: Image file name (e.g., `i116_c425_v7624_i_0146.jpg`)
  - `image_id`: Unique integer identifier
  - `size`: Dictionary with image `width` and `height` in pixels

- **`objects`**: A list of annotated visual elements, each containing:
  - `class`: Category ID  
    (`1` = Table, `2` = Chart-Graph, `3` = Photographic-image, `4` = Visual-illustration)
  - `boundingBox`: Bounding box details, including:
    - `xmin`, `ymin`: Top-left corner
    - `xmax`, `ymax`: Bottom-right corner
    - `width`, `height`: Box dimensions in pixels (optional but included)


> **Note**: For the *LVVO_3k Automatically Labeled Subset*, category information is not available.  
> All objects are labeled with `class = 1`, where `1` simply denotes **“object”** as a general category.

## 📣 Citation

If you use this dataset in your research, please cite:

```
@article{biswas2025lvvo,
title={Lecture Video Visual Objects (LVVO) Dataset: A Benchmark for Visual Object Detection in Educational Videos},
author={Dipayan Biswas and Shishir Shah and Jaspal Subhlok},
journal={arXiv preprint arXiv:2406.00123},
year={2025}
}
```

---


## 🔍 Adapted Metadata from External Datasets

This repository includes metadata derived from two external datasets (LDD and LPM), adapted using a consistent filtering pipeline for compatibility with the LVVO dataset.

For details on how these external datasets were processed and which files were retained or excluded, refer to:  
📄 [`meta-files/README.metadata.md`](meta-files/README.metadata.md)



## 📜 License

This repository includes multiple datasets and metadata files, each under a separate license:

- **LVVO Dataset**: licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
- **LDD-derived metadata** (`meta-files/ldd_filename_selected.csv`):
  - Derived from the [Lecture Design Dataset](https://github.com/imurs34/lecture-design-dataset), licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
- **LPM-derived metadata** (`meta-files/lpm_filename_selected.csv`):
  - Derived from the [LPM Dataset](https://github.com/dondongwon/LPMDataset), licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/). 

See [`LICENSE.txt`](LICENSE.txt) for full details.


---

For questions or additional information, please contact the author at [dipayan1109033@gmail.com](mailto:dipayan1109033@gmail.com).
