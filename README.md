# Final Project

<p align="center"><img width=20% src="./images/logo.png"></p>
<p align="center"><img width=40% src="./images/title.png"></p>


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
![Python](https://img.shields.io/badge/python-v3.8+-blue.svg)
[![Build Status](https://travis-ci.org/anfederico/clairvoyant.svg?branch=master)](https://travis-ci.org/tomp332/Lazy-Wifi)
![Dependencies](https://img.shields.io/badge/dependencies-up%20to%20date-brightgreen.svg)
[![GitHub Issues](https://img.shields.io/github/issues/tomp332/Lazy-Wifi.svg)](https://github.com/tomp332/Lazy-Wifi/issues)
![Contributions welcome](https://img.shields.io/badge/contributions-welcome-orange.svg)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/MIT)



# Table of contents
- [Table of contents](#table-of-contents)
- [About The Project](#about-the-project)
- [our code](#our-code)
- [Installation](#installation)
- [results](#results)
- [Contact](#contact)
- [credits](#credits)
  
<br><br>

# About The Project

<div>
  <img src="./images/wifi_logo.svg" alt="Wifi logo" width=130 height=60>
  <img src="./images/aws_logo.png" alt="Aws logo" width=100 height=80>    
  <img src="./images/mailgun_logo.png" alt="Mailgun logo" width=150 height=60>
  <img src="./images/docker_logo.png" alt="Docker logo" width=100 height=80>
</div>
  <br></br>
  In this project we took a published paper(GraphNLI) restored the outcome by building the model and training it. 
  then we improved the model and used the new model archicture for diffrent problem - hate-speech detector. 

   ## Introduction to the orginal paper
   The "GraphNLI" paper addresses part of the problem of hate or misinformative posts in public discussions on forums. It presents a method called "GraphNLI" which takes into account the context of all replies in a discussion, not just the reply and its corresponding post, to classify whether a reply is supporting or attacking the post it is replying to. This method was found to be the most effective at classifying the polarity of replies when compared to other NLP models and methods. It is based on SBERT using RoBERTa and combines pooling and aggregation of results to create the final embedding vector that is fed into a Softmax classifier.

An example of the arguments made in a Kialo debate:

<div align="center">
  <img src="https://github.com/eladlaks/final_project_GraphNLI/blob/main/images/pro_life_pro_choice_arguments.png">
</div>

the model architecture
<div align="center">
  <img src="https://github.com/eladlaks/final_project_GraphNLI/blob/main/images/GraphNLIArch.png">
</div>
  <br><br>

  # our code
  
- Imports and install all reqirments
- Loads the data 
- trains anchor paper model architecture 
- trains our model architecture
- use the method on hate-speech
 
<br><br>
<br><br>
[link to the colab notebook ](https://drive.google.com/file/d/19l-EeaonCjSV2iajzYFCMypWmkRZ1YzV/view?usp=sharing)

# Installation

### Data set
- Get permission to use the dataset.
- Save it in your drive as requested in the colab notebook.
<br><br>

# results
we succeded to improve the anchor paper as mention in the report.
the models results
<div align="center">
  <img src="https://github.com/eladlaks/final_project_GraphNLI/blob/main/images/results.JPG">
</div>
our best model VS anchor paper model
<div align="center">
  <img src="https://github.com/eladlaks/final_project_GraphNLI/blob/main/images/accuracy.png">
</div>

<br><br>

# Contact

Feel free to open issues and contact me with any question :+1:

<p align="center">

  [![Email](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:eladlakss@gmail.com)
  [![Linkedin](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/elad-laks/)
  [![Github](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/eladlaks)
</p>

<br><br>

# Credits

[anchor paper](https://paperswithcode.com/paper/graphnli-a-graph-based-natural-language)

[anchor github page](https://github.com/socsys/graphnli)


Enjoy :metal:



