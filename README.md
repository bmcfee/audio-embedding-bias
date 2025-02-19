# Bias Correction with Pre-trained Audio Embeddings

Implementation of different bias correction methods for pretrained audio embeddings proposed in the following paper:

Changhong Wang, Gaël Richard, and Brian McFee. "**[Transfer Learning and Bias Correction with Pre-trained Audio Embeddings](https://arxiv.org/abs/2307.10834)**". _Proceedings of the [International Society for Music Information Retrieval (ISMIR) Conference](https://ismir2023.ismir.net/)_, 2023. 

(Ps: deem in `deem.py` is an acronym for "**de**biasing **em**beddings")

## Content

- [Installation](#installation)
- [Datasets](#datasets)
- [Pre-trained embeddings](#pre-trained-embeddings)
- [Bias correction](#bias-correction)
- [Note](#note)
- [Contact](#contact)
- [Cite](#cite)

## Installation
We recommend using Conda environment:

```sh
git clone https://github.com/changhongw/audio-embedding-bias.git
conda env create -f environment.yml
conda activate embedding-bias
```

## Datasets

Download [IRMAS](https://www.upf.edu/web/mtg/irmas) and [OpenMIC](https://zenodo.org/record/1432913) datasets and save in directories `data/irmas` and `data/openmic-2018`, respectively.

## Pre-trained embeddings

Extract [VGGish](https://github.com/tensorflow/models/tree/master/research/audioset/vggish), [OpenL3](https://github.com/marl/openl3), and [YAMNet](https://github.com/tensorflow/models/tree/master/research/audioset/yamnet) embeddings for both datasets. Or use our [extracted pre-trained embeddings](https://zenodo.org/record/8126908) directly.

## Bias correction

Run the note books in `notebooks`:
- `0_data_distribution.ipynb`: investigate the distribution of each dataset in terms of genre distribution and number of samples per class
- `1_debias_linear.ipynb`: linear bias correction (original, LDA, mLDA)
- `2_debias_nonlinear.ipynb`: nonlinear bias correction (K, KLDA, mKLDA)
- `3_cosine_similarity.ipynb`: calculate cosine similarity between dataset separation and instrument classification; check matrix rank for the case of multiple bias correction
- `4_result_summary.ipynb`: summarize results from all bias correction methods

## Note

Thanks to Jayeon Yi, we notice two typos in the paper, i.e. the dimensionality of $W$ and $U$ in Equation (3). We correct them as following:
- $W\in\mathbb{R}^{D\times G}$ -> $W\in\mathbb{R}^{G\times D}$
- $U\in\mathbb{R}^{D\times G}$ -> $U\in\mathbb{R}^{G\times G}$

## Contact

For any questions, support, or inquiries, please feel free to contact [changhong.wang@telecom-paris.fr](mailto:changhong.wang@telecom-paris.fr).

## Cite

Please cite the following paper if you use the code provided in this repository.

 > Changhong Wang, Gaël Richard, and Brian McFee. "Transfer Learning and Bias Correction with Pre-trained Audio Embeddings". _Proceedings of the International Society for Music Information Retrieval (ISMIR) Conference_, 2023. 

```bibtex
@inproceedings{wang2023transfer,
    author = {Changhong Wang and Gaël Richard and Brian McFee},
    title = {Transfer Learning and Bias Correction with Pre-trained Audio Embeddings},
    booktitle = {Proceedings of the International Society for Music Information Retrieval (ISMIR) Conference},
    year = 2023,
}
```
