# Variational_Autoencoder_for_Anomaly_Detection

You can check out the full report here: 

The primary goal of this project is to develop an unsupervised learning framework for the identification of brain tumors in MRI scans. By leveraging the principles of anomaly detection, the system aims to distinguish between healthy brain tissue and pathological structures without requiring extensive labeled datasets of various tumor types.

RESULTS:
The AUC Score (0.893) confirms that the model’s ability to distinguish between healthy and non-healthy tissue is robust and not just a result of a lucky threshold choice. Accuracy (0.93) is significantly higher than the NIR (0.81). This proves the model has learned meaningful anatomical patterns. Healthy Precision (0.75): This suggests that when the model flags a "Healthy" case, it is correct 75% of the time. Conversely, it means there are some "False Positives" (healthy brains flagged as anomalous). The F1-Score for the "Non healthy" class reaches 0.95, indicating that the threshold calibrated using the Youden’s J statistic was highly effective at maximizing the model's diagnostic power.

The visual analysis of the error distributions confirms that while the VAE effectively separates healthy from pathological tissue, there remains a marginal overlap between classes. I believe that this is attributed to the high variance in the input, the inclusion of multiple MRI planes and contrast types introduce 'anatomical noise' into the reconstruction error. Nevertheless, the ROC AUC of 0.893 proves that the model remains a robust discriminator.

LIMITATIONS: 
While the VAE demonstrates strong discriminative power in separating healthy from pathological scans, a detailed qualitative analysis reveals a significant limitation in its local feature extraction.
The model effectively identifies anomalous images primarily through a global increase in reconstruction error rather than a precise spatial identification of the tumor. In many instances, the VAE fails to isolate the tumor, it tends to reconstruct the entire anomalous image with an increased level of blurriness or atmospheric noise.
Therefore, the high Anomaly Scores for tumor images are often the result of an overall loss of structural fidelity across the entire brain slice, rather than a successful segmentation of the lesion itself. This "blurring effect" allows for correct classification at the image level but highlights the model's current inability to act as a reliable tool for localizing specific pathological markers.


performance:
<img width="1964" height="500" alt="performance" src="https://github.com/user-attachments/assets/10a2122b-75ea-43c4-93c0-17e30f47a09a" />

heatmaps:
<img width="1706" height="989" alt="heat6" src="https://github.com/user-attachments/assets/276a74cb-0d58-4822-b189-a56d671d4533" />
<img width="1706" height="989" alt="heat4" src="https://github.com/user-attachments/assets/581ba7fd-e278-43f0-8c47-cf51371e5fec" />
<img width="1708" height="989" alt="heat1" src="https://github.com/user-attachments/assets/558e3372-b76c-4bdd-94fe-9c8ef0d15592" />


