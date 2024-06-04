# Cat Facts API Tests

This project contains tests for the Cat Facts API using pytest.

## Table of Contents
- [Setup](#setup)
- [Test Cases](#test-cases)

## Setup
1. Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```

2. Run the tests:
    ```bash
    pytest
    ```

## Test Cases

| Test Case Name         | Description                                                                                                                     | Steps                                                                                                                                                                                                                                                                                             | Expected Results                                                                                         |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| `test_check_limits`    | Test to check limits for fetching random facts.                                                                                 | 1. **Positive**: Fetch 500 facts using `/facts/random?amount=500`. <br> 2. **Negative**: Fetch 501 facts using `/facts/random?amount=501`.                                                                                                                  | 1. Status code should be 200. <br> 2. Status code should be 405. Message should be "Limited to 500 facts at a time".                            |
| `test_check_facts_id`  | Test to verify that a fact can be correctly retrieved by its ID.                                                                | 1. Get a random fact using `/facts/random` and save its ID and text. <br> 2. Fetch the fact by ID using `/facts/{factID}`. <br> 3. Compare the ID and text from both responses.                                                                              | Texts and IDs from step 1 and step 2 should be the same.                                                  |
