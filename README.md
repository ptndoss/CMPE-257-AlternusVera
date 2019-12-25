# CMPE-257-AlternusVera


### Alternus Vera

   A novel approach to detect Fake News using NLP Distillation process. Fake news is now a major concern in every parts of the world. Unauthorized and highly speculative news or information are one of the greatest threats to democracy, journalism, and freedom of expression. It has weakened public trust in governments and its potential impact on the contentious “Brexit” referendum and the equally divisive 2016 U.S. presidential election – which it might have affected [Pogue 2017] – is yet to be realized. The reach of fake news was best highlighted during the critical months of the 2016 U.S. presidential election campaign, where the top twenty frequently-discussed false election stories generated 8,711,000 shares, reactions, and comments on Facebook, ironically, larger than the total of 7,367,000 for the top twenty most-discussed election stories posted by 19 major news websites [Silverman 2016]. 

   The paper presents various techniques used to identify the factors influencing fake news detection and the process of classifying the fakeness factor by using NLP techniques. Various factors are analyzed using set of supervised classification models and vectorized with values based on the document feature. These factors are then weighted on the basis of their accuracy against the category of a report and a polynomial equation made of vectors is defined. The polynomial equation proposed in this paper is (Writing Style) + () + (Event Based) + (Neural Micro-pattern-misinformation) 

### INTRODUCTION

  Fake news gained considerable attention in the 2016 United States election, with both Democrats and Republicans blaming the other for spreading false information. Many in the media and those publicly polled after the election believed the widespread proliferation of fake news helped influence the election's results. [33]. Fake news, or hoax news, refers to false information or propaganda published under the guise of being authentic news. Fake news websites and channels push their fake news content in an attempt to mislead consumers of the content and spread misinformation via social networks and word-of-mouth [33]

  One of the more colorful definitions of fake news comes from PolitiFact: "Fake news is made-up stuff, masterfully manipulated to look like credible journalistic reports that are easily spread online to large audiences willing to believe the fictions and spread the word."

### FAKE NEWS DETECTION

Identifying fake news from the list of news is challenging for humans. Unless if there is a prior known history of fake news patterns there are high chances that fake news can be so convincing to be a real news. We have identified below factors to detect fake news from legitimate ones.

Two broad categories – Human Intent and Flow of text in news.  Human Intent has Toxicity and Trollness where as in Text flow we have Neural Pattern of Mis-info and Event Based text flow.  

![image](https://user-images.githubusercontent.com/34608166/71450528-8c9cb500-2718-11ea-9fee-02c76a395e8d.png)

 
### A.	Neural Micro-Pattern-Mis information

The most effective linguistic analysis method applied to fake news detection is the n-gram approach [1, 2,3]. n-grams are sequences of n contiguous words in a text, constituting words (unigrams) and phrases (bigrams, trigrams) and are widely used in language modeling and text analysis. 

Approach. Mihalcea and Strapparava 2009 proposed the use of n-grams for lie detection. They constructed datasets using crowd-sourcing which constituted statements of people lying about their beliefs on topics such as abortion and death penalty / lying about their feelings on friendship. Mihalcea and Strapparava 2009 wanted to determine how the texts differed and whether n-grams analysis was enough to differentiate lies from the truth. They trained Naive Bayes and Support Vector Machine (SVM) classifiers with inputs being the term frequency vectors of n-grams in the texts, after tokenization and stemming but without stop word removal. Interestingly enough the classification accuracy was about 70% in identifying people’s lies about their beliefs, and 75% in identifying lies about their feelings. A fine-grained analysis of word usage revealed that in all the deceptive texts, connections to the self (“I, friends, self") were lacking and other human-related word classes (“you, other, humans") were dominant, indicative of the speaker’s discomfort in identifying themselves with the lying statements. Also, it was found that words related to “certainty" were dominant in deceptive texts, which is probably explained by the need for the speaker to explicitly use truth-related words as a means to make their false statements more believable [1][2].

I.	What I did?
The summary on the steps followed are

    - Pre-Processing
    - Term Frequency 
    - Stemming
    - Visualization
    - N-Gram Analysis
    - SVM on TF-IDF vector
    - Bayesian on TF-IDF vector 
    - Random Forest on TF-IDF Vector
II.	What did not work?

    -  Count Vectorization of the headline text and applying classification did not yield great accuracy results. 
    -  The classification performed on vectors created by N-Grams of content along stop words(without stop word removal) did not yield         great results. This resulted in 15% accuracy 
III.	 What worked and Alternate Approach

    - The classification performed on vectors created by N-Grams of content after cleaning resulted in boost in accuracy of 23% from 15%. 
   

Observation
1.	Uni-Gram
Some of the top words are common across both the classes like  'state', 'obama','tax' etc.The other top words in real news after excluding the common ones at the very top are 'open', 'question' etc.The other top words in insincere questions after excluding the common ones are 'people’, ‘care', 'new' etc.
 
   ![image](https://user-images.githubusercontent.com/34608166/71450535-9c1bfe00-2718-11ea-807f-a1a44de96cc7.png)


2.	Bi-Gram
After eliminating all the repetitive words from legitimate news there are few interesting bigram words like 'Scott Walker', 'Social Secure’, ‘Ill Immigrant ' appeared only in FAKE NEWS. So, there are high chances that news with Scott Walker, Ill Immigrant, Unemployed Rate are inclined towards FAKE articles.

   ![image](https://user-images.githubusercontent.com/34608166/71450539-ab02b080-2718-11ea-8240-f89e6ed6bc24.png)

 
3.	Tri-Gram
Trigrams with all these words after eliminating president, Obama and Clinton there are interesting words like 'health care law', 'afford care act', 'health care bill'. These words give a higher level of understanding that FAKE news are targeting on new Laws passed by government where there are lot of speculation among people when the law is still being discussed.
 
  ![image](https://user-images.githubusercontent.com/34608166/71450544-c077da80-2718-11ea-8c7d-ffa57a52a241.png)

Distribution of Words and characters among legitimate and fake news
  
  ![image](https://user-images.githubusercontent.com/34608166/71450549-ccfc3300-2718-11ea-8d64-acd1af5746bb.png)

 
1.	Support Vector Machine
A Support Vector Machine (SVM) is a discriminative classifier formally defined by a separating hyperplane. In other words, given labeled training data (supervised learning), the algorithm outputs an optimal hyperplane which categorizes new examples. In two dimentional space this hyperplane is a line dividing a plane in two parts where in each class lay in either side.[31]

With SVM labels are classified to real or fake news. Applying SVM on the TF-IDF vector gives us the result of 76% in classifying the news into categories.
  
  ![image](https://user-images.githubusercontent.com/34608166/71450552-d9808b80-2718-11ea-846e-9c50ee8ca3f9.png)

2.	Naïve Bayes
Naive Bayes is a simple, yet effective and commonly-used, machine learning classifier. It is a probabilistic classifier that makes classifications using the Maximum A Posteriori decision rule in a Bayesian setting. In the context of text classification, where features may be word counts, features may follow a multinomial distribution. In other cases, where features are continuous, they may follow a Gaussian distribution.

Probabilistic distribution of fake and real news are categorized in below confusion matrix. Accuracy being 57%.
  ![image](https://user-images.githubusercontent.com/34608166/71450554-e7cea780-2718-11ea-94d6-565adeb733c4.png)
 

3.	Random Forest 
Random forest is an ensemble model which groups the features in each decision trees and splits out the classes with most votes. A large number of relatively uncorrelated models (trees) operating as a committee will outperform any of the individual constituent models. [33]
In text classification, TF-IDF vectors are used for performing random forest classifier to predict the effective outcome. Accuracy being 35% on using Random forest. 
 
  ![image](https://user-images.githubusercontent.com/34608166/71450555-f4eb9680-2718-11ea-95ab-f7f93cc55099.png)

