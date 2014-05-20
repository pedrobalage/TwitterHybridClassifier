TwitterHybridClassifier
=======================

- Authors: Pedro Paulo Balage Filho and Lucas Avanço
- Version: 2.0
- Date: 01/05/14

These python scripts provide the HybridClassifier I used for the Semeval 2014 Task9 - Twitter Classification - Track B (http://alt.qcri.org/semeval2014/task9/)

You can reproduce my results or freely adapt my code for your experiments. My code is licensed under GPL version 2.0. (See LISENCE file for details)

In order to run this code, you must have a python 2.7 or a python 3.4 versions and the following libraries:

- Natural Language Toolkit (NLTK - http://www.nltk.org/)
- scikit-learn (Machine Learning in Python - http://scikit-learn.org/stable/)

In debian/ubuntu, you may install these libraries for python 2.7 (usually the default) using these commands:

```shell
sudo apt-get install python-nltk python-sklearn python-pip python-setuptools
sudo pip install -U setuptools scikit-learn nltk
```

Or, alternatively, if you are enthusiast of python3.x, install the libraries using these commands

```sh
sudo apt-get install python3-pip python3-setuptools
sudo pip3 install -U setuptools
sudo pip3 install git+https://github.com/scikit-learn/scikit-learn.git
sudo pip3 install git+https://github.com/nltk/nltk.git
```

I also use ark_twitter_nlp as the Part-of-Speech tagger. This is included in the source code. Due the Ark Twitter NLP GPL license, I also used this license for this code.

The lexicon this library uses are:

1. NRC Hashtag Sentiment Lexicon
http://www.umiacs.umd.edu/~saif/WebPages/Abstracts/NRC-SentimentAnalysis.htm

2. Liu's Opinion Lexicon
http://www.cs.uic.edu/~liub/FBS/sentiment-analysis.html

In order to reproduce my results you have to provide the testset used in SemEval competition. You don't need to provide the trainset or the devset because I am providing the trained model. If you wish, you can re-train my model if you provide such files. 

Due to copyright reasons, the SemEval team didn't allow to distribute these datasets. However, for research purpose, I may e-mail you these datasets under request.

For more information see the folder Data/Semeval

After placing the required data in Data/Semeval folder, you can reproduce my Semeval results with the command:

```sh
python run_Semeval_classifier.py
```
or,

```sh
python3 run_Semeval_classifier.py
```

It is going to generate the file:

    task9-NILC_USP-B-twitter-constrained.output

which contains the predictions.


If you like to use (without any warranty) my TwitterHybridClassifier, you may call it in python using the follow statements:

```python
>>> from TwitterHybridClassifier import TwitterHybridClassifier
>>> classifier = TwitterHybridClassifier()
>>> prediction = classifier.classify("I love Twitter!")
>>> # prediction contains the sentiment and the algorithm used: Rule-Base, Lexicon-based or Machine Learning
>>> prediction
[(u'positive', u'LB')]
>>> # or use in batch
>>> prediction = classifier.classify_batch(["I love Twitter!","No, I don't like this.","Twitter rocks."])
>>> prediction
[(u'positive', u'LB'), (u'negative', u'ML'), (u'neutral', u'ML')]
```

Any doubts or suggestions, please contact me at: pedrobalage (at) gmail (dot) com

