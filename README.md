                                   
# Speech Spoofing Detection

In this project, conducted in 2019, we explored the detection of replayed (spoofed) speech using a Light CNN (LCNN), originally designed for noisy image recognition. We aimed to classify `.wav` audio files from the ASVspoof2017 dataset as either genuine or replayed. To accomplish this, we extracted Mel-Frequency Cepstral Coefficients (MFCCs), applied pre-emphasis to highlight higher frequencies, and then zero-padded the results to ensure consistent input shapes.

<p align="center">
  <img src="images/Pre_amplification.png" alt="Description" width="500"/>
</p>

We leveraged a Maximum Feature Map (MFM) operation after each convolution in our LCNN, which reduced the total number of parameters by filtering out weaker activations.

<p align="center">
  <img src="images/MFM.png" alt="Description" width="500"/>
</p>

Early experiments showed significant overlap in genuine vs. spoof probability distributions when using deeper LCNN configurations. However, by reducing the model’s depth and decreasing the number of filters, we achieved a substantial improvement in class separation.

Training involved cross-entropy loss and Stochastic Gradient Descent with a dynamic learning rate, and performance was assessed by visualizing score distributions for each class.
<p align="center">
  <img src="images/Distribution_Scores_InitialExp vs finalExp.png" alt="Description" width="500"/>
</p> 

