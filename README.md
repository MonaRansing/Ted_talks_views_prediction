# **Obective:**
TED is devoted to spreading powerful ideas on just about any topic. These datasets contain over 4,000 TED talks including transcripts in many languages. Founded in 1984 by Richard Salman as a nonprofit organization that aimed at bringing experts from the fields of Technology, Entertainment and Design together, TED Conferences have gone on to become the Mecca of ideas from virtually all walks of life. As of 2015, TED and its sister TEDx chapters have published more than 2000 talks for free consumption by the masses and its speaker list boasts of the likes of AI Gore, Jimmy Wales, Shahrukh Khan and Bill Gates. The main objective is to build a predictive model, which could help in predicting views of the videos uploaded on the TEDx website.
# Dataset:
**talk_id:** A unique identifier for each TED Talk video.(Numerical)

**title:** The title of the talk.(Categorical)

**speaker_1:** The primary speaker for the talk.(Categorical)

**all_speakers:** A list of all the speakers for the talk.(Categorical)

**occupations:** The occupations of the speakers.(Categorical)

**about_speakers:** Information about the speakers, such as their backgrounds and expertise.(Categorical)

**views:** The number of views the video has received.(Numerical)

**recorded_date:** The date the talk was recorded.(Datetime)

**published_date:** The date the talk was published on the TED Talks YouTube channel.(Datetime)

**event:** The name of the TED event where the talk was given.(Categorical)

**native_lang:** The language the talk was given in.(Categorical)

**available_lang:** The languages the talk is available in.(Categorical)

**comments:** The number of comments on that video.(Numerical)

**duration:** The length of the video.(in sec.)(Numerical)

**topics:** The topics covered in the talk.(Categorical)

**related talks:** Other TED Talks that are related to this talk.(Categorical)

**url:** The URL of the video.(Categorical)

**description:** A brief description of the talk.(Categorical)

**transcript:** A transcript of the talk.(Categorical)

# Data cleaning and manipulation:
# Duplicate values
The given dataset has no any duplicate values.

# Missing values/null values
Dataset has 5 columns which have missing values and those columns are commnets,occupation, about_speakers, all_speakers, recorded_date.
so this values are filled using .fillna() function.

# Outliers
There are outliers in columns views, comments and duration.

# Datatype changed
Some columns like talk_id, views, comment, duration, recorded_date, published_date need to be change their datatype. So datatype is changed.

# Droped columns and rows:
Three columns 'all_speakers','url','talk_id' these columns do not required for analysis so these columns are droped.
'views' column have six rows with 0 value and TED talk videos have 0 views is impossible. So those rows are droped from dataset.

# EDA:
The EDA is done by using 3 analysis Univariate, Bivariate and Multivariate analysis. For the datavisualization following charts are used:

Box plot

Barplot

Countplot

Heatmap

1) Which are first 10 popular TED talks based on title,speaker and views?
2) Which are top 10 most popular speakers based on views?
3) Dealing with outliers in columns comments, viwes and Duration.
4) Check speaker popularity.
5) Check video rating
6) Chek available languages
7) Check different events of TED upto year 2013.
8) Topics of TED talk
# Feature selection:

In this dropped unwanted columns "speakers", "title", "recorded_date", "published_date", "event", "native_lang", "available_lang","topics".

# Check Multicollinearity and Remove

# ML Model Implementation:
### 1) Linear regression:
      * Training data R2 and Adjusted R2 Score is 0.8872985205276127
       0.8870319066863465 respectively.

       * Testing data R2 and Adjusted R2 Score is 0.8849387907523739
         0.8841185988330935 respectively.

       * The performance metrics are:-

         **MAE** 0.27380534823783437

         **MSE** 0.11420981723987313

         **RMSE** 0.33794943000377015 
2) Ridge regression
3) Lasso regression
Conclusion:
City hotel has highest adr.
City hotel has longer waiting time.
GDS distribution channel contributed more to ADR in city hotel.
Optimal stay length in both hotel type is less than 7 days.
Repeated guests do not cancel there bookings.
Number of people increases adr aslo going to increase.
Conclusion from correlation heatmap
arrival_date_year and arrival_date_week_number columns has negative correlation which is -0.51.
stays_in_week_nights and total_stay has positive correlation which is 0.95.
Overall conclusion:
City hotel has almost 60% bookings and resort hotel has 40% bookings.
Agent no. 9 made most bookins and those bookings are 28721.
Percentage of repeated guest is just 4%.
Room type A is most preferred room type 46283 guests preferred A room type.
BB type food is most preferred food type and 67907 preferred this food.
Auust month has maximum number of bookings and those bookings are 11242.
TA/TO distribution channel is mostly prefderred channel and the bookings are 69028.
2016 year has 42313 bookings.
City hotel has highest ADR and trhe average ADR is 111.27.
City hotel has longer waiting time means city hotel is busy hotel type.
GDS contribution channel contributed more to ADR in order to incerease income in city hotel.
Optimal stay length in both hotel type is leaa than 7 days.
Repeated do not cancel there bookings.
The number of people increases ADR increases.
arrival_date_year and arrival_date_week_number columns has negative correlation which is -0.51.
stays_in_week_nights and total_stay has positive correlation which is 0.95.
