## Why Use pandas?

https://colab.research.google.com/drive/1vsANmljtPHhElyS9gOHo1cTsmBkpa9LE?usp=sharing

# Pandas Study Notes - Complete Guide

## Table of Contents
1. [Basic Setup](#basic-setup)
2. [Data Structures](#data-structures)
3. [Data Loading & Saving](#data-loading--saving)
4. [Data Inspection](#data-inspection)
5. [Data Selection & Indexing](#data-selection--indexing)
6. [Data Cleaning](#data-cleaning)
7. [Data Manipulation](#data-manipulation)
8. [Grouping & Aggregation](#grouping--aggregation)
9. [Merging & Joining](#merging--joining)
10. [Time Series](#time-series)
11. [Data Visualization](#data-visualization)
12. [Performance Tips](#performance-tips)

---

## Basic Setup

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# Display options
pd.set_option('display.max_columns', None)
pd.set_option('display.max_rows', 100)
pd.set_option('display.width', None)
```

---

## Data Structures

### Series
```python
# Creating Series
s = pd.Series([1, 3, 5, np.nan, 6, 8])
s = pd.Series([1, 2, 3], index=['a', 'b', 'c'])
s = pd.Series({'a': 1, 'b': 2, 'c': 3})

# Series properties
s.index    # Index labels
s.values   # Underlying data
s.dtype    # Data type
s.size     # Number of elements
```

### DataFrame
```python
# Creating DataFrames
df = pd.DataFrame({
    'A': [1, 2, 3, 4],
    'B': pd.Timestamp('20230101'),
    'C': pd.Series(1, index=list(range(4)), dtype='float32'),
    'D': np.array([3] * 4, dtype='int32'),
    'E': pd.Categorical(["test", "train", "test", "train"]),
    'F': 'foo'
})

# From dictionary
data = {'col1': [1, 2], 'col2': [3, 4]}
df = pd.DataFrame(data)

# From list of dictionaries
data = [{'a': 1, 'b': 2}, {'a': 5, 'b': 10}]
df = pd.DataFrame(data)
```

---

## Data Loading & Saving

### Reading Data
```python
# CSV files
df = pd.read_csv('file.csv')
df = pd.read_csv('file.csv', sep=';', header=0, index_col=0)

# Excel files
df = pd.read_excel('file.xlsx', sheet_name='Sheet1')

# JSON files
df = pd.read_json('file.json')

# SQL databases
df = pd.read_sql('SELECT * FROM table', connection)

# From URLs
df = pd.read_csv('https://example.com/data.csv')
```

### Saving Data
```python
# CSV
df.to_csv('output.csv', index=False)

# Excel
df.to_excel('output.xlsx', sheet_name='Data', index=False)

# JSON
df.to_json('output.json', orient='records')

# Pickle (for Python objects)
df.to_pickle('data.pkl')
df_loaded = pd.read_pickle('data.pkl')
```

---

## Data Inspection

### Basic Info
```python
df.head()           # First 5 rows
df.tail(10)         # Last 10 rows
df.shape            # (rows, columns)
df.info()           # Data types and memory usage
df.describe()       # Statistical summary
df.dtypes           # Data types of each column
df.columns          # Column names
df.index            # Row indices
```

### Missing Data
```python
df.isnull()         # Boolean mask of null values
df.isna()           # Same as isnull()
df.notnull()        # Boolean mask of non-null values
df.isnull().sum()   # Count of null values per column
df.isnull().any()   # True if any null values in column
```

### Unique Values
```python
df['column'].unique()           # Unique values
df['column'].nunique()          # Count of unique values
df['column'].value_counts()     # Frequency count
df.duplicated()                 # Boolean mask of duplicate rows
df.drop_duplicates()            # Remove duplicate rows
```

---

## Data Selection & Indexing

### Column Selection
```python
df['column']                    # Single column (Series)
df[['col1', 'col2']]           # Multiple columns (DataFrame)
df.column                       # Dot notation (if valid identifier)
```

### Row Selection
```python
df.iloc[0]                      # First row by position
df.iloc[0:3]                    # First 3 rows
df.iloc[-1]                     # Last row
df.loc['index_name']            # Row by index label
df.loc['idx1':'idx3']           # Rows by index range
```

### Boolean Indexing
```python
df[df['column'] > 5]            # Rows where column > 5
df[df['col1'].isin([1, 2, 3])]  # Rows where col1 in [1,2,3]
df[(df['col1'] > 5) & (df['col2'] < 10)]  # Multiple conditions
df.query('col1 > 5 and col2 < 10')       # Query string syntax
```

### Advanced Indexing
```python
df.iloc[0:3, 1:4]              # Rows 0-2, columns 1-3
df.loc[df['col'] > 5, 'col2']  # Conditional row, specific column
df.at[0, 'column']             # Single value access (fast)
df.iat[0, 1]                   # Single value by position (fast)
```

---

## Data Cleaning

### Handling Missing Values
```python
# Dropping missing values
df.dropna()                     # Drop rows with any NaN
df.dropna(axis=1)              # Drop columns with any NaN
df.dropna(thresh=2)            # Drop rows with less than 2 non-NaN
df.dropna(subset=['col1'])     # Drop rows where col1 is NaN

# Filling missing values
df.fillna(0)                   # Fill with constant
df.fillna(method='ffill')      # Forward fill
df.fillna(method='bfill')      # Backward fill
df.fillna(df.mean())           # Fill with column means
df['col'].fillna(df['col'].mode()[0])  # Fill with mode
```

### Data Type Conversion
```python
df['col'] = df['col'].astype('int64')
df['col'] = pd.to_numeric(df['col'], errors='coerce')
df['date'] = pd.to_datetime(df['date'])
df['category'] = df['category'].astype('category')
```

### String Operations
```python
df['col'].str.lower()          # Lowercase
df['col'].str.upper()          # Uppercase
df['col'].str.strip()          # Remove whitespace
df['col'].str.replace('old', 'new')  # Replace text
df['col'].str.contains('pattern')    # Boolean mask
df['col'].str.split(',')       # Split strings
df['col'].str.len()            # String length
```

### Renaming
```python
df.rename(columns={'old': 'new'})              # Rename columns
df.rename(index={0: 'first'})                  # Rename index
df.columns = ['new1', 'new2', 'new3']         # Replace all column names
```

---

## Data Manipulation

### Adding/Removing Columns
```python
df['new_col'] = df['col1'] + df['col2']        # Add column
df['constant'] = 1                             # Add constant column
df.drop('column', axis=1, inplace=True)        # Remove column
df.drop(['col1', 'col2'], axis=1)             # Remove multiple columns
```

### Adding/Removing Rows
```python
new_row = pd.Series({'col1': 1, 'col2': 2})
df = df.append(new_row, ignore_index=True)     # Add row (deprecated)
df = pd.concat([df, pd.DataFrame([new_row])], ignore_index=True)  # Modern way
df.drop(0, axis=0)                            # Remove row by index
```

### Sorting
```python
df.sort_values('column')                       # Sort by column
df.sort_values(['col1', 'col2'], ascending=[True, False])  # Multi-column sort
df.sort_index()                               # Sort by index
df.nlargest(5, 'column')                      # Top 5 values
df.nsmallest(5, 'column')                     # Bottom 5 values
```

### Apply Functions
```python
df['col'].apply(lambda x: x**2)               # Apply to Series
df.apply(lambda row: row['col1'] + row['col2'], axis=1)  # Apply to rows
df.apply(lambda col: col.max() - col.min())   # Apply to columns
df.applymap(lambda x: x**2)                   # Apply to all elements
```

---

## Grouping & Aggregation

### Basic Grouping
```python
df.groupby('column').mean()                   # Group by column, calculate mean
df.groupby('column').sum()                    # Sum by group
df.groupby('column').size()                   # Count rows per group
df.groupby('column').count()                  # Count non-null values per group
```

### Multiple Columns
```python
df.groupby(['col1', 'col2']).mean()          # Group by multiple columns
df.groupby('col1')['col2'].mean()            # Group by col1, aggregate col2
```

### Multiple Aggregations
```python
df.groupby('column').agg({
    'col1': 'mean',
    'col2': ['sum', 'count'],
    'col3': lambda x: x.max() - x.min()
})

# Named aggregations
df.groupby('column').agg(
    avg_col1=('col1', 'mean'),
    sum_col2=('col2', 'sum')
)
```

### Advanced Grouping
```python
df.groupby('column').filter(lambda x: len(x) > 5)    # Filter groups
df.groupby('column').transform(lambda x: x - x.mean())  # Transform within groups
```

---

## Merging & Joining

### Concatenation
```python
pd.concat([df1, df2])                         # Vertical concatenation
pd.concat([df1, df2], axis=1)                 # Horizontal concatenation
pd.concat([df1, df2], ignore_index=True)      # Reset index
```

### Merging
```python
pd.merge(df1, df2, on='key')                  # Inner join on key
pd.merge(df1, df2, on='key', how='left')      # Left join
pd.merge(df1, df2, on='key', how='outer')     # Outer join
pd.merge(df1, df2, left_on='key1', right_on='key2')  # Different key names
```

### Joining
```python
df1.join(df2, on='key')                       # Join on index
df1.join(df2, how='outer')                    # Outer join
```

---

## Time Series

### Date/Time Creation
```python
pd.date_range('2023-01-01', periods=30)      # 30 days from start
pd.date_range('2023-01-01', '2023-12-31', freq='D')  # Daily frequency
pd.to_datetime(['2023-01-01', '2023-02-01']) # Convert to datetime
```

### Time Series Operations
```python
df['date'] = pd.to_datetime(df['date'])       # Convert to datetime
df.set_index('date', inplace=True)            # Set date as index
df.resample('M').mean()                       # Monthly resampling
df.shift(1)                                   # Shift by 1 period
df.rolling(window=7).mean()                   # 7-period rolling mean
```

### Date Components
```python
df['year'] = df.index.year                    # Extract year
df['month'] = df.index.month                  # Extract month
df['day'] = df.index.day                      # Extract day
df['weekday'] = df.index.dayofweek            # Day of week (0=Monday)
```

---

## Data Visualization

### Basic Plots
```python
df['column'].plot()                           # Line plot
df['column'].hist()                           # Histogram
df.plot.scatter(x='col1', y='col2')          # Scatter plot
df.boxplot(column='col1', by='col2')         # Box plot
```

### Multiple Plots
```python
df.plot(subplots=True, figsize=(10, 8))      # Subplot for each column
df.plot(kind='bar')                          # Bar plot
df.plot(kind='barh')                         # Horizontal bar plot
```

---

## Performance Tips

### Memory Optimization
```python
# Use categorical data for repeated strings
df['category'] = df['category'].astype('category')

# Use smaller numeric types
df['int_col'] = df['int_col'].astype('int32')

# Check memory usage
df.memory_usage(deep=True)
df.info(memory_usage='deep')
```

### Efficient Operations
```python
# Use vectorized operations instead of loops
df['new_col'] = df['col1'] * df['col2']       # Good
# Instead of: df['new_col'] = [x*y for x,y in zip(df['col1'], df['col2'])]

# Use query() for complex boolean indexing
df.query('col1 > 5 and col2 < 10')          # Often faster than multiple conditions

# Use loc/iloc for explicit indexing
df.loc[mask, 'column'] = value               # Clear and fast
```

### Reading Large Files
```python
# Read in chunks
chunk_list = []
for chunk in pd.read_csv('large_file.csv', chunksize=10000):
    chunk_list.append(chunk)
df = pd.concat(chunk_list, ignore_index=True)

# Use appropriate data types when reading
df = pd.read_csv('file.csv', dtype={'col1': 'category', 'col2': 'int32'})
```

---

## Common Patterns & Examples

### Data Cleaning Pipeline
```python
def clean_data(df):
    # Remove duplicates
    df = df.drop_duplicates()
    
    # Handle missing values
    df = df.fillna(method='ffill')
    
    # Fix data types
    df['date'] = pd.to_datetime(df['date'])
    df['category'] = df['category'].astype('category')
    
    # Remove outliers
    Q1 = df['numeric_col'].quantile(0.25)
    Q3 = df['numeric_col'].quantile(0.75)
    IQR = Q3 - Q1
    df = df[~((df['numeric_col'] < (Q1 - 1.5 * IQR)) | 
              (df['numeric_col'] > (Q3 + 1.5 * IQR)))]
    
    return df
```

### Aggregation Example
```python
# Sales analysis example
sales_summary = (df.groupby(['region', 'product'])
                  .agg({
                      'sales': ['sum', 'mean', 'count'],
                      'profit': 'sum',
                      'customer_id': 'nunique'
                  })
                  .round(2))

# Flatten column names
sales_summary.columns = ['_'.join(col) for col in sales_summary.columns]
sales_summary = sales_summary.reset_index()
```

---

## Quick Reference

### Most Used Methods
- `head()`, `tail()`, `info()`, `describe()`
- `groupby()`, `merge()`, `concat()`
- `fillna()`, `dropna()`, `drop_duplicates()`
- `loc[]`, `iloc[]`, `query()`
- `apply()`, `map()`, `transform()`
- `sort_values()`, `sort_index()`
- `value_counts()`, `unique()`, `nunique()`

### Common Issues
- **SettingWithCopyWarning**: Use `.loc[]` for assignment
- **Memory issues**: Use `chunksize` or optimize data types
- **Performance**: Vectorize operations, avoid loops
- **Index confusion**: Reset index when needed with `reset_index()`

---

*Happy pandas practicing! 🐼*