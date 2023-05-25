# PandasAssignment

Q1. How do you load a CSV file into a Pandas DataFrame?
- 
import pandas as pd
csv_path = 'pathOfCsv.csv'
df = pd.read_csv(csv_path)
print(df.head())	


Q2. How do you check the data type of a column in a Pandas DataFrame?
-
import pandas as pd
col_name = 'column_name'
data_type = data_frame[col_name].dtype
print(f"The datatype of the column is {data_type}")

Q3. How do you select rows from a Pandas DataFrame based on a condition?

-
import pandas as pd
condition = data_frame['column_name'] > 3
result = data_frame[condition]
print(result)

Q4. How do you rename columns in a Pandas DataFrame?

-
import pandas as pd
rankings = {'test': ['India', 'South Africa', 'England',
                            'New Zealand', 'Australia'],
              'odi': ['England', 'India', 'New Zealand',
                            'South Africa', 'Pakistan'],
               't20': ['Pakistan', 'India', 'Australia',
                              'England', 'New Zealand']}

ranking_pd = pd.Dataframe(rankings)
ranking_pd.rename(columns = {'test':'TEST', 'odi':'ODI'}, inplace=True)

print(ranking_pd)

Q5. How do you drop columns in a Pandas DataFrame?
-

import pandas as pd
#Assuming dataframe is made with name data_frame
cols_to_drop = ['col1', 'col2']
data_frame.drop(columns=cols_to_drop, inplace=True)

Q6. How do you find the unique values in a column of a Pandas DataFrame?
-
import pandas as pd

#Assuming dataframe is made with name data_frame
unique_vals = data_frame['col_name'].unique()
print(unique_vals)

Q7. How do you find the number of missing values in each column of a Pandas DataFrame?
-

Can use isnull() to find missing values, when combined with sum() it also provides total value.

import pandas as pd


#Assuming dataframe is made with name data_frame
missing_vals = data_frame.isnull.sum()
print(missing_vals)


Q8. How do you fill missing values in a Pandas DataFrame with a specific value?
-
import pandas as pd

#Assuming dataframe is made with name data_frame
filling = data_frame.fillna('replacement_val')
print(filling)

Q9. How do you concatenate two Pandas DataFrames?
-
import pandas as pd

#Assuming 2 dataframes are made df1 and df2

concat_df = pd.concat([df1, df2])
print(concat_df)

Q10. How do you merge two Pandas DataFrames on a specific column?
-
import pandas as pd

# Assume you have two DataFrames called 'df1' and 'df2'
merged_df = pd.merge(df1, df2, on='common_col')
print(merged_df)

Q11. How do you group data in a Pandas DataFrame by a specific column and apply an aggregation function?
-

import pandas as pd

result = df.groupby('Courses')['Fee'].aggregate(['min', 'max'])
print(result)

Q12. How do you pivot a Pandas DataFrame?
-
import pandas as pd


# Assume you have a DataFrame called 'data_frame'
pivoted_df = data_frame.pivot(index='index_column', columns = 'columns_col', values='values_col')

print(pivoted_df)

Q13. How do you change the data type of a column in a Pandas DataFrame?
-
import pandas as pd


# Assume you have a DataFrame called 'data_frame'
data_frame['col_name'] = data_frame['col_name'].astype('new_data_type')
print(data_frame)

Q14. How do you sort a Pandas DataFrame by a specific column?
- 
import pandas as pd

# Assume you have a DataFrame called 'data_frame'
sorted_df = data_frame.sort_values(by='col_name')
print(sorted_df)


Q15. How do you create a copy of a Pandas DataFrame?
-
import pandas as pd

data = {
  "name": ["Sally", "Mary", "John"],
  "qualified": [True, False, False]
}

df = pd.DataFrame(data)

#Make a copy:

newdf = df.copy()

print(newdf)

Q16. How do you filter rows of a Pandas DataFrame by multiple conditions?
-
import pandas as pd

# Create a DataFrame
df = pd.DataFrame({'A': [1, 2, 3, 4, 5],
                   'B': [6, 7, 8, 9, 10],
                   'C': ['foo', 'bar', 'baz', 'qux', 'quux']})

# Filter rows based on multiple conditions
filtered_df = df.loc[(df['A'] > 2) & (df['C'] == 'qux')]

# Display the filtered DataFrame
print(filtered_df)


Q17. How do you calculate the mean of a column in a Pandas DataFrame?
-
import pandas as pd

# Create a DataFrame
df = pd.DataFrame({'A': [1, 2, 3, 4, 5],
                   'B': [6, 7, 8, 9, 10],
                   'C': [11, 12, 13, 14, 15]})

# Calculate the mean of a column using the DataFrame
mean1 = df['A'].mean()

print(mean1)

Q18. How do you calculate the standard deviation of a column in a Pandas DataFrame?
-
import pandas as pd

# Create a DataFrame
df = pd.DataFrame({'A': [1, 2, 3, 4, 5],
                   'B': [6, 7, 8, 9, 10],
                   'C': [11, 12, 13, 14, 15]})

# Calculate the standard deviation of a column using the DataFrame
std1 = df['A'].std()

print(“Standard Deviation: “, std1)

Q19. How do you calculate the correlation between two columns in a Pandas DataFrame?
-
import pandas as pd

# Create a DataFrame
df = pd.DataFrame({'A': [1, 2, 3, 4, 5],
                   'B': [6, 7, 8, 9, 10],
                   'C': [11, 12, 13, 14, 15]})

correlation = df[‘A’].corr(df[‘B’])
print(“Correlation ”, correlation)

Q20. How do you select specific columns in a DataFrame using their labels?
-
import pandas as pd


df = pd.DataFrame({'A': [1, 2, 3],
                   'B': [4, 5, 6],
                   'C': [7, 8, 9],
                   'D': [10, 11, 12]})


selected_columns = df[['A', 'C']]

print(selected_columns)

Q21. How do you select specific rows in a DataFrame using their indexes?
-
# import pandas
import pandas as pd
 
# List of Tuples
employees = [('Stuti', 28, 'Varanasi', 20000),
            ('Saumya', 32, 'Delhi', 25000),
            ('Aaditya', 25, 'Mumbai', 40000),
            ('Saumya', 32, 'Delhi', 35000),
            ('Saumya', 32, 'Delhi', 30000),
            ('Saumya', 32, 'Mumbai', 20000),
            ('Aaditya', 40, 'Dehradun', 24000),
            ('Seema', 32, 'Delhi', 70000)
            ]
 
# Create a DataFrame object from list
df = pd.DataFrame(employees,
                columns =['Name', 'Age',
                'City', 'Salary'])
 
# Set 'Name' column as index
# on a Dataframe
df.set_index("Name", inplace = True)
 
# Using the operator .loc[] to
# select multiple rows with some
# particular columns
result = df.loc[["Stuti", "Seema"],
            ["City", "Salary"]]
 
# Show the dataframe
result

Q22. How do you sort a DataFrame by a specific column?
-
import pandas as pd

# Create a sample DataFrame
data = {'Name': ['John', 'Emily', 'Michael', 'Jessica', 'David'],
        'Age': [25, 28, 30, 32, 35],
        'City': ['New York', 'London', 'Paris', 'Berlin', 'Tokyo']}
df = pd.DataFrame(data)
sorted_df = df.sort_values(by=’Age’)
print(sorted_df)


Q23. How do you create a new column in a DataFrame based on the values of another column?
-
import pandas as pd

# Create a sample DataFrame
data = {'Name': ['John', 'Emily', 'Michael', 'Jessica', 'David'],
        'Age': [25, 28, 30, 32, 35],
        'City': ['New York', 'London', 'Paris', 'Berlin', 'Tokyo']}
df = pd.DataFrame(data)

df[‘Age Category’] = df[‘Age’].apply(lambda age: ‘Young’ if age<30 else ‘Adult’)

print(df)

Q24. How do you remove duplicates from a DataFrame?
-
import pandas as pd

# Create a sample DataFrame with duplicates
data = {'Name': ['John', 'Emily', 'John', 'Michael', 'Emily'],
        'Age': [25, 28, 25, 30, 28],
        'City': ['New York', 'London', 'New York', 'Paris', 'London']}
df = pd.DataFrame(data)

df_no_dupli = df.drop_duplicates()
print(df_no_dupli)

Q25. What is the difference between .loc and .iloc in Pandas?

.loc:

.loc is primarily label-based indexing, meaning it is used to access data based on labels or index values.
It uses the row and column labels to make selections.
You can pass label-based slices, single labels, lists of labels, or boolean arrays to extract specific rows or columns.
The indexing includes the endpoint when using slicing.
.loc is inclusive of both the start and end indices.


.iloc:

.iloc is primarily position-based indexing, meaning it is used to access data based on integer positions.
It uses integer-based row and column positions to make selections.
You can pass integer-based slices, single integers, lists of integers, or boolean arrays to extract specific rows or columns.
The indexing does not include the endpoint when using slicing.
.iloc is exclusive of the end index.

import pandas as pd

# Create a sample DataFrame
df = pd.DataFrame({'A': [1, 2, 3, 4, 5],
                   'B': ['a', 'b', 'c', 'd', 'e']})

# Using .loc
print(df.loc[2:4, 'A'])  # Select rows 2 to 4 (inclusive) from column 'A'

# Using .iloc
print(df.iloc[2:4, 0])  # Select rows 2 to 3 (exclusive) from the first column
