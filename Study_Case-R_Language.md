# Study Case using R Language

### Importing Data

1. Download the dataset from [https://www.kaggle.com/datasets/ashyou09/apple-global-product-sales-dataset](Kaggle link)
2. Install and load the tidyverse package using install.packages("tidyverse") and library(tidyverse)
3. Import data using apple_sales <- read_csv("Apple_Sales.csv")

### Exploring Data

1. Identify the variable data type by using glimpse(apples_sales)
    *  sale_data shows as chr when it is date
    *  discount_pct shows as dbl when it is percent
2. View data distribution using summary(apple_sales)
3. 
