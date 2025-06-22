
# 🎯 Dartboard Hit Detection and Scoring using OpenCV & cvzone

**Author**: Padmasahithi Kondeti

This project uses computer vision techniques to detect darts hitting a dartboard from a video input, identify the hit location, and compute the score dynamically. The solution uses color segmentation, perspective warping, contour detection, and region-of-interest scoring with pre-defined polygon zones.

---

## 📌 Features

- Real-time dart detection from color-marked darts
- Accurate scoring using pre-drawn polygonal zones
- Live display of total score
- Color segmentation using HSV filters
- Mask post-processing with OpenCV morphology operations
- Easy customization of scoring regions

---

## 🗂 Project Structure

- `Videos/Video2.mp4` – Input video of the dartboard session
- `polygons` – Serialized file containing scoring regions and values
- `ColorModule` – From the `cvzone` library, used for HSV-based color detection
- `main.py` – Core script for detection, scoring, and display

---

## ▶️ How to Run

### 1. Install Dependencies

Make sure you have Python 3 installed. Then install required libraries:

```bash
pip install opencv-python cvzone numpy
```

### 2. Add Input Files

Ensure the following files are present in your directory:
- A video file under `Videos/Video2.mp4`
- A `polygons` pickle file containing polygon coordinates and scores

### 3. Run the Script

```bash
python main.py
```

The script will:
- Read frames from the video
- Warp the dartboard to a top-down view
- Detect color blobs (darts)
- Check if hits land within score zones
- Display and update the total score

---

## 🎯 How Scoring Works

1. The dartboard region is defined via 4 corner points for perspective transformation.
2. Scoring zones are stored as polygons (list of points) with assigned score values.
3. When a hit is detected, the center of the detected blob is checked against each polygon using `cv2.pointPolygonTest()`.
4. If a hit is inside a zone, the corresponding score is added.

---

## 📈 Sample Output

![Example](./output_example.jpg) *(Add a screenshot here)*

---

## 🛠 Customization

- Modify `hsvVals` to adjust color detection for different dart colors.
- Use `ColorFinder`’s live tuning mode to find the best HSV range.
- Add/modify scoring zones by editing the `polygons` file and regenerating with new coordinates.

---

## 🙋‍♀️ Author

**Padmasahithi Kondeti**  
Computer Vision Developer | Passionate about real-time detection systems  
[LinkedIn](https://www.linkedin.com/) | [GitHub](https://github.com/)

---

## ⭐️ Acknowledgments

- [cvzone](https://github.com/cvzone/cvzone) – High-level computer vision utilities
- OpenCV – Image processing and geometric operations
