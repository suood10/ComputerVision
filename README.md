# USV Computer Vision
This document provides a comprehensive overview of the work conducted by the Perception Committee within the Fly Eagle team, in collaboration with Khalifa University, for their participation in MBZIRC. The primary goal of their project is to create a sophisticated algorithm designed for Unmanned Sailing Vehicles (USVs). This algorithm serves the crucial purpose of identifying and targeting vessels suspected of transporting illicit shipments. Once identified, the USV autonomously approaches the suspicious vessel, and upon confirmation, seizes the illegal shipment, thereby contributing significantly to maritime security efforts. 

## Steps: 

### image processing
Our initial step involves the meticulous collection of video data featuring the target object, ensuring a comprehensive coverage of all possible angles, especially focusing on the perspective of the vessel in question. This detailed approach is vital for accurate analysis. Once the videos are acquired, they are meticulously divided into frames, with a preference for a higher frame count as it enhances the precision of our subsequent analysis. These frames act as the foundation for delineating bounding boxes around objects within the footage, a crucial process for object identification. In our specific project, we opted for the utilization of CVAT, an online tool renowned for its effectiveness in drawing these bounding boxes. This meticulous methodology ensures the thoroughness and reliability of our object identification process, paving the way for precise and insightful results.

In the subsequent phase, we initiate the download process, acquiring both the meticulously labeled frames, each adorned with its respective bounding box, and the associated annotation .txt files. These .txt files hold essential data, specifying the exact coordinates of the four corners of the bounding box within every individual frame. This intricate task is accomplished through specialized tools integrated within CVAT, emphasizing precision and accuracy. A pivotal aspect of this process lies in maintaining absolute synchronicity between the frames and their corresponding .txt files. The seamless alignment of frame numbers with the respective .txt files in both order and quantity is paramount. This meticulous attention to consistency guarantees the reliability and integrity of our dataset, forming the foundation for robust and dependable object identification algorithms.

Upon downloading the frames and annotations separately from CVAT, our workflow seamlessly transitioned to Roboflow, an online annotation tool that proved invaluable for our project. Utilizing the augmentation capabilities within Roboflow, we expanded our dataset by generating additional frames, enhancing the diversity and richness of our data. These augmented frames were then meticulously paired with their corresponding annotations. This meticulous process ensured that the vital contextual information regarding object locations was accurately preserved.

The next pivotal step involved the amalgamation of these augmented frames and annotations into a cohesive dataset. This merged dataset was organized and structured into a .yaml file (a file that contains the number of classes and the path required), a crucial configuration file essential for the YOLO (You Only Look Once) algorithm, which we plan to implement in our subsequent analysis. By employing this methodical approach, we not only increased the volume of our dataset but also enriched its quality, laying a robust foundation for our object identification model's accuracy and effectiveness.

### YOLO
after processing the images as described in the step before, the next phase of the process includes the downloading of yolov5 on tyour computer using the follwoing code on your teminal: 
`git clone https://github.com/ultralytics/yolov5  # clone`
`cd yolov5`
`pip install -r requirements.txt  # install`

