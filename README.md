# Multi-Modal Inductive Transfer Learning and Uncertainty-Aware Multi-Modal Ensembling for Detection of Alzheimer’s Dementia and its Severity

> [Multimodal Inductive Transfer Learning for Detection of Alzheimer’s Dementia and its Severity](https://arxiv.org/abs/2009.00700)

> Utkarsh Sarawgi\*, Wazeer Zulfikar\*, Nouran Soliman, Pattie Maes  
> To appear in INTERSPEECH 2020 

> [Uncertainty-Aware Multi-Modal Ensembling for Severity Prediction of Alzheimer's Dementia](https://arxiv.org/abs/2010.01440)

> Utkarsh Sarawgi\*, Wazeer Zulfikar\*, Rishab Khincha, Pattie Maes 

This work was also submitted to the [Alzheimer's Dementia Recognition through Spontaneous Speech (ADReSS) challenge](http://www.homepages.ed.ac.uk/sluzfil/ADReSS/)

## Abstract

Alzheimer's disease is estimated to affect around 50 million people worldwide and is rising rapidly, with a global economic burden of nearly a trillion dollars. This calls for scalable, cost-effective, and robust methods for detection of Alzheimer's dementia (AD). We present a novel architecture that leverages acoustic, cognitive, and linguistic features to form a multimodal ensemble system. It uses specialized artificial neural networks with temporal characteristics to detect AD and its severity, which is reflected through Mini-Mental State Exam (MMSE) scores. We first evaluate it on the ADReSS challenge dataset, which is a subject-independent and balanced dataset matched for age and gender to mitigate biases, and is available through DementiaBank. Our system achieves state-of-the-art test accuracy, precision, recall, and F1-score of 83.3\% each for AD classification, and state-of-the-art test root mean squared error (RMSE) of 4.60 for MMSE score regression. To the best of our knowledge, the system further achieves state-of-the-art AD classification accuracy of 88.0\% when evaluated on the full benchmark DementiaBank Pitt database. Our work highlights the applicability and transferability of spontaneous speech to produce a robust inductive transfer learning model, and demonstrates generalizability through a task-agnostic feature-space.

## Highlights

- **Simple:** Fast and elegant models which when ensembled produces competitive results in multiple tasks

- **Multimodal:** Uses Disfluency, Acoustic, and Inter-vention features with voting for a robust model

- **Strong:** Our ensemble model achieves _83.3\%_ classification accuracy and _4.60_ rmse for MMSE score regression in ADReSS

- **Robust:** Balanced dataset for gender and age by ADReSS ensures rigid testing

## Main Results

### ADReSS

### Test Set

| Model                 | Accuracy | Precision | Recall | F1-Score | RMSE (MMSE\*)|
|-----------------------|----------|-----------|--------|----------|--------------|
| Luz et al.            | 0.75     | **0.83**      | 0.62   | 0.71     | 5.21         |
| Sarawgi et al. (_ours_) | **0.83**     | **0.83**     | **0.83**   | **0.83**     | **4.60**         |

### LOSO (LOOCV) on dataset

| Model                 | Accuracy | Precision | Recall | F1-Score | RMSE (MMSE\*)|
|-----------------------|----------|-----------|--------|----------|--------------|
| Luz et al.            | 0.77     |  0.77     | 0.76   | 0.77     | 4.38         |
| Sarawgi et al. (_ours_) | **0.99**     | **0.99**     | **1.0**   | **0.99**     | **0.82**         |

_\* Mini Mental State Exam scores_

### Full DementiaBank Corpus

| Model                 | Accuracy | Precision | Recall | F1-Score |
|-----------------------|----------|-----------|--------|----------|
| Fraser et al.         | 0.82     | -         | -      | -        |
| Masrani               | 0.85     | -         | -      | 0.85     |
| Kong et al.           | 0.87     | 0.86      | **0.91**   | **0.88**     |
| Sarawgi et al. (_ours_) | **0.88**     | **0.92**      | 0.82   | **0.88**     |

*Above results for DementiaBank are using 10 fold cross validation*

### Individual modal performance on ADReSS dataset

![roc](https://github.com/wazeerzulfikar/ad-mmse/blob/master/img/roc.png)

## Usage 

### Dataset Download

Request access from [DementiaBank](https://dementia.talkbank.org/)

### Setup

1. Install dependencies using `pip install -r requirements.txt`
2. Install and setup OpenSmile for Compare features extraction following [COMPARE.md](https://github.com/wazeerzulfikar/ad-mmse/blob/master/COMPARE.md)
3. Extract compare features

### Run

Set config parameters in `config.py` and run `python main.py`

### Model Architecture
We use an Ensemble model of (1) Disfluency, (2) Acoustic, and (3) Inter-ventions models for AD classification.
Then (4) Regression module is added at the top of the Ensemble for MMSE regression.

![model architecture](https://github.com/wazeerzulfikar/ad-mmse/blob/master/img/model_final.jpeg)

## License

This code is released under the MIT License (refer to the [LICENSE](https://github.com/wazeerzulfikar/ad-mmse/blob/master/LICENSE) for details).

## Citation

If you find this project useful for your research, please use the following BibTeX entries.

    @article{sarawgi2020multimodal,
      title={Multimodal Inductive Transfer Learning for Detection of Alzheimer's Dementia and its Severity},
      author={Sarawgi, Utkarsh and Zulfikar, Wazeer and Soliman, Nouran and Maes, Pattie},
      journal={arXiv preprint arXiv:2009.00700},
      year={2020}
    }
    
    @misc{sarawgi2020uncertaintyaware,
      title={Uncertainty-Aware Multi-Modal Ensembling for Severity Prediction of Alzheimer's Dementia}, 
      author={Utkarsh Sarawgi and Wazeer Zulfikar and Rishab Khincha and Pattie Maes},
      year={2020},
      eprint={2010.01440},
      archivePrefix={arXiv},
      primaryClass={cs.LG}
    }
