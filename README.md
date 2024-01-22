**Acknowledgements**

My sincere gratitude to my project supervisor.  
The support and guidance you have provided is a testament to the high reputation of Royal 
Holloway, and it has been an absolute pleasure to have this opportunity to perform the necessary 
tasks associated with this project.  
To my loving family for always showing such an interest in my work and passions, for always 
making me believe I can achieve whatever I set out to accomplish in life. 
 
 
**Contents** 
 
Acknowledgements 
Contents           
List of figures           
List of tables        

**Chapter 1: Executive Summary** 

**Chapter 2: Introduction**
 2.1 Motivation for this project
 
**Chapter 3: Background**         
 3.1 Cyber Crime
 
**Chapter 4: Related Work**                
 4.1 Data Mining techniques and Apriori algorithm            
 4.2 The current situation of Intrusion Detection System (IDS)   
 
**Chapter 5: Design and Methodology**            
 5.1 Problem Statement                  
 5.2 Methodology             
 5.3 Tools and Technologies used          
 5.4 Description of Wireshark          
 5.5 Review of Python and it's libraries     
 
**Chapter 6: Implementation**             
 6.1 Data Collection Process            
 6.2 Data Pre-processing techniques           
 6.3 Description of Apriori algorithm           
 6.4 Application of Apriori algorithm       
 
**Chapter 7: Results**              

**Chapter 8: Discussion**              
 8.1 Performance             
 8.2 Comparison with other algorithms           
 8.3 Limitations of the proposed methodology          
 8.4 Suggestions for future developments           
 8.5 My role and contributions
 
**Chapter 9: Conclusion** 

**Bibliography**                                 
 
 
 
 
 
 
 
 
 
**List of figures** 

Figure 1 - Display of the overall structure of the Wireshark application.  
Figure 2 – Display of the overview of the iLabs setup.     
Figure 3 – Identification of the IP address of Parrot OS (attacker machine).
Figure 4 – Identification of the IP address of Windows Server 2019 (target machine).       
Figure 5 – ICMP flooding attack.      
Figure 6 – Display of the launching of the Wireshark.      
Figure 7 – Recording of ICMP flooding attack.      
 
**List of Tables** 

Table 1 – An example of a row in the dataset.       
Table 2 – The row after applying the lambda function. 
Table 3 – A pandas dataframe 
Table 4 – The groups of countries. 
Table 5 – The count of each country. 
Table 6 – Countries in 1-itemsets. 
Table 7 – Scanning of the data and their results before forming 2-itemsets. 
Table 8 – Most frequent itemsets in the output. 
 
 
       
**Chapter 1: Executive Summary** 

The MSc project titled “Network Intrusion Detection Using Apriori Algorithm” is an attempt 
to create a methodology for detecting network intrusion using a classification algorithm called 
Apriori algorithm. This is a small-scale attempt which will give insight into the efficiency, 
accuracy, and other aspects of Apriori Algorithm in detecting a Denial-Of-Service attack in the 
form of ICMP flooding attack [1][2].  

In this project, the operations will be conducted on the platforms of iLabs from EC-Council and 
the Jupyter Notebook. The iLabs is a virtual learning environment and the Jupyter Notebook is 
a platform for developing and executing Python code. The primary programming language used 
for this project is the Python. There are many advantages of using Python. The detailed 
information about these tools will be discussed in the further sections [3][4][5]. 

The project involves conducting a small scale ICMP flooding attack from the attacker’s 
machine to the target’s machine. In addition to that, the network traffic will be recorded. The 
network traffic will be the input of the Apriori algorithm. In summary, the Apriori algorithm 
will be used to analyse the recorded network traffic and give a report on the network traffic to 
indicate an attack. Two key points to remember here is that the entire attack is static and small 
scale [1][2].  

Given that this experiment is static and small scale, there will be limitations of this methodology. 
Since this experiment is in the initial stages of development. That is why there will be a 
considerable scope of improvement. Both the limitations and the improvements will be 
discussed in the “Limitations” and “Future Enhancements” sections. Alongside this, the various 
applications of this project will be discussed [1][2][6][7]. 

Lately, it is observed that malicious agents in cyber-space are creative, and they modify their 
attacks to overcome already existing mitigation tactics. In this never-ending chase of being at 
par with the new attack techniques, it is important and beneficial to explore newer ways of 
keeping the cyber-space safe and secure. This calls for testing various algorithms to find ideal 
methods of detecting cyber-attacks [8]. 

It is also important to find if the experiment is accurate and performs well. In other words, one 
should calculate important metrics such as the Precision, Recall, F1 score and Computation 
time. Calculation of these metrics will give an idea regarding how far away the result from the 
expectations is. They will provide information regarding if the experiment has performed in a 
way it was intended to [9].  

Overall, one will be able to understand the nature of Apriori algorithm in the scenario of a 
Cyber-Crime detection situation. Insights regarding accuracy of Apriori algorithm will help in 
determining its efficiency of detecting Network Intrusion [1][2][6][7][9]. 

 
**Chapter 2: Introduction** 

This is a technical project involving various concepts of cyber security and data mining. It is 
to be noted that this is a small-scale project. In this section, we will explore concepts in cyber 
security and data mining to understand how they co-relate with each other and how they can 
be used in this project [1][8]. 

**2.1 Motivation of this project** 

In the world we live in, there are many businesses that interact with each other. Some businesses 
are big, and some are small. In addition to this, there are also malicious agents present. The 
usual reasons for malicious agents to conduct illegal and malicious activities is to manipulate 
or sabotage business communications taking place between different enterprises. Having stated 
this, all businesses, big or small, are at risk of being victims of malicious agents and their 
activities. One of the key methods of evading or preventing such malicious activities is by using 
IDS (Intrusion Detection System) [1]. 

IDSs are a popular choice for monitoring activities in cyber space. They are also considered 
one of the most mandatory requirements in securing cyber space. It enhances the scope of 
monitoring of the activities within an enterprise and the associated activities beyond [1]. 

When spoken in terms of network security, the specific type of IDS called the Network IDS 
(NIDS) comes into play. This specific type of IDS is installed in network segments with the 
sole purpose of monitoring the network traffic. The NIDS does not involve or interact with any 
other entity within the network segment it is installed in. The NIDS exists in the network 
segment only to “see” and “interpret”. Care and caution are always in place to keep the NIDS 
hidden so that malicious agents do not detect these instalments and learn how to bypass the 
scope of supervision of the NIDS and eventually find it’s blind spots [1].  

This project explores one of the methodologies of implementing the NIDS. NIDS can include 
many methodologies in detecting intrusions. The methodology proposed in this project is to use 
the Apriori algorithm to detect intrusion. Apriori algorithm is a classification algorithm which 
can be used to analyse the network traffic [1].  

In this project, the programming language used is the Python programming language. The 
Python has an inbuilt functionality of the Apriori algorithm. The Apriori functionality in the 
Python programming language is present in the Python library called the “mlxtend”. The 
mlxtend library is a library of applications. This library is used for activities in data-science and 
machine learning. The Apriori functionality is present inside the mlxtend library [10][11]. 


**Chapter 3: Background** 

This chapter explores the present-day scenario of cyber-crime and how it has developed from 
the past. In addition to that, there will be a discussion regarding the potential for the future of 
the creativity and development in cyber-crime and how much more we should be prepared to 
defend cyber space [8][12]. 

**3.1 Cyber Crime**

The word “Cyber-Crime” refers to those offenses that have computational equipment involved 
in it. Usually, the end goals of Cyber Crime are to spread fear and anxiety. It can be understood 
as a way in which a criminal commits a certain offence, but the only difference here is that the 
criminal has not committed the offence in the real world but in cyber space [8].  

We are facing many cyber threats inside cyber space today. Since there are many cyber 
criminals, there needs to be some way of predicting the occurrence of cyber-crime. It is always 
beneficial to develop a way of predicting a cybercrime before it’s commencement to keep 
mitigation measures in place to face such threats and reduce the impact of the cyber-crime [8].  
It makes more sense to find a mathematical way of predicting a cyber-crime based on statistics, 
criminology, probability, and behavior analysis. Over the years there have been many cyber
crime occurrences. A main issue of cyber-crimes is false alerts. Most resources for mitigating 
cyber-crimes are allocated to handling false alerts [8].  

When cyber-crimes happen, the consequences of the event can lead to a chaos or in some cases 
death. That’s why, to prevent life threatening situations, there must be a way to know about a 
cyber-attack before it happens [8].   

The significant part of this project is the Apriori algorithm and specifically how it works. 
Apriori algorithm is used for classification as stated earlier. When using the Apriori algorithm 
in the field of Cyber Crime, it is mainly used for finding patterns in cyber space. More 
importantly, it is used for finding frequent patterns. These patterns can help us in identifying 
the potential attacks if these frequent patters are unwarranted [12]. 
 
**Chapter 4: Related Work**

This chapter explores the existing literature and research associated with cyber-crime, data 
mining, cyber security, Apriori algorithm and Network Intrusion Detection Systems. In addition 
to that, this chapter also makes an attempt to interpret the existing literature and research to 
understand the methodology proposed in this project [1][8][12].  

**4.1 Data mining techniques and Apriori algorithm**

On a broad note, there are four different activities when using such an algorithm as Apriori 
algorithm in cybercrime. They are data extraction, clustering, detecting anomalies and finding 
associations. These activities are not directly in sequence or order. These activities can be 
modified to suit the needs of the situation and environment. The description of these four 
activities is given as follows [12]. 

1. Data extraction: This work refers to collecting the necessary data that can be used for 
identifying patterns in the other activities. This data collected can be raw. This data can also 
be refined in other activities. It is to be understood that the collection of data can also be 
made in bulk, and this means that refining the data for the rest of the analysis cannot always 
be done manually and may need the assistance of computing technologies [12].

3. Clustering: The word “Clustering” means grouping objects with similar characteristics on 
a broad sense. To a limited extent, this is what will be done in a process involving finding 
frequent patterns using Apriori algorithm. What data is collected, may it be network 
transactions between two or more businesses, the source, destination, nature or type of 
transaction and the protocol used will be recorded. This data can be clustered into a set of 
groups based on classifications that the analyser selects [12].

5. Detecting anomalies: These activities include finding and measuring how far the network 
traffic recorded in the collected data has deviated from “normal” behaviour. By studying 
these odd patterns, an analyst can identify if there are any suspicious entities in the network 
[12].

7. Detecting associations: This is an important activity where there are co-relations formed 
between two items in the collected data containing recorded network traffic. These corelations
are called associations. These associations can help reveal and identify the nature of the network
traffic [12].
 
This approach of using classification and association rule algorithms to detect cybercrimes are 
generally called Data Mining techniques for cyber crime detection. These techniques work 
based on inputting the raw data recorded into a particular form of database and then applying 
data mining algorithms to the database for analysis. The eventual result of the analysis will be 
a refined interpretation of the data set that was given as input originally [8].  

Data mining techniques are an important part of understanding and analyzing huge data today. 
We have discussed the four important activities in using the Apriori algorithm that are data 
extraction, clustering, detecting anomalies, and detecting associations. These activities are 
stated in a broad sense. To understand the complete methodology of using Apriori algorithm in 
detail, one needs to understand the practical steps associated with data mining. To be more 
elaborate, datamining has eight different steps, and they are briefly described below [13].

1. Selection of data: This process involves the gathering of data. The data gathered data can 
be raw or unrefined. It is to be noted that the data gathered should be suitable for the kind 
of analysis that will be done in the subsequent steps. In other words, different situations 
demand different kinds of data, and the selection of the data is at the discretion of the 
analyzer [13].

3. Data pre-processing: This process involves refining the gathered data to keep it ready for 
consideration. This step involves filling the missing places, eliminating the wrong values, 
reducing the redundancies, and removing unwanted or irrelevant data [13].

5. Data consideration: This process involves finding and extracting the data required for a 
particular type of analysis. The data collected from the raw data after pre-processing should 
be selective and suit the needs of a particular objective or purpose. In other words, not all 
the data is required. The analyzer should select only what data is required from the pre
processed data [13].

6. Data transformation: This is an important process where the collected data is converted 
into a Boolean format. Converting the data considered into a Boolean format is necessary 
for data mining algorithms because the Boolean format is how data mining algorithms read 
the data [13].

8. Selecting of the data mining method: This process revolves around selection of an ideal 
data mining algorithm which can suit the characteristics of the data collected. The design 
of the data mining algorithm selected should comply with the characteristics of the data 
mining algorithm selected [13].

10. Application of the data mining algorithm: This process involves the application of the 
data mining algorithm to the pre-processed and transformed data. The expected out put in 
the data containing interpretation of the data. This may include certain co-relations that was 
otherwise hidden to the naked eye. Such information can only be revealed by applying data 
mining algorithms [13].

12. Evaluation of the results: This process involves finding the necessary data and discarding 
the unwanted data in the end results. This can be thought of as a second form of the second 
stage of data pre-processing where the data was refined [13].

14. Final interpretation of the end results: This is the final stage where the analyzer will find 
co-relations in the end results. These co-relations may be in the form of graphical 
visualizations. This is considered the endgame of the application of data mining results [13].

When we speak about data mining algorithms such as the Apriori algorithm, then the endgame 
of the application of the Apriori algorithm is finding association rules. Association rules are 
very important in finding co-relation between two entities. The formation of association rules 
between two entities can benefit the analyzer to find certain suspicious nature between two or 
more entities [13]. 

There are limitations to this approach. Data mining techniques are not always accurate because 
the recorded and collected data that is used for the application of data mining techniques are 
very raw. This means that the recorded data can have some discrepancies such as missing values 
or redundancies. Consequently, such discrepancies can cause drastic changes to the results 
provided by data mining algorithms. These discrepancies need to be treated before they are 
used for analysis. Therefore, experts in the field of data mining and cyber-crime are required 
for this additional support in preparing the data for the application of the data mining techniques 
[8].  

Some important data mining algorithms that are used in cyber-crime detection are Apriori, K
Means algorithm and RF algorithm. These are considered efficient and the most popular when it comes 
to cyber-crime detection. Since we are using the Apriori algorithm in this project, let’s 
dive into the nature of Apriori algorithm to understand it’s working [8]. 

The Apriori algorithm was designed by Rakesh Agrawal and Ramakrishnan Srikant in 1994. 
This algorithm was designed to address the issue of mining large chunks of data which 
contained essential customer information. The end goal of the Apriori algorithm was to create 
association rules that can help business strategists to use these association rules to make 
important business decisions to increase profits and continue the business efficiently [14].  
For example, consider that a business owner of toiletries and cleaning products is trying to 
analyze the recorded customer information regarding what customers have bought recently. 
Using the Apriori algorithm the business strategist can formulate the association rule that the 
customers who have bought toothpaste have also bought toothbrushes. By formulating and co
relating the sales between the toothbrush and toothpaste the business owner can make important 
decisions to increase the sales of toothbrush and toothpaste to make higher profits [14]. 
As we already know, there are many data mining algorithms available in the field of data 
science. Some of the most popular data mining algorithms that are used are the Apriori 
algorithm, K means algorithm, RF algorithm etc. It is also important to understand the 
performance metrics of how these [14].  

**4.2 The current situation of Intrusion Detection Systems (IDS)**

In the world of cyber-crime detection there are many algorithms that are used for the purpose 
of identifying suspicious cybercrime activities. The available methodologies will help in finding 
criminal patterns in a network. However, these methodologies are suited only for the criminal 
patterns that are already recorded. In other words, cybercrime detection should be well prepared 
and creative for new kinds of attacks. There should be new methodologies for dynamic network 
environments [1].  

On of the primary devices used today for the intrusion detection is the Intrusion Detection 
Systems (IDS). This is a sophisticated system that is used to observe network patterns and the 
activities in cyber space to identify criminal or illegal activities. Until recently, this technology 
has been able to give a somewhat considerable quality of network checking and cyber-crime 
identification. However, in the recent years, there have been new kinds of attacks that evade the 
scope of IDSs and stay in the blind spots [1].  

The IDS may be a good system for intrusion detection. However, there are some drawbacks of 
the IDS. The IDS has no provision for identifying legitimate entities from the illegitimate 
entities. Although the identifying legitimate entities is not the operation of the IDS, it is 
important for IDS to incorporate this operation to enhance security [1]. 

Given that cyber criminals are always creative in their attacks, the cyber criminals almost 
always manage to bypass the security mechanisms of the already outdated network security 
protocols. The present condition of the IDS does not acknowledge the need to support the weak 
network security protocols. It is important that an IDS takes a partial responsibility of providing 
partial form of network security [1]. 

Integrity is a primary aspect of cyber security. However, the present models of the IDS does 
not provide the necessary operations to verify the integrity of the network communications. 
Even if integrity check is not part of the IDS, it can still benefit if the IDS incorporates certain 
mechanisms to verify the integrity of network communications. IDS may be a fantastic 
approach to identifying intrusions inside a network. However, there is a flipside to this. An IDS 
can cover only a limited size of a network. IDSs are not suitable for large networks. In other 
words, the IDS is not suitable to analyze large chunks of data. In addition to this. The IDS is 
not dynamic in nature. Due to it’s static nature, IDSs cannot adapt to new environments. The 
IDSs are not equipped to rectify the errors inside it’s system [1]. 

The IDS do not update all by itself. It is not capable of identifying new threats and recording 
them for future identification. This is the major problem in signature based IDSs that always 
depend on the pre-installed signatures of suspicious patterns to aid them in identifying the threat. 
Such IDSs will not be able to identify the new threats that arise due to the creative methods of 
cyber criminals [1]. 

An anomaly-based IDS is a type of IDS that raises an alert if it finds a suspicious pattern that 
deviates from the already installed baseline. Due to the creative methods of the present-day 
cyber criminals, it is possible to deceive anomaly-based IDS and bypass security measures 
because it is possible to conduct cyber crimes and conform to the baseline installed in anomaly 
based IDSs. Another disadvantage of anomaly based IDSs is that it may give false alerts on 
legitimate network patterns when it deviates from the baseline. Anomaly based IDSs needs very 
careful and regular tuning [1]. 

Network Intrusion Detection System (NIDS) is some of the most popularly used IDSs in the 
world. The primary reason for its use is that it is easy to install. On the other hand, the NIDS is 
not capable of monitoring large networks. In addition to that, if the network transactions contain 
encrypted content, then this cannot be identified by the NIDS [1]. 

Having discussed the limitations of the present technology concerning the IDSs, it is high time 
that there are explorations into newer technologies and methodologies to identify intrusions and 
detect cyber-crimes [1]. 

**Chapter 5: Design and Methodology**

This chapter is a blueprint of the project. It serves as a guide and explains the sequence of steps 
involved in this project. This chapter includes the problem statement and it’s explanation. It 
gives the brief overview of the methodology used and the explanation of different metric 
parameters that are to be used to evaluate the performance. In addition to that, it gives a brief 
description of the tools and technologies that are to be used in this project [1][8][12][13][14].

**5.1 Problem Statement**

To dive into the design and methodology of this project, one first needs to understand the 
problem statement for this project. The following is the problem statement of the project 
[1][2][3][6][7][8][9]. 

Problem Statement:  
Network Intrusion Detection using Apriori algorithm and determining the accuracy, 
performance, limitations, and scope of improvement of this methodology 
[1][2][3][6][7][8][9]. 

This problem statement has some primary objectives and secondary objectives. The primary 
objectives include the implementation of Network Intrusion Detection System specifically 
using the Apriori Algorithm. The secondary objectives of this project are to find the accuracy, 
performance, limitations, and the scope of this implementation. For the secondary objectives, 
the performance metrics such as the accuracy, precision, recall and F1 score. These metrics will 
indicate if this methodology is on the correct path or how much more this methodology needs 
to be enhanced and developed [1][2][3][6][7][8][9].  

**5.2 Methodology**

This project is for the purpose of detecting Network Intrusion using the Apriori algorithm. As 
it is known, Network Intrusion Detection revolves around monitoring the network and detecting 
anomalies. There are many types of attacks a target can experience. It is important to be 
prepared with a good Network Intrusion Detection System to avoid or divert an attack. 
Sometimes, these Network Intrusion Detection Systems will have methodologies to detect 
intrusion. Today there are many methodologies to detect intrusion. Some of them are simple 
and some of them are sophisticated. This project is an attempt to develop a particular 
methodology to implement a Network Intrusion Detection System using Apriori algorithm 
[1][6][7][8][12][13][14]. 

The proposed methodology uses the Apriori algorithm to detect network intrusions. Apriori 
algorithm is a classification algorithm. This algorithm is considered because it can filter the 
network traffic and give out the most frequent patterns out. The programming language used 
for the implementation is the Python Programming Language. The python programming 
language has in-built functionalities that can be used in the implementation. For instance, it has 
the in-built functionality of the Apriori algorithm in the python library called mlxtend. Due to 
its user-friendliness, Python programming language is a suitable programming language. To 
run and test the python code, the Jupyter notebook will be used. In addition to that, iLabs will 
also be used for the simulations in this project. iLabs is a virtual environment where simulations 
of cyber attacks can be studied for the purpose of learning how to mitigate such attacks 
[3][4][5][10][11]. 

The methodology proposed here has four steps. They are Data collection process, data pre
processing, application of Apriori algorithm and the interpretation of the results [1][6][13][14]. 
Data collection process will include using Wireshark tool. In addition to that, simulations in 
iLabs between two different virtual machines and recording of the network traffic will be 
conducted. These attack simulations and recording will be for the purpose of studying the 
attacks [13][15][16][17][18][19]. 

After that, there will be a discussion on the data pre-processing stage where the data that is 
collected will be prepared for the purpose of the application of the Apriori algorithm. 
Preparation of the data is for making the data ready for the Python program to analyze the data 
and apply the Apriori algorithm efficiently. There is often a need for data preprocessing because 
without data preprocessing the format of the raw data cannot be used for the Python program 
to analyze. Due to the incompatibility of the format of the raw data it is necessary for the data 
preprocessing. Data- preprocessing often includes cleaning and sanitizing the data. For instance, 
it may include removing white spaces and restoring missing values in the data in order to have 
whole data [10][20][21][22][23]. 

Next, there will be a discussion on the application of the Apriori algorithm on pre-processed 
data. The application of the Apriori algorithm in this project involves the usage of the in-built 
Apriori functionality inside the mlxtend library in the Python programming language. The 
Apriori algorithm is an algorithm which finds the most frequent item sets in the dataset it 
analyzes. Even though the in-built Apriori algorithm functionality in the mlxtend python library 
will be used, the entire Apriori algorithm will be explained in the subsequent sections by using 
a pseudocode. In addition to this, there will be a detailed explanation of the Apriori algorithm 
using an example [1][6][10][11][13][24][25][26].  

In the last step of the methodology, that is the interpretation of the results, there will be a 
discussion regarding how the output of the Apriori algorithm can be interpreted to identify 
suspicious traffic to raise an alert. In addition to this, I will be using different values of the 
parameters like the minimum support for the Apriori algorithm to acquire different kinds of 
outputs to understand the nature of the Python program and the Apriori algorithm. Following 
this, I will then explain how the Apriori algorithm depends on other factors. Factors which 
include the size of the dataset and the network environment [1][6][10][11][13][24][25][26]. 

Towards the end, there will be a discussion of the performance of the methodology used. I will 
be using parameters such as accuracy, precision, recall, F1 score and the computational time. 
Let us try to understand a little bit about all these parameters [9].  

Accuracy is a measure of the correctness of the output of the methodology. Precision is a 
measure of how many correct predictions are actually correct. For instance, out of all the 
network transactions in the dataset, the number of correctly identified attacks divided by the 
number of all the apparent attacks will give the precision. On the other hand, recall is the 
number of correctly identified attacks divided by the number of actual attacks in the dataset. 
The F1 score is defined as the harmonic mean of the precision and the recall. The formula for 
the F1 score is as follows [9]. 

F1 Score = (2 × Precision × Recall)
 Precision + Recall
 
 Finally, the computational time is the time required for presenting the results of the Apriori 
algorithm. Jupiter Notebook is used in this implementation to develop and execute the code. 
The Jupyter Notebook will provide information regarding the time taken for the execution 
[9][27]. 

Following the analysis of the performance of the Python program using the Apriori algorithm, 
there will be a comparison of the Apriori algorithm with other available algorithms for pattern 
identification. In addition to this, I will be discussing the advantages and disadvantages of each 
algorithm when compared to the Apriori algorithm [28][29][30][31][32][33][34][35][36][37]. 

We already know that there is no system that is ideal and perfect. There will always be 
imperfections and defects. Similarly, it is important to note that even though the methodology 
would work, there will be limitations with it. A discussion of the limitations will be made 
following the comparison of the Apriori algorithm with other data mining algorithms 
[1][8][12][13][14]. 

After that, there will be a discussion of the ways in which this methodology can be developed 
or improved in the future. Future developments would include the selection of the programming 
languages, the network environment, and the size of the dataset [38][39][40][41][42][43][44][45].

We are facing a lot many cyber threats today inside cyber space. Since we have a lot many 
cyber criminals to face, there needs to be some way of predicting the occurrence of cyber-crime. 
It is always beneficial to develop a way of predicting a cyber-crime before it’s commencement 
in order to keep mitigation measures in place to face such threats and reduce the impact of the 
cyber-crime [1][8].  

It makes more sense to find a mathematical way of predicting a cyber-crime based on statistics, 
criminology, probability, and behavior analysis. Over the years there have been many cyber
crime occurrences. A main issue of cyber-crimes are the false alerts. Most resources for 
mitigating cyber-crimes are allocated to handling false alerts [1][8].  

To formulate a way of detecting potential cyber-crime, we first need to understand the nature 
of cyber-crime and what exactly it is. There are many categories of cyber-crimes. The most 
prominent are Denial-Of-Service attacks (DoS) [1][8].  

When events like this happen, the consequences of the event can lead to a chaos or in some 
cases death. That’s why, to prevent life threatening situations, there must be a way developed 
to know about a cyber-attack before it happens [1][8].   

**5.3 Tools and Technologies used.**

In this project, a combination of virtual labs and software has been used. Each utility used in 
this project plays a vital role in the successful execution of this project. However, the main 
highlight of the execution of this project is the Python programming language which proves to 
be a suitable programming language for the execution of the Apriori algorithm because of its 
dynamic programming nature and its inbuilt functionality for the Apriori algorithm 
[1][3][4][5][10][11][17][40].  

The description of each utility employed in this project is given below: 

1. Python programming language: Python is a dynamic coding language. It has diverse 
libraries for statistical analysis and testing. Specifically, it has the inbuilt functionality of 
the Apriori algorithm inside the “mlxtend” library within the Python set of libraries. The 
inbuilt functionality of the Apriori algorithm must be imported into the main program to 
analyze the network traffic and provide the relevant frequencies. Python has the capability 
of manipulating the input data and providing appropriate statistical values 
[3][10][21][22][23].

3. Jupyter Notebook: Jupyter Notebook is a platform for executing Python code. It has a 
modular design in the form of cells. In other words, a set of Python code can be managed 
separately from different locations of Python code. The execution flow in this platform is 
flexible and dynamic. It is a web-based interactive development environment that works on 
the local host of the user [4].

5. Anaconda Navigator: This is a desktop graphical user interface. It allows for launching 
applications like the Jupyter Notebook. It also acts as a repository for applications. Using 
applications without command line interfaces can be considered a shortcut [47].

7. Wireshark: This is a network traffic analysis tool. It’s used for monitoring the network on 
the local host. In this project, Wireshark records the network traffic between the attacker 
machine (Parrot OS) and the target machine (Windows server 2019). This tool is also used 
for exporting network traffic as a Pcap and CSV file. This tool provides comprehensive 
feedback on network traffic [48].

9. iLabs from EC Council: iLabs from EC Council is a virtual lab. It gives a simulated 
environment to conduct cyber security attacks and various other activities related to cyber 
security. It provides a platform for multiple virtual machines, two of which are used for this 
project. The two machines used in this project are the Parrot OS and the Windows Server 
2019. iLabs also provides access to various applications, such as Wireshark and AD 
Explorer, for Cyber security simulations. The combination of the tools and the virtual 
machines from iLabs makes it suitable for this project [5].

6. Hping3: This is a network tool used for sending custom made UDP/TCP/ICMP packets 
according to the needs of the sender. It also allows fragmentation and variable packet size. 
It is mostly used for testing firewall rules. The main function of this tool is perform port 
scanning, Network testing, perform path MTU discovery, perform traceroute-like actions, 
recon different operating systems and check TCP/IP stacks [49].

8. Python libraries: Besides the technologies and software, I have extensively used Python 
libraries for the coding part of this project. More details of the functionality of these 
libraries will be discussed further [10][21][22][23].

**5.4 Description of Wireshark**

Wireshark is a Network Protocol Analyzer. It is a widely used tool for packet sniffing. It helps 
capture network packets for analysis. It has filters to display network transactions that can 
narrow down the search. It is comprehensive in identifying anomalies in the network. Due to 
its reliability in comprehensively analyzing the network traffic, it can provide detailed 
information on network packets. It can determine the IP addresses of the source and destination 
of a network packet. In some cases, it can also detect the device's MAC address. In addition to 
this, it can determine the protocol being used in a network transaction. It sees the number of 
bytes for each packet and displays it under the information provided under the “Length” field. 
Next, it gives brief information about the package being sent [48][50][51][52]. 

Wireshark helps troubleshoot the network, identifying reasons for weak network performance, 
tracing network connections, viewing the contents of suspected network transactions, and 
identifying sudden bursts of network traffic. It provides a microscopic view of packets and 
network traffic [48][50][51][52].

![image](https://github.com/AgniHombali/Network-Intrusion-Detection-using-Apriori-Algorithm/assets/41777150/36fc0d84-83f7-4ff2-ac47-c2f0ec37645f)


