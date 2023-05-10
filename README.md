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
### 2) Ridge regression
      * Training data R2 and Adjusted R2 score is 0.8872978749437399
         0.8870312595752391 respectively.


      * Testing data R2 and Adjusted R2 score is 0.8849257240863323
        0.8841054390238112 respectively.


      * Cross-validation score and best params are as follows:

         **The best parameters** is {'alpha': 0.001}

          **cross-validation score** is 0.884838466969393


     * The performance metrics are as follows:

         **MAE** 0.27379874378382013

         **MSE** 0.11422278721950664

         **RMSE** 0.3379686186904143
### 3) Lasso regression
       * Training data R2 and Adjusted R2 Score as follows:

    **R2 score** 0.8856772370433994

    **Adjusted R2 score** 0.885406787790038


* Testing data R2 and Adjusted R2 Score as follows:

    **R2 score** 0.8824740403319331

    **Adjusted R2 score** 0.8816362789086374


* Cross-validation score and best params are as follows:

    **The best parameters** is {'alpha': 1e-08}

    **cross-validation score** 0.8832671645096054


* The performance metrics are as follows:

    **MAE** 0.275916310909462

    **MSE** 0.11665632981262587

    **RMSE** 0.3415498935918819
    
### Conclusion:
The performance metrics of all three models (linear regression, Ridge regression, and Lasso regression) are very similar, with R2 scores ranging from 0.885 to 0.888 and RMSE values ranging from 0.338 to 0.342. However, Ridge regression and linear regression have slightly better R2 scores and lower RMSE values compared to Lasso regression.

Therefore, based on the performance metrics, both linear regression and Ridge regression appear to be good choices for this dataset.
