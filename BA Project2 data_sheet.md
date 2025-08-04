# Datasheet Template

## Motivation

- **Purpose of dataset creation:**  
  The dataset was created to support the development and benchmarking of credit scoring models — particularly models that can predict the likelihood of default on credit card payments.

- **Who created it and funded it:**  
  The dataset was prepared by I-Cheng Yeh from the Department of Information Management, Chung Hua University, Taiwan. It was used in the paper _"Comparisons of data mining techniques for predicting consumer credit default."_  
  Funding details are not explicitly listed, but the dataset was made publicly available through the UCI Machine Learning Repository.

 
## Composition

- **What do the instances represent?**  
  Each row represents a credit card client in Taiwan, with attributes describing their demographic profile, payment history, and credit behaviour.

- **How many instances are there?**  
  30,000 records.

- **Missing data?**  
  There are no missing values in the dataset.

- **Confidential data?**  
  No direct identifiers are included. However, the dataset reflects sensitive financial behavior and should still be handled carefully.


## Collection process

- **How was the data acquired?**  
  Data was collected from the credit card records of clients from a Taiwanese financial institution.

- **Sampling strategy?**  
  The dataset appears to be a structured extract but exact sampling details are not disclosed.

- **Time frame of collection?**  
  April to September 2005.

  
## Preprocessing/cleaning/labelling

- **Was preprocessing done?**  
  Yes. Categorical and ordinal fields were pre-encoded. Monthly payment histories (`PAY_0` to `PAY_6`) were encoded as discrete variables.

- **Raw data availability?**  
  No, only the preprocessed version is publicly available.

  
## Uses

- **Other tasks it could support:**  
  - Credit risk modeling
  - Fairness and bias auditing
  - Classification under class imbalance
  - Education in supervised learning

- **Risks and limitations:**  
  - Dataset is geographically limited (Taiwan)
  - Potential bias based on gender, marital status, etc.
  - May not generalize to different populations

- **Tasks it should not be used for:**  
  - Real-time lending decisions
  - Personal financial profiling without context
  - Deployment without local validation
    
## Distribution

- **Distribution history:**  
  Distributed via the UCI Machine Learning Repository.

- **Licensing and usage terms:**  
  Publicly available for academic research. No specific license terms given.

## Maintenance

- **Maintainer:**  
  Maintained by the UCI ML Repository. Contributed by I-Cheng Yeh (Chung Hua University).


