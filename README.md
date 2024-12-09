# Library-Management-System
import java.util.ArrayList;
class Book{
    public String name, author;

    public Book(String name, String author) {
        this.name = name;
        this.author = author;
    }
    @Override
    public String toString() {
        return "Book{" +
                "name='" + name + '\'' +
                ", author='" + author + '\'' +
                '}';
    }
}
class MyLibrary{
    public ArrayList<Book> books;
    public MyLibrary(ArrayList<Book> books) {
        this.books = books;
    }
    public void addBook(Book book){
        System.out.println("The book has been added to the library");
        this.books.add(book);
    }
    public void issueBook(Book book, String issued_to){
        System.out.println("The book has been issued from the library to " + issued_to);
        this.books.remove(book);
    }
    public void returnBook(Book b,String name){
        System.out.println("The book has been returned by "+name);
        this.books.add(b);
    }
    public void showAvailableBook()
    {
        
        System.out.println(books);
    }
}

    public class CWh_113_ex7sol {
    public static void main(String[] args) {
        ArrayList<Book> bk = new ArrayList<>();
        Book b1 = new Book("C", "Dennis Ritchie");
        bk.add(b1);

        Book b2 = new Book("Ramayana", "Valmiki ji");
        bk.add(b2);

        Book b3 = new Book("Atomic Habits", "James Clear");
        bk.add(b3);

        Book b4 = new Book("C++", "Bjarne Stroustrup");
        bk.add(b4);


        Book b5 = new Book("Java","James Gosling");
        bk.add(b5);


        MyLibrary l = new MyLibrary(bk);
        l.addBook(new Book("Mocking Bird", "Harper Lee"));
        System.out.println(l.books);
        l.issueBook(b3, "UnizzTech");
        System.out.println(l.books);
        l.returnBook(b3,"Himanshu");
        l.showAvailableBook();

    }
}
