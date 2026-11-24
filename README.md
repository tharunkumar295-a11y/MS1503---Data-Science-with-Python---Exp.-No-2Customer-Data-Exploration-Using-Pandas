# Experiment 2 : Customer Data Exploration Using Pandas

## Aim
To create a sample customer dataset and perform data exploration, filtering, sorting, grouping, and basic statistical analytics using Pandas functions in Python.

## Algorithm

1. **Start** the program.
2. **Import Library**: Import the `pandas` library as `pd` for tabular data manipulation and analysis.
3. **Initialize Dataset**: Create a Python dictionary `data` containing customer attributes (`Customer_ID`, `Customer_Name`, `Region`, `Age`, `Annual_Income`, `Spending_Score`, `Loyalty_Years`).
4. **Construct DataFrame**: Convert the dictionary into a structured Pandas DataFrame `df` using `pd.DataFrame(data)` and print the dataset.
5. **Inspect Structure & Summary**:
   * Display dataset dimensions (`df.shape`), column names (`df.columns`), data types and null counts (`df.info()`), and descriptive statistics (`df.describe()`).
   * Display the first 3 records (`df.head(3)`) and last 3 records (`df.tail(3)`).
6. **Sort & Filter Records**:
   * Sort customers in descending order of `Annual_Income` using `df.sort_values()`.
   * Filter high-income customers where `Annual_Income > 70000`.
7. **Perform Group-Wise & Frequency Analysis**:
   * Group customers by `Region` and calculate regional averages for `Annual_Income` and `Spending_Score` using `df.groupby().mean()`.
   * Count customer distribution across each region using `df["Region"].value_counts()`.
8. **Compute Overall Metrics & Top Performer**:
   * Identify the customer record with the highest `Spending_Score` using `df["Spending_Score"].idxmax()` and `df.loc[]`.
   * Calculate overall mean `Annual_Income` and mean `Spending_Score`.
9. **Stop** the program.

## Functions and Methods Used

| Category | Function / Method | Purpose / Description |
| :--- | :--- | :--- |
| **Data Creation** | `pd.DataFrame()` | Converts a Python dictionary into a 2D labeled tabular DataFrame |
| **Structural Inspection** | `df.shape`, `df.columns` | Retrieves dimensions `(rows, columns)` and column labels |
| | `df.info()`, `df.describe()` | Summarizes column data types, memory usage, and descriptive statistics |
| | `df.head(n)`, `df.tail(n)` | Views the first `n` and last `n` rows of the dataset |
| **Sorting & Filtering** | `df.sort_values()` | Orders records by `Annual_Income` in descending order |
| | Boolean Indexing (`df[...]`) | Filters customers with `Annual_Income > 70000` |
| **Grouping & Aggregation** | `df.groupby().mean()` | Aggregates mean income and spending score per `Region` |
| | `df["Region"].value_counts()` | Counts occurrences of customers in each region |
| | `idxmax()`, `df.loc[]`, `.mean()` | Locates the top spender row and computes dataset-wide averages |

## Program

#Customer Data Exploration using Pandas

#Step 1: Create a sample customer dataset

#Step 2: Convert to a Pandas DataFrame

#Step 3: Basic exploration

#Step 4: Display first and last few records

#Step 5: Sort customers by Annual Income (descending)

#Step 6: Filter high-income customers (Income > 70000)

#Step 7: Group customers by Region and find average Income and Spending Score

#Step 8: Count number of customers in each Region

#Step 9: Identify customer with maximum Spending Score

#Step 10: Compute overall averages

# Customer Data Exploration using pandas (Default Values)
import pandas as pd

# Step 1: Create a sample Customer dataset
data = {
    "Customer_ID": [101, 102, 103, 104, 105, 106, 107, 108],
    "Customer_Name": ["Anita", "Rajesh", "Priya", "Vikram", "Divya", "Manoj", "Sita", "Amit"],
    "Region": ["North", "South", "East", "West", "North", "South", "East", "West"],
    "Age": [25, 32, 41, 29, 35, 45, 28, 40],
    "Annual_Income": [55000, 72000, 61000, 48000, 85000, 90000, 64000, 58000],
    "Spending_Score": [78, 62, 45, 88, 92, 55, 70, 60],
    "Loyalty_years": [2, 5, 4, 3, 6, 7, 3, 4]
}

# Step 2: Convert to a Pandas DataFrame
df = pd.DataFrame(data)
print("--- CUSTOMER DATASET ---")
print(df)

# Step 3: Basic exploration
print("\nShape of Dataset:", df.shape)
print("Columns:", df.columns.tolist())
print("\n--- Dataset Info ---")
df.info()

# Step 4: Display first and last few records
print("\n--- First 3 Records ---")
print(df.head(3))
print("\n--- Last 3 Records ---")
print(df.tail(3))

# Step 5: Sort customers by Annual Income (descending)
print("\n--- Sorted by Annual Income (Descending) ---")
print(df.sort_values(by="Annual_Income", ascending=False))

# Step 6: Filter high-income customers (Income > 70000)
print("\n--- High Income Customers (Income > 70000) ---")
print(df[df["Annual_Income"] > 70000][["Customer_Name", "Annual_Income"]])

# Step 7: Group customers by Region and find average Income and Spending Score
print("\n--- Average Income and Spending Score by Region ---")
print(df.groupby("Region")[["Annual_Income", "Spending_Score"]].mean())

# Step 8: Count number of customers in each Region
print("\n--- Customer Count per Region ---")
print(df["Region"].value_counts())

# Step 9: Identify customer with maximum Spending Score
print("\n--- Customer with Maximum Spending Score ---")
max_spender = df.loc[df["Spending_Score"].idxmax()]
print(max_spender)

# Step 10: Compute overall averages
print("\n--- Overall Averages ---")
print("Average Annual Income:", df["Annual_Income"].mean())
print("Average Spending Score:", df["Spending_Score"].mean())

## Output

<img width="1276" height="515" alt="image" src="https://github.com/user-attachments/assets/a6324f80-e7d7-4aea-bbed-42b69fc3e310" />
<img width="801" height="475" alt="image" src="https://github.com/user-attachments/assets/4ccce272-2239-48ca-9385-fec2cda41071" />
<img width="918" height="585" alt="image" src="https://github.com/user-attachments/assets/b5e96f9e-82b0-4d20-b90f-f153c4defdd8" />
<img width="756" height="687" alt="image" src="https://github.com/user-attachments/assets/bee2ac38-066e-4c1b-bbb0-7a1fda7cfb3c" />
<img width="737" height="301" alt="image" src="https://github.com/user-attachments/assets/3d682909-f66d-4ebc-9839-fa04369d1464" />


## Result
The program successfully creates a customer dataset using Pandas and performs exploratory analysis, sorting, filtering, regional grouping, and summary statistics.
