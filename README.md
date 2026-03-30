Drone vs Non-Drone Image Classification
Problem
Binary classification of aerial images into drone and non-drone (bird) for automated aerial threat detection.

Dataset
Total images: 4,106
Bird: 1,607
Drone: 2,499
Moderate class imbalance (~1.55×)
Random 80/20 train–validation split
Model
Architecture: ResNet-18
Pretrained on ImageNet
Final fully connected layer replaced for binary classification
Transfer learning used due to limited dataset size
Training Setup
Input resolution: 224×224
Optimizer: Adam
Learning rate: 1e-4
Loss: Class-weighted CrossEntropyLoss
Data augmentation: Random horizontal flip
Training epochs: 5
Platform: Google Colab (GPU)
Results
Best validation accuracy: 99.39%
Confusion matrix:
Bird → Drone: 3
Drone → Bird: 7
Ablation Study
Frozen Backbone vs Fine-Tuning

Frozen backbone accuracy: 94.40%
Fine-tuned accuracy: 99.39%
This confirms that end-to-end fine-tuning significantly improves performance over feature extraction alone.

Limitations
Dataset likely contains background bias
No separate test set provided
Performance may degrade in real-world sky conditions
