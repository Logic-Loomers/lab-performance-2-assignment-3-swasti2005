Assume you oversee a small library and would like to develop a program that looks up books using their ISBNs. A list of books with their corresponding ISBN digits is in front of you. After the librarian inputs an ISBN, your software will look through the list to locate the relevant book.  The book's title and other details will be shown if the book is located. A notice stating that the book is not available in the library will appear if it cannot be located.
#include <iostream>
#include <map>
#include <string>
using namespace std;

struct Book {
    string isbn;
    string title;
};

int main() {
    
    cout << "Name- Swasti" << endl;
    cout << "Roll no.- 2310997292" << endl;
    cout << endl;
    
    // Create a list of books with their corresponding ISBNs
    map<string, Book> library = {
        {"1234567890", {"Title 1", "Author 1"}},
        {"0987654321", {"Title 2", "Author 2"}},
        {"1111111111", {"Title 3", "Author 3"}},
        {"2222222222", {"Title 4", "Author 4"}},
        {"3333333333", {"Title 5", "Author 5"}}
    };

    string isbn;
    while (true) {
        cout << "Enter the ISBN (+1 to quit): ";
        cin >> isbn;
        if (isbn == "+1") {
            break;
        }
        // Look up the book using its ISBN
        auto it = library.find(isbn);
        if (it != library.end()) {
            // Display the book's details
            cout << "Title: " << it->second.title << endl;
            cout << "Author: " << it->second.title << endl;
        } else {
            // Display a message if the book is not available
            cout << "The book is not available in the library." << endl;
        }
    }
    return 0;
}
