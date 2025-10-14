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

 What Is This Code Meant For?
This program is designed to help a fictional business called Magwima Magic manage customer orders. It stores and displays:
• 	The Order ID
• 	The Customer’s name
• 	The Number of Magwimas ordered
• 	The Total amount paid

 
These lines tell the computer:
• 	“I want to use input/output tools” like  to print things.
• 	“I want to use text (string) data” for customer names.


 We have 3 orders, so our arrays will hold 3 items.
This makes it easy to change the size later if needed.
use parallel arrays to store different parts of each order:
• 	 holds the order numbers.
• 	 holds the names.
• 	 holds how many Magwimas were ordered.
• 	 holds the total cost.
Each array uses the same index to match the data:
• 	Index  = Lerato’s order
• 	Index  = Nomvula’s order
• 	Index  = Sipho’s order

This loop repeats the same block of code three times (because SIZE is 3). Each time, it uses a different index  to access the next order.
 What the loop does:
• 	First time (): shows Lerato’s order
• 	Second time (): shows Nomvula’s order
• 	Third time (): shows Sipho’s order
Without a loop, you would  have to write the same  code three times manually. That is slow and hard to update.
With a loop, you write a code once, and it repeats automatically.
