- class Book:
 def __init__(self, title, author, isbn):
 self.title = title
 self.author = author
 self.isbn = isbn
 def __str__(self):
 return f"Title: {self.title}, Author: {self.author}, 
ISBN: {self.isbn}"
class Library:
 def __init__(self):
 self.books = []
 def add_book(self, book):
 if book not in self.books:
 self.books.append(book)
 print(f"Book '{book.title}' added to the 
library.")
 else:
 print(f"Book '{book.title}' already exists in the 
library.")
 def remove_book(self, title):
 for book in self.books:
 if book.title == title:
 self.books.remove(book)
 print(f"Book '{title}' removed from the 
library.")
 return True
 print(f"Book '{title}' not found in the library.")
 return False
 def show_books(self):
 if self.books:
 print("*** Books in the Library ***")
 for book in self.books:
 print(book)
 else:
 print("The library is currently empty.")
book1 = Book("The Lord of the Rings", "J.R.R. Tolkien", "978-
0395074235")
book2 = Book("The Hitchhiker's Guide to the Galaxy", "Douglas 
Adams", "0345391822")
library = Library()
library.add_book(book1)
library.add_book(book2)
library.add_book(book1) # Duplicate, won't be added
library.remove_book("The Martian") # Not found
library.remove_book("The Hitchhiker's Guide to the Galaxy")
library.show_books()
