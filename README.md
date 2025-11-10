# Week-one
# Problem Statemnt :- 
Here is a concise summary of "Fruit Images for Object Detection" for your exam review:

Task: Object detection is Classification + Localization. It's harder than simple classification because the model must output both a class label (e.g., "apple") and a bounding box ([x, y, w, h]) for every fruit in the image, not just one label for the whole image.

Why Fruit? It's a classic problem because it clearly demonstrates all the key challenges:

Occlusion: A leaf covering an apple.

Scale Variation: A tiny grape and a large watermelon in the same frame.

Clutter: A fruit bowl with many overlapping objects.

Intra-Class Variation: Red apples, green apples, sliced apples.

Why Not MLPs? Standard Multilayer Perceptrons (MLPs) are terrible for this. They require "flattening" the 2D image into a 1D vector, which destroys all spatial information (what's next to what). They are also not translation invariant (an apple in a new spot is seen as a new pattern).

The Solution: Convolutional Neural Networks (CNNs). These are the correct type of feedforward network for images. They use convolution layers to preserve spatial info and learn hierarchical features. This is a perfect example of Representation Learning:

Layer 1: Learns edges, colors.

Layer 2: Learns textures, simple shapes (like "round").

Layer 3: Learns objects (like "apple").

Key Algorithms:

Two-Stage (e.g., Faster R-CNN): "Propose regions, then classify." Very accurate but slow.

One-Stage (e.g., YOLO): "Look once, predict all." Very fast (real-time) but can be less accurate on small/crowded objects.

Data: Requires annotated images. For every image.jpg, you need a label file (image.xml) that lists the ground-truth class and bounding box for every single fruit.

DataSet Link :- https://www.kaggle.com/datasets/mbkinaci/fruit-images-for-object-detection
