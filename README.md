# Mentor-Mentee Recommender System on DBLP
## Project_Presentation :

##### < Note: Work in progress, given that it is exam season I could only execute a part of the project. However the entire pipeline is described as follows: >

## GOAL : 

The goal of this project is to come up with a recommender system that matches a Mentor to a Mentee. 
The recommendation should be based on the topics and expertise of mentors and the interests of mentees.
Each Author in the DBLP dataset is a potential mentor and their topics and expertise needs to be learnt.

## DATASET :

The dataset in play is the DBLP Computer Science Bibliography from the University of Trier (http://dblp.uni-trier.de/xml/).
This contains a large dataset of Articles, Books, Theses, Persons, Proceedings , Inproceedings, Incollections etc. 
The data is in xml format.

## ASSUMPTIONS: 

Mentors are a collection of topics and their relative expertise per topic 
Think of each mentor as a vector of tuples: 

M = [(w1,t1), (w2,t2),.....(wN,tN)] -- where N is the number of topics we choose to represent. 
                                    -- t1,....tN are topics (learnt from the text)
                                    -- w1,....wN are the respective expertise 'weights'
                                    
N is a hyperparameter that would need tuning during the cross-validation of the recommender system.

Mentees are a collection of topics that come from a certain Ontology of topics and  preferences per topic.
Similarly, Think of each mentee as a vector of tuples:

m = [(p1,T1), (p2, T2),....(pN, TN)]-- where N is the number of topics chosen above. 
                                    -- T1,....TN are topics (expressed in any Ontology)
                                    -- p1,....pN are the respective preference 'weights'

## PROBLEM DESCRIPTION :

If we can represent the mentee vectors in the same 'semantic space' as that of the mentors, the problem of recommendation boils down to a simple correlation maxiisation problem.
