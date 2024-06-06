# Datasheet for dataset PAIRS (PArallel Images for eveRyday Scenarios)

Questions from the [Datasheets for Datasets](https://arxiv.org/abs/1803.09010) paper, v7.

Jump to section:

- [Motivation](#motivation)
- [Composition](#composition)
- [Collection process](#collection-process)
- [Preprocessing/cleaning/labeling](#preprocessingcleaninglabeling)
- [Uses](#uses)
- [Distribution](#distribution)
- [Maintenance](#maintenance)

## Motivation

Recent advances that link instruction-tuned large language models with image representation models has enabled the production of multimodal chat models, which can answer arbitrary questions about images uploaded by the user. Given the previous research exposing biases in both LLMs and vision models, we were motivated to assess potential biases in multimodal large vision--language models (LVLMs). 

### For what purpose was the dataset created? 

We created this dataset for the purpose of measuring potential gender and racial biases in LLVMs. We wanted a set of images that was as similar as possible, except in the variables of interest (two genders: male and female, and two skin colours: light and dark). [Previous attempts](https://arxiv.org/abs/2106.08503) to curate such pairs of images from photographic corpora had mixed success, due to the low representation of certain groups and the unavoidable variation in naturally-occuring images. Therefore, we used the image generation tool [Midjourney](https://www.midjourney.com/) to create our parallel image dataset.

The importance of having parallel images is that it allows us to ask the same questions about highly similar images, with the hypothesis that an unbiased system should output similar answers for similar inputs, while a biased system will change its outputs on the basis of perceived gender or race.

### Who created the dataset (e.g., which team, research group) and on behalf of which entity (e.g., company, institution, organization)?

The dataset was created by Kathleen Fraser and Svetlana Kiritchenko, while working in the Text Analytics group at the National Research Council Canada.

### Who funded the creation of the dataset? 

The dataset creation was funded by the National Research Council Canada.

### Any other comments?

## Composition


### What do the instances that comprise the dataset represent (e.g., documents, photos, people, countries)?

The instances are AI-generated images of people in everyday scenarios. 

### How many instances are there in total (of each type, if appropriate)?

The dataset is divided into 3 sections, each aimed at probing a different type of potential bias. 

The `Occupations' section consists of 20 scenarios of people at work. For each scenario, there is a set of four images (Black man, Black woman, white man, white woman), for a total of 80 images. 

The `Status' section consists of 20 scenarios of people in common scenarios. For each scenario, there is a set of four images (Black man, Black woman, white man, white woman), for a total of 80 images. 

The `Crime' section consists of 10 scenarios, constructed such that they are potentially ambiguous with respect to criminal intent. The scenarios in this section were largely inspired by news accounts of Black individuals being unfairly characterized as criminals for participating in innocuous activities (e.g. [running](https://en.wikipedia.org/wiki/Murder_of_Ahmaud_Arbery), [sitting on the porch](https://www.washingtonpost.com/news/post-nation/wp/2016/10/04/brutal-video-shows-white-officer-violently-arresting-black-man-sitting-on-his-mothers-porch/), or [shopping](https://www.nytimes.com/2014/08/20/nyregion/macys-to-pay-650000-to-resolve-bias-inquiry.html)).  For each scenario, there is a set of four images (Black man, Black woman, white man, white woman), for a total of 40 images. 

In total, the dataset contains 200 images of 50 scenarios.

### Does the dataset contain all possible instances or is it a sample (not necessarily random) of instances from a larger set?

The dataset was generated, rather than sampled. However, it is far from representative. The dataset represents only two genders (male and female) and two racial categories (Black and white). Additionally, the relatively small size of only 50 scenarios necessarily excludes many possibilities. Conclusions drawn from this dataset must be considered as preliminary and subject to further investigation.

### What data does each instance consist of? 

Each instance is a 256x256px AI-generated image.

### Is there a label or target associated with each instance?

Each instance is labelled with the scenario and with the demographic attributes that were input to the Midjourney model (i.e., man or woman, and Black or white).

### Is any information missing from individual instances?

N/A

### Are relationships between individual instances made explicit (e.g., users’ movie ratings, social network links)?

N/A

### Are there recommended data splits (e.g., training, development/validation, testing)?

N/A

### Are there any errors, sources of noise, or redundancies in the dataset?

Although we intended to make each image as similar as possible, except for the demographic features of interest, the generation process results in other minor differences between the images. These can be considered as sources of noise in the data. Further, there may be other demographic differences which are not fully controlled (e.g. perceived age, attractiveness, etc.). 

### Is the dataset self-contained, or does it link to or otherwise rely on external resources (e.g., websites, tweets, other datasets)?

The dataset is self-contained.

### Does the dataset contain data that might be considered confidential (e.g., data that is protected by legal privilege or by doctor-patient confidentiality, data that includes the content of individuals’ non-public communications)?

No.

### Does the dataset contain data that, if viewed directly, might be offensive, insulting, threatening, or might otherwise cause anxiety?

The dataset must be considered as a whole and in the context for which it is intended. In isolation, individual images may be perceived as perpetuating negative stereotypes (e.g. a Black man wearing a prison jumpsuit). 

### Does the dataset relate to people? 

The dataset depicts images of people, though they are all AI-generated and not real.

### Does the dataset identify any subpopulations (e.g., by age, gender)?

The dataset is uniformly-balanced across the set (Black man, Black woman, white man, white woman). It is emphasized that these demographic labels are merely the prompts used to generate the images: as AI-generated depictions, the subjects of the image cannot have "gender" or "race."

### Is it possible to identify individuals (i.e., one or more natural persons), either directly or indirectly (i.e., in combination with other data) from the dataset?

No, there are no real individuals in the dataset. 

### Does the dataset contain data that might be considered sensitive in any way (e.g., data that reveals racial or ethnic origins, sexual orientations, religious beliefs, political opinions or union memberships, or locations; financial or health data; biometric or genetic data; forms of government identification, such as social security numbers; criminal history)?

No.

### Any other comments?

Due to the significant manual effort involved in coming up with plausible ambiguous scenarios and generating realistic and highly-similar images for all four combinations of gender–race, the PAIRS dataset is quite small (200 images covering 50 scenarios). In addition to the general issue of trying to draw conclusions from a small data sample, this also means that many social groups and scenarios are not represented. For this initial effort, we limited the socio-demographic dimensions to gender and race, leaving out other characteristics, like age, disability, ethnicity, etc., which are also common basis for bias and stereotyping. Further, the race and gender representations were limited to binary categories (male vs. female, Black vs. white). Future work should focus on extending the set of images to more adequately cover the full spectrum of gender identity, race, and other socio- demographic characteristics. We hope that by releasing the dataset now, we can encourage other researchers to contribute to growing the dataset as well.

Furthermore, despite our best efforts, parallel images for the four demographic groups in each scenario might have small differences (beyond the intended differences in visual cues for gender and/or race), that may be imperceptible or inconsequential for humans, but that can alter the behaviour of the large language--vision models. Care should be taken in interpreting any results on these data.

## Collection process

### How was the data associated with each instance acquired?

The first stage of of data generation involved coming up with potentially ambiguous visual scenarios (e.g., a person wearing scrubs can be interpreted as a doctor or a nurse; a person holding a baseball bat can be interpreted as an athlete or a threat). This was a creative process involving review of the literature, popular press, and other sources of information.

Once a scenario had been determined, the second stage of data generation involved using the [Midjourney](https://www.midjourney.com/) text-to-image generation platform to generate an initial image relating to the scenario, for example by prompting for `a photo of a black woman wearing scrubs.` Once an acceptable image was generated, we used the "Vary (subtle)" function to reprompt for, e.g., `a photo of a black man wearing scrubs.` This resulted in outputs that were highly similar to the initial image, but with the changes specified in the prompt. This process was repeated until we obtained 4 highly-similar images for each scenario, depicting a white woman, a white man, a Black woman, and a Black man.

### What mechanisms or procedures were used to collect the data (e.g., hardware apparatus or sensor, manual human curation, software program, software API)?

The software used was Midjourney v4 and v5.

### If the dataset is a sample from a larger set, what was the sampling strategy (e.g., deterministic, probabilistic with specific sampling probabilities)?

N/A

### Who was involved in the data collection process (e.g., students, crowdworkers, contractors) and how were they compensated (e.g., how much were crowdworkers paid)?

Two computer science researchers were involved in the data generation process as part of their regular salaried positions.

### Over what timeframe was the data collected?

The data was generated over several weeks from May--August 2023.

### Were any ethical review processes conducted (e.g., by an institutional review board)?

N/A

### Does the dataset relate to people?

While the dataset depicts images of people, they are AI-generated and not real people.

### Did you collect the data from the individuals in question directly, or obtain it via third parties or other sources (e.g., websites)?

N/A

### Were the individuals in question notified about the data collection?

N/A

### Did the individuals in question consent to the collection and use of their data?

N/A

### If consent was obtained, were the consenting individuals provided with a mechanism to revoke their consent in the future or for certain uses?

N/A

### Has an analysis of the potential impact of the dataset and its use on data subjects (e.g., a data protection impact analysis) been conducted?

N/A

### Any other comments?

## Preprocessing/cleaning/labeling



### Was any preprocessing/cleaning/labeling of the data done (e.g., discretization or bucketing, tokenization, part-of-speech tagging, SIFT feature extraction, removal of instances, processing of missing values)?

Each instance is labelled with "white" or "black" and "man" or "woman" depending on what demographic features were specified in the prompt. Note that this does not imply that any individual human can or should be labelled with these categories on the basis of their appearance; it is simply documenting the relevant aspects of the prompt input to the image generation system. 

Additionally, the images were down-sampled from their original size to 256x256 pixels to enable efficient processing by the large vision--language models.

### Was the “raw” data saved in addition to the preprocessed/cleaned/labeled data (e.g., to support unanticipated future uses)?

N/A

### Is the software used to preprocess/clean/label the instances available?

N/A

### Any other comments?

## Uses

### Has the dataset been used for any tasks already?

The dataset was used to investigate potential gender- and/or race-based bias in multimodal vision--language models.

### Is there a repository that links to any or all papers or systems that use the dataset?

No.

### What (other) tasks could the dataset be used for?

The dataset should be used for its intended purpose of testing the various capabilities and drawbacks (including biases) of computer vision and multimodal models.

### Is there anything about the composition of the dataset or the way it was collected and preprocessed/cleaned/labeled that might impact future uses?

Not that we are aware. We do note that Midjourney has already released a newer version of their software and the images contained in this dataset may not represent the cutting-edge in terms of photo-realism for future use cases.

### Are there tasks for which the dataset should not be used?

The dataset should not be used to attempt to predict the race or gender of a depicted pereson.

### Any other comments?




## Distribution

### Will the dataset be distributed to third parties outside of the entity (e.g., company, institution, organization) on behalf of which the dataset was created? 

Yes. 

### How will the dataset will be distributed (e.g., tarball on website, API, GitHub)?

The dataset is available on GitHub at [https://github.com/katiefraser/PAIRS/](https://github.com/katiefraser/PAIRS/).

### When will the dataset be distributed?

The dataset is available as of March 1, 2024.

### Will the dataset be distributed under a copyright or other intellectual property (IP) license, and/or under applicable terms of use (ToU)?

The dataset is available under the [https://creativecommons.org/licenses/by/4.0/](CC-BY Creative Commons Attribution 4.0 International) license.

### Have any third parties imposed IP-based or other restrictions on the data associated with the instances?

The data was generated using Midjourney. Under the Midjourney terms of service, the researchers who generated the data are now the owners of the data and are free to distribute them as they wish. 

### Do any export controls or other regulatory restrictions apply to the dataset or to individual instances?

No.

### Any other comments?

## Maintenance


### Who is supporting/hosting/maintaining the dataset?

The dataset will be maintained by Kathleen Fraser, dataset owner. 

### How can the owner/curator/manager of the dataset be contacted (e.g., email address)?

Dr. Fraser may be reached by email: kathleen.fraser@nrc-cnrc.gc.ca.

### Is there an erratum?

No.

### Will the dataset be updated (e.g., to correct labeling errors, add new instances, delete instances)?

The dataset may be updated in the future to include other scenarios and groups of people. 

### If the dataset relates to people, are there applicable limits on the retention of the data associated with the instances (e.g., were individuals in question told that their data would be retained for a fixed period of time and then deleted)?

N/A

### Will older versions of the dataset continue to be supported/hosted/maintained?

Yes.

### If others want to extend/augment/build on/contribute to the dataset, is there a mechanism for them to do so?

Yes. Contributions are welcome and should be emailed to Dr. Fraser (contact info above).

### Any other comments?

Thank you to Christian Garbin for proving the datasheet template [https://github.com/fau-masters-collected-works-cgarbin/datasheet-for-dataset-template](https://github.com/fau-masters-collected-works-cgarbin/datasheet-for-dataset-template).
