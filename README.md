# Budget Manager

The Budget Manager is a Python module designed to help users manage their budgets by providing a simple and intuitive way to track expenses across different categories. This module consists of a `Category` class for managing individual budget categories and a `create_spend_chart` function for visualizing spending patterns across multiple categories.

## Features

- **Category Class**: The `Category` class allows users to create and manage budget categories. Each category maintains a ledger of transactions, including deposits and withdrawals. Users can perform operations such as deposit, withdraw, transfer funds between categories, and check the current balance.

- **Visualization**: The `create_spend_chart` function generates a bar chart that visually represents the percentage of spending in each category. This chart helps users understand their spending habits and identify areas where they may need to adjust their budgets.

## Usage

### Category Class

To create a new budget category, instantiate the `Category` class with the desired category name:

```python
food_category = Category("Food")
```

Once a category is created, you can perform various operations on it:

- **Deposit**: Add funds to the category ledger.

```python
food_category.deposit(100, "Groceries")
```

- **Withdraw**: Deduct funds from the category ledger.

```python
food_category.withdraw(50, "Dinner")
```

- **Transfer**: Transfer funds between categories.

```python
clothing_category = Category("Clothing")
food_category.transfer(25, clothing_category)
```

- **Get Balance**: Retrieve the current balance of the category.

```python
balance = food_category.get_balance()
```

### create_spend_chart Function

The `create_spend_chart` function takes a list of `Category` instances as input and returns a string representing a bar chart showing the percentage of spending in each category.

```python
categories = [food_category, clothing_category]
chart = create_spend_chart(categories)
print(chart)
```

## Example

```python
# Create budget categories
food_category = Category("Food")
clothing_category = Category("Clothing")

# Perform transactions
food_category.deposit(1000, "Initial deposit")
food_category.withdraw(10.15, "Groceries")
food_category.withdraw(15.89, "Restaurant")
food_category.transfer(50, clothing_category)

# Generate spending chart
categories = [food_category, clothing_category]
chart = create_spend_chart(categories)
print(chart)
```

Output:
```
Percentage spent by category
100|          
 90|          
 80|          
 70|          
 60| o        
 50| o        
 40| o        
 30| o        
 20| o  o     
 10| o  o  o  
  0| o  o  o  
    ----------
     F  C     
     o  l     
     o  o     
     d  t     
        h     
        i     
        n     
        g     
```

## Contributing

Contributions are welcome! If you encounter any issues or have suggestions for improvements, please open an issue on GitHub or submit a pull request.
