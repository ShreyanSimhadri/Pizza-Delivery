Pizza Delivery API
A FastAPI-based backend API for managing pizza orders, user authentication, and order tracking.

To run the Pizza Delivery API locally, first ensure you have Python 3.11 and PostgreSQL installed on your machine.

Navigate into the project directory. Create and activate a virtual environment, then install the required dependencies with:

pip install -r requirements.txt

Next, set up your PostgreSQL database and create a new database (e.g., pizzadb). Update the database connection URI in database.py to match your PostgreSQL credentials. Create a .env file in the project root with your database URL and a secret key for authentication:

DATABASE_URL=postgresql://postgres:yourpassword@localhost/pizzadb
SECRET_KEY=your_secret_key_here

Initialize the database tables by running:

python init_db.py

Finally, start the FastAPI server using:

uvicorn main:app --reload

Access the interactive API documentation at http://127.0.0.1:8000/docs to test the endpoints.

API Routes
Method: POST
Route: /auth/signup/
Functionality: Register new user
Access: All users

Method: POST
Route: /auth/login/
Functionality: Login user
Access: All users

Method: POST
Route: /orders/order/
Functionality: Place an order
Access: All users

Method: PUT
Route: /orders/order/update/{order_id}/
Functionality: Update an order
Access: All users

Method: PUT
Route: /orders/order/status/{order_id}/
Functionality: Update order status
Access: Superuser

Method: DELETE
Route: /orders/order/delete/{order_id}/
Functionality: Delete/Remove an order
Access: All users

Method: GET
Route: /orders/user/orders/
Functionality: Get user's orders
Access: All users

Method: GET
Route: /orders/orders/
Functionality: List all orders
Access: Superuser

Method: GET
Route: /orders/orders/{order_id}/
Functionality: Retrieve an order
Access: Superuser

Method: GET
Route: /orders/user/order/{order_id}/
Functionality: Get user's specific order
Access: All users

Method: GET
Route: /docs/
Functionality: View API documentation
Access: All users

