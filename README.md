# Classify Women's Hanfu by Dynasty
### Bayes Machine Learning to classify traditional chinese clothing by time period

In this project I want to work with two things I really like! Probability and Traditional Chinese clothing. I will preprocess my own dataset and perform image compression before I can get to the classification part, which will be supervised learning with Bayesian networks.

Hanfu (汉服) is traditional chinese clothing that has been worn since the 2nd millennium BCE and has a long history of evolution. It's best defined by a robe structure with upper and lower garments, and different accessories.

## Background
Bayes Theorem, a foundational theorem in statistics for conditional probability and a personal favourite of mine, is the engine for this classifier. This is mathematically defined by 

### P(A∣B) = P(B∣A)*P(A)/P(B) 
where

* Posterior Probability P(A∣B) is the updated probability of hypothesis A after observing evidence B
* Likelihood P(B∣A) is the probability of observing evidence B assuming hypothesis A is true.
* Prior Probability P(A) is the initial belief about hypothesis A before observing any evidence.
* Evidence (Marginal Likelihood) P(B) is the total probability of observing evidence B acting as a normalization factor.

For the purpose of this project we will need to use Bayes Theorem for Multiple Hypotheses (n Events):

Let E1, E2,…, En be a set of events associated with the sample space S, in which all the events E1, E2,…, En have a non-zero probability of occurrence. All the events E1, E2,…, E form a partition of S. Let A be an event in space S for which we have to find the probability, then according to Bayes theorem,

### P(Ei|A) = P(Ei)*P(A|Ei)/SUM(P(Ek)*P(A|Ek))

for k = 1, 2, 3, …., n

Below is an outline of hanfu's evolution for Chinese women in history, and what the major eras of clothing are best defined by.

### Qin Han Dynasty (221–206 BCE) (206 BCE–220 CE)
The Qin Han dynasty introduced a unified dress code of robe-based structures, best characterized by:
* Robes with straight or curved hems
* Wide sleeves and large lapels
* Fabric sashes for women
* Gender-neutral silhouettes

<img src="references/qin han.jpg" alt="drawing" height="250"/><img src="references/han.png" alt="drawing" height="250"/><img src="references/han.webp" alt="drawing" height="250"/>

### Wei Jin Dynasty (220–265) (266–420) 
The Wei Jin era is defined by philisophical freedom, shifting to a more elegant and simplistic fashion characterized by:
* Loose tops with wide cuffs
* Minimal embroidery, emphasis on color and drape
* Light, flowing skirts

<img src="references/wei jin.jpg" alt="drawing" height="250"/><img src="references/weijin2.png" alt="drawing" height="250"/><img src="references/weijin.png" alt="drawing" height="250"/>

### Tang Dynasty (618-906)
The Tang Dynasty emphasized prosperity, and openness. Fashion was expressive and bold, characterized by:
* High-waisted skirt sitting above the chest
* Short top (襦) with narrow or small sleeves
* Accessory of a shawl (披帛) or cape
* Luxurious and bold fabrics, floral or geometric prints

<img src="references/tang.jpg" alt="drawing" height="250"/><img src="references/tang2.jpg" alt="drawing" height="250"/><img src="references/tang3.jpg" alt="drawing" height="250"/>


### Song Dynasty (960-1279)
The Song Dynasty sees a big shift to simplicity and practicality, characterized by:
* Beizi: straight-cut overcoat with side slits
* Introduction of (百迭裙) pleated skirt with layered folds
* Gender-neutral clothing
* Grace and elegance

<img src="references/song.png" alt="drawing" height="250"/><img src="references/song2.jpg" alt="drawing" height="250"/><img src="references/song3.jpg" alt="drawing" height="250"/>

### Ming Dynasty (1368-1644)
The Ming Dynasty saw a shift back to traditional styles, characterized by:
* Short upper jacket (袄) with pipa sleeves
* High-waisted pleated skirt (马面裙)
* Floral or animal embroidery
* Rich radiant colors and heavy brocade

<img src="references/ming.jpg" alt="drawing" height="250"/><img src="references/ming.png" alt="drawing" height="250"/><img src="references/ming3.jpg" alt="drawing" height="250"/>



### Qing Dynasty (1644–1911)
The Qing Dynasty, founded by the Northeast saw a change to the traditional cut, defined by:
* Arrow sleeves, short top with robe skirt
* Bold embroidery on bright fabrics
* Straight silhouette, high Pi collars

<img src="references/qing.jpg" alt="drawing" height="250"/><img src="references/qing4.jpg" alt="drawing" height="250"/><img src="references/qing3.jpg" alt="drawing" height="250"/>


## Dataset

For the dataset of this project, I will be collecting my own set of images and labelling each image by dynasty. Specifically full-body images of one person in the frame, facing the front or sides.