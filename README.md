CSE18R272-LAB MANUAL
KALASALINGAM ACADEMY OF RESEARCH AND EDUCATION
COMPUTER SCIENCE AND EDUCATION


Date: 16-09-2020   				
Day: Tuesday






Name:J.V. SAISESIKIRAN 
Regno: 9919004115
Section: A5
Course name: java programming
Course Code: CSE18R272
Date of submission : 16-09-2020




1.write  a java program to implement inheritance using super keyword.
Program:
class Box {
    private double width ;
    private double height ;
    private double depth ;
Box ( double w , double h , double l) {
    width = w;
    height = h ;
    depth = l;
}
Box () {
    width = -1;
    height = -1;
    depth = -1;
}
double volume () {
    return width * height * depth ;
}
}
class BoxWeight extends Box {
    double weight ; // weight of box
    BoxWeight ( double w , double h , double d , double m) {
        super (w , h , d ); // call superclass constructor
        weight = m;
    }
    BoxWeight (){
        super ();
        weight = -1;


}
}
public class Main
{
public static void main(String[] args) {
BoxWeight b1 = new BoxWeight(5.4,3.6,2.4,4.8);
BoxWeight b2 = new BoxWeight();
double v ;
        v = b1 . volume ();
        System . out . println (" Volume of mybox1 is " + v );
        v = b2 . volume ();
        System . out . println (" Volume of mybox3 is " + v );
}
}
Output:
volume of mybox1 is 46.656                                                                                                                   
 Volume of mybox3 is -1.0

2. Create a class called Date that includes three pieces of information as instancevariables—a month (typeint), a day (typeint) and a year (typeint). Your classshould have a constructor that initializes the three instance variables andassumes that the values provided are correct. Provide a set and a get method foreach instance variable. Provide a method displayDate that displays the month,day and year separated by forward slashes(/). Write a test application namedDateTest that demonstrates cl
Program:
class Date {
    int  day ;
    int month ;
    int year ;
    public Date ( int d , int m , int y) {
        if(m<13 && d<31){
            month = m; day=d; year=y;
        }
        else{
            System.out.println("incorrect date");
        }
            
        }
    void setMonth(int m){
        if(m<13)
            month=m;
        else 
            System.out.println("incorrect format");
    }
    void setDay(int d){
        if(d<31)
            day=d;
        else 
            System.out.println("incorrect format");
    }
    void setYear(int y){
        if((y/10000)==0)
            year=y;
        else
            System.out.println("incorrect format");
    }
    int getMonth(){
        return month;
    }
    int getDay(){
        return day;
    }
    int getYear(){
        return year;
    }
    void display () {
        System.out.println("The date is " + day +"/" + month + "/" + year);
    }


}
public class Main
{
public static void main(String[] args) {
Date d1 = new Date(16,9,2020);
d1.display();
d1.setDay(15);
d1.setMonth(9);
d1.setYear(2020);



        
        
}
}
Output:
The date is 16/9/2020



3. Create class SavingsAccount. Usea static variable annualInterestRate to store theannual interest rate for all account holders. Each object of the class contains aprivate instance variable savingsBalance indicating the amount the savercurrently has ondeposit. Provide method calculateMonthlyInterest to calculatethe monthly interest by multiplying the savingsBalance by annualInterestRatedivided by 12 this interest should be added to savingsBalance. Provide a staticmethod modifyInterestRate th
Provide a staticmethod modifyInterestRate that sets the annualInterestRate to a new value.Write a program to test class SavingsAccount. Instantiate two savingsAccountobjects, saver1 and saver2, with balances of $2000.00 and $3000.00, respectively.Set annualInterestRate to 4%, then calculate the monthly interest and print thenew balances for both savers. Then set the annualInterestRate to 5%, calculate the next month’s interest and print the new balances for both savers.
Program:
class SavingsAccount{
    static float AnnualIntrestrate = (float)4;
    private float SavingsBalance;
    void caluclateMonthlyIntrest(){
        float intrest = ((SavingsBalance*AnnualIntrestrate)/12);
        SavingsBalance+=intrest;
        System.out.println("balance is " + SavingsBalance);
    }
    static void  ModifyIntrestrate(float rate){
        AnnualIntrestrate=rate;
    }
    public SavingsAccount(float balance){
        SavingsBalance=balance;
        
    }
    
}
public class Main
{
public static void main(String[] args) {
SavingsAccount s1 = new SavingsAccount(2000.0f);
SavingsAccount s2 = new SavingsAccount(3000.0f);
s1.caluclateMonthlyIntrest();
s2.caluclateMonthlyIntrest();
SavingsAccount.ModifyIntrestrate(5.0f);
s1.caluclateMonthlyIntrest();
s2.caluclateMonthlyIntrest();




        
        
}
}
Output:
balance is 2666.6667                                                                                                                          
balance is 4000.0                                                                                                                             
balance is 3777.7778                                                                                                                          
balance is 5666.6665
4.write a java program create a class callled book and initialize the respective details of book using class constructor  and access them by creating objects and perform required operations.
Program:
import java.util.Scanner;
class Book 
{
    String bookName;
    String author;
    String ISBN, publisher;
    Book(String title, String auth, String isbn, String publish)
    {
        bookName = title;
        author =auth;
        this.ISBN = isbn;
        publisher = publish;
    }
    void setTitle(String name)
    {  bookName = name; }
    void setAuthor(String auth)
    { author = auth; }
    void setISBN(String s) 
    { ISBN = s; }
    void setPublisher(String p)
    {
        publisher = p;
    }
    String getTitle()
    {  return bookName; }
    String getAuthor() 
    { return author; }
    String getISBN() 
     { return ISBN; }
     String getPublisher() 
     { return publisher; }
    String bookInfo()
    {
        String info = bookName + " " + author + " " + ISBN + " " + publisher;
        return info;
        
    }
}
  
public class Main
{
public static void main(String[] args) {
    Book b[] = new Book[30];
    b[0] = new Book("Programming in Java", "Rama", "12345", "Wiley");
    String title, auth, isbn, publisher;
    Scanner s = new Scanner(System.in);
    for (int i =1; i < 3; i++)
     {
         title = s.next();
         auth = s.next();
         isbn = s.next();
         publisher = s.next();
         b[i] = new Book(title,auth,isbn,publisher);
     }
    b[2].setTitle("Software Testing");
    System.out.println(b[2].getTitle());
    String info;
    for (int i =0; i<3; i++) {
        info = b[i].bookInfo();
        System.out.println(info);
    }


}
}
Sample input and output;
Head First java
Kathy sierra
987456321
Orelly
Barry burd
123456789
Learning made easy
Programming in Java Rama 12345 Wiley
Head First java kathy sierra 987456321 Orelly
Software testing Barry burd 123456789 Learning made easy









