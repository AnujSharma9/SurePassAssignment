# SurePassAssignment

Bill Management System
A simple and efficient web-based bill management system to generate bills, download invoices, and manage customer data using React, Redux, and Bootstrap.

Features
Bill Generation: Generate bills with customizable inputs (customer information, phone, and bill details).
Success Modal: Display success messages upon successful bill generation.
Invoice Download: Ability to download generated invoices.
Customer Data Management: Add the bill data to the customer list after successful generation.
State Management: Redux is used to manage the application state (bill generation, customer data).
Responsive UI: Clean and responsive UI using Bootstrap for mobile and desktop views.
Technologies Used
Frontend: React.js
State Management: Redux
CSS Framework: Bootstrap
Routing: React Router
Toast Notifications: React Toastify
Installation
Follow these steps to run the project locally:

1. Clone the repository
bash
Copy code
git clone https://github.com/your-username/bill-management.git
cd bill-management
2. Install dependencies
Make sure you have Node.js installed. Then, run the following command to install the required dependencies:

bash
Copy code
npm install
or if you use Yarn:

bash
Copy code
yarn install
3. Run the app
Once the installation is complete, start the development server:

bash
Copy code
npm start
or if you use Yarn:

bash
Copy code
yarn start
The app should now be running at http://localhost:3000.

How to Use
Generate a Bill:

Enter the customer details (name, phone number, etc.).
Fill in the bill details and click the "Generate Bill" button.
A success modal will appear with a success message.
The generated bill data will be saved and can be viewed in the customer list.
Download the Invoice:

After the bill is generated, click on the "Download Invoice" button to download the invoice as a PDF or other file format (implementation pending).
Redux State Management
This application uses Redux to manage the state for customer data and bill generation:

Action:
The action to add customer details is dispatched when a new bill is generated.
Reducer:
customerReducer handles the customer list and updates the store when new customer data is added.
Example of Redux Action:
javascript
Copy code
export const addCustomer = (customer) => ({
  type: 'ADD_CUSTOMER',
  payload: customer,
});
Example of Redux Reducer:
javascript
Copy code
const initialState = {
  customers: [],
};

const customerReducer = (state = initialState, action) => {
  switch (action.type) {
    case 'ADD_CUSTOMER':
      return {
        ...state,
        customers: [...state.customers, action.payload],
      };
    default:
      return state;
  }
};

export default customerReducer;
