# RAFT_PItCH_Deck
NATIONAL STUDENT HACK-A-STAGE 2026

# Reflectance-Aware 3D Facade Digital Twin

> **AI-powered facade inspection that distinguishes real defects from reflections and maps them onto a 3D building model.**

## Problem

High-rise glass facades are difficult to inspect automatically.

Glass reflections from the **sky, sunlight, and nearby buildings** can look like real defects such as:

* Dirt and stains
* Water patches
* Soap residue
* Sealant cracks
* Gaps and breaches

Traditional computer vision can therefore produce **false detections**. Even after detecting a defect, locating its exact position on a large building is challenging.

## 💡 Solution

We propose a **Reflectance-Aware 3D Facade Digital Twin** that combines:

**Multi-Sensor Imaging → Reflection Analysis → AI Detection → 3D Mapping → Severity Heatmap**

The key concept is:

> **Physics First, AI Second.**

Instead of directly asking AI to detect defects, we first analyze reflection behavior using **polarization and multi-view geometry** to distinguish reflections from surface-fixed defects.

## ⚙️ How It Works

### 1. Multi-Sensor Capture

The system collects facade data using available sensors such as:

* RGB camera
* Polarization camera
* Thermal camera
* Multispectral/SWIR camera *(where available)*
* Positioning data from GPS/IMU

### 2. Reflection-Aware Processing

We analyze the facade from multiple viewpoints.

**Core principle:**

> Reflection changes with viewpoint.
> A real surface defect remains attached to the same facade location.

Polarization information and multi-view geometry are combined to reduce reflection-induced false positives.

### 3. Dual AI Detection

The system uses two specialized detection branches.

**Surface Condition Branch**

* Dirt
* Water stains
* Soap residue
* Organic fouling

**Structural Integrity Branch**

* Sealant cracks
* Gaps
* Breaches
* Potential water-ingress regions

### 4. 3D Spatial Mapping

A 3D facade model is reconstructed using photogrammetry.

Detected defects are projected onto the 3D model and associated with specific:

* Building faces
* Floors
* Panels
* Joints

### 5. Severity & Digital Twin

Each defect receives a severity score based on factors such as:

* Defect type
* Area
* Crack length
* Location
* Structural/maintenance risk

The final result is an interactive **3D quality heatmap / digital twin** showing where maintenance is required.

## 🧠 Key Innovation

### Moving vs. Fixed Reflection Analysis

A dark region in a glass image is not automatically considered a defect.

The system compares multiple viewpoints:

<img width="1178" height="1335" alt="image" src="https://github.com/user-attachments/assets/b9904d08-d7b5-410c-94c6-a524792ebd94" />


This reduces false positives before final AI classification.

## 🏗️ System Architecture

<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/7d1323f1-971e-49d0-8801-84c96b6096c8" />


## 🎯 Expected Outcome

The system aims to provide maintenance teams with an actionable answer:

> **What is damaged? Where exactly is it? How severe is it?**

Instead of simply returning an image with a bounding box, the system produces a **spatially anchored defect record** such as:

```text
Building: Tower A
Face: North
Floor: 10
Panel: 42
Defect: Sealant Crack
Severity: High
```

## 🌍 Impact

The proposed system can support:

* Automated facade inspection
* Preventive maintenance
* Reduced manual inspection effort
* Safer high-rise building assessment
* Historical defect tracking
* Data-driven maintenance planning

## 🚀 Vision

Transform facade inspection from:

**“Find a defect in an image.”**

into:

**“Understand the condition of the entire building in 3D.”**
