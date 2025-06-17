# DummyJson E-Commerce API Testing

This project is a hands-on QA portfolio showcasing API testing skills using Postman on the [DummyJson E-Commerce API](https://dummyjson.com).

## Objectives

- Perform end-to-end testing on dummy e-commerce API endpoints.
- Use Postman features like environments, variables, test scripts, pre-request scripts, and CSV data.
- Validate API behavior using assertions and chaining.

--------------------------

## Folder Structure

| Folder | Description |
|--------|-------------|
| `Postman/` | Contains the collection JSON and test data file |
| `Scripts/` | Postman scripting method notes |

--------------------------

## How to Run

### 1. Import Collection
- Open Postman.
- Click `Import` > Choose `DummyJson E-Commerce.postman_collection.json`.

### 2. Set Environment Variable
- Add a variable called `baseurl` with the value:  

### 3. Use Dynamic Variables
- The collection uses dynamic data generation (`{{$randomFirstName}}`).
- Environment values like `token`, `Id`, `sentName` are set programmatically.

### 4. Run Collection
- Use `Runner` to run all test cases.
- Optional: Load test data via CSV if applicable.

--------------------

## Key API Tests Covered

### ✅ Authentication
- Login and store access token dynamically.

### 👤 Users
- Get all users
- Get user by ID
- Search, filter, pagination
- Add, update, delete users
- Validations like:
- Email format using RegEx
- Response time under 800ms

### 🛍️ Products
- Get products (all/single)
- Validate `title`, `price`, `brand`
- Use of CSV data
- Search, filter, limit, sort

### 🛒 Cart
- Add to cart
- Get user cart
- Update/delete cart

-----------------------------

## Sample Assertions Used

pm.test("Status is 200", () => {
pm.response.to.have.status(200);
});

pm.test("Price is a number", () => {
let res = pm.response.json();
pm.expect(res.price).to.be.a('number');
});
