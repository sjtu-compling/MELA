# MELA: Multilingual Evaluation of Linguistic Acceptability

This repository contains data for the MELA (Multilingual Evaluation of Linguistic Acceptability) benchmark. 

**Note that to prevent data contamination, we put the data in a zip file with the password: 200240.**

## Description

MELA contains 46k acceptable and unacceptable sentences from 10 languages: English, Chinese, Italian, Russian, German, French, Spanish, Japanese, Arabic, and Icelandic. 
Sentences in English, Italian, Russian, and Chinese are consolidated from previous works, which are refered to as *high-resource* languages. 
Samples in other languages (i.e., *low-resource* languages) are sourced from renounced linguistics publications such as syntax textbooks and journal articles. 
In our [paper](https://arxiv.org/abs/2311.09033), we showcase three potential usages of MELA: 
- Benchmarking LLMs
- Cross-lingual transfer
- Syntax acquisition

Here are example sentences from MELA:

![MELAexamples](figures/table1.png)

## Data

**Note that we have two versions of data splits: 1) ``data/v1.0``, and 2) ``data/v1.1``. Differences lie in *low-resource* language (see prompt in ``prompts.txt``).**

- ``data/v1.0``: We used this version to fine-tune XLM-R, we had to keep a training set of 500 samples for each *low-resource* language. 

- ``data/v1.1``: To better evaluate LLMs, we re-split the data and only keep 100 samples as development set for 6 *low-resource* languages. 
Thus, more data can be utilized to evaluate LLMs. 

![MELA Data Splits](figures/MELA_results.jpg)


## Benchmarking results 

We list the results of several multilingual LLMs (evaluated on ``v1.1``) along with fine-tuned XLM-R (evaluated on ``v1.0``).
Following previous works in linguistic acceptability, we use MCC as the evaluation metric.

![Benchmarking results](figures/benchmark_results.jpg)

## Cross-lingual transfer results

To observe the transfer of acceptability judgements across languages, we train the model on one language, and evaluate it on all 10 development sets.

![Cross-lingual transfer results](figures/crosslingual_results.jpg)

## Probing results

We train probing classifiers using span representations from XLM-Rs on English probing tasks, including 1) part-of-speech tagging, 2) dependency labeling, 3) constituency labeling, 4) named entity labeling, 5) semantic role labeling, and 6) co-reference.

![Probing results](figures/probing_results.jpg)

## Contributors

Ziyin Zhang, Yikang Liu, Weifang Huang, Junyu Mao, Rui Wang, Hai Hu

## Citation

If you use our dataset, please cite us plus all other corpora of linguistic acceptability used in MELA (see ``citations.bib`` file).

```
@misc{Zhang2023MELA,
      title={MELA: Multilingual Evaluation of Linguistic Acceptability}, 
      author={Ziyin Zhang and Yikang Liu and Weifang Huang and Junyu Mao and Rui Wang and Hai Hu},
      year={2023},
      eprint={2311.09033},
      archivePrefix={arXiv},
      primaryClass={cs.CL}
}
```

