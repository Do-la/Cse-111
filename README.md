#include <iostream>
#include <string>
using namespace std;

class BankUser {
public:
    string name;
    double balance;
    double fdr_amount;
    double dps_amount;

    BankUser(string n) {
        name = n;
        balance = 1000; 
        fdr_amount = 0;
        dps_amount = 0;
    }

    void deposit(double amount) {
        balance += amount;
        cout << name << " deposited " << amount << endl;
    }

    void withdraw(double amount) {
        if (amount > balance) {
            cout << name << " does not have enough money!" << endl;
        } else {
            balance -= amount;
            cout << name << " withdrew " << amount << endl;
        }
    }

    void openFDR(double amount) {
        if (amount > balance) {
            cout << name << " cannot open FDR. Not enough money." << endl;
        } else {
            balance -= amount;
            fdr_amount = amount * 1.07; 
            cout << name << " opened FDR. Will get back " << fdr_amount << endl;
        }
    }

    void openDPS(double monthly_amount, int months) {
        double total = monthly_amount * months;
        dps_amount = total * 1.05; 
        cout << name << " opened DPS. Will get back " << dps_amount << endl;
    }
};

int main() {
    
    BankUser users[10] = {
        BankUser("User1"),
        BankUser("User2"),
        BankUser("User3"),
        BankUser("User4"),
        BankUser("User5"),
        BankUser("User6"),
        BankUser("User7"),
        BankUser("User8"),
        BankUser("User9"),
        BankUser("User10")
    };

   

    return 0;
}
