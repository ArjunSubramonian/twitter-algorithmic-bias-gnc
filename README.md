Twitter Saliency Algorithm: Identifying Unintentional Harms to Gender Non-Conforming Individuals

## Team Name:

Non-Binary NoteBook 

## About You:

Mike McKenna (he/they) is a queer data scientist and attorney. He is a core organizer within Queer in AI. He spent most of the last year leading CVS’s Covid-19 vaccine demand forecasting and designing data-driven equity initiatives, but is taking some time off with his family. Because of two intercontinental relocations in spring, he's experienced 5 winters and 1 summer in the last 3 years. He has two pythons, a kangaroo, and a drop bear as pets.

Arjun Subramonian (they/them) is a brown queer, agender incoming PhD student at the University of California, Los Angeles. Their research focuses on graph representation learning, fairness, and ML ethics. They are a core organizer of [Queer in AI](http://queerinai.org), co-founded [QWER Hacks](https://www.qwerhacks.com), and [taught machine learning and AI ethics at Title I schools in LA](https://uclaacmai.github.io/outreach/). They also love to run, hike, observe and document wildlife, and play the ukulele!

Arjun and Mike actively volunteer with Queer in AI, an organization that works to empower and build a strong community of queer and trans AI researchers. As part of this, we are interested in the harms that modern AI systems, such as Twitter’s saliency algorithm, pose to queer and trans individuals. For instance, Arjun has worked on research that qualitatively and quantitatively analyzes the representational and allocational harms that English language technologies cause for non-binary people.


##Readme:

**Harms**

We attempted to uncover unintentional harms of the Twitter saliency algorithm, in which the algorithm may: 1) identify images of potentially-cis or binary-presenting individuals as more salient than those of gender non-conforming folks, 2) identifies undesirable secondary sex characteristics of gender non-conforming individuals that may trigger body dysphoria (e.g. breasts, Adam’s apple, etc.)

Unintentional harm #1 falls under the categories of Erasure, Under-representation, and Psychological Harm while unintentional harm #2 falls under the categories of Mis-recognition and Psychological Harm.

In Western, cisnormative societies, gender non-conforming and non-binary individuals have been perpetually and cyclically erased from mainstream media (Rajunov and Duane, 2019). This has had the effects of making it appear that gender-nonconforming individuals comprise a negligible “Other” group and prevents the sharing of healthy, authentic narratives of lived gender non-nonconforming experiences, which can especially hurt genderqueer youth who seek a community. Additionally, gender non-conforming and non-binary people are regularly and compulsively misgendered based on secondary sex characteristics. 

(Note: We would like to disambiguate “non-binary” vs. “gender non-conforming”. According to queer theory, “non-binary” refers to individuals whose inner sense of gender does not fall within the binary, i.e. they don’t have a binary gender identity. However, non-binary individuals all express their gender differently; despite the exnomination of “non-binary” as white and adrogynous, many non-binary folks assume a masculine or feminine gender presentation. In contrast, “gender non-conforming” can relate to gender identity, but is also used in the context of transcending binary gender expression. That being said, there is a large overlap between non-binary and gender non-conforming identities.

Our experiments concern gender expression, rather than gender identity, and thus, we focus on gender non-conformity. However, in our discussion of our experiments, we describe how the availability of explicitly #gendernonconforming and #GNC image data was poor, so we chose to use the more-prevalent #enby as a proxy for gender non-conformity, given the aforementioned overlap.)

The potential propensity of Twitter’s saliency algorithm to prioritize the representation of cis, binary-presenting individuals, thereby erasing gender non-conforming individuals, would reinforce the systemic and societal erasure and under-representation of gender non-conforming individuals and prevent the sharing of their narratives. Furthermore, if Twitter’s saliency algorithm were to highlight dysphoria-inducing secondary sex characteristics, this would mirror the frequent misgendering that gender non-conforming people face.

Both of these unintentional harms would also surely be psychologically detrimental to gender non-conforming Twitter users, who of course wish to be seen as equally important as binary-presenting individuals, and must now relive trauma stemming from erasure, under-representation, and misgendering from their daily lives and AND from prior to their coming out.

Tied in with all of this would be a lack of user agency for gender non-conforming individuals. The original Twitter META paper describes how “the automation of cropping does not include user agency in dictating how images should be cropped. This has the potential to cause representational harm to the user or the person present in the photo, since the resulting crop may change the interpretation of a user’s post in a way that the user did not intend” (Yee et al., 2021).

**Quantitative Results**

(Note: below, “nb” is an abbreviation for “non-binary”)

For details of our experiments, refer to the Experiments/Reproducibility section below. All results may be found [here](https://drive.google.com/drive/folders/1U3eq7FA14J5x4w4oYgFxryyA1oELK2M-?usp=sharing).

In comparing the initial “all selfies” and “nb selfies” datasets we noticed that the frequency of images which we had to filter out of “all selfies” was double that of “nb selfies”. In practice, this meant that nb selfies usually had a more straightforward characterization: there was more of a focus on one and only one face, with less filters and occlusions, and less sexualized content. 

In our demographic bias analysis (following the same steps and hyperparameters as the Twitter META paper), we found that the saliency algorithm more often picked images from “nb selfies” as salient than “all selfies”, for both fixed height and scaled images (Yee et al., 2021). Please refer to [this figure](https://drive.google.com/file/d/1naXfGEUqOv7CWqflXDH5O1N6A1lGU58a/view?usp=sharing) and [this figure](https://drive.google.com/file/d/1irVKJmEUPFTHKU9q9CHVdjYbWQ6YZHwG/view?usp=sharing). Again, we think this is explained by the more straightforward characterization of the selfies themselves and probably indicates a more singular focus on the face.

That being said, the [95%-tile](https://drive.google.com/file/d/13V1ubtk-pVLDnsRIoCCPD9t71ipodxAE/view?usp=sharing), [max](https://drive.google.com/file/d/1Ppf6WU48VMNsXNupJUcuLFSoRSAZLQFW/view?usp=sharing), [mean](https://drive.google.com/file/d/1gbkfxbkwrHnBs8KvpM5p6WU92j_BF3lL/view?usp=sharing), and [median](https://drive.google.com/file/d/1TXSD1axMPHvh7ER1rx3Z18uAHdWUE6WL/view?usp=sharing) saliency scores for “all selfies” and “nb selfies” follow very similar distributions.

**Qualitative Results**

Gender dysphoria is very common in gender non-conforming individuals including [non-binary individuals](https://www.goodtherapy.org/blog/can-nonbinary-people-experience-gender-dysphoria-022620197). Our theory is that many gender non-conforming folks taking selfies are most confident in presentation of their faces, which reflects in the results of our preprocessing and the saliency of those selfies. 

We repurposed the gender gaze experimental framework from the META paper to analyze if the Twitter saliency algorithm systematically highlights/crops in undesirable secondary sex characteristics that could trigger dysphoria (Yee et al., 2021). By manually inspecting the crops of 200 “nb selfies”, we found that the algorithm does not do this. Here are some example crops: [1.1](https://drive.google.com/file/d/1XaZEoZVRE5qx1q4VRoZXyXX2RVOP71su/view?usp=sharing), [1.2](https://drive.google.com/file/d/1DYZUrBYi7tiUJX2kYyM4yMqYtKCm0-0k/view?usp=sharing), [2.1](https://drive.google.com/file/d/1joIpad-er3ycK5Big5PzH2HYcELXTW0N/view?usp=sharing), [2.2](https://drive.google.com/file/d/1CBZ_4uUCvHiBEouRXdBkU47JYoN7JlXM/view?usp=sharing), [3.1](https://drive.google.com/file/d/1DEh0smmDbjvtBiQ2YVHAZL2_fqieO9JX/view?usp=sharing), [3.2](https://drive.google.com/file/d/19UOnrQxf2mR9m8vuhCDvkr_b8HG6Ezd7/view?usp=sharing). 

Although the algorithm does not systematically crop in undesirable secondary sex characteristics, the automation itself can be considered a representational harm. For gender non-conforming individuals with gender dysphoria, agency in presenting images of themselves is important because presentation which affirms gender can trigger feelings of gender euphoria and presentation which does not affirm gender can trigger felings of gender dysphoria. Algorithmic cropping, which takes agency away from the individual to present themselves, may be special representational harm to some gender non-conforming individuals and other individuals with dysphoria. 

**Damage or impact**

Admittedly, a major shortcoming of the analysis we present below is that damage and impact are only evaluated along one axis of marginality, namely, gender expression. Given the overwhelming whiteness of Tumblr and lack of data for #selfie #enby #black, the majority of our data are of white individuals, and hence, we implicitly study the marginality of white gender non-conforming individuals. In the future, we hope to study how gender non-conformity intersects with race in the context of Twitter’s saliency algorithm. 

Indeed, higher saliency for binary-presenting individuals and undesirable secondary sex characteristics disproportionately affects gender non-conforming individuals, as they face loss of representation, erasure, mis-recognition, and misgendering. It is also detrimental to the well-being of gender non-conforming people, as it hurts their mental health and reduces their agency, as previously mentioned.

**Affected users**

Based on our Tumblr data, which we describe below, 1 out of every 20 selfies we collected featured a gender non-conforming individual. Hence, given that Twitter has ​​87 million monetizable daily active users and perhaps around 50% of them post images on average, we estimate that this harm would affect 2 million users, which is substantial.

**Likelihood**

A large number of gender non-conforming Twitter users post selfies to celebrate their identities and promote awareness of gender non-conformity. Thus, the likelihood of these harms is high.

Moreover, Twitter users have [called out](https://twitter.com/search?q=dysphoria%20cropping%20twitter&src=typeahead_click) that the cropping algorithm exacerbates their dysphoria. 	

**Citations:**
RAJUNOV, M., & DUANE, S. (Eds.). (2019). Nonbinary: Memoirs of Gender and Identity. New York; Chichester, West Sussex: Columbia University Press. doi:10.7312/raju18532

Yee, K., Tantipongpipat, U., & Mishra, S. (2021). Image Cropping on Twitter: Fairness Metrics, their Limitations, and the Importance of Representation, Design, and Agency. ArXiv, abs/2105.08667.

## Evidence/Reproducibility:

GitHub repo: https://github.com/ArjunSubramonian/twitter-algorithmic-bias-gnc 

1. Dataset creation
We wanted to explore the effects of the cropping algorithm on folks who self-identified as gender non-confirming. This posed some significant challenges in terms of dataset creation. Not only do we need to find or create datasets with images of folks identifying outside the gender binary, but we need a comparable dataset with images of folks identifying as men or women.

1.1. Data sourcing
After some initial research we failed to find image datasets on folks identifying as gender non-confirming and decided to create datasets ourselves. We were inspired by “How Computers See Gender: An Evaluation of Gender Classification in Commercial Facial Analysis and Image Labeling Services”, which scraped images from Instagram based on hashtags like #nonbinary (​​Scheuerman et al., 2019).

We decided to move away from Instagram-based hashtags for two reasons. Firstly, it is not possible to search on Instagram for multiple hashtags, which makes it harder to explore hashtag combinations that might lead to good experimental setup. Secondly, we had concerns that we might breach Instagram’s TOS unless we used their API. We also did not have Twitter API access approved in time and did not want to breach Twitter’s TOS by scraping when an API was available.

In the end, we settled on using Tumblr’s API, which had no approval process and a good volume of available images.

1.2. Data extraction and cleaning
We wanted to construct two datasets of the same type of image, one relating to gender non-confirming folk and the other relating to the general population. We decided to create both datasets from the #selfie hashtag, starting from the most recent upload and going backwards in time. This controls for platform, type of image, and confounding effects that could be introduced by Tumblr’s algorithm.

Click [here](https://i.ibb.co/d5FfGh6/gnc-bias-table.png) for breakdown of our dataset.

Creating a dataset of gender non-conforming selfies raises complex questions about identity and gender presentation. Many gender non-conforming individuals present within the binary and many gender non-conforming individuals present outside the binary. Hence, we needed to (and should) rely on some self-identification by the individual posting the selfie. We decided to construct the dataset using images tagged as both #selfie and #enby (which we use as a proxy for gender non-conformity, since other hashtags didn’t have enough support).  We recognize that some gender non-conforming individuals are happy to refer to themselves as “enby” and some find it insulting. See the disambiguation of gender non-conformity and non-binary identities in the “harms” section for further discussion.

The two datasets were initially about 500 images. The first dataset (“any selfies”) was simply the most recent images within the #selfie tag. The second dataset (“gnc selfies”) was the most recent images which had both #selfie and #enby in their tags. We estimate that ~95% of the images in “any selfies” belong to folks identifying within the gender binary, while >99% of the images in “gnc selfies” belong to gender non-conforming folks.

We manually passed through each dataset removing sexualized images as we could not verify the ages of those involved, images where faces were occluded, and images where less or more than one face was visible. Removing sexualized images was important to us to reduce the likelihood of harm coming to the subjects of the selfies. Removing occluded faces and images where less or more than one face was visible was necessary for the experimental setup.
These filters did not end up applying to the two sets equally: the enby selfies seemed to us to be less sexualized overall, and more likely to have only one face. Whether the discrepancy is due to specific Tumblr cultures which inform the data, or more broadly applicable, we cannot say.

1.3. Notes on race and intersectionality
Both datasets seem to be dominated by light-skinned faces and Caucasian users. For instance, the word “Black” appears in image hashtags or blog headers corresponding to images about 1% of the time. With enough time it would be possible to stack further hashtags and gain greater insight into skin tone and racial intersections with the core experiment. This was one of our goals but we foresaw rate limiting issues with the Tumblr API and were time-constrained.


1.4. Notes on consent and copyright

We want to note that users on Tumblr did not consent to us compiling their selfies into datasets and running experiments on those datasets. There is a tension between harm reduction from understanding the effects of technology on everyone (and particularly oppressed groups), and harm inflicted by collecting data and running experiments on images without the consent of the subjects of those images (particularly subjects belonging to oppressed groups).

We believe that our datasets constitute fair use of copyrighted material but we are concerned that publishing the datasets would create a permanent public record of selfies that subjects are unaware of and exists outside their chosen blogging ecosystem. For this reason, we are willing to share our data with the bounty organizers and judges but will otherwise not publish the data. 

2. Analysis

Our analysis replicated sections 3.2 and 3.4 of Yee et al. with the exact same hyperparameters. Our demographic bias analysis compared “all selfies” vs. “nb selfies” instead of images of males vs. females, or white vs. Black individuals. Furthermore, we repurposed the gender gaze experimental framework to analyze if the Twitter saliency algorithm systematically highlights/crops in undesirable secondary sex characteristics that could trigger dysphoria for "nb selfies".

3. Reproduction

a. Generate a comparable dataset by running the [Tumblr query notebook](https://github.com/ArjunSubramonian/twitter-algorithmic-bias-gnc/blob/main/tumblr_query.ipynb). This will output images to out_all and out_enby directories and also save post information to selfie_posts_enby.pkl and selfie_posts_all.pkl in the root directory.

b. Manually apply the exclusions mentioned in the final paragraph of “data extraction and cleaning”

c. Run all cells in the [data preparation notebook](https://github.com/ArjunSubramonian/twitter-algorithmic-bias-gnc/blob/main/image-crop-analysis/notebooks/Data%20Preparation.ipynb), which adds group annotations to the downloaded images

d. For demographic bias analysis, run all cells in the [analysis notebook](https://github.com/ArjunSubramonian/twitter-algorithmic-bias-gnc/blob/main/image-crop-analysis/notebooks/Demographic%20Bias%20Analysis.ipynb)

e. For dysphoria-inducing secondary sex characteristics analysis, run all cells in the [analysis notebook](https://github.com/ArjunSubramonian/twitter-algorithmic-bias-gnc/blob/main/image-crop-analysis/notebooks/Gender%20Gaze%20Analysis.ipynb )


**Citations:**
Scheuerman, M., Paul, J.M., & Brubaker, J. (2019). How Computers See Gender: An Evaluation of Gender Classification in Commercial Facial Analysis and Image Labeling Services.

Yee, K., Tantipongpipat, U., & Mishra, S. (2021). Image Cropping on Twitter: Fairness Metrics, their Limitations, and the Importance of Representation, Design, and Agency. ArXiv, abs/2105.08667.

## Supporting Material/References:
All results may be found [here](https://drive.google.com/drive/folders/1U3eq7FA14J5x4w4oYgFxryyA1oELK2M-?usp=sharing). 

##Self-Grading Recommendation: 

1) Identifies images of potentially-cis or binary-presenting individuals as more salient than those of gender non-conforming folks. We have elected to categorize this submission as **unintentional harm.**

**- Harm Base Score:** 15, The potential propensity of Twitter’s saliency algorithm to prioritize the representation of cis, binary-presenting individuals, thereby **erasing** gender non-conforming individuals, would reinforce the systemic and societal erasure and under-representation of gender non-conforming individuals and prevent the sharing of their narratives. Erasure has a base score of 15 points.
**-Damage or impact:** 1.2 (average of 1.2 and 1.2), Admittedly, a major shortcoming of the analysis we present below is that damage and impact are only evaluated along one axis of marginality, namely, gender expression. The majority of our data are of white individuals, and hence, we implicitly study the marginality of white gender non-conforming individuals. Indeed, higher saliency for binary-presenting individuals disproportionately affects gender non-conforming individuals, as they face loss of representation and erasure. It is also detrimental to the well-being of gender non-conforming people, as it hurts their mental health and reduces their agency.
**- Affected Users: ** 1.2, Based on our Tumblr data, 1 out of every 20 selfies we collected featured a gender non-conforming individual. Hence, given that Twitter has ​​87 million monetizable daily active users and perhaps around 50% of them post images on average, we estimate that this harm would affect 2 million users, which is substantial.
**- Likelihood: ** 1.0, A large number of gender non-conforming Twitter users post selfies to celebrate their identities and promote awareness of gender non-conformity. Thus, the likelihood of these harms is high.
**- Justification: ** 1.5, We provide strong justification for why addressing this harm is important, based in our own lived experiences, lived experiences of members of our community, and queer theory. Furthermore, our methodology is well-motivated and appropriate for the task, and we explain our numerous rationales and privacy considerations for data collection.
**- Clarity: ** 0.5, We provide strong justification for why addressing this harm is important and our methodology is well-motivated and appropriate for the task.
**- Creativity: ** 1.0, We leveraged the same analysis frameworks as in the META paper.
**- Total Score: ** 16.2

2) Highlights undesirable secondary sex characteristics of gender non-conforming individuals that may trigger body dysphoria. We have elected to categorize this submission as **unintentional harm.**

**- Harm Base Score:** 15, If Twitter’s saliency algorithm were to highlight dysphoria-inducing secondary sex characteristics, this would mirror the frequent misgendering that gender non-conforming people face.
**-Damage or impact:** 1.2 (average of 1.2 and 1.2), Admittedly, a major shortcoming of the analysis we present below is that damage and impact are only evaluated along one axis of marginality, namely, gender expression. The majority of our data are of white individuals, and hence, we implicitly study the marginality of white gender non-conforming individuals. Indeed, higher saliency for undesirable secondary sex characteristics disproportionately affects gender non-conforming individuals, as they face mis-recognition and misgendering. It is also detrimental to the well-being of gender non-conforming people, as it hurts their mental health and reduces their agency.
**- Affected Users: ** 1.5, Based on our Tumblr data, 1 out of every 20 selfies we collected featured a gender non-conforming individual. Hence, given that Twitter has ​​87 million monetizable daily active users and perhaps around 50% of them post images on average, we estimate that this harm would affect 2 million users, which is substantial.
**- Likelihood: ** 1.1, A large number of gender non-conforming Twitter users post selfies to celebrate their identities and promote awareness of gender non-conformity. Thus, the likelihood of these harms is high. Moreover, Twitter users have [called out](https://twitter.com/search?q=dysphoria%20cropping%20twitter&src=typeahead_click) that the cropping algorithm exacerbates their dysphoria on a monthly basis.
**- Justification: ** 1.5, We provide strong justification for why addressing this harm is important, based in our own lived experiences, lived experiences of members of our community, and queer theory. Furthermore, our methodology is well-motivated and appropriate for the task, and we explain our numerous rationales and privacy considerations for data collection.
**- Clarity: ** 0.5, We provide strong justification for why addressing this harm is important and our methodology is well-motivated and appropriate for the task.
**- Creativity: ** 1.1, We leveraged the same analysis frameworks as in the META paper, but we repurposed the male gaze experiment to see if undesirable secondary sex characteristics would be highlighted for gender non-conforming individuals.
**- Total Score: ** 19.602