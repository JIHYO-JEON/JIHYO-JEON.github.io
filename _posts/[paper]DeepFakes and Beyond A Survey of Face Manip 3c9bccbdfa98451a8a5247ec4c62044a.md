# [paper]DeepFakes and Beyond: A Survey of Face Manipulation and Fake Detection

---
---
layout: post
title: "DeepFakes and Beyond: A Survey of Face Manipulation and Fake Detection"
date: 2021-02-15 20:46:00
tags: [ML paper]
---



# DeepFakes and Beyond: A Survey of Face Manipulation and Fake Detection

[DeepFakes and Beyond: A Survey of Face Manipulation and Fake Detection](https://arxiv.org/pdf/2001.00179v3.pdf)

## **Types of Facial Manipulation**

### 1. Entire Face Synthesis

This is about creating entire non-existent face images, usually through powerful GAN for video game, 3D-modelling. It can be used for harmful ways such as very realistic fake photo includes wrong infromation.

1. StyleGAN

    T. Karras, S. Laine, and T. Aila, “A Style-Based Generator Architecture for Generative Adversarial Networks,” in Proc. IEEE/CVF Conference on Computer Vision and Pattern Recognition, 2019.

2. ProGAN

    T. Karras, T. Aila, S. Laine, and J. Lehtinen, “Progressive Growing of GANs for Improved Quality, Stability, and Variation,” in Proc. International Conference on Learning Representations, 2018.

    ### **Public Database**

    - **100K-Generated-Images**

    This database which is a set of 100k synthetic face images was generated using their proposed StyleGAN architecture which was trained with FFHQ dataset.

    - **100K-Faces**

    This database contains 100K synthetic images generated using STYLE-GAN.

    - **Fiverse Fake Face Dataset(DFFD)**

    Regarding the entire face synthesis manipulation, the authors created 100,000 and 200,000 fake images through the pre-trained ProGAN and StyleGAN models, respectively.

    - **iFakeFaceDB**

    This database comprises 250,000 and 80,000 synthetic face images created with StyleGAN and ProGAN, respectively. It  produced by the GAN architectures were removed through an approach named GANprintR (GAN fingerprint Removal), while keeping very realistic appearance. So, it presents a higher challenge for advanced fake detectors compared with the other databases.

    ### Manipulation Detection

    ![%5Bpaper%5DDeepFakes%20and%20Beyond%20A%20Survey%20of%20Face%20Manip%203c9bccbdfa98451a8a5247ec4c62044a/Untitled.png](%5Bpaper%5DDeepFakes%20and%20Beyond%20A%20Survey%20of%20Face%20Manip%203c9bccbdfa98451a8a5247ec4c62044a/Untitled.png)

### 2. Identity Swap

'Identity Swap' is replacing the faces in a video. There are 2 approaches: 1. classical computer graphics-based techniques.

1. FaceSwap
2. DeepFakes

### 3. Attribute Manipulation

Attribute manipulation is modifying some attributes of the face includes the hair colour, skin colour, gender, age, or accesarries to edit or retouch the face.

1. StarGAN

    Y. Choi, M. Choi, M. Kim, J. Ha, S. Kim, and J. Choo, “StarGAN: Unified Generative Adversarial Networks for Multi-Domain Imageto-Image Translation,” in Proc. IEEE/CVF Conference on Computer Vision and Pattern Recognition, 2018.

### 4. Expression Swap

Expression swap means face reenactment consists of modifying the facial expression of the person.

1. Popular GAN architectures

    M. Liu, Y. Ding, M. Xia, X. Liu, E. Ding, W. Zuo, and S. Wen, “STGAN: A Unified Selective Transfer Network for Arbitrary Image Attribute Editing,” in Proc. IEEE/CVF Conference on Computer Vision and Pattern Recognition, 2019.

2. Face2Face

    J. Thies, M. Zollhofer, M. Stamminger, C. Theobalt, and M. Nießner, “Face2face: Real-Time Face Capture and Reenactment of RGB Videos,” in Proc. IEEE/CVF Conference on Computer Vision and Pattern Recognition, 2016.

3. Neural-Textures

    J. Thies, M. Zollhofer, and M. Nießner, “Deferred Neural Rendering: ¨ Image Synthesis using Neural Textures,” ACM Transactions on Graphics, vol. 38, no. 66, pp. 1–12, 2019.