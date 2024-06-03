1. The  PrimeOwner contract is made to change the contract owner by making a call to the changeOwnerIfPrime function with an input of prime number. The function first checks if the input number is greater than zero, then it determines whether if it is prime by calling helper function isPrime. In order to check primality, I've made isPrime function which employs an algorithm that covers such base cases as checking divisibility by 2 and iterating through all odd numbers from 3 up to square root of the number. When the input number turns out to be prime, the changeOwnerIfPrime function updates state variable owner with caller address and emits OwnerChanged event. If the input is less than 1 the function call is simply reverted. I've used Newton's method in calculating integral square roots to optimize the prime checking process.
![Screenshot (38)](https://github.com/DeFi-Unchained-IITK/assignment-2-weird-polaroid/assets/169828145/d04170bb-1ed6-44be-9731-5ab6bb6745d6)
![Screenshot (39)](https://github.com/DeFi-Unchained-IITK/assignment-2-weird-polaroid/assets/169828145/7dd6b00e-1de5-440f-8ae1-8031603a2ab1)

2.The first thing I did was define a struct, called Employee, that would contain key details such as ID, name, position and salary of employees. Then I created an employees mapping to store examples of the Employee struct in which the key is employee’s ID for easier retrieval, updating and deletion.
In order to find out the next available ID for new employees, I started a state variable named nextID in the contract constructor with value 1
Among others, three events were also declared: EmployeeAdded, EmployeeUpdated and EmployeeDeleted. These will be emitted whenever an employee is added, updated or deleted respectively in order to allow interested external parties to monitor and respond accordingly.
The addEmployee function takes name, position and salary as input parameters. It creates a new instance of Employee struct using these details and current nextID as its id; it saves it within the employees mapping; emits the event “EmployeeAdded”;and so on.
In updateEmployee function I am accepting ID ,name ,position and salary .It checks whether employee exists then it updates details and emit “employeeupdated” event. If not found revert transaction.
The getEmployeeDetails function retrieves the name, position, and salary of an employee based on their ID. It returns these details if the employee is found, otherwise, it reverts.
The deleteEmployee function removes an employee from the mapping based on their ID. It first emits the EmployeeDeleted event with the employee's details, then deletes the employee from the mapping. If the employee is not found, it reverts.

![Screenshot (40)](https://github.com/DeFi-Unchained-IITK/assignment-2-weird-polaroid/assets/169828145/a64185d5-580b-4a08-beca-7ae9699235ba)
![Screenshot (41)](https://github.com/DeFi-Unchained-IITK/assignment-2-weird-polaroid/assets/169828145/303236f5-e4ff-4a3c-915c-02bedb2d10e5)
![Screenshot (42)](https://github.com/DeFi-Unchained-IITK/assignment-2-weird-polaroid/assets/169828145/b3264ede-112e-4028-b644-72cfe2249d69)

3.To easily access, the books mapping stores all the books that are available in the library, with each book’s ID serving as a key. The Ethereum address of the user is used to map which borrowed books belong to him.
In order to assign unique IDs automatically to every new book I introduced nextID state variable that is set equal to 1 in the constructor.
The function addBook allows users to add new books by providing a title and author for this book. It then creates a new instance of Book, keeps it in the books mapping together with nextID at present, sets its availability as true and increases nextID for subsequent book.
Borrowers can use borrowBook function to borrow available books. Whether or not both requirements are met will depend on if it has a valid book ID and whether it is free. Thus, if all these conditions are satisfied, then such publication will be marked as “not available” and its identifier added into list of those borrowed_books belonging to this user.
The details contained here include such aspects as the name, authorship and stock status of any given entry based on its identification number once looked up using getBookDetails.
When users want to return a borrowed book, they can use the returnBook function. It validates the book ID, checks if the book is currently borrowed (not available), and verifies if the user is the one who borrowed the book. If all conditions are met, it marks the book as available and removes its ID from the user's borrowed_books list.
To support the returnBook function, I implemented two internal helper functions: isBorrowedBy and removeBookFromBorrowedList. The isBorrowedBy function checks if a given book ID is present in the user's borrowed_books list, and the removeBookFromBorrowedList function removes a book ID from that list.

![Screenshot (43)](https://github.com/DeFi-Unchained-IITK/assignment-2-weird-polaroid/assets/169828145/5bc058c4-e0a7-4514-93a9-701e3f761aec)
![Screenshot (44)](https://github.com/DeFi-Unchained-IITK/assignment-2-weird-polaroid/assets/169828145/a42f414d-b6fd-4786-907c-090ff2f44028)
![Screenshot (45)](https://github.com/DeFi-Unchained-IITK/assignment-2-weird-polaroid/assets/169828145/93c71d66-09ec-4a58-a946-b56283052583)


You have to create one folder named "FirstName_Roll". In that folder, you have to add three files, one for each question. You can code in Remix IDE and download the file. Also, ensure to update the readme file, the unupadated readme files will not be considered valid. The readme file should contain the description of the code of each question and the screenshots of the function's output deployed in Remix IDE.











