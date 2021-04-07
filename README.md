# MaleX

_MaleX_ is a curated dataset of malware and benign Windows executable samples for malware researchers. The dataset contains 1,044,394 Windows executable binaries with 864,669 labelled as malware and 179,725 as benign. This dataset has reasonable number of samples and is sufficient to test data-driven machine learning classification methods and also to measure the performance of the designed models in terms of scalability and adaptability. 

## Malware Visualization in Frequency Domain

The motivation to visualize malware in frequency domain is because of the "sparse" feature representations of malware in literature that are typically extracted from raw bytes of the binaries or disassembled instructions (n-grams, n-perms). 

A given executable binary file is read as a 16-bit signed hexadecimal vector and divided into corresponding bi-grams (n-grams of bytes with n=2). As an example, for the byte-stream _0a1bc48a_, the corresponding bi-grams will be _0a1b_, _1bc4_ and _c48a_. We then use the bi-gram frequency count to get a sparse image of dimensions 256x256 (where each pixel intensity value corresponds to normalized frequency count of a particular bi-gram). The image dimensions is the primary reason for choosing bi-grams (n=2) as it aids image-based machine learning classification with low time complexity in the training phase. Finally, we compute the full frame Discrete Cosine Transform (DCT) of this image to de-sparsify and get a resulting "bigram-dct" image with distinctive textured patterns. Before normalizing frequency count to get the sparse image, we zero out the first frequency count value corresponding to the bi-gram _0000_, as this value is relatively very large compared to that of other bi-grams and the bi-gram either corresponds to empty space or new line(s) in the code with no useful information. The overview of the proposed feature extraction method is shown below.

![Bigram-dct image](figs/overview.png "Visualizing malware as a grayscale image in DCT domain")

```diff
- CODE NOT AVAILABLE FOR RELEASE YET
```

## Comparing Malware Visualization Methods

Previous research has shown that malware variants belonging to the same family exhibit visual similarity in the byteplot images. These are based on visualization of malware binaries in the spatial domain by converting bytes to pixels. The frequency domain-based visualization is another such "orthogonal" depiction of malware binary that is shown (in our [paper](https://arxiv.org/abs/2101.10578)) to aid computer vision algorithms to detect malware. The comparison of the byteplot and "bigram-dct" representations is shown in the figure below.

![Byteplot vs Bigram-DCT](figs/comparison.png "Byteplot vs. Bigram-dct")

## Download Policy

We are not responsible, or liable to you or any third party, for the content or accuracy of any materials provided by us. The release of data is conditioned on accepting the following terms to avoid the dataset being misused. 

-   If you are a student (or postdoc) in academia, please ask your advisor (or host) to fill out the [form](https://mayachitra.com/#contact-us) with subject that starts with [MaleX Request]. If you are a faculty member, please provide university's email account in the form. In your message, please include your name, affiliation, and homepage. The information is needed for verification purpose.
-   If you are in research (industrial) labs, please fill out the [form](https://mayachitra.com/#contact-us) by providing your company's email account with subject that starts with [MaleX Request]. In the message, please briefly introduce yourself (e.g., name and title) and your company. In the form, please attach a justification letter (in PDF format) in official letterhead. The justification letter needs to acknowledge the "MaleX Malware Dataset" from Mayachitra, Inc. and state clearly the reasons why the dataset is being requested.

Please note that, your request will be ignored if you are unable to follow these conditions.

```diff
+ ONLY IMAGES AVAILABLE
- BINARIES NOT AVAILABLE FOR RELEASE YET
```

## Citing

If you use _MaleX_ in your research or wish to refer to the content published here, please use the following BibTeX entry to cite our [paper](https://arxiv.org/abs/2101.10578):

```BibTeX
@inproceedings{mohammedmalware,
  title={Malware Detection Using Frequency Domain-Based Image Visualization and Deep Learning},
  author={Mohammed, Tajuddin Manhar and Nataraj, Lakshmanan and Chikkagoudar, Satish and Chandrasekaran, Shivkumar and Manjunath, BS},
  booktitle={Proceedings of the 54th Hawaii International Conference on System Sciences},
  pages={7132}
}
```

## License

_MaleX_ is released under GPL-3.0 License.

Copyright © 2021 [Mayachitra, Inc.](https://mayachitra.com/)
