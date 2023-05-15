# loan-predictor-knn

## Overall
This project predicts mortgage loan approval result based on 2017 hawaii loan dataset obtained from Consumer Finance Protection Bureau

## How to use
1. Make your loan candidate following format:
[loan_type, property_type, purpose, occupancy, amount, sex, income]
```
Numerical options:
- amount
- income

Categorical options
-------loan_type--------
Conventional       
VA-guaranteed      
FHA-insured        
FSA/RHS-guaranteed 
-------property_type--------
One-to-four family dwelling (other than manufactured housing)    
Multifamily dwelling                                              
Manufactured housing                                                
-------purpose--------
Home purchase      
Refinancing        
Home improvement 
-------occupancy--------
Owner-occupied as a principal dwelling       
Not owner-occupied as a principal dwelling 
Not applicable                             
-------sex--------
Male                                                                                 
Female                                                                               
Information not provided by applicant in mail, Internet, or telephone application     
Not applicable

Candiate example:
['Conventional', 'One-to-four family dwelling (other than manufactured housing)', 'Home improvement', 'Owner-occupied as a principal dwelling', 588, 'Male', 313],
```

2. Put the candidate array into test.ipynb and hit run
```
df = pd.DataFrame(
    [
        ['Conventional', 'One-to-four family dwelling (other than manufactured housing)', 'Home improvement', 'Owner-occupied as a principal dwelling', 588, 'Male', 313],
        ['Conventional', 'One-to-four family dwelling (other than manufactured housing)', 'Home improvement', 'Owner-occupied as a principal dwelling', 35, 'Male', 12]
    ], columns=['loan_type', 'property_type', 'purpose', 'occupancy', 'amount', 'sex', 'income'])
```
- Each candidate will return a 1 if approved or 0 if denied
```
# example return value from above
[1, 1] # this means both candidate were approved
```