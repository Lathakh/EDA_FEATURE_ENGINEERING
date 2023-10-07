# EDA_FEATURE_ENGINEERING
When ever you are doing exploratory data analysis or feature engineering you need ask yourself with some of the question regarding data.

1.Shape of data or size of the data rows an columns? df.shape, df.size=total number entires
2.How much memory usage  occupied by data?  df.memory_usage(deep=True) RAM
3.How the data look likes?  df.head() -top 5,df.tail() # we can take df.sample(5)
4.What is datatype of columns?   df.dtypes, df.info()
5.How data look like in mathematically?  df.describe().T only integer columns not for object type
6.Do we have null value or missing value?   df.isnull()
7.How total number of null-value for entire data?  df.isnull().sum().sum() 
8.Check the duplicate values or rows?  df.duplicated().sum()
9.Check the unique value?  df.nunique()
10.Check correlation between columns? c=df.corr()  ,sns.heatmp(c,annot=True)

# From each  code we make some conculsoin on data  it may be plots , segregate data

# univeriate  analysis
        This is  process of performing independent analysis by takng single column. 
        1. pattern of data in that column
        2. how many unique value in that column

   # we seperate numerical and categorical columns
         perform univeriate ananysis 
   # categorical column
         1.count plot/bar plot - catagorical data 
             sns.countplot(df[col_name])
         2.pie chart
     # value counts
          df[col_name].value_counts().plot(kind='pie',autopct="%.2f") -percentage
          
   # numrical column
        
         1.histogram
            import matplotlib.pyplot as plt
            plt.histplot(df[col_name])
            bin - interval for frequency of data
        
          2. distribution plot
             seaborn.distplot(df["age"],bins=5)  # 5 interval

   # box plot -dispersion of data 
      sns.boxplot(df[col_name])
    
      5 number suumary:
       1. dispersion of fdata
       2. lower limit
       3. median -50% of data
       4. higher limit
       5. above higher limit - outlier
       6. df[col_name].skew()
       
# Bi-veriate Analysis   - tips dataset, flight data,-iris dataset
        categorical 
        numerical
  # combinations 
        x-cat y-cat
        x-num- ,y-num
        x-num,y-cat
        x-cat,y-num
   # bivarerate ananylsis
  # 1.scatter plot- when we use  x-> numerical variable  y-> numerical varibale
         sns.scatterplot(tips[tips["total_bill"],tips["tip"])

# Multi-varerate ananylsis- plot 2 or more  features/column

 # x-cat y-cat
 # x-num- ,y-num
 # x-num,y-cat
 # x-cat,y-num

 # 1.scatter plot- when we use  x-> numerical variable  y-> numerical varibale
   sns.scatterplot(tips[tips["total_bill"],tips["tip"],hue=tips["sex"],style=tips["smoker"],size=tips["size"])    
# 2. Bar plot   - x->numerical varibale y-> categorical variable 
     sns.barplot(titanic[pclas],titanic["age"],hue=titanic["sex"])

# 3.boxplot -   x->numerical varibale y-> categorical variable 
     sns.boxplot(titanic["age"],titanic["sex"],hue=titanic["survived"])
# 4. distplot 
  sns.distplot(titanic[titanic["survived"]==1]["Age"], hist=False)

# 1, heat map - x-> categorical  y-> categorical


     
