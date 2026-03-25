# Study Case using R Language

### Importing Data

1. Download the dataset from [https://www.kaggle.com/datasets/ashyou09/apple-global-product-sales-dataset](Kaggle link)
2. Install and load the tidyverse package using install.packages("tidyverse") and library(tidyverse)
3. Import data using apple_sales <- read_csv("Apple_Sales.csv")

### Exploring Data

1. Identify the **variable data type** by using `glimpse(apples_sales)`
   *  sale_data shows as chr when it is date
   *  discount_pct shows as dbl when it is percent
2. View **data distribution** using `summary(apple_sales)`
3. Check for **missing values** with `apple_sales %>% map(~sum(is.na(.)))`
   * $customer_rating shows 3360 missing values
   * Replaced $customer_rating = NA using apple_sales_nona <- `apple_sales %>% replace_na(list(customer_rating = 0))`
      * Another way to clean that only column would be `apple_sales %>% mutate(customer_rating = replace_na(customer_rating, 0))`
4. Separating the dates
   * Separated $sale_date with `data_clean <- apple_sales_nona %>% separate(sale_date, sep = "/", into = c("month", "day", "year"))`
   * Changed $month, $day, $year format
 
  `data_clean <- data_clean %>%
    mutate(across(c(month, day, year), ~as.numeric(type.convert(.x))))`

  * Converted quarter, country, region, city, product_name, category, color, sales_channel, payment_method, customer_segment, customer_age_group as factors

  `data_clean <- data_clean %>%
  mutate(across(c(quarter, country, region, city, product_name, category, color, sales_channel, payment_method, customer_segment, customer_age_group), as.factor))`
  
### Data Wrangling

1. Names normalization
    * 
