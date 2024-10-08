# 🖼️ Pose Estimation: SAM2 vs YOLOv8 📸

This project compares the results of pose estimation using **Segment Anything Model (SAM2)** and **YOLOv8**. The goal is to demonstrate the differences between segmentation using bounding box prompts with SAM2 and object detection with YOLOv8, providing visual comparisons of segmented masks, bounding boxes, and their respective centers.

## 🚀 Features

- **Segmentation with SAM2**: Use bounding box prompts to generate segmented masks for objects in the image.
- **Object Detection with YOLOv8**: Detect objects and calculate the centers of their bounding boxes.
- **Visualization**: Plot the segmented masks, bounding boxes, and centers on the input image to visually compare SAM2 and YOLOv8 results.

## 🛠️ How It Works

1. **Segmentation with SAM2**: Given a list of bounding boxes, SAM2 generates segmented masks for objects in the image.
2. **Object Detection with YOLOv8**: YOLOv8 detects objects and calculates the centers of their bounding boxes.
3. **Plot Comparison**: The segmented masks, YOLO bounding boxes, and their respective centers are plotted together for side-by-side comparison.

## 📦 Installation

1. Clone this repository:
    ```bash
    git clone https://github.com/Shubhankar2003/SAM2.git
    ```

2. Install the required dependencies:
    ```bash
    pip install ultralytics matplotlib numpy
    ```

## 🖼️ Example Usage

To run the script, provide the image path and bounding boxes:

```bash
python main.py
```

The `segment_with_bboxes` function performs segmentation using SAM2, and the `calculate_centers_with_yolo` function calculates the centers of the detected objects using YOLOv8.

## Sample Image
You can replace the path in the script with any image you want to test. In this example, the following image is used: `assets/person.jpg`.

### Visualization Output

The segmented masks and bounding boxes are visualized on top of the input image with color-coded markers:

- **SAM Segmentation**: Red X marks the center of segmented masks.
- **YOLO Bounding Boxes**: Green rectangles with blue circles marking the centers.

---

## 🧠 Key Functions

### `segment_with_bboxes(image_path, bbox_list)`

- Segments the image using the SAM2 model with bounding box prompts.
- **Parameters**:
    - `image_path` (str): Path to the input image.
    - `bbox_list` (list): List of bounding boxes in the format `[x_min, y_min, x_max, y_max]`.
- **Returns**: List of segmented masks.

### `calculate_centers_with_yolo(image_path)`

- Detects objects using YOLOv8 and calculates their centers.
- **Parameters**:
    - `image_path` (str): Path to the input image.
- **Returns**: List of centers and bounding boxes in the format `[[center_x, center_y, [x_min, y_min, x_max, y_max]]]`.

### `plot_segmented_masks_and_yolo_results(segmented_masks, yolo_results, image_path)`

- Plots the segmented masks, YOLO bounding boxes, and centers on the image.
- **Parameters**:
    - `segmented_masks` (list): List of SAM-segmented masks (arrays of `[x, y]` coordinates).
    - `yolo_results` (list): List of YOLO results containing centers and bounding boxes.
    - `image_path` (str): Path to the input image for visualization.

---

## 📊 Example Output

After running the script, the results will look something like this:

- **Red X**: Represents the center of each SAM-segmented mask.
- **Green Rectangle**: Represents YOLO's detected bounding box.
- **Blue Circle**: Represents the center of YOLO-detected objects.

---

## 📝 License

This project is licensed under the MIT License. See the `LICENSE.md` file for more details.
