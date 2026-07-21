# Arche Vision PO4: Automated Defect Detection in Automotive Assembly

## About the Project
* This project was developed as a Master's thesis at the Renault Tanger Exploitation plant[cite: 1, 2].
* The objective is to design and implement an intelligent embedded system for the automated detection of automobile assembly defects using artificial vision[cite: 1, 2].
* The system is specifically deployed in the PO4 zone, which is dedicated to the visual inspection of vehicle doors[cite: 1, 2].

## Problem & Objective
* Manual quality control faces limitations such as high production rates, human error, and limited traceability[cite: 2].
* To address this, the project aims to automate the inspection to reliably detect non-conformities[cite: 2].
* Another objective is to ensure total traceability by linking inspection results to the vehicle's ID[cite: 2].
* The system must also provide immediate alerts to the operator for corrections[cite: 2].

## Methodology
* The project follows the DMAIC methodology (Define, Measure, Analyze, Improve, Control) adapted for industrial vision[cite: 1, 2].
* A custom dataset of 9,192 annotated images was built using 6 industrial cameras on the assembly line[cite: 2].
* The dataset includes 17 classes representing different control points and states (OK / NOK)[cite: 1, 2].

## Models & Performance
* Three object detection architectures were trained and compared: YOLOv8, YOLOv11, and Faster R-CNN[cite: 1, 2].
* YOLOv11 was selected as the final model due to its high precision, stability, and fast inference time of under 50ms[cite: 2].
* YOLOv11 achieved a mAP@0.5 of 93.9% and a mAP@0.5:0.95 of 68.7%[cite: 1, 2].
* YOLOv8 achieved a mAP@0.5 of 93.2% and a mAP@0.5:0.95 of 66.5%[cite: 1, 2].
* Faster R-CNN achieved a mAP@0.5 of 90.3% and a mAP@0.5:0.95 of 59.5%[cite: 1, 2].

## System Architecture
The integration architecture consists of three communicating entities:
* **Vision Box**: Hosts the perception module and executes the YOLOv11 model[cite: 1, 2].
* **Automate S7-1500**: Interfaces and synchronizes with the assembly line[cite: 1, 2].
* **HMI (Supervision)**: Returns the verdict to the operator and logs the control data[cite: 1, 2].
* The system connects to Renault's internal networks, including PSF for vehicle identification and GRET for defect reporting[cite: 1, 2].