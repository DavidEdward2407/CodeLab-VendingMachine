#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    // item names
    string items[9] = {"Water", "Coca-Cola", "Fuzetea", "Mars", "Snickers", "Kinder", "Crisps", "Popcorn", "Biscuits"};
    // item prices
    double prices[9] = {1.00, 2.00, 2.00, 1.30, 1.30, 1.50, 0.85, 1.15, 1.00};
    // item codes
    string codes[9] = {"A1", "A2", "A3", "B1", "B2", "B3", "C1", "C2", "C3"};
    // item stock
    int stock[9] = {5, 5, 5, 5, 5, 5, 5 ,5 ,5};

    string inputCode;
    double money;
    char another;
    char pound = 156; // used ASCII caracters to display the pound symbol

    do {
        // display the menu
        cout << "\n--- Vending Machine Menu ---\n";
        for (int i = 0; i < 9; i++) {
            cout << codes[i] << " - " << items[i] << " - " << pound << fixed << setprecision(2) << prices[i];
            if (stock[i] == 0) cout << " [Out of Stock]";
            cout << endl;
        }

        // ask for item code
        cout << "\nEnter item code: ";
        cin >> inputCode;

        // find the item
        int index = -1;
        for (int i = 0; i < 9; i++) {
            if (inputCode == codes[i]) {
                index = i;
                break;
            }
        }

        if (index == -1) {
            cout << "Invalid code. Try again.\n";
            continue;
        }

        if (stock[index] == 0) {
            cout << "Sorry, " << items[index] << " is out of stock.\n";
            continue;
        }

        // input the money value 
        cout << "Insert money ("<< pound<< "): ";
        cin >> money;

        if (money < prices[index]) {
            cout << "Not enough money. " << items[index] << " costs "<< pound << prices[index] << ".\n";
            continue;
        }

        // dispense item and calculate change 
        stock[index]--;
        double change = money - prices[index];
        cout << "Dispensing " << items[index] << "...\n";
        cout << "Here's your change: "<<pound<< fixed << setprecision(2) << change << "\n";

        // ask to buy something else 
        cout << "\nWant to buy something else? (y/n): ";
        cin >> another;

    } while (another == 'y' || another == 'Y');

    cout << "Thank you for your purchase. Please come again.\n";
    return 0;
}
