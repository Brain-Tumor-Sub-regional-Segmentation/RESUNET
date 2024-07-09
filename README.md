### ResUNet

ResUNet, a semantic segmentation model inspired by deep residual learning and U-Net, combines the strengths of both architectures for accurate pixel-wise predictions.

#### ResNets

Deep Residual Networks (ResNets) address the vanishing/exploding gradient problem by introducing residual blocks with skip connections. These connections enable the network to learn identity mappings, facilitating the training of very deep networks.

#### Architecture Main Parts

1. **Encoder (Contracting Path)**:
   - 📉 Captures essential image features through multiple encoder blocks with pre-activated residual blocks.
   - 🔄 Each block's output serves as a skip connection for the corresponding decoder block.
   - Stride-2 convolutions in some layers reduce spatial dimensions.
   - Each encoder block includes pre-activated residual blocks.

2. **Bottleneck Layer (Bridge)**:
   - 🔗 Connects the encoder and decoder, further processing feature maps with a pre-activated residual block.

3. **Decoder (Expansive Path)**:
   - 🔼 Upscales features for pixel-wise predictions.
   - Uses upsampling layers and concatenates with skip connections from the encoder.
   - Each decoder block includes pre-activated residual blocks.

4. **Output Layer**:
   - 🎯 A 1×1 convolutional layer with sigmoid activation produces the final segmentation mask.
  
5. **Training and Datasets**:

   - 🏋️‍♂️ We run the model on BraTS-20 and BraTS-21 datasets using Kaggle's free GPU (GPU T4 x2).
   - Learns to assign labels to pixels based on features extracted and localized through the contracting and expansive paths.

ResUNets excel in medical imaging tasks such as organ and tumor segmentation.

### Papers:
📄 Read the Deep Residual U-Net paper [here](https://arxiv.org/pdf/1711.10684) on ArXiv for a formal introduction.

#### ResUNet Arcitecture:
![ResUNet Architecture](https://idiotdeveloper.com/wp-content/uploads/2021/02/arch.png)

