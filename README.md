# PAIRS
PAIRS (PArallel Images for eveRyday Scenarios)

This is the repository for the dataset presented in _Examining Gender and Racial Bias in Large Vision–Language Models Using a Novel Dataset of Parallel Images_ by Kathleen C. Fraser and Svetlana Kiritchenko (EACL 2024).

## Motivation 

Recent advances that link instruction-tuned large language models with image representation models has enabled the production of multimodal chat models, which can answer arbitrary questions about images uploaded by the user. Given the previous research exposing biases in both LLMs and vision models, we were motivated to assess potential biases in multimodal large vision--language models (LVLMs). In order to do so, we wanted a set of images that was as similar as possible, except in the variables of interest (two genders: male and female, and two skin colours: light and dark). Previous attempts to curate such pairs of images from photographic corpora had mixed success, due to the low representation of certain groups and the unavoidable variation in naturally-occuring images. Therefore, we used the image generation tool [Midjourney](https://www.midjourney.com/) to create our parallel image dataset.

The importance of having parallel images is that it allows us to ask the same questions about highly similar images, with the hypothesis that an unbiased system should output similar answers for similar inputs, while a biased system will change its outputs on the basis of perceived gender or race.

Example: 

## Dataset Description 

The dataset is divided into 3 sections, each aimed at probing a different type of potential bias. 

The *Occupations* section consists of 20 scenarios of people at work. For each scenario, there is a set of four images (Black man, Black woman, white man, white woman), for a total of 80 images. 

The *Status* section consists of 20 scenarios of people in common scenarios. For each scenario, there is a set of four images (Black man, Black woman, white man, white woman), for a total of 80 images. 

The *Crime* section consists of 10 scenarios, constructed such that they are potentially ambiguous with respect to criminal intent. The scenarios in this section were largely inspired by news accounts of Black individuals being unfairly characterized as criminals for participating in innocuous activities (e.g. [running](https://en.wikipedia.org/wiki/Murder_of_Ahmaud_Arbery), [sitting on the porch](https://www.washingtonpost.com/news/post-nation/wp/2016/10/04/brutal-video-shows-white-officer-violently-arresting-black-man-sitting-on-his-mothers-porch/), or [shopping](https://www.nytimes.com/2014/08/20/nyregion/macys-to-pay-650000-to-resolve-bias-inquiry.html)).  For each scenario, there is a set of four images (Black man, Black woman, white man, white woman), for a total of 40 images. 

Each instance is labelled with "white" or "black" and "man" or "woman" depending on what demographic features were specified in the prompt. Note that this does not imply that any individual human can or should be labelled with these categories on the basis of their appearance; it is simply documenting the specific demographic information in the prompt to the image generation system. 

Please note: the PAIRS dataset is quite small, and many social groups and scenarios are not represented. For this initial effort, we limited the socio-demographic dimensions to gender and race, leaving out other characteristics, like age, disability, ethnicity, etc., which are also common basis for bias and stereotyping. Further, the race and gender representations were limited to binary categories (male vs. female, Black vs. white). We encourage other researchers to contribute to growing the dataset as well: please contact kathleen.fraser@nrc-cnrc.gc.ca if you would like to contribute data to the dataset.

Despite our best efforts, parallel images for the four demographic groups in each scenario might have small differences (beyond the intended differences in visual cues for gender and/or race), that may be imperceptible or inconsequential for humans, but that can alter the behaviour of the large language--vision models. Care should be taken in interpreting any results on these data.

## Usage 

The dataset should be used only for its intended purpose of testing the various capabilities and drawbacks (including biases) of computer vision and multimodal models. Please see the [Datasheet](https://github.com/katiefraser/PAIRS/blob/main/Data%20Sheet.md) for more information about intended use.


## Contact 

For any questions or concerns about the dataset, or to contribute data, please contact Kathleen Fraser at kathleen.fraser@nrc-cnrc.gc.ca.

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

