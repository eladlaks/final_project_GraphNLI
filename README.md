# final project

link to the colab notebook 
{https://drive.google.com/file/d/19l-EeaonCjSV2iajzYFCMypWmkRZ1YzV/view?usp=sharing}

link to the full paper we wrote about the project{https://github.com/eladlaks/final_project_GraphNLI/blob/main/graphNLI_report.pdf}

## About The Project
in this project we took published paper(GraphNLI) restore the outcome by building the model and training it. 
then we founded way to improve the accuracy and used the model archicture for diffrent problem - hate-speech detector. 

## introduction

Talk-backs and debates of users on public discussion on forums can escalate into hate or
misinformative posts.To be able to tackle or understand those posts the ”GraphNLI”
paper tries to classify whether a reply is supporting or attacking the post it is replying to.
The problem is that when trying to identify the polarity between post and reply, the reply
to a post may be based on an external context beyond the post. to explain the problem
the paper defines the ”local context” as the context between a post and its reply, and
”global context” as the context to all the other replies before and after the local context,
including the local context. The paper suggests a method to overcome the problem using
the other replies and the replies to the reply from the ’root post’. They suppose it will
give a lot more information to decide whether the reply is supporting or attacking the
post it is replying to. They named this method ”GraphNLI”. They compared several
NLP models and methods on a data-set from Kialo - a debate web, where every time
user uploads a reply to a post he first labels his reply with an attack/support flag. All
the methods based on GraphNLI were better than the others, and the best one was
”GraphNLI: Root-seeking Graph Walk + Weighted Avg”. It was inspired based on SBERT using RoBERTa, Pooling, and aggregation between the results making the final
embedding vector which is fed into Softmax-classifier in the end. The specialty in this
method is the way the graph walks considering all the ”tree” of replies and not only the
reply and its post(considering the global context).

## the dataset
The data set contains 324373 posts and replies, each one of them is a part of the ”conversation tree”. we split the data into train(80%) and test (20%). each conversation tree
represents the global context, of the local context between 2 sentences in the tree.


## the results
we achieved 82.97% Accuracy compared to 82.41% of the orginal paper result.

## using the same methon to detect hate-speech
we achieved 92.6% Accuracy on "A Benchmark Dataset for Learning to Intervene
in Online Hate Speech”.
