# Requirements

- Create a new project in Net that exposes the following functionality using an RESTful API 
    - Create a customer
    - Get the customer based on an identifier
    - Create a loyalty card for the customer
- Create a UnitTest project to test our functionality of our customer service
- Use Postman or other way to test our API

# Entities example
```C# Example of entities
public class Customer
{
    public Guid Id { get; set; } // Unique identifier for the customer
    public string CustomerNumber { get; set; } // Unique customer number
    public string Name { get; set; } // Name of the customer
    public List<LoyaltyCard> LoyaltyCards { get; set; } // List of loyalty cards associated with the customer
}

public class LoyaltyCard
{
    public Guid Id { get; set; } // Unique identifier for the loyalty card
    public string CardNumber { get; set; } // Card number of the loyalty card
    public DateTime IssueDate { get; set; } // Date when the card was issued
}
```

# Acceptance criteria
```
Scenario: Creating a customer
    Given a new customer with valid data
    When the CreateCustomer method is called
    Then the customer should be created

Scenario: Getting a customer based on an identifier
    Given a customer with a known identifier
    When the GetCustomerById method is called with the identifier
    Then the customer with the specified identifier should be returned

Scenario: Creating a loyalty card for the customer
    Given an existing customer with valid data
    And a new loyalty card with valid data
    When the CreateLoyaltyCardForCustomer method is called
    Then the loyalty card should be associated with the customer
```

## Data used for testing
```C#
var customer1 = new Customer
{
    Id = Guid.NewGuid(),
    CustomerNumber = "CUST12345",
    Name = "John Doe",
    LoyaltyCards = new List<LoyaltyCard>
    {
        new LoyaltyCard
        {
            Id = Guid.NewGuid(),
            CardNumber = "CARD98765",
            IssueDate = DateTime.Parse("2023-12-08")
        }
    }
};
```
