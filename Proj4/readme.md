# Speech Enhancement search with Emerging and Exotic Architectures
Exploration of different architectures in speech enhancement.
Converted degraded speech into its spectrogram. 
Performed end-to-end learning of cleaning spectrograms.
Converted enhanced spectrograms to waveform using istft using the phase of the degraded spectrogram. 

# Preliminary Experiments
## V1 : CNN + RNN Model
      4 x Inception + BiGRU + GRU
## V2 : Perceptual Loss Model
      4 x Inception + 2 VGG-pretrained 
      Single loss from the output of the VGG network
## V3 : UNet Model
      4 Encoder with skip connections to 4 Decoder in a U-shape format
## v4 : DenseNet
      Not explored.
## V5 : Perceptual+Auxilliary Loss Model
      4 x Inception + 2 VGG-pretrained 
      Dual losses: 1) Loss from the output of the VGG network
                   2) Loss from the output of the Enhancement sub-network
    
    
### Since v1 works the best in short preliminary experiments, focus on going deeper for V1 and training for longer duration. 
## V6 : CNN + RNN Model
      14 x Inception + BiGRU + GRU
      Unable to learn well due to model being too deep. Require huge computing power and time to determine effectiveness of the performance. Return to train V1 instead.

# Final_Prediction.ipynb
After training V1 for a long time. 
Final Prediction shows the result of the V1, with plots of spectrogram and waveforms.
Even though the RNN is train on a fixed 100 time_step, it can generalise pretty well to variable length time samples, up to 400 time_steps.
