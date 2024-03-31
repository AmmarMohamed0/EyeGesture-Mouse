# EyeGesture-Mouse

1. **Imports**: It imports necessary libraries - `cv2` for computer vision tasks, `mediapipe` for accessing facial landmarks, and `pyautogui` for controlling the mouse cursor and performing clicks.

2. **Setup**: It sets up the video capture from your webcam (`cv2.VideoCapture(0)`), initializes the Face Mesh model for detecting facial landmarks (`mp.solutions.face_mesh.FaceMesh()`), and gets the screen size for later use.

3. **Main Loop**: The program enters a loop that continuously processes frames from the webcam.

4. **Frame Processing**: It reads a frame from the webcam, flips it horizontally (since the webcam typically shows a mirrored image), and converts it to RGB format for compatibility with Mediapipe.

5. **Facial Landmark Detection**: It processes the frame to detect facial landmarks using the Face Mesh model. It extracts the landmark points if any faces are detected.

6. **Mouse Movement**: It calculates the position of the mouse cursor based on the position of specific facial landmarks. The program monitors the movement of a particular pair of facial landmarks (475th and 476th landmarks) to control the mouse cursor's movement. As the user moves their face, the cursor follows.

7. **Mouse Click**: It detects a specific facial expression or movement (in this case, when the distance between two particular facial landmarks becomes very small) and simulates a mouse click using `pyautogui.click()`.

8. **Display**: It displays the processed frame with added visual cues (circles around detected facial landmarks) and the current position of the mouse cursor.

9. **Input Handling**: It waits for the user to press the 'q' key to exit the program.

10. **Cleanup**: Once the user exits the loop, it releases the webcam (`cap.release()`) and closes all OpenCV windows (`cv2.destroyAllWindows()`).
