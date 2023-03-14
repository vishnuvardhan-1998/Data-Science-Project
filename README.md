# 	Predicting The Loan Defaulter Status
Our objective is to figure out the customers who are not a loan defaulter, sanction loan to gain profit and build 
relationship with customer for mutual benefit for a long period. 

# Attributes of the data

ID ; Customer ID of Applicant

year ; Year of Application

loan limit ; maximum avaliable amount of the loan allowed to be taken

Gender ; sex type

approv_in_adv ; Is loan pre-approved or not

loan_type ; Type of loan

loan_purpose ; the reason you want to borrow money

Credit_Worthiness ; is how a lender determines that you will default on your debt obligations, or how worthy you are to receive new credit.

open_credit ; is a pre-approved loan between a lender and a borrower. It allows the borrower to make repeated withdrawals up to a certain limit.

business_or_commercial ; Usage type of the loan amount

loan_amount ; The exact loan amount

rate_of_interest ; is the amount a lender charges a borrower and is a percentage of the principal—the amount loaned.

Interest_rate_spread ; the difference between the interest rate a financial institution pays to depositors and the interest rate it receives from loans

Upfront_charges ; Fee paid to a lender by a borrower as consideration for making a new loan

term ; the loan's repayment period

Neg_ammortization ; refers to a situation when a loan borrower makes a payment less than the standard installment set by the bank.

interest_only ; amount of interest only without principles

lump_sum_payment ; is an amount of money that is paid in one single payment rather than in installments.

property_value ; the present worth of future benefits arising from the ownership of the property

construction_type ; Collateral construction type

occupancy_type ; classifications refer to categorizing structures based on their usage

Secured_by ; Type of Collatoral

total_units ; number of unites

income ; refers to the amount of money, property, and other transfers of value received over a set period of time

credit_type ; type of credit

co-applicant_credit_type ; is an additional person involved in the loan application process. Both applicant and co-applicant apply and sign for the loan

age ; applicant's age

submission_of_application ; Ensure the application is complete or not

LTV ; life-time value (LTV) is a prognostication of the net profit

Region ; applicant's place

Security_Type ; Type of Collatoral

status ; Loan status (Approved/Declined)

dtir1 ; debt-to-income ratio

# Tools Used:

1) Python 

2) Michine Learning

# Importing Required Libraries:

![image](https://user-images.githubusercontent.com/115528472/224947826-c735c5f7-6912-40ce-9e84-ed666c0d5e60.png)

# Summary and Conlusion Of The Project

1) This model was created for predicting the eligibility for a loan (approved or not) according to many features.
2) There were large number of features must be dropped , as: (ID, Year, rate_of_interest, Interest_rate_spread, Upfront_charges)
3) some features are having high bias so these should be droped they are "Secured_by", "construction_type", "co-applicant_credit_type", "Security_Type"
4) from all the features we have selected best features using voting_mechanism from the top 4 models and best features are "Credit_Worthiness_l2",
"credit_type_EQUI", "dtir1", "LTV", "loan_amount", "lump_sum_payment_not_lpsm", "Neg_ammortization_not_neg" and "income"
5) we were supposed to fill null values with median for numerical and mode for categroical columns. for the DTIR1 column there were more 
then 15% of the null values so we predicted using KNN imputer and checked the data distribution and it resulted the distribution remains same.
6) Number of unapproved loans were larger than approved. for our target varible class balance is 75% for non approval 25% for approval it 
is pretty goood and doesnt required any Smote Technique.
7) Loan amounts were between (3,576,500 and 16,500) and The largest category applied for alone there ages were between (45-54) for loan of (type 3)
8) After handling scaling, we were suppose to check significane of the variable using statistical test and convert all values to numerical values 
to be ready to be used for the model.
9) we have built 8 models out of it 4 were choosen based on precision they are ADA-Boosting, XG-Boosting, Gradient-Boosting, and Random-Forest.
10) based on the best features which are selected by voting-mechanism we built 4 models along with tunning and selected a best model as
XGboosting_tunned with precision of 0.94%
11) after all we again performed feature engineering and created a new feature prapotion_of_property_value and dropped the two columns that were 
used to create new feature.
12) the best model which is Xgboost we built another model for new features and performed the tunning it gave us much better precision as 0.956 
so this can be our final model.

# BUSINESS SUGGESTIONS

1) we have see bank is approving loan with high dtir1(debt to income ratio) no matter what is their credit Score of gender

2) And we observed loan is approved for few people with low property value and high dtir1(debt to income ratio) bank have to take care of them.

3) Another thing LTV of above 100 is almost everyone getting their loan approved no matter what is their dtir1 high dtir1 and low Ltv also getting loan approved

4) from the dataset we seen very less income get their loan approved even if loan_amount is very large need to figure out

5) Their is positive linear relationship between loan_amount and property_vslue one thing we can notice that applicant with low loan_amount
having low property_value are mostly decline so business have to take care of this in such kind of scenerio bank is unescessary losing business it can approve small loans.
