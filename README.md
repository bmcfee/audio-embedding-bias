# Eembedding Bias Correction

## Preparation

### Intall requirements
`git clone https://github.com/changhongw/examod.git`
`conda env create -f environment.yml`
`conda activate embedding-bis-correction`

### Download dataset
[IRMAS](https://www.upf.edu/web/mtg/irmas) dataset and [OpenMIC](https://zenodo.org/record/1432913) dataset

### Pre-trained embedding extraction
[VGGish](https://github.com/tensorflow/models/tree/master/research/audioset/vggish), [OpenL3](https://github.com/marl/openl3), and [YAMNet](https://github.com/tensorflow/models/tree/master/research/audioset/yamnet) 

## Bias correction
Run the note books in `scripts`:
- `0_data_distribute.ipynb`: investigate the distribution of each dataset
- `1_debias_linear.ipynb`: linear bias correction (original, LDA, mLDA)
- `2_debias_nonlinear.ipynb`: linear bias correction (K, KLDA, mKLDA)
- `3_cosine_similarity.ipynb`: calculate cosine similarity between dataset separation and instrument classification
- `4_performance_change_linear.ipynb`: anlayze results for linear case
- `4_performance_change_nonlinear.ipynb`: anlayze results for nonlinear case

## Cite
Changhong Wang, Brian McFee, and Gaël Richard. "Transfer Learning and Bias Correction with Pre-trained Audio Embeddings". International Society for Music Information Retrieval (ISMIR) conference, 2023.
