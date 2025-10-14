# isat-subtask-3
//Mhloli Mazithi
//0408080954089
#include <iostream>
#include <string>
using namespace std;

// we only have 3 orders for now
const int SIZE = 3;

// Arrays to store order information
int orderIDs[SIZE] = {102, 103, 104};
string customerNames[SIZE] = {"Lerato", "Nomvula", "Sipho"};
int numMagwimas[SIZE] = {6, 5, 4};
float totalAmounts[SIZE] = {30.00, 10.00, 22.00};

int main() {
    cout << "Magwima Magic Orders:\n\n";

    // Loop through each order and display the details
    for (int i = 0; i < SIZE; i++) {
        cout << "Order ID: " << orderIDs[i] << endl;
        cout << "Customer Name: " << customerNames[i] << endl;
        cout << "Magwimas Ordered: " << numMagwimas[i] << endl;
        cout << "Total Amount: R" << totalAmounts[i] << endl;
        cout << "-----------------------------\n";
    }

    return 0;
}

