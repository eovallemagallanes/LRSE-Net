# LRSE-Net: Lightweight Residual Squeeze-and-Excitation Network for stenosis detection in X-ray Coronary Angiography

----------
 
This repository hosts the dataset employed for the paper **LRSE-Net: Lightweight Residual Squeeze-and-Excitation Network for stenosis detection in X-ray Coronary Angiography**, publised at [MDPI-Electronics: Special Issue "Convolutional Neural Networks and Vision Applications, Volume II"](https://www.mdpi.com/2079-9292/11/21/3570)

----------

## Datasets

----------

Two public datasets were used to evaluate the proposed model: the [Deep Stenosis Detection Dataset (DSDD)](https://github.com/KarolAntczak/DeepStenosisDetection) and the [Angiographic Dataset for Stenosis Detection (ADSD)](10.17632/ydrm75xywg.2).

DSSS consists of small XCA image patches of size $32 \times 32$ taken from different image positions and sources. It contains a total of 1,519 images, whre only 125 are positive cases of stenosis and 1,394 negative cases, which generate an unbalanced ratio of 1:11 \ie one positive case for eleven negative ones.
This database does not specify a partition for training and testing sets. 

ADSD presented a set of XCA images with a total of 8,325 grayscale images (100 patients) of $512 \times 512$ to $1000 \times 1000$ pixels. XCA images were taken using Coroscop (Siemens) and Innova (GE Healthcare) image-guided surgery systems at the Research Institute for Complex Problems of Cardiovascular Diseases (Kemerovo, Russia). A bounding box around stenotic segments were set with different areas: small ($<322$ pixels), medium ($322\leq area\leq 962$ pixels), and large ($> 962$ pixels). 
The training and test subset are specified with 7,493 and 832 images, respectively.

A patch-based dataset was generated to evaluate the proposed patch-based approach from ADSD, taking square patches centered on the stenosis bounding box for the positive cases and the 4-connected neighbors around the bounding box as negative cases. During the patch selection, patches smaller than $32 \times 32$ pixels were omitted. 
In this way, the new dataset (P-ADSD) consists of 6,769 positive patches, and 26,699 negative patches were obtained (1:4 unbalanced ratio). Thus, the training subset contains 6,080 positive and 23,986 negative cases, while the test subset has 689 positive and 2,713 negative cases.
Patches were re-sized to $64 \times 64$ to homogenize the image dimensions. 

On the other hand, to deal with the small size of data with the unbalanced ratio of the DSSS, a data augmentation policy was applied, generating four additional images by input image. The policy includes random rotation around $90, 180$, and $270$ degrees, random horizontal flip, random horizontal and vertical shift of $-10\%$ to $10\%$, random zoom-in of $0\%$ to $10\%$, and random brightness change. 
Additionally, a partition of 80:20 was set to split the dataset into training and testing. The data augmentation policy was applicable only in the training and positive subset. 

In this manner, the augmented dataset (A-DSSS), including 430 positive and 1,394 negative stenosis cases was obtained, reducing the unbalanced ratio to 1:3. 

----------

## How to cite

----------

If you use the datasets, please cite the original papers and the current work as:

Deep Stenosis Detection Dataset:

```
@inproceedings{antczak2018stenosis,
  title={{Stenosis Detection with Deep Convolutional Neural Networks}},
  author={Antczak, Karol and Liberadzki, {\L}ukasz},
  booktitle={MATEC Web of Conferences},
  volume={210},
  pages={04001},
  year={2018},
  organization={EDP Sciences},
  doi={10.1051/matecconf/201821004001}
}
```

Angiographic Dataset for Stenosis Detection:

```
@article{danilov2021real,
  title={{Real-time coronary artery stenosis detection based on modern neural networks}},
  author={Danilov, Viacheslav V and Klyshnikov, Kirill Yu and Gerget, Olga M and Kutikhin, Anton G and Ganyukov, Vladimir I and Frangi, Alejandro F and Ovcharenko, Evgeny A},
  journal={Scientific reports},
  volume={11},
  number={1},
  pages={1--13},
  year={2021},
  publisher={Nature Publishing Group},
  doi={10.1038/s41598-021-87174-2}
}
```

```
@misc{DBSTENOSIS2,
    author= {Danilov, Viacheslav and Klyshnikov, Kirill and Kutikhin, Anton and Gerget, Olga and Frangi, Alejandro and Ovcharenko, Evgeny},
    title = {{Angiographic dataset for stenosis detection}},
    doi={10.17632/ydrm75xywg.2},
    month = {Nov},
    year = {2021}
}
```

Augmented Deep Stenosis Detection Dataset and Patched Angiographic Dataset for Stenosis Detection:

```
@article{ovalle2022lrsenet,
	author = {Ovalle-Magallanes, Emmanuel and Avina-Cervantes, Juan Gabriel and Cruz-Aceves, Ivan and Ruiz-Pinales, Jose},
	title = {LRSE-Net: Lightweight Residual Squeeze-and-Excitation Network for stenosis detection in X-ray Coronary Angiography},
	journal = {Electronics},
	volume = {11},
	year = {2022},
	pages={3570},
  	doi={10.3390/electronics11213570},
```

----------

Want to contribute? Great!. Contact us.

Follow our research work at: 
* [Personal Page](https://emmanuelovalle.netlify.app/)
* [Researchgate](https://www.researchgate.net/profile/Emmanuel-Ovalle-Magallanes)
* [Google Academic](https://scholar.google.com/citations?user=zql1lk8AAAAJ&hl=es#)
