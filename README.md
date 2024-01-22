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

Figure 1 – Display of the overall structure of the Wireshark application [48][50][51][52]. 

Wireshark provides the functionality to record and save the network traffic from a specified 
time to another fixed point. Such saved data will come in use for detailed research purposes. 
The official format supported by Wireshark is the pcapng file format. When exporting the data, 
the files can be exported in pcapng and other forms such as CSV and libpcap. Wireshark is 
considered a rich GUI (Graphical User Interface) that can be used easily by cyber security 
professionals for network analysis [48][50][51][52]. 

In this context, Wireshark captures simulated network transactions between the attacker 
machine (Parrot OS) and the target machine (Windows Server 2019). The Parrot OS machine 
is used for a simulated Denial-Of-Service (DoS) attack on the Windows Server 2019. 
Meanwhile, Wireshark is kept for recording on the Windows Server 2019. After a few minutes, 
we stopped the recording and saved the recorded network traffic as a CSV file. After recording 
the simulated network transactions, the recorded network traffic file should be input into the 
Python program for data pre-processing and application of the Apriori algorithm 
[48][50][51][52]. 

The Wireshark is compatible with multiple operating systems including Windows and UNIX. 
This makes it a very popular choice for network monitoring. The Wireshark has features for 
identifying the content of the network messages and the protocol that is used for the 
transmission of the network message. It can also help the network analyzer in filtering the 
search so that the analyzer gets only the relevant information regarding the network transactions. 
The Wireshark deals with a lot of packets and often with different network protocols. For a 
normal human being, it is very difficult to identify the protocol of each network transaction and 
analyze. Wireshark overcomes this difficulty by providing coloration to different protocols so 
that the analyzer can identify easily. The Wireshark encounters encrypted content at times. For 
analysis, Wireshark also provides decryption capabilities. The default format of the export files 
in Wireshark is pcapng format. In addition to that, Wireshark also provides features for file 
decompression and checking for different network protocols [53][54][55][56].

**5.5 Review of Python and its libraries** 

Python programming language is a dynamic programming language. It is used widely around 
the world. It was designed by Guido Van Rossum in 1991. The main highlight of Python is 
readability. Compared to older programming languages like Java and C, Python has smaller 
programs. It has the kind of syntax that allows programmers to use fewer lines than Java or C 
to execute an objective. It is a flexible and easy-to-use language. This programming language 
is spreading vibrantly worldwide because of its user-friendliness. It works on different 
platforms like Windows, Mac, Linux, and Raspberry Pi. It has very readable and easy-to
understand syntax, which is connected to English. The Python code can be executed as soon as 
the code is written because Python runs on an interpreter system. In addition, Python can be 
written in a procedural, object-oriented, or functional way [57][58]. 

Python has many advantages, and its main advantage is that it is portable and interactive. In 
addition to that, Python has comprehensible structures. Python also has extensive support 
libraries, such as NumPy and Pandas, that can be used for numerical and statistical operations 
[57][58].

On the other hand, the Python programming language also has some demerits. The performance 
of Python is slower than that of Java and C because Python is an interpreted language. In other 
words, Python can be an issue for performance-intensive tasks. The Global Interpreter Lock 
(GIL) is a feature in Python that prevents parallel executions of the same Python code. This 
feature limits the similar capabilities of Python. In addition to this, Python is highly dynamic in 
nature. In other words, the types of Python variables can change during execution, making it 
difficult to rectify. Lastly, Python is known for its vast memory consumption. This can be 
noticed while working with large data [57][58]. 

The Pandas Library: The Pandas Library was designed by Wes McKinney in 2008. This library 
deals with the exploration and the editing of large data sets. This library helps programmers 
and developers sanitize the data sets of unwanted characters. It helps in making the data sets 
more readable and comprehensible. It uses statistical methods to aid an analyst in making 
decisions. For instance, the Pandas library can give statistical measures like average, maximum 
value, minimum value, and correlation. For this project, the Pandas library helps analyze the 
captured network traffic file datasets in CSV format [21]. 

mlxtend library: This library was created by Sabastian Raschka. It is a library that has 
capabilities for machine learning. This library is mainly used for data analysis. For this project, 
the mlxtend library can provide the in-built functionality of the Apriori algorithm. The Apriori 
algorithm is used in this project for Network Intrusion Detection. The mlxtend library has many 
such built functionality. From the mlxtend library, the Transaction Encoder and association 
rules are also used in this project. These functionalities mainly help in pre-processing the data 
and finding patterns. How these functionalities work will be discussed in further sections 
[10][22][23]. 

**Chapter 6: Implementation** 

This chapter is the most significant chapter of the project. It showcases the exact methodology 
proposed in this project. It explores the tools and technologies used. It explains the necessary 
aspects of the python program that is being used in this project. More importantly, this chapter 
explains the syntax of the python program used and the exact working of the Apriori algorithm 
using an example[1][8][12][13][14]. 

**6.1 Data Collection Process**

I have used the capabilities of the iLabs provided by the EC Council to simulate the attack. 
iLabs is a virtual lab. Inside the virtual lab, there are many machines with different operating 
systems. I am using the Parrot OS machine and the Windows Server 2019 for this project. I 
have considered the Parrot OS my attacker machine and the Windows Server 2019 as my target 
machine. One of the main advantages of using iLabs is that all the machines will have essential 
ethical hacking tools. Wireshark is one of the ethical hacking tools I have used for this project. 
As discussed earlier, Wireshark is the tool used for recording the network traffic between the 
Parrot OS and the Windows Server 2019. First, I will login in the EC council iLabs portal using 
the credentials. Next, I will launch the iLabs practice labs. Inside the iLabs, there are the 
following virtual machines available to use: Windows 11, Windows Server 2022, Windows 
Server 2019, Parrot Security, Ubuntu, and Android [15][16][17][18][19]. 

![image](https://github.com/AgniHombali/Network-Intrusion-Detection-using-Apriori-Algorithm/assets/41777150/4d20358a-7cc2-4343-80d3-c3b6c5758f99)

Figure 2 – Display of the overview of the iLabs setup [15][16][17][18][19].

I am going to open the Parrot Security to configure to launch the terminal and start a flooding 
attack. So first, I am going to open the Parrot Security virtual machine and login using the Parrot 
OS credentials. Next, I am going to open the terminal and type the “ifconfig” command to learn 
the IP address of the Parrot Security in the network [15][16][17][18][19].

![image](https://github.com/AgniHombali/Network-Intrusion-Detection-using-Apriori-Algorithm/assets/41777150/ad858eb1-a4fa-4a1f-bf8a-273ac9f965fc)

Figure 3 – Identification of the IP address of Parrot OS (attacker machine) [15][16][17][18][19].

I have now learned that the IP address of Parrot Security is 10.10.1.13. Now, I am going to 
switch over to the Windows Server 2019 to find it’s IP address. Using the login credentials of 
Windows Server 2019, I am going to login and open a command prompt. In the command 
prompt, I am going to execute the command “ipconfig” to learn the IP address of Windows 
Server 2019 [15][16][17][18][19].

![image](https://github.com/AgniHombali/Network-Intrusion-Detection-using-Apriori-Algorithm/assets/41777150/d946de66-fd38-4f19-b29e-9994ff790a8b)

Figure 4 – Identification of the IP address of Windows Server 2019 (target machine) 
[15][16][17][18][19].

I have now learned that the IP address of Windows Server 2019 is 10.10.1.19. Since we are 
going to consider that the attacker machine is Parrot Security and the target machine is 
Windows Server 2019, we can now consider that the IP address of the attacker machine is 
10.10.1.13 and the IP address of the target machine is 10.10.1.19 [15][16][17][18][19].

**Parrot Security – 10.10.1.13** 

**Windows Server 2019 – 10.10.1.19** 

Next, I am going to switch back to Parrot Security to download and install the hping3 tool to 
create and launch the ICMP flooding attack from 10.10.1.13(Parrot Security) to 
10.10.1.19(Windows Server 2019). In the Parrot Security, I am going to open the terminal and 
execute the command “sudo apt-get install hping3” [15][16][17][18][19]. 

This command will install the hping3. After this, I am going to launch an ICMP flood attack on 
10.10.1.19(Windows Security 2019) by using the command “sudo hping3 -1 –flood 10.10.1.19” 
[15][16][17][18][19]. 

This will now launch an ICMP flooding attack on the Windows Server 2019 
[10][15][16][17][23]. 

![image](https://github.com/AgniHombali/Network-Intrusion-Detection-using-Apriori-Algorithm/assets/41777150/558cc187-2464-4184-8559-7752e09ea65c)

Figure 5 – ICMP flooding attack [10][15][16][17][23].

After this, we are going to switch to the Windows Server 2019 machine. In the Windows Server 
2019 machine, we will open the Wireshark tool [15][16][17][18][19].

![image](https://github.com/AgniHombali/Network-Intrusion-Detection-using-Apriori-Algorithm/assets/41777150/085c461a-d915-4ec8-ab0c-449186cc69dc)

Figure 6 – Display of the launching of the Wireshark [15][16][17][18][19]. 

In Wireshark, I am going to select the Ethernet 2 option to start recording the incoming and 
outgoing network transactions on 10.10.1.19 [15][16][17][18][19].

![image](https://github.com/AgniHombali/Network-Intrusion-Detection-using-Apriori-Algorithm/assets/41777150/8de84c4b-da93-40ff-a20b-be3d08b18044)

Figure 7 – Recording of ICMP flooding attack [15][16][17][18][19]. 

As you can see in the figure above, most of them are ICMP packets incoming and outgoing. 
What needs to be understood here is that the ICMP packets have flooded the receiver with 
ICMP packets and is not allowing the receiver (10.10.1.19) to accept other legitimate packets 
from other legitimate sources. As a result, the Denial-Of-Service attack is taking place. After a 
few seconds, I will stop recording the transactions and then export the recorded transactions in 
CSV format. The reason for exporting the recorded network traffic in CSV format is that the 
Python program which we will be using can recognize the file of the network traffic only in the 
form of CSV file. We will name the CSV as testfile3. This is the procedure of the data collection 
for the project [15][16][17][18][19]. 

To conclude the data collection process, I will switch back to Parrot Security and then terminate 
the ICMP flooding from 10.10.1.13 to 10.10.1.19. After that, I will shut the iLabs down and 
log out of the iLabs. This is the completion of the data collection process [23][24][25][26][27]. 

The significance of this step is to collect enough data for the purpose of the analysis of the 
Python program using Apriori algorithm to find the frequency of a certain type of packet. In 
this case, I am going to apply the Apriori algorithm to find the frequency of the ICMP packet 
and determine if it’s suspicious or not. However, before the Apriori algorithm can be applied 
to the collected data, the recorded data needs to be pre-processed and sanitized. I will be 
demonstrating this in further sections [15][16][17][18][19]. 

Regarding the scale of the data, since this is a small experiment, I have decided to collect data 
that for a duration of only 15 seconds. The computational power within my resources allows 
me to analyze the data of only short durations. Should the data be collected for more than a few 
seconds, it will be difficult for the proposed Python program to analyze the entire data and give 
an output regarding the frequency of the ICMP packets. It is important to note that 
computational power in the Cyber Security industry will be much more advanced and can 
process large chunks of data. Furthermore, I am analyzing static data that is already recorded 
and exported. On the other hand, the Cyber Security industry will be able to analyze data on 
the fly, dynamically and in real time [15][16][17][18][19]. 

The ethical aspects of collecting data also should be acknowledged. The data collected is within 
the confinements of iLabs and are safe from external agents. There is no scope for external 
information. Both the IP addresses of the target and the attacker are within the Local Area 
Network inside the network of the iLabs virtual machine. Due to the separation of the internal 
network activity of iLabs, it can be assured that the operations required for the data collection 
are ethical and secure [15][16][17][18][19].

**6.2 Data Pre-processing Techniques** 

Data pre-processing refers to the operations related to refining raw data. It is a common process 
used before data mining and machine learning. The purpose of this step is to keep the data ready 
for analysis. Without this step, it will be difficult for analysis given the unwanted and defects 
in the data. Data pre-processing converts the raw data into a certain format that can be easily 
understood by data mining algorithms and programs [18]. 

There are several techniques for data pre-processing such as the ones given below [20]. 

• Sampling: This technique involves finding and considering a subset of a large data chunk. 
This subset will generally represent the characteristic of the entire data chunk. Since this 
sample will represent the entire chunk, it can be used as an input for processing algorithms 
because it is of a smaller size [20]. 

• Transformation: This technique is used for converting the data into a tabular form for easy 
processing. It converts the data of a packet that is source, destination, and source into one 
hot-encoded format. For instance, the attributes such as source, destination, and protocol 
get their own column and each packet gets its own row. If that attribute is present in that 
packet, then that row will be marked as 1 or else it will be marked as 0 [20]. 

• Denoising: This technique is used for removing unnecessary noise from the data. This 
means cleaning the data of anomalies and inaccuracies that can distort the data and hinder 
the processing performance [20].  

• Imputation: This technique is for replacing missing values with statistically relevant data. 
The purpose of this is to fill in the gaps in the data that has missing values. By doing this, 
one can prevent statistical inaccuracies due to missing data [20]. 

• Normalization: This method is used for maintaining one single scale throughout the data 
collected. Often, when a large data is considered, there are a lot of different scales present 
in the data. To make the data uniform, normalization is done to convert all the data to one 
scale [20]. 

• Feature Selection: This is the extraction of the most significant and common features in 
the data and create a representative sample out it to have an input of reduced size [20].

Data pre-processing is important because one needs to make sure that the output of a certain 
processing methodology is reliable. If the data holds inaccuracies and defects, then it will be 
difficult to maintain a genuine and legitimate output. The raw data is always with defects and 
the larger the data is, the more irregularities. If humans were to pre-process the data, then all 
these irregularities can be identified easily and rectified. On the other hand, however, it will be 
difficult for computer algorithms and programs to identify such errors. Pre-processing of the 
data is done to compensate for the lack of error identification by machine learning, data mining 
and cyber security processes [20].  

There is one issue that must be kept in mind while conducting data pre-processing and that is 
the issue of potential bias. Sometimes, certain characteristics, while not being included in the 
data directly, can influence the results of the processing due to association rules. These things 
must be looked out for to gain correct and efficient results [20]. 

In this project, we will be using three methods of data pre-processing to sanitize and clean the 
data. The three methods are selection, construction, and transformation. To begin with, we need 
the proper libraries already imported in our Python program for the data pre-processing and for 
further operations. I am going to import the pandas and mlxtend libraries into my python 
program [10][21][22][23].  

I am going to use the following code [59][60][61][62]. 

**import pandas as pd** 
**from mlxtend.preprocessing import TransactionEncoder** 
**from mlxtend.frequent_patterns import apriori, association_rules** 

Each of these lines of code is explained below. 

Consider the line of code ‘import pandas as pd’ where we are importing the pandas library. 
Here, I am making the pandas library available for use. In addition to that, I am also giving an 
alias ‘pd’ to the pandas library so that I don’t have to type the whole name ‘pandas’ every time 
I call pandas. The step ‘as pd’ is not always necessary. However, it enhances the ease of 
programming [59]. 

Next, consider the line ‘from mlxtend.preprocessing import TransactionEncoder’ which 
imports the library ‘mlxtend’, package ‘preprocessing’ and the functionality 
‘TransactionEncoder’. The mlxtend library is used for conducting data science techniques. The 
‘preprocessing’ package is called for cleaning the data. The ‘TransactionEncoder’ functionality
has a unique purpose here. When the data in the CSV file in in the tabular form, it can be 
considered as a list of lists when seen in the perspective of Python Programming Language 
[60][61][62]. 

When we use the TransactionEncoder functionality to pre-process the data, it will convert the 
list of lists into a NumPy array. In other words, the TransactionEncoder converts the list of lists 
into a one-hot encoded NumPy Boolean array. This is done by considering the unique identifiers 
in the dataset and assigning columns and rows accordingly [60][61][62].

For instance, consider the following dataset in python [60][61][62]. 
dataset = [['Apple', 'Beer', 'Rice', 'Chicken'], 
['Apple', 'Beer', 'Rice'], 
['Apple', 'Beer'], 
['Apple', 'Bananas'], 
['Milk', 'Beer', 'Rice', 'Chicken'], 
['Milk', 'Beer', 'Rice'], 
['Milk', 'Beer'], 
['Apple', 'Bananas']] 
Using the TransactionEncoder, this will get converted into the following format [60][61][62]. 
array([[ True, False,  True,  True, False,  True], 
[ True, False,  True, False, False,  True], 
[ True, False,  True, False, False, False], 
[ True,  True, False, False, False, False], 
[False, False,  True,  True,  True,  True], 
[False, False,  True, False,  True,  True], 
[False, False,  True, False,  True, False], 
[ True,  True, False, False, False, False]], dtype=bool) 

In this way, the dataset is made ready for the python program to process and apply Apriori 
algorithm [60][61][62]. 

After this, consider the line ‘from mlxtend.frequent_patterns import apriori, association_rules’ 
where I am calling the frequent_patterns package from mlxtend library to use the apriori and 
association rules functionality. The frequent_patterns package is used for mainly two purposes.

That is for frequent itemset mining and association rule learning. Frequent itemset mining refers 
to finding patterns of items that stay together. Association rule learning refers to the formation 
of rules regarding the items in each itemset. For example, if a customer purchases toothpaste, 
the customer will also purchase a toothbrush. The further understanding and implications of 
this will be explained in further sections [63][64][65][66].

The apriori functionality is called in this line of code for the application of the Apriori algorithm. 
The association_rules functionality is called here for forming association rules [63][64][65][66]. 
Now I will discuss the primary data pre-processing part of the Python program. To begin the 
data pre-processing, we first have to load the dataset into the pandas DataFrame for analysis. 
For this we are going to use the pandas library to read the CSV file. Generally, this step is called 
Selection. I am going to use the following python code for this purpose [67][68].

**df=pd.read_csv('C:/Users/agnih/OneDrive/Desktop/MSc project/testfile3.csv')**

In this step, the read_csv() function will take a parameter. Here the parameter is the file path of 
the testfile3. The read_csv() function will take the data set in testfile3 and then read the data 
into the memory as a pandas dataframe. Here, ‘df’ is the name assigned that pandas dataframe. 
Now, df contains all the network transactions that was recorded during the simulated ICMP 
flood attack [65][66].

Next step in data preprocessing is called construction. I am going to use the following code for 
this purpose [69][70][71][72].

**df['itemset']=df.apply(lambda row: (row['Source'], row['Destination'], row['Protocol']), axis=1)**

In this step, I am creating one more column in the stored data in df. The column’s name is 
‘itemset’. In this code of line, the apply() function is used to apply the lambda function to a row. 
The lambda function here is to create a tuple that contains the information regarding the source, 
destination and the protocol used for that network transaction in that row. The axis is the 
parameter that specifies if the function must be applied to the row or to the column. If the axis 
is 1 then the lambda function will be applied to the row. If the axis is 0 then the lambda function 
will be applied to the column [69][70][71][72].

For example, consider the following row.

![image](https://github.com/AgniHombali/Network-Intrusion-Detection-using-Apriori-Algorithm/assets/41777150/3f4b3a87-20f1-4dd4-863c-c0457a6870bd)

Table 1 – An example of a row in the dataset.

After I apply this lambda function, there will be one more column with the tuple containing the 
source, destination, and the protocol. For the example mentioned above, the update will be as 
follows [37][38][39][40]. 

![image](https://github.com/AgniHombali/Network-Intrusion-Detection-using-Apriori-Algorithm/assets/41777150/22c99b2a-763d-4ad0-b863-6bd8eca07040)

Table 2 – The row after applying the lambda function.

This is how each row in the data set will be updated [69][70][71][72]. 

After this, the next and final step of data preprocessing is the Transformation. This is the heart 
of the data pre-processing stage. I am going to use the following code for the Transformation 
[61][62][73][74][75][76][77][78]. 

**itemsets = df['itemset'].tolist()** 
**encoder = TransactionEncoder().fit(itemsets)**
**onehot = encoder.transform(itemsets)** 
**onehot_df = pd.DataFrame(onehot, columns=encoder.columns_)**

This step of data pre-processing can be broken down into three sub steps. Now I will discuss 
each sub step [61][62][73][74][75][76][77][78].

First, the column of itemsets in the dataset contained by df is to be transformed into a list of 
item sets where each itemset contains three pieces of information regarding source, destination 
and the protocol used for that network transaction. Similarly, all the itemsets will be gathered 
to form a list of itemsets. The function tolist() is used for this purpose and stores the resulting 
list of itemsets in the memory assigned to ‘itemsets’ [61][62][73][74][75][76][77][78].

Second, the itemsets are then used to initialize the encoder. Here, I am using the fit() function 
and the TransactionEncoder package. The working of the fit function revolves around finding 
the most unique items in the entire collection itemsets. It takes the itemsets are the input and 
outputs the most unique items in the itemsets. For example, consider the dataset to be the 
following [61][62][73][74][75][76][77][78]. 

[[‘Brazil’,’India’,’Germany’,’UK’], [‘Brazil’,’China’,’Japan’], [‘India’,’USA’], [‘France’,’India’]] 

After I apply the fit() function to this data set, the result will be as follows 
[61][62][73][74][75][76][77][78].

[[UK], [USA], [Japan], [China], [Brazil], [Germany], [India], [France]]

If you observe, the resulting dataset has included only the unique items in it 
[61][62][73][74][75][76][77][78].

Third, the line ‘onehot=encoder.transform(itemsets)’ and ‘onehot_df = pd.DataFrame(onehot, 
columns=encoder.columns_)’ will apply the encoder object to the itemsets and convert to a 
pandas DataFrame. To be clearer, all the itemsets will be assigned a row and all the unique 
items will be assigned a column. Now the code will check each itemset against each unique 
item. If that item is present in that itemset then the value for that item corresponding to that 
itemset in that table will be 1. Else, it will be 0. Here, 0 represents false and 1 represents true. I 
will explain this more clearly using an example. Consider the example of countries stated earlier. 
When the transformation happens, there will be a table as shown below 
[61][62][73][74][75][76][77][78]. 

![image](https://github.com/AgniHombali/Network-Intrusion-Detection-using-Apriori-Algorithm/assets/41777150/41eaddeb-9299-43e5-bfc4-7c5259c23498)

Table 3 – A pandas dataframe 

This is the conclusion of the data pre-processing. Now the data is ready for application of the 
Apriori algorithm [61][62][73][74][75][76][77][78].

**6.3 Description of Apriori algorithm** 

I am now going to explain the application of the Apriori algorithm to the dataset. I will be using 
the in-built function of the Apriori algorithm present in the mlxtend library. Before that, I will 
explain how the Apriori algorithm works [24][25][26]. 

The Apriori algorithm was proposed by Rakesh Agarwal and Ramakrishnan Srikant in 1994. 
This algorithm was designed for finding frequent items in a dataset. The approach used in this 
algorithm is to consider a large dataset and keep filtering it through various iteration till a 
threshold is met. The algorithm creates a candidate itemset and a frequent itemset in each 
iteration and moves forward with the subsequent iteration. The filtering is done in such a way 
that the less frequent itemsets are filtered out. The algorithm will continue this process in till a 
residual frequent itemset is found and the last frequent itemset contains the most frequent items 
in the large dataset. This is just an overview of how the Apriori algorithm works. The detailed 
working of the Apriori algorithm is as follows. Consider the following data set of groups of 
countries [24][25][26]. 

![image](https://github.com/AgniHombali/Network-Intrusion-Detection-using-Apriori-Algorithm/assets/41777150/0ea0b562-e502-4e34-81fc-1ddeb3f6ac7a)

Table 4 – The groups of countries.

When the Apriori algorithm is applied to this data set, first all the unique items are listed into a 
collection called 1-itemsets. The procedure of forming the 1-itemsets is slightly complicated. 
To start with, all the unique items are listed below with their count [24][25][26]. 

![image](https://github.com/AgniHombali/Network-Intrusion-Detection-using-Apriori-Algorithm/assets/41777150/8fa47041-89ae-4d94-a4cb-d83bf7dff807)

Table 5 – The count of each country.

In this procedure we are supposed to set a parameter called minimum support. If the frequency 
of an item falls below this minimum support, then it will be discarded. Else, it will qualify for 
the next repetition of the process [24][25][26].

In this example, let’s set the minimum support as 60%. This means that if an item appears in 
60% of the groups or more then it will qualify for the next round. In other words, if an item 
appears in 3 or more groups, then it will qualify for the next round. If not, it will be discarded. 
In this case, India, China and Nigeria will qualify for the next round [24][25][26]. 

![image](https://github.com/AgniHombali/Network-Intrusion-Detection-using-Apriori-Algorithm/assets/41777150/1c3c19ea-3ede-4d6b-abb1-6037063c36bd)

Table 6 – Countries in 1-itemsets.

These countries will fall into 1-itemsets. So, the 1-itemsets will contain the following items 
[24][25][26].

{India, China, Nigeria}

Next, the next group of 2-itemsets will be created. 2-itemsets will be formed by pairing the 
itemsets in 1-itemsets with themselves as shown below [24][25][26].

{India, China} 
{China, Nigeria} 
{India, Nigeria} 

Now I must scan the dataset and find out how many groups have {India, China}, {China, 
Nigeria}, and {India, Nigeria} together. The findings are as shown below [24][25][26]. 

![image](https://github.com/AgniHombali/Network-Intrusion-Detection-using-Apriori-Algorithm/assets/41777150/8f48e65a-7e32-47f4-8083-487720922f1c)

Table 7 – Scanning of the data and their results before forming 2-itemsets. 

Given that the minimum support is 60%, only two itemsets qualify for the third round and they 
are {India, China} and {China, Nigeria}. So, the 2-itemsets will contain {India, China} and 
{China, Nigeria} [24][25][26]. 

After this, for the next round, I will create an itemset of three qualified countries. In this case, 
there happens to be only one possibility and that is {India, China, Nigeria}. This possibility 
occurs in G1 and G5. In other words, this possibility occurs in 40% of the dataset and it falls 
below the minimum support of 60%. Hence, there will be nothing in 3-itemsets and this 
concludes the process of Apriori algorithm [24][25][26]. 

In conclusion, the Apriori algorithm has given information about the most occurring patterns. 
In this case, the pairs {India, China} and {China, Nigeria} are the most frequent pairs. This 
means two things. First, India and China appear the most. Second, whenever India appears, 
there is a huge probability that China appears in the same group. This is how Apriori algorithm 
identifies frequent patters [24][25][26]. 

Now that the working of the Apriori algorithm is clear, I will now discuss the pseudocode of 
the Apriori algorithm. Consider the following pseudocode of the Apriori algorithm 
[40][79][80][81]. 

**Pseudocode:** 

Input: The network transaction database T; Minimum support threshold m. 
Output: The itemset L which contains the most frequent itemsets. 
Variables: Ck is the candidate itemset for each iteration. Lk is the k-itemset for each iteration. 
Methods: make_candidate_itemset(Lk-1); make_frequent_itemset(Ck, m) 
Procedure:  

   k = 2; 
   L1 = All the elements in the database T. 
   while Lk-1 is not empty: 
         //make_candidate_itemset(Lk-1) function takes the input which is the frequent 
         //itemset in the previous iteration and forms a candidate itemset. The candidate 
         //itemset contains the paired up itemsets from the previous frequent itemset.
         Ck = make_candidate_itemset(Lk-1);
         //make_frequent_itemset(Lk-1) function takes the input which is the candidate 
         //itemset in the current iteration and forms a new frequent itemset. The new 
         //frequent itemset contains the most frequent itemsets from the current 
         //candidate itemset. The itemsets that enter the new frequent itemset are the 
         //itemsets that have a frequency equal to or more than the minimum support 
         //threshold m.
         Lk = make_frequent_itemset(Ck, m); 
         k++; 
return Lk-2

**6.4 Application of Apriori algorithm**

I have used the inbuilt functionality of the Apriori algorithm in my Python program. The 
following code is the code that I have used for the application of the Apriori algorithm 
[82][83][84][85][86]. 

**frequent_itemsets = apriori(onehot_df, min_support=0.01, use_colnames=True)** 
**print(frequent_itemsets)**

In these lines of code, the frequent_itemsets is the memory buffer which will hold output. The 
output of the apriori() function includes the frequent itemsets and it’s support in the data set. 
The parameters of the apriori() function are the One-Hot encoded dataset, the minimum support 
that is to be assigned by the user and the columns that have the boolean value true. Not that the 
minimum support assigned here is 0.01 [82][83][84][85][86]. 

Finally, the frequent itemsets are printed [82][83][84][85][86].

**Chapter 7: Results**

This is an important chapter where the results of the methodology will be discussed. This 
chapter also includes the techniques to tune the minimum support threshold and to interpret the 
corresponding results. In addition to that, it gives us a meaningful way to learn how to find the 
ideal range for the minimum support threshold [82][83][84][85][86]. 

The output of the Python program is two columns. The first column is the column of the support. 
The support tells us what is the most frequent itemset in the given dataset. The value of the 
support will be a decimal value between 0 and 1. It denotes what portion of the dataset contains 
the corresponding itemset. The second column is that of the itemsets. This is the column that 
contains the most frequent itemsets. To be clearer, it contains the itemsets whose support is 
equal to or more than that of the minimum support of 0.01 [82][83][84][85][86].

**Output Display:** 

support                                     itemsets 
0   0.782209                                 
(10.10.1.13) 
1   0.024540                                 (10.10.1.14) 

2   0.840491                                 (10.10.1.19) 

3   0.018405                                 (10.10.1.22) 

4   0.018405                                (10.10.1.255) 

5   0.021472                             (142.250.200.42) 

6   0.018405                                (224.0.0.251) 

7   0.012270                                    (BROWSER) 

8   0.782209                                       (ICMP) 

9   0.046012                                     (ICMPv6) 

10  0.079755                                       (MDNS) 

11  0.049080                                        (TCP) 

12  0.067485                    (fe80::15:5dff:fe12:438b) 

13  0.030675                  (fe80::3f56:de95:b62b:7e61) 

14  0.036810                                   (ff02::16) 

15  0.061350                                   (ff02::fb) 

16  0.782209                     (10.10.1.19, 10.10.1.13) 

17  0.782209                           (ICMP, 10.10.1.13) 

18  0.018405                    (224.0.0.251, 10.10.1.14) 

19  0.018405                           (MDNS, 10.10.1.14) 

20  0.021472                 (142.250.200.42, 10.10.1.19) 

21  0.782209                           (ICMP, 10.10.1.19) 

22  0.049080                            (10.10.1.19, TCP) 

23  0.018405                    (10.10.1.255, 10.10.1.22) 

24  0.012270                        (BROWSER, 10.10.1.22) 

25  0.012270                       (BROWSER, 10.10.1.255) 

26  0.012270                        (142.250.200.42, TCP) 

0.018405                              (MDNS, 224.0.0.251) 

28  0.024540            (ICMPv6, fe80::15:5dff:fe12:438b) 

29  0.012270          (ICMPv6, fe80::3f56:de95:b62b:7e61) 

30  0.036810                           (ICMPv6, ff02::16) 

31  0.042945              (MDNS, fe80::15:5dff:fe12:438b) 

32  0.018405            (MDNS, fe80::3f56:de95:b62b:7e61) 

33  0.061350                             (ff02::fb, MDNS) 

34  0.024540          (ff02::16, fe80::15:5dff:fe12:438b) 

35  0.042945          (ff02::fb, fe80::15:5dff:fe12:438b) 

36  0.018405        (ff02::fb, fe80::3f56:de95:b62b:7e61) 

37  0.782209               (ICMP, 10.10.1.19, 10.10.1.13) 

38  0.018405              (MDNS, 224.0.0.251, 10.10.1.14) 

39  0.012270            (142.250.200.42, 10.10.1.19, TCP) 

40  0.012270           (BROWSER, 10.10.1.255, 10.10.1.22) 

41  0.024540  (ICMPv6, fe80::15:5dff:fe12:438b, ff02::16) 

42  0.042945    (ff02::fb, MDNS, fe80::15:5dff:fe12:438b) 

43  0.018405  (ff02::fb, MDNS, fe80::3f56:de95:b62b:7e61) 


**Interpretation:** 

The most frequent itemsets in the output are:

![image](https://github.com/AgniHombali/Network-Intrusion-Detection-using-Apriori-Algorithm/assets/41777150/a93bdf00-fcf8-413c-99eb-b79fe1de0f24)

Table 8 – Most frequent itemsets in the output.

If you observe, the itemset with a high frequency is (ICMP, 10.10.1.19, 10.10.1.13). This shows 
that this frequency is suspicious and above the minimum support. The 10.10.1.19 is the IP 
address of the target. The 10.10.1.13 is that of the attacker. ICMP is the protocol used. The 
understanding here should be that the attacker whose IP address is 10.10.1.13 is attempting a 
ICMP flooding attack on 10.10.1.19. This should potentially create an alert form the Network 
Intrusion Detection System. There is one itemset that is more than that of  (ICMP, 10.10.1.19, 
10.10.1.13) and that is 10.10.1.19 with the support of 0.840491 which translates to 84.0491%. 
However, that is the host’s IP address and can be ignored [82][83][84][85][86]. 

Now let us see how we can fine tune this Network Intrusion Detection System (NIDS). One 
possible way to fine tune this NIDS is by managing the value of the minimum support. 
Essentially, the output will show all those itemsets that are equal or more than the minimum 
support. If the minimum support is too less, then even the less frequent and irrelevant itemsets 
will be included. This will create false positives. If the minimum support is too high, then the 
Python program may miss out on the relevant data or the actual threats and may not raise the 
necessary warnings. In other words, it may cause a lot of false negatives [82][83][84][85][86]. 

Let us try to keep the minimum support as low as 0.001 and see what is the possible outcome. 
Output when minimum support is 0.001:

**Output Display:** 

support                                       itemsets 
0    0.782209                                   (10.10.1.13) 
1    0.024540                                   (10.10.1.14) 
2    0.840491                                   (10.10.1.19) 
3    0.018405                                   (10.10.1.22) 
4    0.018405                                  (10.10.1.255) 
..        
…                                            
… 
106  0.024540    (ff02::16, fe80::15:5dff:fe12:438b, ICMPv6) 
107  0.006135  (ff02::16, fe80::3f56:de95:b62b:7e61, ICMPv6) 
108  0.006135   (ff02::2, fe80::3f56:de95:b62b:7e61, ICMPv6) 
109  0.042945      (fe80::15:5dff:fe12:438b, ff02::fb, MDNS) 
110  0.018405    (MDNS, ff02::fb, fe80::3f56:de95:b62b:7e61) 

[111 rows x 2 columns] 

Here, we can see that almost the entire dataset has come out in the output. There are 111 rows. 
Most of this data is not even necessary to conclude with a warning or not [82][83][84][85][86]. 

Now, let us try to keep the minimum support as high as 0.9 and see what the possible outcome 
is. Output when minimum support is 0.9: 

**Output Display:**
Empty DataFrame 
Columns: [support, itemsets] 
Index: [] 

As you can see in the output, the DataFrame is empty. There is no itemset that qualified in the
 Apriori algorithm [82][83][84][85][86].  
 
Now, let us try to keep the minimum support as moderate as 0.5 and see what the possible out
 come is. Output when minimum support is 0.5:
 
**Output Display:**

support                        itemsets 
0  0.782209                    (10.10.1.13) 
1  0.840491                    (10.10.1.19) 
2  0.782209                          (ICMP) 
3  0.782209        (10.10.1.13, 10.10.1.19) 
4  0.782209              (ICMP, 10.10.1.13) 
5  0.782209              (ICMP, 10.10.1.19) 
6  0.782209  (ICMP, 10.10.1.13, 10.10.1.19) 

Here, the output is a better and more comprehensive output. A Network Intrusion 
Detection System can easily find the most frequent itemset and raise an alert. This is 
one possible way to fine tune the Python program for detection of network intrusion 
[82][83][84][85][86]. 

**Chapter 8: Discussion**

This chapter discusses the performance, limitations, and potential future enhancements of the 
proposed methodology. This chapter highlights my contributions towards the research and 
implementation of this project. In addition to that, there will be a discussion on the comparison 
of the Apriori algorithm with other data mining algorithms and appropriate interpretations of 
the comparisons. Consequently, we can learn of the advantages and the disadvantages of the 
Apriori algorithm [1][8][9][12][13][14][87][88][89]. 

**8.1 Performance**

Performance metrics are very important for evaluating the performance of the Python program 
running the Apriori algorithm. I will be discussing performance metrics such as precision, recall, 
F1 Score and Computation time [9]. 

1. Precision: Precision refers to the proportion of identified attacks that were true attacks. 
Calculating the precision is not so simple as this would depend on the minimum support. 
What must be understood is that Network Intrusion Detection is a complicated mechanism. 
The minimum support will reveal how well the Apriori algorithm can identify the attacks. 
If the minimum support is too low, then even the legitimate traffic will be qualified for 
hostile analysis. On the other hand, if the minimum support is too high then even hostile 
network traffic will appear for analysis. So, the minimum support should be adjusted ideally 
to increase performance. For the dataset I am using, the minimum support of 0.5 to 0.65 
seems to be ideal. This range is ideal because it accounts for discarding the legitimate traffic 
which should not qualify as hostile, and it accounts for the intrusion network traffic which 
should qualify as hostile. The minimum support should be adjusted to avoid both false 
positives and false negatives. In addition to this, speaking of the proportion of identified 
attacks, sometimes, it may so happen that a large surge of ICMP traffic may be legitimate. 
Care should be taken to efficiently distinguish the legitimate traffic from the hostile 
incoming traffic. It should be noted that a careful and sophisticated analysis, which is 
beyond the scope of this project should be undertaken before raising an alert 
[9][87][88][89].
 
As for the calculation of the precision, let’s consider the minimum support to be 0.5. 
Keeping the minimum support as 0.5, the formula for precision is as follows [64][65][66]. 

Precision = True Positives/(True Positives + False Positives) 
          = Number itemsets corresponding to true attacks / Number of itemsets in the output 
          = 6/7 
          = 0.8571 
          
2. Recall: This metric refers to the proportion of the true attacks that are correctly classified 
as true attacks. In other words, this metric represents if the Python program was able to 
identify the attacks correctly or not. What needs to be understood here is that the reason 
why some traffic will be considered hostile or not depends on the proportion of the network 
traffic it occupies, its frequency, its source and the protocol used. In the case of this project, 
there was a huge surge of ICMP packets incoming on the target. It was considered hostile 
because the sudden surge did not allow for accepting any other packets. It was a Denial
Of-Service attack. Contrary to this, it may also be possible that the incoming large traffic 
has a high frequency and legitimate. So, calculating the Recall is not very simple. If Recall 
can be considered for only Denial-Of-Service attack then, according to the results obtained, 
the Python program is able to identify the surge in ICMP packets which can eventually be 
considered as hostile [9][87][88][89].

As for the calculation of the recall, let’s consider the minimum support to be 0.5. Keeping 
the minimum support as 0.5, the formula for recall is as follows [9][87][88][89]. 

Recall = Number of correctly identified hostile itemsets / (Number of 
         correctly identified hostile itemsets + Number of itemsets that are 
         hostile but not retained after getting the filtered output) 
       = 6/(6+0)= 1 
       
Note: Number of itemsets that are hostile but not retained after getting 
the filtered output is considered 0 here because all the ICMP flooding 
packets were identified [9][87][88][89]. 

3. F1 Score: This is the score that represents the balanced measure of the Python program’s 
performance. It is the harmonic means of precision and recall. The formula is as follows 
[9][87][88][89].

F1 Score = 2*(Recall*Precision) / (Recall + Precision) 
         = 2*(1*0.8571) / (1+0.8571) 
         = 1.7142 / 1.8571 
         = 0.9230 
         
It is to be noted here that these performance factors largely depend on minimum support. 
If the ideal minimum support for a particular type of network traffic is not selected correctly 
then it may or may not hinder the performance. As for the Python program and the dataset 
in question, the ideal minimum support of considered to be 0.5 – 0.65. Anything outside 
this range may cause a different performance and accuracy [9][87][88][89]. 

4. Computation time: The dataset that I am using is in CSV format. It contains 326 network 
transactions. For the proper analysis of 326 transactions, the Python program takes 7.79 ms. 
The computational time largely depends on the size of the data. If the data is too large, the 
Python program will take a lot of time to analyze the data. Maybe even minutes. I have 
taken the dataset only of few seconds. Therefore, the computational time is small. One 
should consider the size of the dataset when running the execution of the Python program 
[9][87][88][89].

The algorithm performed as expected. I would like to emphasize here that accuracy and 
performance depends a lot on the minimum support of the ideal range of 0.5 to 0.65. However, 
little is known about the performance of large datasets. The dataset I used was recorded only 
for a few seconds. For a larger dataset, the accuracy and performance may vary. Testing for 
large datasets is necessary to see how the Python program reacts [9][87][88][89]. 

Again, two of the major factors that could have influenced the accuracy and the performance 
are the minimum support and the size of the dataset. If the minimum support was too low or 
high, the accuracy and performance would reduce. A moderate range of 0.5 to 0.65 is ideal for 
the Python program. In addition to this, the size of the dataset was small for the purpose of this 
project. If the dataset was larger the performance would vary according to the minimum support. 
In other words, the minimum support and the size of the dataset have a very big connection 
[9][87][88][89]. 

**8.2 Comparison with other algorithms used for the Network Intrusion Detection**

Network Intrusion Detection is a very common and important task in Cyber Security. For this 
project, I am using the Apriori algorithm. However, there are many other algorithms available 
for this task. The most common algorithms that can be used for this purpose are discussed and 
compared with the Apriori algorithm below. 

1. FP-Growth algorithm: This algorithm uses a data structure called the FP tree for storing the 
most frequent itemsets. This algorithm works based on recursively dividing the FP-tree into
different partitions. After that, the most frequent itemsets are selected from each partition. 
Again, this process is repeated for each partition dividing it into smaller partitions. This 
algorithm is faster than the Apriori algorithm because FP-Growth algorithm analyses the 
dataset only twice. FP-Growth algorithm is more scalable than Apriori algorithm. The 
drawback of FP-Growth algorithm is that if the dataset is too large, then the FP-Tree will 
become too large. Consequently, the Python program will suffer from high memory 
consumption. In addition to that, it can also be very difficult to handle low minimum 
support or longer frequent itemsets [28][29][30][31].

2. Eclat algorithm: This algorithm uses the transaction identifiers (TID) which are assigned to 
every item in the dataset. The TIDs of items that have common prefixes. This is helpful 
because it essentially reduces the size of the dataset. However, there will also be a large 
consumption of memory for storing TIDs. Therefore, the larger the datasets, the more the 
memory used for storing TIDs [28][29][30][31].

3. XGBoost algorithm: This is an algorithm used for machine learning. It uses a mechanism 
called ‘gradient boosting’. This mechanism is used for making decision trees for predictions. 
The greatest advantage of this algorithm is that it can be used in messy or uneven data. 
Major functions of this algorithm include classifying the items into certain categories and 
predicting numerical values. It adds new trees to make predictions which are as accurate as 
possible. The drawback of this algorithm is that it is sensitive to parameters 
[28][29][30][31].

4. Deep Learning algorithms: Artificial neural networks are used in this algorithm to learn 
complex features and patterns from any given dataset. These algorithms are computationally 
expensive when compared with Apriori algorithm [32][33][34][35][36][37]. 

**8.3 Limitations of the proposed methodology**

As good as the Python program is working and giving expected results, it is important to 
understand and acknowledge the limitations of this project [1][8][9][12][13][14][87][88][89]. 

The Python Programming Language, as discussed earlier, consumes a lot of memory. Even 
though Python is one of the most user-friendly programming languages, there is a certain trade 
off in terms of the consumption of memory. This must be kept in mind if ever this methodology 
is to be implemented on a large scale. If Python is being used for implementing this 
methodology, then care must be taken to ensure the establishment of enough memory to hold 
and store the data for analysis [1][8][9][12][13][14][87][88][89]. 

The issue of minimum support is one of the most significant limitations in this project. If the 
minimum support is too high or low, the accuracy in the results will differ and may not be 
precise. In addition to that, the minimum support is a subject to change with respect to the 
environment and size of the dataset. If the size of the dataset is too large, then the ideal minimum 
support will vary. Same goes for the network environment. The major challenge here is, for a 
given size of dataset and network environment, the ideal range of minimum support should be 
established [1][8][9][12][13][14][87][88][89]. 

The methodology explained here is suitable only for simple and small-scale testing. If ever this 
methodology is to be used for large scale and in the Cyber Security industry, then it would need 
to be more sophisticated and robust. Having said this it is worthwhile to point out that with such 
a sophistication, this methodology will be able to handle larger datasets and environments. The 
limitation in this methodology is the necessary enhancements to handle dynamic network 
environments and larger datasets [1][8][9][12][13][14][87][88][89]. 

If you have observed, this methodology first involves recording the network traffic, converting 
it into the CSV format, pre-processing the dataset and applying the Apriori algorithm to find 
the frequent datasets. In the real world, there is a need to do all these steps simultaneously and 
dynamically. Obviously with further enhancements and sophistications, one can achieve this. 
However, it is to be noted that this is the limitation of this project. In the real world, all these 
steps must happen parallelly and dynamically to track an intrusion in real time 
[1][8][9][12][13][14][87][88][89]. 

**8.4 Suggestions for future developments**

The future developments of this methodology should overcome the limitations previously 
discussed. To begin with, the programming language used for this methodology should be 
selected ideally. Every programming language has its own advantages and disadvantages. It is 
important to consider these factors and select a programming language that is ideal for the given 
network environment and the size of the dataset. For instance, the Python programming 
language is user friendly, but it consumes a lot of memory. Contrary to this, Java is not as user
friendly as Python, but it does not use as much memory as Python does. So, to have peak 
performance, the ideal programming language must be selected. For instance, if user
friendliness is preferred more than memory consumption then Python can be selected. If 
memory optimization is preferred over user-friendliness, then Java can be selected 
[38][39][40][41][42][43][44][45]. 

There should be expertise developed with respect to the establishment of an ideal range of 
minimum support. The ideal range of minimum support depends on the network environment 
and the size of the dataset. In future developments, the minimum support would also depend on 
the dynamics of the methodology. Therefore, there needs to be development in expertise in 
selecting the correct range of minimum support for a particular situation 
[1][8][9][12][13][14][87][88][89]. 

In the future, there needs to be developments that would allow this methodology to adapt to 
analyzing large datasets. In addition to this the development should also include making this 
methodology adapt to new and dynamic environments. The methodology given in this project 
is static and each step is done one after the other. Developments should be made to perform 
these steps simultaneously and in a synchronized way in a dynamic environment 
[1][8][9][12][13][14][87][88][89]. 

**8.5 My Role and Contributions**

This project is merely an attempt to implement a way of detecting a stealthy attack before the 
target experiences heavy loss or impact. There have been many attempts like this so far. I have 
made a small-scale attempt to use the Apriori algorithm as a form of an in-built functionality 
called apriori within the mlxtend library which is one of the most used libraries inside the 
Python set of libraries in the Python programming language. These techniques of using the 
apriori functionality, mlxtend library is a part of my exploration of building a connection and 
co-relation between data mining and cyber-security [1][8][12][13][14].  

There is a primary reason why I wanted to build such a connection. That primary reason 
involves finding a way to read, analyze and comprehend an extremely large amount of data in 
the field of cyber security. This is the part where data mining comes into play. The human eye 
may be the best camera in the world. However, the reception of the world within the human 
brain through the human eye is honestly not that efficient. In other words, it is almost impossible 
to analyze large chunks of data manually. Performing manual analysis of huge data on the 
monitor was applicable perhaps 40 years ago where the cyber space was not very vast when it 
came to protecting the networks of businesses and enterprises. At that time, it was easier to 
defend a network simply by monitoring the network manually. On the other hand, the 
identification of threats within the vastness of cyber space today is manually impossible. It 
would take hours to find a hidden threat within the network of a business or an enterprise and 
the analysts of a business or an enterprise do not have the luxury of a large amount of time to 
identify threats in their cyber space [1][8][12][13][14]. 

In today’s world, cyber security analysts must be technologically fast if not humanly fast. This 
calls for gathering necessary technologies and methodologies for finding efficient ways to drill 
through large data sets and find threats [1][8][12][13][14]. 

I have gathered the necessary tools required for this project. This includes investing in the iLabs 
provided by EC Council. The reason for acquiring the iLabs from the EC Council is to have a 
standard platform to simulate attacks and record the required network traffic. The iLabs is a 
virtual environment where there are different machines with different operating systems. All 
the machines have a common set of tools that can be used for ethical hacking. Using these tools, 
I have simulated the attack from the attacker machine, which is Parrot OS, to the target machine, 
which is Windows Server 2019 [1][8][12][13][14][17][18]. 

The attack I selected is the ICMP flooding attack. I have carefully timed the attack and 
established a suitable data set for subsequent steps. During the attack, I used the Wireshark tool 
for the purpose of recording network traffic. The data set formed is in the form of a CSV file 
which is exported from the Wireshark tool [1][8][12][13][14][16][17][18]. 

I have carefully studied all the data mining algorithms that are used today for classification. 
Some examples of data mining algorithms are Apriori, K means and RF algorithms. I have 
made comparisons of all the classification algorithms with Apriori algorithm highlighting the 
advantages and the disadvantages of each algorithm when compared with Apriori algorithm. 
This portrays the important reasons why I have selected the Apriori algorithm for this project 
[1][8][12][13][14].  

Even though the in-built functionality of the Apriori algorithm is used in this project, I have 
made a discussion about how the Apriori algorithm works. Using the in-built functionality in 
the mlxtend library without understanding how the Apriori algorithm works is a futile attempt 
to implement a Network Intrusion Detection using Apriori algorithm because without the 
knowledge of the Apriori operation, one cannot understand the output. Therefore, I have 
explained the working of the Apriori algorithm in detail so that even a layman can understand 
how the Apriori algorithm works [1][8][12][13][14][82][83][84][85][86].  

It is to be noted that it is difficult to understand the Apriori algorithm and the project by 
analyzing the Apriori algorithm alone. To understand the Apriori algorithm better, one needs 
to engage in an example of how the Apriori should work. To realize this, I have established an 
example of how the Apriori algorithm works. By using this example, even a layman can 
understand how the Apriori algorithm works and more importantly, how the in-built 
functionality of the Apriori works in the Python programming language [1][8][12][13][14][57][82][83][84][85][86]. 

While it is important to understand how the Apriori algorithm works, it is more important to 
understand what the variables, factors, constants, and parameters in this methodology are. There 
is one important parameter in the working of Apriori algorithm called the minimum support 
which determines the filtering level at each iteration in the working of Apriori algorithm on a 
given dataset. I have taken this opportunity to do multiple trials to find out what is the best 
value for support group as this parameter is the most important one in the working of Apriori 
algorithm and it determines how well the Apriori algorithm works. After performing a few trail 
and error attempts, I have found the ideal range of minimum support. I have showcased the 
examples in the report. By going through the report one can understand how important it is to 
set the minimum support right. Also, by looking at the trial-and-error attempts I have made, 
one can realize that if the minimum support is adjusted incorrectly, there will be false alarms 
and it would unnecessarily cost the system [1][8][12][13][14].

As we already know, there can be no system that is 100% ideal, in a similar way, this 
methodology is also far from ideal. That is why I have pinpointed the limitations of this project. 
The limitations will help a layman understand the scope of the project. It will highlight where 
the boundary of expectation should lie. As it is evident that this is a small-scale attempt to create 
a network intrusion detection system using the Apriori algorithm, there can be attempts to make 
such a methodology using other algorithms as well to understand which algorithm is better. I 
have noted that each algorithm is special in it’s own way and each one is suited for a particular 
scenario. It is important to identify what algorithm corresponds to which scenario 
[1][8][12][13][14].  

It is important to understand that this project is a small-scale attempt. In other words, there can 
be enhancements and future developments. I have taken the time to completely understand the 
limitations and find out how this methodology can be improved [1][8][12][13][14].  

These enhancements and future developments can be used in the future for the analysts to find 
a way to project this method in identifying threats. I have highlighted the enhancements and 
future developments for this project for the sole purpose of improving and refining this 
methodology. Again, since there can be no system that is 100% ideal, there is always some 
room for improvement. To enhance this methodology, for starters, one can concentrate on the 
limitations that I have highlighted. In this way, the most immediate limitations will be addressed, 
and one can see results soon [1][8][12][13][14]. 

This project is a way forward towards thinking about how to approach identification of threats 
in cyber space given that today’s cyber space is vast and contains large amounts of data. The 
Apriori algorithm is not the absolute algorithm that can be used for threat identification. There 
are many algorithms out there that can be used. There should be exploration of these algorithms 
to find new ways to identify threats. In other words, there should always be constant exploration 
in this field [1][8][12][13][14]. 

This experiment can be understood as a way to connect two different fields in computer science, 
that are data mining and cyber security. Originally, Apriori algorithm, which is a data mining 
algorithm, is used for text classification and finding frequent data sets. Very few or no attempts 
have been made to connect Data Mining and Cyber Security. Given that we have already 
achieved milestones in computer science and specifically Cyber Security, as we are entering a 
new era in cyber space, it is important to understand how to bring in new branches of computer 
science or any other field of science for that matter to find a way to integrate a new concept into 
cyber security to enhance, protect and secure cyber space in a better way than before. Using 
cyber security alone for securing cyber space is an outdated method today. There needs to be 
integration of new fields in computer science to secure cyber space. In other words, we need all 
the help we can get. In order to integrate new technologies, I have tried to make a connection 
between Data Mining and Cyber Security. I believe that this is an important connection which 
is to be enhanced and developed in the years to come. The integration of Data Mining and Cyber 
Security will reveal a wide range of opportunities, possibilities, and potential ideas 
[1][8][12][13][14]. 

There are a wide range of applications of this methodology. The static version of the 
methodology which has been portrayed in this project is a first step. Such a static approach 
where the steps in operation are not happening simultaneously can be used in the field of Digital 
Forensics. This involves finding suspicious patterns within the network after the network traffic 
has been recorded. This methodology can aid digital forensics experts in finding the nature of 
each transaction in the recorded network traffic in question. In addition to this, the digital 
forensics expert should be familiar with the working of the Apriori algorithm. Familiarity with 
the Apriori algorithm should include how to tune the minimum support of the Apriori algorithm 
to suit the needs of the digital forensics’ expert and to the forensics situation in hand 
[1][8][12][13][14].  

On the other hand, as mentioned in the section of future enhancements, the methodology may 
be developed to incorporate all the operations inside the methodology to happen simultaneously. 
If such an incorporation is done, then this methodology has almost reached it’s potential to 
operate as a Network Intrusion Detection System. The reason for all the operations to happen 
simultaneously is to have this methodology work in real time. It will be beneficial if this 
methodology’s operations work simultaneously because its only then the methodology will be 
able to track threats when it happens. A static version of this methodology will not give the 
same performance in terms of the time. In the present scenario, we need sophisticated 
methodology which can work in real time to defend against threats. Cyber attackers are not 
always easy to track. They always come up with new techniques to attack cyber space and the 
defenders of cyber space do not have the luxury of time to be prepared for that. Thus, it’s 
important to enhance this methodology to incorporate and conduct all it’s functions 
simultaneously to save that precious time to defend cyber space [1][8][12][13][14]. 

I have carefully studied the advantages and disadvantages of the commonly used programming 
languages to implement this methodology. The study regarding which programming language 
for implementation includes looking into programming languages of Python, Java, C and C++. 
I have selected the Python programming language for the implementation because it is user 
friendly and because it has the necessary in-built functionality of the Apriori algorithm to aid 
the implementation of the Network Intrusion Detection System. By far, the Python 
programming language has proved to be a wonderful option considering it’s advantages over 
the disadvantages over the other programming languages [1][8][12][13][14][57]. 

Given my contributions, there is still scope for improvement in this project. The highlights of 
my contributions do not mean that there is no room for exploration. This is a call for finding 
new ways to identify threats. This is an opportunity to find a way to detect a threat before the 
impact is experienced. There have been many attempts made already. In conclusion, this project 
is a step towards the direction of finding a suitable methodology for threat detection 
[1][8][12][13][14].








































