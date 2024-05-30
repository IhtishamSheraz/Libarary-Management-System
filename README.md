# Libarary-Management-System
#include <iostream>
#include <string>
using namespace std;
struct library
{
    string book_name;
    string author;
    int pages;
    float price;
};
int main()
{
    library lib[100] =
    {
        {"The Forty Rules of Love", "Elif Shafak", 368, 10.99},
        {"The Bastard of Istanbul", "Elif Shafak", 368, 12.99},
        {"The Architect's Apprentice", "Elif Shafak", 464, 14.99},
        {"Three Daughters of Eve", "Elif Shafak", 384, 13.99},
        {"10 Minutes 38 Seconds in This Strange World", "Elif Shafak", 320, 15.99},
        {"Payam-e-Mashriq", "Iqbal", 200, 8.50},
        {"Javid Nama", "Iqbal", 180, 7.99},
        {"1984", "George Orwell", 328, 9.99},
        {"Animal Farm", "George Orwell", 112, 5.99},
        {"Twisted Love", "Ana Huang", 338, 11.99},
        {"Twisted Games", "Ana Huang", 400, 13.99},
        {"Twisted Lies", "Ana Huang", 576, 14.99},
        {"Twisted Hate", "Ana Huang", 512, 14.99},
        {"Twisted Emotions", "Cora Reilly", 322, 10.99},
        {"Twisted Pride", "Cora Reilly", 368, 11.99},
        {"Twisted Loyalties", "Cora Reilly", 320, 10.99},
        {"The Love Hypothesis", "Ali Hazelwood", 384, 16.99},
        {"Love on the Brain", "Ali Hazelwood", 368, 15.99},
        {"Under One Roof", "Ali Hazelwood", 112, 7.99},
        {"The Wrong Bride", "Catharina Maura", 330, 12.99},
        {"The Ties That Bind", "Catharina Maura", 350, 13.99},
        {"Devils Bargain", "Catharina Maura", 340, 12.99},
    };
    string ar_nm, bk_nm;
    int input, count;
    count = 23;
    while (true)
    {
        cout << "\n\n****######"
            << "WELCOME TO E-LIBRARY "
            << "#####****\n";
        cout << "\n\n1. Add book information\n2. Display book information\n";
        cout << "3. List all books of given author\n";
        cout << "4. List the count of books in the library\n";
        cout << "5. Exit\n";
        cout << "\n\nEnter one of the above: ";
        cin >> input;
        cin.ignore();
        switch (input)
        {
        case 1:
            if (count >= 100)
            {
                cout << "Library is full, cannot add more books.\n";
                break;
            }
            cout << "Enter book name: ";
            getline(cin, lib[count].book_name);
            cout << "Enter author name: ";
            getline(cin, lib[count].author);
            cout << "Enter pages: ";
            cin >> lib[count].pages;
            cout << "Enter price: ";
            cin >> lib[count].price;
            cin.ignore();
            count++;
            break;
        case 2:
            cout << "You have entered the following information\n";
            for (int i = 0; i < count; i++)
            {
                cout << "Book name: " << lib[i].book_name;
                cout << "\tAuthor name: " << lib[i].author;
                cout << "\tPages: " << lib[i].pages;
                cout << "\tPrice: " << lib[i].price << endl;
            }
            break;
        case 3:
            cout << "Enter author name: ";
            getline(cin, ar_nm);
            {
                bool found = false;
                for (int i = 0; i < count; i++)
                {
                    if (ar_nm == lib[i].author)
                    {
                        cout << "Book name: " << lib[i].book_name;
                        cout << "\tAuthor name: " << lib[i].author;
                        cout << "\tPages: " << lib[i].pages;
                        cout << "\tPrice: " << lib[i].price << endl;
                        found = true;
                    }
                }
                if (!found)
                {
                    cout << "No books found by author " << ar_nm << endl;
                }
            }
            break;
        case 4:
            cout << "\nNumber of books in library: " << count << endl;
            break;
        case 5:
            return 0;
        default:
            cout << "Invalid input, please try again.\n";
        }
    }
}
