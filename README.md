How to Run the Project
To run the Pizza Delivery API locally, first ensure you have Python 3.11 and PostgreSQL installed on your machine. Clone the repository using:

bash
Copy
Edit
git clone https://github.com/jod35/Pizza-Delivery-API.git
Navigate into the project directory. Create and activate a virtual environment, then install the required dependencies with:

bash
Copy
Edit
pip install -r requirements.txt
Next, set up your PostgreSQL database and create a new database (e.g., pizzadb). Update the database connection URI in database.py to match your PostgreSQL credentials. Create a .env file in the project root with your database URL and a secret key for authentication:

env
Copy
Edit
DATABASE_URL=postgresql://postgres:yourpassword@localhost/pizzadb
SECRET_KEY=your_secret_key_here
Initialize the database tables by running:

bash
Copy
Edit
python init_db.py
Finally, start the FastAPI server using:

bash
Copy
Edit
uvicorn main:app --reload
Access the interactive API documentation at http://127.0.0.1:8000/docs to test the endpoints.

API Routes
Method	Route	Functionality	Access
POST	/auth/signup/	Register new user	All users
POST	/auth/login/	Login user	All users
POST	/orders/order/	Place an order	All users
PUT	/orders/order/update/{order_id}/	Update an order	All users
PUT	/orders/order/status/{order_id}/	Update order status	Superuser
DELETE	/orders/order/delete/{order_id}/	Delete/Remove an order	All users
GET	/orders/user/orders/	Get user's orders	All users
GET	/orders/orders/	List all orders	Superuser
GET	/orders/orders/{order_id}/	Retrieve an order	Superuser
GET	/orders/user/order/{order_id}/	Get user's specific order	All users
GET	/docs/	View API documentation	All users
