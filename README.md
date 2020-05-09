# Predictive models for antimicrobial peptides 

This repository implements various machine learning algorithms for classifying peptides as active or non-active against gram-positive bacteria Staphylococcus aureus, with an eye towards antibiotic [drug discovery](https://en.wikipedia.org/wiki/Drug_discovery). See [this link](https://sciforum.net/paper/view/conference/6359)
for an expert-level discussion of the problem. 

For non-bioinformaticians (like me), a short summary of the setup is as follows. Peptides are sequences, consisting of amino acids -- small molecules, coming in a variety of a couple of dozen kinds. Different amino acids are characterized by different physical and chemical properties and are usually coded by capital Latin letters, so that e.g. the peptide known as Distinctin would be represented as NLVSGLIEARKYLEQLHRKLKNCKV. Using the laws of biophysics, out of every such sequence one can extract twelve numeric characteristics of the given peptide (see [this link](https://pubs.acs.org/doi/abs/10.1021/ci4007003) for a discussion of how exactly this is done). These twelve numbers serve as features for our classification task. Their names, together with their respective data types, are:

1. Normalized Hydrophobic Moment (float64)
1. Normalized Hydrophobicity (float64)                     
1. Net Charge (int64)                                      
1. Isoelectric Point (float64)                              
1. Penetration Depth (int64)                               
1. Tilt Angle (int64)                                         
1. Propensity to Disordering (int64)                         
1. Linear Moment (float64)                                    
1. Propensity to in vitro Aggregation (float64)               
1. Angle Subtended by the Hydrophobic Residues (int64)       
1. Amphiphilicity Index (float64)                            
1. Propensity to Coil Conformation (float64)   

There are 372 instances of peptides in the dataset, labeled by the target variable 'Class' that takes on values 0 or 1, depending on whether the given peptide is active or non-active against Staphylococcus aureus. For all 372 instances, the target variable represents an expensive experimental measurement, hence the relative smallness of the dataset. 

The data used in the analysis (and much more) is publicly available in the [Database of Antimicrobial Activity and Structure of Peptides](https://dbaasp.org/) (DBAASP).
