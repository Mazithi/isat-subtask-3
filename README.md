# isat-subtask-3
//Mhloli Mazithi
//0408080954089
#include <iostream>
using namespace std;

const int MAX_ORDERS = 50;
int orderIDs[MAX_ORDERS];
string customerNames[MAX_ORDERS];
string orderDetails[MAX_ORDERS];
float totalCosts[MAX_ORDERS];
int orderCount = 0;

void addOrder() {
    if (orderCount >= MAX_ORDERS) {
        cout << "Error: Maximum number of orders reached.\n";
        return;
    }

    int id;
    cout << "Enter Order ID: ";
    cin >> id;

    // Check for duplicate ID
    for (int i = 0; i < orderCount; i++) {
        if (orderIDs[i] == id) {
            cout << "Error: Order ID already exists.\n";
            return;
        }
    }

    cin.ignore(); // Clear input buffer
    string name, details;
    float cost;

    cout << "Enter Customer Name: ";
    getline(cin, name);
    cout << "Enter Order Details: ";
    getline(cin, details);
    cout << "Enter Total Cost: R";
    cin >> cost;

    // Store data
    orderIDs[orderCount] = id;
    customerNames[orderCount] = name;
    orderDetails[orderCount] = details;
    totalCosts[orderCount] = cost;
    orderCount++;

    cout << "Order added successfully!\n";
}

void displayOrders() {
    if (orderCount == 0) {
        cout << "No orders to display.\n";
        return;
    }

    cout << "\nOrderID\tCustomerName\tOrderDetails\tTotalCost\n";
    for (int i = 0; i < orderCount; i++) {
        cout << orderIDs[i] << "\t" << customerNames[i] << "\t\t"
             << orderDetails[i] << "\t\tR" << totalCosts[i] << endl;
    }
}

void findOrder() {
    int searchID;
    cout << "Enter Order ID to search: ";
    cin >> searchID;

    for (int i = 0; i < orderCount; i++) {
        if (orderIDs[i] == searchID) {
            cout << "\nOrder Found:\n";
            cout << "Order ID: " << orderIDs[i] << "\n";
            cout << "Customer Name: " << customerNames[i] << "\n";
            cout << "Order Details: " << orderDetails[i] << "\n";
            cout << "Total Cost: R" << totalCosts[i] << "\n";
            return;
        }
    }

    cout << "Error: Order ID not found.\n";
}

int main() {
    int choice;

    do {
        cout << "\n--- Magwiyas Magic Order System ---\n";
        cout << "1. Add New Order\n";
        cout << "2. Display All Orders\n";
        cout << "3. Find Order by ID\n";
        cout << "4. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1: addOrder();
            break;
            case 2: displayOrders();
            break;
            case 3: findOrder();
            break;
            case 4: cout << "Thank you for using the system.\n";
            break;
            default: cout << "Invalid choice. Try again.\n";
        }
    } while (choice != 4);

    return 0;
}
