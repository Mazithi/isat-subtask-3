# isat-subtask-3
#include <iostream>
#include <string>
using namespace std;

const int MAX_ORDERS = 50;

// Parallel arrays
int orderIDs[MAX_ORDERS];
string customerNames[MAX_ORDERS];
string orderDetails[MAX_ORDERS];
double totalCosts[MAX_ORDERS];
int orderCount = 0;

// Function to find order index by ID
int findOrderIndex(int id) {
    for (int i = 0; i < orderCount; i++) {
        if (orderIDs[i] == id) {
            return i;
        }
    }
    return -1;
}

// Add a new order
void addOrder() {
    if (orderCount >= MAX_ORDERS) {
        cout << "Cannot add more orders. Limit reached.\n";
        return;
    }

    int id;
    cout << "Enter Order ID: ";
    cin >> id;

    if (findOrderIndex(id) != -1) {
        cout << "Error: Order ID already exists.\n";
        return;
    }

    cin.ignore(); // Clear buffer
    cout << "Enter Customer Name: ";
    getline(cin, customerNames[orderCount]);

    cout << "Enter Order Details: ";
    getline(cin, orderDetails[orderCount]);

    cout << "Enter Total Cost (e.g., 35.00): R";
    cin >> totalCosts[orderCount];

    orderIDs[orderCount] = id;
    orderCount++;

    cout << "Order added successfully!\n";
}

// Display all orders
void displayOrders() {
    if (orderCount == 0) {
        cout << "No orders to display.\n";
        return;
    }

    double totalRevenue = 0;
    cout << "\n--- All Orders ---\n";
    for (int i = 0; i < orderCount; i++) {
        cout << "Customer Name: " << customerNames[i] << endl;
        cout << "Order ID: " << orderIDs[i] << endl;
        cout << "Order Details: " << orderDetails[i] << endl;
        cout << "Total Cost: R" << totalCosts[i] << "\n\n";
        totalRevenue += totalCosts[i];
    }
    cout << "Total Revenue: R" << totalRevenue << "\n";
}

// Find order by ID
void findOrder() {
    int id;
    cout << "Enter Order ID to search: ";
    cin >> id;

    int index = findOrderIndex(id);
    if (index == -1) {
        cout << "Error: Order ID not found.\n";
    } else {
        cout << "Customer Name: " << customerNames[index] << endl;
        cout << "Order ID: " << orderIDs[index] << endl;
        cout << "Order Details: " << orderDetails[index] << endl;
        cout << "Total Cost: R" << totalCosts[index] << endl;
    }
}

// Main menu
int main() {
    int choice;
    do {
        cout << "\n--- Magwinya Magic Order System ---\n";
        cout << "1. Add New Order\n";
        cout << "2. Display All Orders\n";
        cout << "3. Find Order by ID\n";
        cout << "4. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1:
                addOrder();
                break;
            case 2:
                displayOrders();
                break;
            case 3:
                findOrder();
                break;
            case 4: {
                cout << "Goodbye! Summing up total revenue...\n";
                double total = 0;
                for (int i = 0; i < orderCount; i++) {
                    total += totalCosts[i];
                }
                cout << "Total Revenue: R" << total << "\n";
                break;
            }
            default:
                cout << "Invalid choice. Please try again.\n";
        }
    } while (choice != 4);

    return 0;
}

 
