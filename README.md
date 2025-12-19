# Camera Calibration

Fisheye camera calibration system for correcting distortion in computer vision applications.

## Install

```bash
uv sync
```

## Workflow

### 1. Distortion Test (Optional)

Visually analyze your camera's distortion:

```bash
uv run calibration.py
```

Generates images with grids and circles to evaluate distortion severity.

### 2. Fisheye Calibration

Calibrate your camera using a chessboard pattern (9x6):

```bash
uv run calibrate_fisheye.py
```

The interactive process captures 20 images from different angles and calculates calibration parameters. Generates `fisheye_calibration.npz` with camera matrix and distortion coefficients.

### 3. Tracking Usage

Apply calibration in a tracking system:

```bash
uv run test.py
```

Example integration with YOLOv8 that corrects distortion in real-time before tracking.
