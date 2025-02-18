
# Pydantic Example: Building a Simple Custom Class & AI Agent Integration

This repository demonstrates how to use **Pydantic** for data validation and defines custom classes that model real-world scenarios, such as user data management. It also includes a practical example of integrating Pydantic with an AI agent built using the `pydantic-ai` library to provide customer support services.

## Table of Contents

- [Pydantic Example: Creating a Simple Custom Class](#pydantic-example-creating-a-simple-custom-class)
- [Handling Validation Errors in Pydantic](#handling-validation-errors-in-pydantic)
- [Building an AI Agent with Pydantic](#building-an-ai-agent-with-pydantic)

---

## Pydantic Example: Creating a Simple Custom Class

This example shows how to use **Pydantic's** `BaseModel` to create a custom class. The class, `User`, models a user with fields like `id`, `name`, `signup_ts` (a timestamp), and `tastes` (a dictionary of user preferences with associated ratings). The code demonstrates how to handle incoming data, such as converting timestamp strings to `datetime` objects and validating the values in the dictionary.

In this scenario, `Pydantic` ensures that the `id` is an integer and the `tastes` dictionary contains valid `PositiveInt` values. The example uses `model_dump()` to view the final validated model data.

---

## Handling Validation Errors in Pydantic

This section demonstrates how **Pydantic** handles validation errors. If invalid data is passed into the `User` class (for example, a string value where an integer is expected), **Pydantic** will raise a `ValidationError`. This error will detail which field had an issue and why, such as an incorrect data type or missing required fields. The example shows how these errors can be caught and displayed with detailed messages for debugging purposes.

---

## Building an AI Agent with Pydantic

In this example, **Pydantic** is used to define the structure of a **customer support AI agent** powered by the `pydantic-ai` library. The `Agent` class is created by specifying the input dependencies and the result type, both of which are defined using **Pydantic** models. This allows the AI agent to validate and process customer queries in a structured manner.

The example includes a **SupportDependencies** class that holds customer data and a **SupportResult** class that defines the expected structure of the response. The agent uses a system prompt to simulate the role of a bank's customer support system, processing queries about account balances and lost cards. It also includes tools that interact with a database (mocked by the `DatabaseConn` class) to retrieve customer information.

The AI agent's functionality is demonstrated with different customer queries, and it returns structured responses that include advice, the status of the customer’s card, and a risk rating based on the query.

---

## How to Run

1. Install the required dependencies using the following command:

    ```bash
    pip install pydantic pydantic-ai
    ```

2. Create or adjust your custom database connection (`bank_database.py`) to interact with the AI agent.

3. Run the script and observe the AI agent in action, processing different customer queries and providing responses.

---

## Contributing

Feel free to fork the repository, submit issues, or create pull requests to improve the examples or add new ones.

---

Read the full blog [Learn Pydantic AI by ProjectPro](https://www.projectpro.io/article/pydantic-ai/1088) for a detailed explanation.
