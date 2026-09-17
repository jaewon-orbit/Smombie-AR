# Smombie AR

An Android prototype that recognizes the surroundings seen by a phone camera and displays warnings while the user is viewing another app.

## Goal

The project explored how to alert pedestrians to surroundings such as stairs and crosswalks when they are looking at their phones.

## System

```text
Phone camera → Image preprocessing → ONNX classifier → Warning overlay
```

The Android app uses Kotlin and ONNX Runtime. The training code uses PyTorch and EfficientNet-B0 with five classes: sidewalk, road, crosswalk, stair, and door.

## My Contribution

I collected image data and trained the classification model. This connected the data-collection and model-training work to a mobile application that could present warnings over other content.

## Implementation

- [`model/train.py`](model/train.py) contains training, evaluation, and ONNX export code.
- [`ORTAnalyzer.kt`](app/src/main/java/com/example/smombie/analysis/camera/ORTAnalyzer.kt) preprocesses camera frames, runs inference, and passes classification results to the interface.
- The repository includes model files and a sample dataset under `model/`.

## Demo

[![Smombie AR demo](https://img.youtube.com/vi/ECNi-IljLDc/0.jpg)](https://www.youtube.com/watch?v=ECNi-IljLDc)

| Press Start | Just Walk! |
|----------|----------|
| <img src="https://github.com/pogihae/Smombie/assets/76048647/a1ac532a-6ccc-4a19-8a93-9d3bb0e54bc4" alt="Image" width="200" height="360" /> | <img src="https://user-images.githubusercontent.com/76048647/236119168-647fa600-6a6b-40f7-84b9-d629b8288438.gif" alt="Image" width="200" height="360" /> |

## Scope

The original prototype used data collected around Gachon University. Its behavior in other environments would require further data and evaluation. The repository includes evaluation code, but no consolidated measured accuracy result is reported here.
