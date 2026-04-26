# Face Recognition Attendance System

A simple real-time face recognition attendance system using Python, OpenCV, and the `face_recognition` library. This project captures video from a webcam, identifies known faces, and logs attendance into an Excel file.

---

## Features

- Real-time face detection and recognition
- Automatic attendance recording
- Prevents duplicate entries on the same day
- Stores attendance in Excel format (`kehadiran.xlsx`)
- Displays live video with face labels

---

## Requirements

Install the required dependencies:
```bash 
pip install opencv-python face-recognition numpy pandas openpyxl
```
---

## Project Structure

```bash
FACE-RECOGNITION/
├── dataset/
│   └── ahsanul.JPG
├── dlib-19.24.1-cp311-cp311-win_amd64.whl
├── encode_face.py
├── encodings.pickle
├── face_attendance.py
├── kehadiran.xlsx
```
---

## How It Works

1. Loads known face encodings from `encodings.pickle`
2. Captures video from the webcam
3. Detects faces in each frame
4. Matches detected faces with stored encodings
5. If a match is found:
   - Checks if attendance already exists for today
   - If not, records name and timestamp in Excel
6. Displays the video with bounding boxes and names

---

## Key Function

### is_already_recorded(name)

Checks whether a person’s attendance has already been recorded on the current date.

---

## Attendance Format

The system saves attendance in `kehadiran.xlsx` with the following structure:

| Name | Attendance Time |
|------|----------------|
| John | 2026-04-26 08:30:12 |

---

## Running the Project

python main.py

Press **q** to exit the application.

---

## Notes

- Make sure `encodings.pickle` exists and contains valid face data.
- The Excel file will be created automatically if it does not exist.
- Good lighting conditions improve recognition accuracy.
- The system uses the first matched face (not the best match).

---

## Future Improvements

- Improve matching accuracy using face distance
- Add a graphical user interface (GUI)
- Store attendance in a database
- Support multiple cameras
- Export reports (CSV/PDF)

---

## License

This project is open-source and intended for learning purposes.
