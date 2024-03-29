Assume you oversee a small library and would like to develop a program that looks up books using their ISBNs. A list of books with their corresponding ISBN digits is in front of you. After the librarian inputs an ISBN, your software will look through the list to locate the relevant book.  The book's title and other details will be shown if the book is located. A notice stating that the book is not available in the library will appear if it cannot be located.
#include <iostream>
#include <map>
#include <string>

using namespace std;

// Define a structure to represent a book
struct Book {
    string title;
    string author;
    string isbn;
};

int main() {
    // Create a map to store books with their ISBN as the key
    map<string, Book> library;

    // Populate the library with some books
    library["978-0590353427"] = {"Harry Potter and the Sorcerer's Stone", "J.K. Rowling", "978-0590353427"};
    library["978-0439064873"] = {"Harry Potter and the Chamber of Secrets", "J.K. Rowling", "978-0439064873"};
    library["978-0439136365"] = {"Harry Potter and the Prisoner of Azkaban", "J.K. Rowling", "978-0439136365"};
    // Add more books as needed...

    // Prompt the librarian to input an ISBN
    cout << "Enter the ISBN of the book: ";
    string inputISBN;
    cin >> inputISBN;

    // Search for the book in the library
    if (library.find(inputISBN) != library.end()) {
        // Book found, print its details
        Book foundBook = library[inputISBN];
        cout << "Book Title: " << foundBook.title << endl;
        cout << "Author: " << foundBook.author << endl;
        cout << "ISBN: " << foundBook.isbn << endl;
    } else {
        // Book not found
        cout << "The book is not available in the library." << endl;
    }

    return 0;
}
