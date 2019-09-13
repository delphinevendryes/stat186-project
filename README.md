# Causal Inference: judge decision data

We will carry on an observational study to investigate statistical evidence of partisanship in judge decisions with a quasi-experimental design. We use permutation hypothesis tests to show empirical evidence of American political polarization affecting justice decisions. We use logistic regression to quantify the effect of partisanship with different methods, including a comparative study of justice's behavior close to election dates or far from election dates, and the use of inputs from political sciences, i.e. a Partisan Conflict Index. The causal effect of the Partisan Conflict Index is tested by including lagged predictors in the logistic regression model. Our results show statistical evidence but a more robust quantification procedure should be run on a dataset collected over a longer period of time. 

Impartiality of justices is subject to much debate. 
Although judicial decisions have been shown to be correlated with demographic characteristics such as race and gender, whether these correlations reflect *per se* bias or differences in legal philosophy is an open question. 
Similarly, when it comes to politics, dissents between two justices with different political affiliations cannot quite be directly interpreted to manifest partisan behavior, as it might result from different philosophies that exist *prior* to political affiliation. 
In U.S. State Supreme Courts, a panel of Justices is assigned to a case, hears the oral arguments, and proceeds to a vote. A Justice is chosen in the majority to write the majority opinion. In most circuits, the majority opinion writer is the most senior judge in the majority, or the Chief Justice if they are in the majority. 
Any Justice may write a separate concurring or dissenting opinion. 
In the following, we are interested in pairs of justices on a panel, composed of the majority opinion writer and any other judge on the panel. 
For instance, a panel with 5 justices *{A, B, C, D, E}* where *A* writes the majority opinion will have 4 such pairs: *{A, B}; {A, C}; {A, D}; {A, E}*. 


## Background on U.S. State Supreme Courts
### U.S. State Supreme Courts procedures
A panel of Justices assigned to a case, hears the oral arguments, and proceeds to a vote. The majority opinion writer wrote a majority opinion -- other judges on the panel can join the majority, propose a concurring opinion (same outcome but different rationale for the case) or dissent (different outcome). The different options available to judges on the panel, as described in the State Supreme Court dataset, are:

    - Joins majority  opinion without writing
    - Writer of concurring  opinion
    - Joins concurring  opinion without writing (if there is a concurring opinion)
    - Concurs without  comment
    - Writer of dissenting  opinion
    - Joins dissenting  opinion without writing (if there is a dissenting opinion)
    - Dissents without  comment
    - Concurs in  part / dissents in part
    - Joins concurring  opinion and writes a  concurring opinion (if there is a concurring opinion)
    - Joins dissenting  opinion and writes a  dissenting opinion (if there is a dissenting opinion)
    - Did not participate 
    - Other - unable to  classify using the above  categories

In the rest of the study, some of those categories are aggregated to define "dissent", e.g.: 5, 6, 7, 8, 10.


### U.S. State Supreme Court data
An open-source [dataset](http://www.ruf.rice.edu/~pbrace/statecourt/ "dataset") will be used to answer the question of interest. The dataset contains roughly 21,000 decisions reached by over 400 State Supreme Court justices seated between 1995 and 1998.
Roughly 83% of justices are affiliated to a party, with a majority of justices affiliated to the Democrat party. 
U.S. State Supreme Courts between 1994 and 1998 are composed of roughly 81% of male judges and 92% of white judges.
