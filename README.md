# PAIRS
PAIRS (PArallel Images for eveRyday Scenarios)

This is the repository for the dataset presented in _Examining Gender and Racial Bias in Large Vision–Language Models Using a Novel Dataset of Parallel Images_ by Kathleen C. Fraser and Svetlana Kiritchenko (EACL 2024).

## Motivation 

Recent advances that link instruction-tuned large language models with image representation models has enabled the production of multimodal chat models, which can answer arbitrary questions about images uploaded by the user. Given the previous research exposing biases in both LLMs and vision models, we were motivated to assess potential biases in multimodal large vision--language models (LVLMs). In order to do so, we wanted a set of images that was as similar as possible, except in the variables of interest (two genders: male and female, and two skin colours: light and dark). [Previous attempts](https://arxiv.org/abs/2106.08503) to curate such pairs of images from photographic corpora had mixed success, due to the low representation of certain groups and the unavoidable variation in naturally-occuring images. Therefore, we used the image generation tool [Midjourney](https://www.midjourney.com/) to create our parallel image dataset.

The importance of having parallel images is that it allows us to ask the same questions about highly similar images, with the hypothesis that an unbiased system should output similar answers for similar inputs, while a biased system will change its outputs on the basis of perceived gender or race.

Example: 

## Dataset Description 

## Usage 

## Contact 

## Citation

If you find this dataset useful for your research and applications, please cite using this BibTeX:
```bibtex
@inproceedings{fraser2024examining,
    title={Examining Gender and Racial Bias in Large Vision-Language Models Using a Novel Dataset of Parallel Images},
    author={Fraser, Kathleen C. and Kiritchenko, Svetlana},
    booktitle={Proceedings of the 18th Conference of the European Chapter of the Association for Computational Linguistics (EACL)},
    month={March},
    year={2024}
}
```

