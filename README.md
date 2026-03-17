# Mini Project: Library Management System
# Language: Python

library = []

def add_book():
    book_id = input("Enter Book ID: ")
    book_name = input("Enter Book Name: ")
    author = input("Enter Author Name: ")

    book = {
        "id": book_id,
        "name": book_name,
        "author": author,
        "status": "Available"
    }

    library.append(book)
    print("Book added successfully!\n")


def display_books():
    if not library:
        print("= No books in library.\n")
        return

    print("\n Library Books:")
    print("-" * 50)
    for book in library:
        print(f"ID: {book['id']} | Name: {book['name']} | "
              f"Author: {book['author']} | Status: {book['status']}")
    print("-" * 50 + "\n")


def issue_book():
    book_id = input("Enter Book ID to issue: ")

    for book in library:
        if book["id"] == book_id:
            if book["status"] == "Available":
                book["status"] = "Issued"
                print(" Book issued successfully!\n")
            else:
                print(" Book is already issued.\n")
            return

    print("Book not found.\n")
