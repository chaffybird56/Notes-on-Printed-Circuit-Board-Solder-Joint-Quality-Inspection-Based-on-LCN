1 Introduction
These notes explore the paper “Printed circuit board solder joint quality inspection based on lightweight
classification network” by Zhang et al. We (i.e., our team) intend to apply these ideas to a real-time
soldering robot project, where the robot can inspect each joint right after soldering, decide if it is
defective, and attempt corrections. Our roadmap includes first creating a simple binary good/bad model,
then building up to more advanced multi-class defect detection with real-time feedback.

2 Context and Motivation
Solder joints are critical connections on a PCB. Defective joints can cause intermittent or outright failures.
Manually inspecting every joint can be slow and prone to human error, so automatic visual inspection
is a desirable solution.
Zhang et al. propose a pipeline with two main parts:
1. A specialized segmentation method (the “Select Joint” approach) to locate each solder joint on the
PCB.
2. A lightweight classification network (“MobileXT”) that determines whether the extracted soldered
joint is normal (i.e good) or belongs to a specific defect category.
