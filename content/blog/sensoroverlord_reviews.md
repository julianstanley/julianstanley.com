---
title: "Peer Review: SensorOverlord Paper"
date: '2020-05-20'
draft: false
tags: [
  "peer-review",
  "rejections",
  "papers"
]
---

## Overview and purpose

I would like to keep a record of my submission history and peer review results for each of my first-author papers and grants.

I've heard that the peer review process can be really disheartening for many people, and that it often involves many, many rounds of rejection.

I also appreciate reading peer reviews, and think that they can be helpful to read after reading a published paper. 

So, without further ado, here's my first round of peer reviews. I'll update this page with each round.

## Paper details

Paper: The SensorOverlord predicts the accuracy of measurements with ratiometric biosensors

[biorxiv link](https://www.biorxiv.org/content/10.1101/2020.01.31.928895v1)

## Submissions and reviews

### First submission: Nature Methods

Submission date: 10 February 2020

Result: Desk rejection (12 February 2020)

### Second submission: PLOS Biology

Submission Date: 12 February 2020

Result: Desk rejection (17 February 2020)

### Third submission: BMC Biology

Submission Date: 18 February 2020

Result: Major revisions/rejected (19 May 2020)

#### Decision email

> BMCB-D-20-00169
<br><br>
The SensorOverlord predicts the accuracy of measurements with ratiometric biosensors
Julian A Stanley; Sean B Johnsen; Javier Apfeld, PhD
<br><br>
Dear Dr. Apfeld,
<br><br>
Please accept my apologies for this prolonged review process. Your manuscript has now been seen by referees whose comments are appended at the bottom of this email.
<br><br>
You will see that while the reviewers comment on the interest of the study, they have raised significant issues, in the light of which I must regretfully tell you that we are unable to offer publication in BMC Biology. In particular, Reviewer 1 points out that solvent conditions such as temperature and pH affect the performance of the probes, and this has not been accounted for in the method presented here. This strikes us as a significant issue (and in fact we have received very similar feedback from another reviewer who was unable to submit his/her full review), that would need to be resolved in order to move forward with the paper here.
<br><br>
It might be more productive to submit the manuscript to another journal, however, if you can address the criticisms, which as we see it will require further experiments, we should be happy to see a resubmission.
<br><br>
Should you resubmit, you will need to provide a point-by-point response to the referees' comments, and indicate on your revised manuscript the changes that have been made. Please also be sure to quote the manuscript number of the original submission.
<br><br>
Please don't hesitate to let us know if you have any questions.
<br><br>
Kind regards,
Mirna
<br><br>
Mirna Kvajo, PhD
Editor, BMC Biology

#### Peer Reviews

##### Reviewer #1

>Reviewer #1: I have reviewed the manuscript entitled "The SensorOverlord predicts the accuracy of measurements with ratiometric biosensors" by Julian A. Stanley, Sean B. Johnsen, and Javier Apfeld. This manuscript has a high impact to some extent. The authors described a mathematical method to predict the accuracy and limitation of ratiometric redox sensor. This method can provide us to quantify the improvement in experimental methodologies and the increased accuracy of measurement. The result in Fige 3, section "comparing glutathione redox potential biosensors", is much informative and useful for users and developers. The list of the dynamic range of current probes predicted by the present method provides the probe users the effective information unknown so far. It is also interesting to replace the protein network with the market. The authors are trying to generalize the method. I personally enjoyed to read the manuscript. However, overall, it is too immature to publish in
BMC biology.
<br><br>
The biggest problem is that the authors failed to show the significance of improving the measurement accuracy with this method. roGFPs are based on protonated-deprotonated state transfer. The protonated/deprotonated ratio strongly depends on the solvent condition, such as pH, temperature, and pressure. The experimenter cannot control these parameters in in vivo observations. Therefore, it is more important to accurately acquire the relative value than to accurately acquire the absolute value. Their method is good enough standard to choose the best probe to use in specific condition, but those parameters, at least pH, can change in behaviour of interest. This change causes the measurement error. The method must be extended to multi-parameter, E(GST) and pH dependency. Second, the validity and credibility of this method cannot be evaluated because there is no comparison with the actual measured value. The authors should pick up two or three probes, and investigate the same correlations to ones shown in Fig 1, with adding the various artificial error. While the authors predicted accuracy of pH and ligand-binding biosensors in the manuscript, the simulator on web cannot. I feel that this project is incomplete.
<br><br>
Also, the text is very difficult to read to me, because the chapter and/or subtitle is not properly formed. There is a mix of introduction and discussion in the results section. The authors wrote text about their on-going project in the results section, but it was not the result of this work and should be deleted. Unfortunately, I cannot recommend publishing the manuscript in BMC biology at this time. Again, the content is so interesting that I hope it will be better next time if obtaining additional investigations. Or, I recommend the author to rewrite the manuscript as a methodology paper to publish in the more specific journal: supplementals are informative.

Julian interpretation: Major revisions/reject. The reviewer enjoyed the manuscript, but thought it was too immature to publish in BMC biology. They recommended that we rewrite the manuscript as a methodology paper (although, I think we did submit this as a methodology paper). They do raise valid points: the method we present does not account for differences in pH or other factors (which are significant, but we can't address). They also raise issues in the idea of acquiring absolute values, which I definitely take issue with: other papers already have good rationalate for aquiring absolute values, so maybe we can make that more clear in the introduction.

##### Reviewer #2

> Reviewer #2: In the manuscript, Stanley et al. provided the SensorOverlord tool for the predication of the accuracy of biochemical measurements using genetically encoded ratiometric biosensors. Unlike sensors with single output, these sensors allows quantitative measurements of the analytes not affected by the sensor's concentration, however, the precision of such measurements have not yet been studied systematically.   To this end, the SensorOverlord tool should be quite useful for the evaluation of different radiometric sensors, and helpful for researchers to identify biosensors that suit for specific experimental needs. Overall I think the experiments are well executed and controlled, and the manuscript is well written. I am therefore in favor of the publication of the manuscript on BMC Biology, provided that following minor questions can be addressed satisfactorily.
<br><br>
(1) In addition to imaging, quantitative measurement using ratiometric biosensors can also be performed on microplate readers and flow cytometers. Are the hypothesis and conclusions made by the authors still valid in these measurements? I suggest the authors to extend their scope to applications involving these instruments, which would benefit the readers of different discipline.
<br><br>
(2) As shown in the manuscript, the measurement error is dependent on the relative error in R.  The relative error in R may significantly vary depending on the sensor's in vivo brightness and the instruments' sensitivity. Weak fluorescence ought to markedly deteriorate the accuracy of the sensors measurement. These are very important for practical studies and should be discussed.
<br><br>
(3) The plots of predicted accuracy shown in Fig 3 and Fig 4 are misleading, which only represent the data obtained under the current imaging experimental setting described in the manuscript. Microplate reading and flow cytometry may have higher relative error of R depending on the sensitivity of the instruments. The authors should clearly state and label the relative error of R that they used to calculate the accuracy of measurement in these panels.  Plots of predicted accuracy with larger relative error of R (for example, 5% for flow cytometer or 8% for microplate reader) would be helpful for researchers working with these instruments.

Julian interpretation: minor revisions. This was a super nice and helpful peer review. They make very valid points that we should talk about the application of our framework to in-vitro microplate measurements and mention that the framework assumes empirical precision, which should account for differences in fluorescence.