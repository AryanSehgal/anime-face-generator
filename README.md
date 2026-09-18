# Anime Face Generator BTP

Contributors :-

##### Aryan Sehgal    - 2019UCS2019

##### Sourabh         - 2019UCS2025

##### Aditya Divyang  - 2019UCS2012

##### M Aman Chaudhry - 2019UCS2020

<hr style="border:2px solid gray">

Animations play an important role in our daily life and have been widely used in entertainment, social, and educational applications. We aim to automatically translate a photo-face into an anime-face based on the styles of a reference anime-face. We refer to such a task as Style-Guided Face-to-Anime Translation (StyleFAT). 

We implement a generator architecture that preserves the global information (e.g., pose) of a source photo-face, while transforming local facial shapes into anime-like ones and transferring colors/textures based on the style of a reference anime-face. Our insight is that the local shapes (e.g., large and round eyes) can be treated as a kind of style like color/texture. In this way, transforming a face’s local shapes can be achieved via style transfer. To transform local facial shapes via style transfer, we explore where to inject the style information into the generator. In particular, the multi-layer feature maps extracted by the decoder represent multi-level semantics (i.e., from high-level structural information to low-level textural information). Our generator therefore injects the style information into the multi-level feature maps of the decoder. Guided the injected style information and different levels of feature maps, our generator adaptively learns to transfer color/texture styles and transform local facial shapes.


<img src="https://user-images.githubusercontent.com/59551957/206827795-200422a7-5ed0-4c44-adc6-11ae74b03ce5.jpeg" width="500">


In addition to the generator, we propose a discriminator that discriminates between real and generated human-faces, and real and generated anime faces. In particular, we assume that anime-faces and photo-faces partially share common distributions and such cross-domain shared distributions constitute meaningful face information, since these two domains are both about faces. Our discriminator network uses pre-trained layers of VGG16 model to classify the image given to the network.

<img src="https://user-images.githubusercontent.com/59551957/206827781-de18e3cc-a474-4577-b270-dd6291f58598.jpg" width="500">

* After experimenting with miultiple different archtectures for content encoder and style encoder, we came up with the following architecture 

## Content Encoder


![Content Encoder](https://user-images.githubusercontent.com/59551957/206828179-1c5cfedb-c604-444d-a343-b09e4eed2c23.jpeg)


## Style Encoder

![Style Encoder](https://user-images.githubusercontent.com/59551957/206828182-1414c698-9ed2-448f-bb81-407daa071904.jpeg)


## Decoder


![Decoder (1)](https://user-images.githubusercontent.com/59551957/206827890-614e946d-4f55-4514-9d6a-3da15b6c4a86.jpg)


## Discriminator


![Discriminator](https://user-images.githubusercontent.com/59551957/206827911-78dedaec-2556-47d8-90f1-08f0128d459d.jpg)


<hr style="border:2px solid gray">

## Comparison of our model with others


![Comparison](https://user-images.githubusercontent.com/59551957/206827942-88a1b453-6235-40e4-b560-f9a33c249c0b.jpg)


<hr style="border:2px solid gray">

## References :-

[1] AnimeFace2009, https://github.com/nagadomi/animeface-2009

[2] Danbooru2019, https://www.gwern.net/Danbooru2019

[3] Jimmy Lei Ba, Jamie Ryan Kiros, and Geoffrey E Hinton. Layer
normalization. arXiv preprint arXiv:1607.06450, 2016

[4] Andrew Brock, Jeff Donahue, and Karen Simonyan. Large scale gan
training for high fidelity natural image synthesis. In Proc. Int. Conf. Learn.
Rep., 2019.

[5] Kaidi Cao, Jing Liao, and Lu Yuan. Carigans: Unpaired photo-tocaricature
translation. ACM Trans. Graphics, 2018.

[6] Hung-Jen Chen, Ka-Ming Hui, Szu-Yu Wang, Li-Wu Tsao, Hong-Han
Shuai, and Wen-Huang Cheng. Beautyglow: Ondemand makeup transfer
framework with reversible generative network. In Proc. IEEE/CVF Conf.
Comput. Vis. Pattern Recognit., pages 10042–10050, 2019.

[7] Lei Chen, Le Wu, Zhenzhen Hu, and Meng Wang. Qualityaware unpaired
image-to-image translation. IEEE Trans. on Multimedia, 21(10):2664–2674,
2019.

[8] Yang Chen, Yu-Kun Lai, and Yong-Jin Liu. Cartoongan: Generative
adversarial networks for photo cartoonization. In Proc. IEEE/CVF Conf.
Comput. Vis. Pattern Recognit., pages 9465–9474, 2018

[9] Yunjey Choi, Minje Choi, Munyoung Kim, Jung-Woo Ha, Sunghun
Kim, and Jaegul Choo. Stargan: Unified generative adversarial networks for
multi-domain image-to-image translation. In Proc. IEEE/CVF Conf. Comput.
Vis. Pattern Recognit., 2018.

[10] Yunjey Choi, Youngjung Uh, Jaejun Yoo, and Jung-Woo Ha. Stargan
v2: Diverse image synthesis for multiple domains. In Proc. IEEE/CVF Conf.
Comput. Vis. Pattern Recognit., 2020.

[11] Leon A Gatys, Alexander S Ecker, and Matthias Bethge. A neural
algorithm of artistic style. arXiv preprint arXiv:1508.06576, 2015

[12] Gatys, Leon A and Ecker, Alexander S and Bethge, Matthias. Image
style transfer using convolutional neural networks. In Proc. IEEE/CVF Conf.
Comput. Vis. Pattern Recognit., pages 2414–2423, 2016

[13] Ian Goodfellow, Jean Pouget-Abadie, Mehdi Mirza, Bing Xu,
DavidWarde-Farley, Sherjil Ozair, Aaron Courville, and Yoshua Bengio.
Generative adversarial nets. pages 2672– 2680, 2014

[14] Ishaan Gulrajani, Faruk Ahmed, Martin Arjovsky, Vincent Dumoulin,
and Aaron C Courville. Improved training of wasserstein gans. In Proc. Adv.
Neural Inf. Process. Syst., pages 5767–5777, 2017

[15] Bin He, Feng Gao, Daiqian Ma, Boxin Shi, and Ling-Yu Duan. Chipgan:
A generative adversarial network for chinese ink wash painting style transfer.
In Proc. ACM Int. Conf. Multimedia, pages 1172–1180, 2018

[16] Martin Heusel, Hubert Ramsauer, Thomas Unterthiner, Bernhard
Nessler, and Sepp Hochreiter. Gans trained by a two time-scale update rule
converge to a local nash equilibrium. In Proc. Adv. Neural Inf. Process.
Syst., pages 6626– 6637, 2017

[17] Xun Huang and Serge Belongie. Arbitrary style transfer in real-time
with adaptive instance normalization. In Proc. IEEE/CVF Conf. Comput.
Vis. Pattern Recognit., pages 1501–1510, 2017

[18] Phillip Isola, Jun-Yan Zhu, Tinghui Zhou, and Alexei A Efros.
Image-to-image translation with conditional adversarial networks. In Proc.
IEEE/CVF Conf. Comput. Vis. Pattern Recognit

[19] Ting-Chun Wang, Ming-Yu Liu, Jun-Yan Zhu, Andrew Tao, Jan
Kautz, and Bryan Catanzaro. High-resolution image synthesis and semantic
