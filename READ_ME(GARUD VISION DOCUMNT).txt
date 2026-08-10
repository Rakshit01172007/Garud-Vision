GARUD VISION - BASIC USER GUIDE
================================

This guide is for a first-time user. You do not need programming knowledge to use GARUD VISION.

1. START THE APPLICATION
------------------------
Option A - Open the ready application
  1. Open the release folder supplied with the project.
  2. Double-click GARUD_VISION.exe.
  3. Wait for the dashboard to appear. The first AI analysis can take a short time while the local models load.

Option B - Run from VS Code / Python
  1. Open this project folder in VS Code.
  2. Open Terminal in VS Code.
  3. Run:  python -m pip install -r requirements.txt
  4. Run:  python main.py
  5. Keep the models and assets folders in the project; do not rename or remove them.

2. PROCESS A VIDEO
------------------
  1. Choose Upload Video from the left menu.
  2. Choose an MP4, MOV or AVI traffic video.
  3. The dashboard opens automatically and begins analysis.
  4. Use Pause or Stop if needed. The AI analysis continues in the background when you navigate to another screen.
  5. Every time you process a video, GARUD VISION creates a NEW analysis run. Processing the same file again does not mix it with old detections.

3. USE LIVE CCTV
----------------
  1. Choose Live CCTV.
  2. Select PC webcam to use the computer camera. Enter the webcam index (normally 0); no URL is needed.
  3. Select Ethernet RTSP or Mobile sync for a network camera and enter its valid stream URL.
  4. Select Connect Live Feed. Vehicle, number-plate, tracking and alert logic work the same way as an uploaded video.

4. UNDERSTAND THE DASHBOARD
---------------------------
  - The main preview shows live vehicle boxes, stable track IDs and verified plates.
  - Recent Number Plate shows repeat-confirmed Indian registration readings only.
  - Vehicle Summary, Density Trend and Summary Today update for the CURRENT processing run only.
  - The latest table lists verified number plates, not every raw vehicle track.

5. ALERTS (IMPORTANT)
---------------------
  1. Choose Alerts.
  2. Select a vehicle type, for example Car, Truck or Tank.
  3. Select a colour, for example Red.
  4. Select Flash message, Beep or Siren, then click Save changes.
  5. When a matching vehicle is newly detected, a GARUD VISION alert appears.
  6. For Beep and Siren, the sound repeats until the operator presses OK - Acknowledge and silence.
  7. Reset and disable stops active alerts and disables further alert actions.

Tank detection:
  - The pretrained tank model is included in the current project build.
  - If another copy of the project does not contain models/tank_yoloworld.pt, run setup_models.bat once with internet access before using a Tank alert.

6. ANALYTICS, STATISTICS AND DATABASE
-------------------------------------
  - Analytics shows the large evidence snapshot and details only for vehicles with verified plates.
  - Statistics shows vehicle type and vehicle colour charts for the selected/current run.
  - Database stores uploaded-video records, snapshots and generated reports separately.
  - Use View saved data to inspect a selected old run.
  - Process as a new run re-analyses the selected video without changing the saved old run.
  - Each Database tab has its own clear action. Clear all data permanently clears the three sections.

7. GENERATE A PDF EVIDENCE REPORT
---------------------------------
  1. Choose Reports.
  2. Select one processed video source.
  3. Enter one to ten verified registration numbers. Use Add vehicle number for more fields.
  4. Click Generate PDF report.
  5. The PDF contains only the selected video and the registration numbers you entered. It does not include old-run or unrelated snapshots.
  6. Open, preview or delete reports from Database > Reports.

8. ACCURACY NOTES
-----------------
  - GARUD VISION uses pretrained vehicle detection, plate detection, ByteTrack and a dedicated Indian registration OCR reader.
  - A plate is published only after repeat confirmation. This reduces false readings but can reject a plate that is too blurred, tiny, blocked or overexposed.
  - For the best result, use a clear front/rear traffic view, good lighting and a high-resolution source. No visual AI system can promise 100 percent recognition in every real-world frame.

9. IF SOMETHING DOES NOT WORK
-----------------------------
  - Video will not open: verify the file still exists and plays in a normal media player.
  - Webcam will not connect: start with camera index 0, close other apps using the camera, then try again.
  - CCTV will not connect: check the RTSP/mobile URL, camera network and username/password.
  - Tank option says model unavailable: run setup_models.bat once with internet access.
  - The app is slow on the first run: allow the pretrained models to initialise; performance depends on video resolution and computer hardware.

All evidence remains local to this project folder unless you manually copy or share it.
