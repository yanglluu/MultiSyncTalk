# Controllable-and-Temporally-Stable-Audio-Driven-Talking-Head-Generation-for-Multi-User-Interactions
Official implementation of **MultiSyncTalk**, a controllable audio-driven talking-head generation framework for multi-user interactive scenarios.
# MultiSyncTalk: Controllable and Temporally Stable Audio-Driven Talking-Head Generation for Multi-User Interactions



Official implementation of **MultiSyncTalk**, a controllable audio-driven talking-head generation framework for multi-user interactive scenarios.

## Overview

MultiSyncTalk is designed for audio-driven talking-head generation with:

- personalized speech-driven facial and head motion
- explicit head-pose control for multi-user interaction
- temporally stable motion trajectories with lightweight smoothing

The framework follows a **generation → control → stabilization** pipeline:

1. **GAN-based audio-to-motion generator**  
   Predicts facial expression and head-pose parameters from speech while preserving speaker-specific motion style.

2. **Interaction-guided Head Pose Expert (IHPE)**  
   Injects user-defined pose trajectories into the generated motion sequence, enabling controllable gaze and attention shifts.

3. **Stabilized and Adaptive Smoothing Module (SASM)**  
   Suppresses motion jitter and abrupt transitions in a lightweight, parameter-free manner.

## Highlights

- Controllable head-turn generation for multi-user conversational scenarios
- Personalized motion style preservation
- Lightweight smoothing with negligible runtime overhead
- Real-time friendly design based on 3DMM parameter-space manipulation

## Method

Given an input audio sequence, a reference video, and an optional pose-control sequence, MultiSyncTalk generates a talking-head video whose lip motion, expressions, and head movements are temporally coherent and controllable.

The method is built around three main components:

- `G_time`: temporal generator for sequence-level motion coherence
- `G_audio`: local audio generator for frame-wise motion refinement
- `IHPE`: explicit pose injection module
- `SASM`: motion-aware smoothing over pose, expression, and illumination parameters
