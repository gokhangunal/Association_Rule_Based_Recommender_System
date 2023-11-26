# Association Rule Based Recommender System

"Armut, Türkiye's largest online service platform, brings together service providers and those seeking services. It enables easy access to services such as cleaning, renovation, and transportation with just a few taps on a computer or smartphone.

The aim is to create a product recommendation system using Association Rule Learning, utilizing the dataset that includes the service-receiving users and the services and categories they have received."


## Dataset Overview

The dataset consists of services received by customers and the categories of these services. Each service includes information about the date and time it was received.

There are four variables: 
- UserId
- ServiceId
- CategoryId
- CreateDate

The dataset contains 162,523 observations with a size of 5 MB.

- UserId: Customer number
- ServiceId: Anonymized services for each category (Example: Upholstery cleaning service under the cleaning category)
- A ServiceId can be found under different categories and may represent different services under different categories (Example: A service with CategoryId 7 and ServiceId 4 is radiator cleaning, while the same ServiceId under CategoryId 2 is furniture assembly)
- CategoryId: Anonymized categories (Example: Cleaning, transportation, renovation categories)
- CreateDate: The date of service purchase


## Task 1: Data Preparation

- Step 1: Read the 'armut_data.csv' file.
- Step 2: ServiceID represents different services for each CategoryID. Create a new variable by combining ServiceID and CategoryID with an underscore '_'. Expected output: UserId, ServiceId, CategoryId, CreateDate, Service (Example: 4_5, 48_5, 0_8)
- Step 3: The dataset consists of the dates and times services were received without any basket definition (like invoice). To apply Association Rule Learning, a basket definition must be created. Here, the basket definition is the services each customer receives monthly. For example, services 9_4 and 46_4 received by customer 7256 in August 2017 form one basket; services 9_4 and 38_4 received in October 2017 form another basket. Baskets need to be identified with a unique ID. First, create a new date variable containing only year and month, then combine UserID and this new date variable with an underscore '_' to create a new variable named ID.


## Task 2: Generating Association Rules and Making Recommendations

- Step 1: Create a service basket pivot table.
- Step 2: Generate association rules.
- Step 3: Use the 'arl_recommender' function to make a service recommendation for a user who last received the 2_0 service."
