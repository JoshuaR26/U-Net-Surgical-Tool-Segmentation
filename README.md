# Surgical Tool Segmentation

---

This project focuses on multiclass segmentation of surgical tools. The team has implemented the multiclass segmentation using ensemble methods that combine six U-net models. Each U-net model yields a binary segmentation mask for each class. These masks are then concatenated to formulate a segmentation mask.

### Goals
1. **Precise segmentation:** *We aim to precisely segment each class in all frames of the given image.*
2. **Real Time Inference:** *We aim to obtain the segmented masks in real time.*

---

## Approaches Reviewed
- ### BCD-Unet
The [Binary Convolutional Decoder-Unet (BCD-Unet)](https://github.com/rezazad68/BCDU-Net) merges binary convolutions with
U-Net's structure for robust semantic segmentation. It employs binary convolutions in
both encoder and decoder stages, reducing computational complexity without sacrificing accuracy. This architecture, with its binary operations and refined decoder, excels in real-time applications, medical imaging, and autonomous systems. Integrating attention mechanisms further enhances its ability to capture intricate details, making BCD-Unet a powerful tool for efficient and accurate semantic segmentation in various domains.
- ### SurgicalSAM
[SurgicalSAM](https://github.com/wenxi-yue/SurgicalSAM) represents a significant advancement in pediatric surgical training. This innovative simulator surpasses traditional mannequins by offering a remarkably realistic environment that mimics a living child. Developed in collaboration with Boston Children's Hospital, Sam allows surgical teams to practice complex procedures on a high-fidelity platform that breathes, bleeds, and even features a beating heart.

---

## Proposed Approach
We use six u-net models to obtain the final segmented mask. Each U-net model is fed the same image but they all predict different classes. According to the target class, loss function of each U-net is assigned. Classes surgical instruments and clamps use jaccard distance as their loss function while classes suturing needles, threads, clamps and suturing instruments use dice loss as their loss functions. The input image is passed through all the six models and the segmented masks obtained for each class are then concatenated to obtain the final segmented mask.

---

## Train Sequence

![Train Sequence 1](https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExM2RtNmliOTdzN3Z5cjlteHF4YW0xYXI0aGllOWNzcmJlMTFvZDVoOSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/Lim01RkkIaE3B8Cb79/giphy.gif)
![Test Sequence 1]()
![Test Sequence 2]()
![Test Sequence 3]()
***
# Team 
- [Radhika A Desai](https://github.com/Radhika-Amar-Desai)
- [Joshua S Raju](github.com/JoshuaR26)
- [Hitesh Krishna](https://github.com/hiteshhhh007)
