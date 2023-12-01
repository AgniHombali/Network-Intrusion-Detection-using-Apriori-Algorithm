**Project Title: Network Intrusion Detection using Apriori Algorithm**

**Description**

This project aims to enhance network security by implementing a robust Network Intrusion Detection System (NIDS) using the Apriori algorithm. The Apriori algorithm, known for its application in association rule mining, is adapted to analyze network traffic patterns and identify potential intrusions.

**Key Steps and Components**

1) Dataset Preparation: Wireshark is utilized to capture network traffic, creating a comprehensive dataset for analysis. There was a capturing of the network data from an attacker IP address to a target IP address. This network data includes the simulation of the ICMP flooding attack from the attacker IP address to the target IP address. 

2) Data Preprocessing: The captured data undergoes cleaning, handling missing values, and normalization to prepare it for Apriori algorithm implementation.

3) Feature Selection: Relevant features, crucial for intrusion detection, are identified to reduce dimensionality and focus on critical aspects of network behavior.

4) Apriori Algorithm Implementation: Leveraging the mlxtend library, the Apriori algorithm is applied to extract frequent itemsets from the dataset.

5) Intrusion Detection Rule Generation: Association rules generated by Apriori serve as the foundation for creating a model to detect network intrusions.

**Tools and Libraries Used**

Python with mlxtend, pandas, numpy, scikit-learn, matplotlib, seaborn, and more.
Wireshark for capturing network traffic.

**Expected Outcome**

The NIDS developed through this project is anticipated to provide accurate and efficient detection of network intrusions, contributing to the broader field of cybersecurity.

Note: This project is part of the MSc in Information Security program at Royal Holloway, University of London, undertaken by Agni.
