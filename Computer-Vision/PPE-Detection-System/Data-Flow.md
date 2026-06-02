# Data Flow

## Overview
The PPE Detection System processes visual data from monitored work environments to determine whether personnel are wearing required Personal Protective Equipment. The system converts video streams into image frames, detects workers and PPE items, evaluates compliance rules, and generates alerts when violations occur.

## Primary Data Flow
1. Security cameras capture video from monitored work areas.
2. Video streams are sent to the Video Stream Ingestion Layer.
3. The system extracts image frames from the incoming video stream.
4. Image frames are preprocessed for size, quality, and model readiness.
5. The Object Detection Model identifies personnel and PPE items within each frame.
6. The PPE Classification Engine evaluates whether required PPE is present.
7. The Compliance Evaluation Layer compares detections against site-specific safety rules.
8. Each event is classified as compliant, non-compliant, or uncertain.
9. Non-compliant events are sent to the Alert Engine.
10. Alerts are displayed in the Safety Dashboard and may trigger email or SMS notifications.
11. Detection events are stored in the Detection Database.
12. Audit logs capture alerts, reviews, user actions, and administrative changes.

## Model Training Data Flow
1. Historical safety footage and labeled images are collected.
2. Images are annotated for personnel and PPE classes.
3. The dataset is split into training, validation, and test sets.
4. The model is trained on labeled PPE detection data.
5. Model performance is evaluated using precision, recall, F1 score, and mAP.
6. Approved models are registered in the Model Management Service.
7. Updated models are deployed to the detection pipeline.
8. Performance is monitored over time for drift and accuracy degradation.

## Data Stores
* Detection Database
* Alert Records
* Audit Log Store
* Training Dataset Repository
* Model Registry
* Dashboard Analytics Store

## Data Flow Controls
* Secure camera access
* Encrypted video transmission
* Confidence threshold tuning
* Human review for uncertain detections
* Role-based dashboard access
* Retention policies for video and detection logs

## Output
The final output is a compliance event record that identifies whether required PPE was detected, where the event occurred, when it occurred, the confidence score, and whether an alert was generated.
