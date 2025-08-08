# Network-Traffic-Anomaly-Detection
Anomaly detection in network involves identifying deviations from normal network behavior that may indicate potential cyber threats. Instead of relying on predefined  signatures, anomaly detection methods use statistical models, machine learning, and deep  learning to analyze network traffic and distinguish between normal and malicious activities.
 Traditional network intrusion detection systems (NIDS) rely on signature-based methods, which are ineffective against zero-day attacks and evolving cyber threats. Existing machine learning-based anomaly detection models face critical challenges, including high false positive rates, poor generalization across different network environments, and computational inefficiency in real-time detection.This project aims to develop a real-time network traffic anomaly detection system using unsupervised learning and deep packet inspection. The goal is to enhance accuracy,scalability, and adaptability while reducing false positives and improving threat detection in dynamic network environments.

# Model Development
 framework is designed as a two-stage pipeline that sequentially applies
 the models to incoming network traffic records:
 ˆ
 Stage 1: Anomaly Detection using CNN + LSTM
 Each network traffic instance first passes through the hybrid CNN + LSTM model developed for anomaly detection. This model leverages the strengths of convolutional layers to extract local spatial features from network traffic patterns and uses LSTMunits to capture temporal dependencies. The output is a binary classification indicating whether the traffic record is normal or anomalous. This initial filtering is critical to reduce the processing load on the subsequent, more computationally intensive classification stage.
 
 Stage 2: Attack Category Classification using CNN
If the first stage flags the traffic as anomalous, the record is forwarded to the CNN based multi-class classification model. This model analyzes the traffic features further to classify the specific type of attack, such as DoS, Probe, R2L, or U2R. This detailed classification helps security analysts prioritize and respond to threats based on the attack severity and nature.By structuring the deployment in this manner, the system ensures efficient utilization of computational resources. Normal traffic is quickly filtered out, preventing unnecessary processing by the attack classification model. Meanwhile, anomalous traffic receives detailed scrutiny, facilitating precise threat identification
