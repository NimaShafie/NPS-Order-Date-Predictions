# NPS-Order-Date-Predictions
* This was a two person project, this project was created by myself and another group member for the graduate level course: Data Mining (California State University Northridge)

Based off data provided from the Recreation Information Database (RIDB), a supervised machine model will be created to predict when campsites where booked given past records of bookings for the most popular national park campsites in California.

Due to growing trends for camping in recent years, it is more important than ever for campers to plan
ahead. Most national park campgrounds require reservations through Recreation.gov. Popular destinations, such as
Yosemite National Park or Joshua Tree National Park, are often booked weeks or months in advance. Our motive is
to aid those planning to camp in national parks within California. Therefore, our project aims to analyze historical
reservation data and predict how far in advance a campground was booked.

### Data
Datasets for historical online campground reservations were obtained through the Recreation Information
Database (RIDB). These datasets include booking information such as the campground name, parent
national park where the campground is located, date the booking was ordered, date the reservation starts, number of
people per campsite, and type of equipment that was used, among other things.

For the purpose of this project, we selected four datasets that span years 2018-2022. The years previous to
2018 are not verified by the RIDB as accurately reported data.
<br />

  **Summary of Raw Data**
| Year | # Objects (rows) | # Attributes (columns) |
| ----------- | ----------- | ----------- |
| 2018 | 2,712,818 | 57
| 2019 | 3,479,643 | 36
| 2020 | 5,114,789 | 37
| 2021 | 8,354,633 | 35
| Total | 19,661,883 | 202
| Average | 4,915,471 | 40

**Summary of Selected Campgrounds**
| National Park | Campground | # Sites |
| ----------- | ----------- | ----------- |
| Channel Islands | Santa Cruz Scorpion | 31
| Death Valley | Furnace Creek | 136
| Joshua Tree | Jumbo Rocks | 124
|Lassen Volcanic | Manzanita Lake | 179
| Pinnacles | Pinnacles | 134
| Sequoia and Kings Canynon | Sunset | 158
| Yosemite Upper | Pines | 235

### Method - Linear Regression
Using a 80/20 split for training/testing this supervised machine learning method was used to
predict the exact date a campsite was booked. Linear Regression is a model used for predicting real-value quantities
such as an integer. The model makes predictions based on computing a weighted sum of feature inputs and a
constant called the bias term. This model was chosen to use on our dataset because the trend of starting dates and
order dates were shown to have a positive linear relationship. The raw data has been preprocessed in order to fit this
model, since regression requires only numerical data, all categorical values have been converted using a
one-hot-encoder method. This method seeks to determine an exact date, it is expected that this model will have a lower accuracy than the others. Testing
the data on a single park from 2018-2021 yields roughly the same results as testing the data on all parks, so it is
apparent the amount of data points in this test did not contribute significantly for the linear regression model.

### Evaluation -
The evaluation metrics for linear regression are based on a few major variables. The evaluation for
determining accuracy is based on the R2 score which is a measure of variance in the predictions explained in the
dataset. It is the difference between the predictions made by the regression model and the samples in the dataset. The
other two metrics are used to evaluate the errors in the dataset, in this category we used Mean Square Error (MSE)
and Mean Absolute Error (MAE). These metrics are considered the loss/cost function that measures the error
between the predicted target value (booking_horizon) and the true target value. The metric that was more
significantly used to evaluate between the regression model with KNN and RF Classification was the R2 accuracy
score.
