# Instructions
- The test consists of four sections: Coding Challenge, System Design, Code Review, Problem-Solving and SQL Skills.
- Complete the tasks in a local development environment.
- Submit your solutions as a zip file containing source code files and documentation.
- Time allotted: 8 hours.

# Section 1: Coding Challenge
## Task 1: API Development
Build a simple RESTful API using .NET Core C# that manages a list of transactions. Each transaction should have the following properties:

- AccountID
- TransactionID
- TransactionAmount
- TransactionCurrencyCode
- LocalHour
- TransactionScenario
- TransactionType
- TransactionIPaddress
- IpState
- IpPostalCode
- IpCountry
- IsProxyIP
- BrowserLanguage
- PaymentInstrumentType
- CardType
- PaymentBillingPostalCode
- PaymentBillingState
- PaymentBillingCountryCode
- ShippingPostalCode
- ShippingState
- ShippingCountry
- CvvVerifyResult
- DigitalItemCount
- PhysicalItemCount
- TransactionDateTime

**A sample with the data that can be used is provided in [Sales.txt](Sales.txt)**

The API should support the following operations:

1. Get all transactions: GET /api/transactions
2. Get a transaction by ID: GET /api/transactions/{id}
3. Add a new transaction: POST /api/transactions
4. Update a transaction: PUT /api/transactions/{id}
5. Delete a transaction: DELETE /api/transactions/{id}

**Requirements:**

- Use Dapper for data access;
- Include input validation;
- Implement appropriate error handling;
- Write at least one unit test for each operation;
- Use CQRS concepts;
- Consider Oracle as the persistent storage database.

# Section 2: System Design
## Task 2: Design a Scalable System
Design a system that can handle high traffic for a book recommendation service. The system should:

- Handle millions of users;
- Provide personalized book recommendations;
- Store user data and book metadata;
- Be scalable and highly available.

**Deliverables:**

- High-level architecture diagram (Draw.io can be used);
- Explanation of the technologies and design patterns used;
- Considerations for scalability, availability, and performance.

# Section 3: Code Review
## Task 3: Review the Following Code
You have been provided with a snippet of code below. Review it and provide feedback on potential improvements, code quality, and best practices.
```c#
public class TransactionService
{
    private readonly List<Transaction> Transactions = new List<Transaction>();

    public List<Transaction> GetTransactionByIdList(List<string> idList)
    {
        foreach (var transaction in Transactions)
        {
            foreach (var id in idList)
            {
                if (transaction.Id == id)
                {
                    return transaction;
                }
            }
        }
        return null;
    }

    public Transaction GetTransactionById(string id)
    {
        foreach (var transaction in Transactions)
        {
            if (transaction.Id == id)
            {
                return transaction;
            }
        }
        return null;
    }

    public void AddTransaction(Transaction transaction)
    {
        Transactions.Add(transaction);
    }

    public void RemoveTransaction(string id)
    {
        var transaction = GetTransactionById(id);
        if (transaction != null)
        {
            Transactions.Remove(transaction);
        }
    }
}
```

# Section 4: Problem-Solving
## Task 4: Algorithm Challenge
Write a C# function that checks if a string or a phrase is a palindrome.

**Function Signature:**
```c#
public bool CheckPalindrome(string value);
```

**Example:**
```
Input: "rotor"
Output: true

Input: "motor"
Output: false
```

**Requirements:**

- Optimize for time and space complexity;
- Use a recursive strategy;
- Provide a brief explanation of your approach.

# Section 5: SQL Skills
## Task 5: Complex PL/SQL Query
Consider the following database objects structure:

**Customers Table:**
- customer_id (NUMBER) - Unique identifier for each customer.
- name (VARCHAR2) - Name of the customer.
- email (VARCHAR2) - Email of the customer.
- created_date (DATE) - The date the customer was created.

**Orders Table:**
- order_id (NUMBER) - Unique identifier for each order.
- customer_id (NUMBER) - The ID of the customer who placed the order.
- order_date (DATE) - The date the order was placed.
- total_amount (NUMBER) - The total amount of the order.

**Order_Items Table:**
- order_item_id (NUMBER) - Unique identifier for each order item.
- order_id (NUMBER) - The ID of the order to which this item belongs.
- product_id (NUMBER) - The ID of the product.
- quantity (NUMBER) - The quantity of the product ordered.
- price (NUMBER) - The price of the product.

**Products Table:**
- product_id (NUMBER) - Unique identifier for each product.
- product_name (VARCHAR2) - Name of the product.
- category (VARCHAR2) - Category of the product.

**Requirements**
1. Write a PL/SQL block that retrieves the top 5 customers who have spent the most money on orders in the last 6 months. For each of these customers, retrieve the following details:
- Customer ID
- Customer Name
- Total Amount Spent
- The list of product names they purchased and their respective quantities

2. Detailed Explanation: Include comments in your PL/SQL code explaining each step.

## Deliverables
- A SQL file containing the PL/SQL block.
- Any assumptions or considerations taken.
- Include test data insertion scripts if necessary to demonstrate the functionality.

Example Output
```yaml
Customer ID: 123
Customer Name: John Doe
Total Amount Spent: $5000
Products Purchased:
    - Product A: 5 units
    - Product B: 3 units

Customer ID: 456
Customer Name: Jane Smith
Total Amount Spent: $4500
Products Purchased:
    - Product C: 2 units
    - Product D: 4 units
    ...
```

---

## Submission
Please zip your solutions and submit them via e-mail to the sender provided during the interview. Include a README file with instructions on how to run your code and any other relevant information.

## Evaluation Criteria
- Correctness and completeness of solutions;
- Code quality and readability;
- Adherence to best practices and design patterns;
- Effective use of .NET Core features;
- Problem-solving skills and algorithmic efficiency;
- Clarity and thoroughness of documentation and explanations.
