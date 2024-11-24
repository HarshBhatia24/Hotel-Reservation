Hotel Reservation System

Overview

This Java-based application simulates a hotel reservation system. It allows customers to register, log in, view and manage their profiles, search available rooms, make reservations, and view their reservation history. Administrators can manage rooms (add, remove, update), view all reservations, and manage reservations.

Features

Customer:
Register and log in.
View and edit profile.
Search available rooms.
Make reservations.
View reservation history.
Administrator:
Log in.
View and edit profile.
Add, remove, and update rooms.
View all reservations.
Manage reservations.
Classes
1. User (Abstract Class)
Attributes:
userID: Unique identifier for the user.
username: Username of the user.
password: Password for login.
Methods:
login(String username, String password): Abstract method for user login validation.
viewProfile(): Abstract method for viewing profile details.
2. Customer (Extends User)
Attributes:
reservationHistory: List to store the reservation history of the customer.
Methods:
login(String username, String password): Validates login credentials.
viewProfile(): Displays the customer profile.
makeReservation(Reservation reservation): Adds a reservation to the history.
viewReservationHistory(): Displays all past reservations of the customer.
3. Administrator (Extends User)
Methods:
login(String username, String password): Validates login credentials for the admin.
viewProfile(): Displays the administrator profile.
4. Room
Attributes:

roomNumber: Unique number of the room.
roomType: Type of room (e.g., Single, Double, Suite).
isAvailable: Availability status of the room.
pricePerNight: Price for one night stay in the room.
Methods:

isAvailable(): Checks if the room is available.
bookRoom(): Marks the room as booked.
releaseRoom(): Marks the room as available.
getPricePerNight(): Returns the price per night.
getRoomNumber(): Returns the room number.
getRoomType(): Returns the room type.
5. Reservation
Attributes:

reservationID: Unique identifier for the reservation.
customer: The customer who made the reservation.
room: The room reserved.
checkInDate: Date when the reservation starts.
checkOutDate: Date when the reservation ends.
totalAmount: Total cost for the reservation.
status: Current status of the reservation (Booked, Cancelled, etc.).
Methods:

calculateTotal(): Calculates the total cost based on the room price and the duration of the stay.
toString(): Returns a string representation of the reservation.
6. HotelReservationSystem
Attributes:
users: List of users (both customers and administrators).
rooms: List of available rooms.
scanner: Scanner object for input.
Methods:
main(String[] args): Main method to start the application and present the main menu.
registerCustomer(): Registers a new customer.
login(): Allows a user to log in.
customerMenu(Customer customer): Displays the menu for a logged-in customer.
adminMenu(Administrator admin): Displays the menu for a logged-in administrator.
editProfile(User user): Allows a user to edit their profile.
searchAvailableRooms(): Allows a customer to search for available rooms.
makeReservation(Customer customer): Allows a customer to make a reservation.
addRoom(): Allows the admin to add a new room.
removeRoom(): Allows the admin to remove a room.
updateRoom(): Allows the admin to update room details.
viewAllReservations(): Allows the admin to view all reservations.
manageReservations(): Allows the admin to manage reservations.
How to Run
Prerequisites: Ensure you have the latest version of Java installed.
Compilation and Execution:
Compile the Java classes:
Copy code
javac HotelReservationSystem.java
Run the application:
Copy code
java HotelReservationSystem
Example Usage
1. Register as a Customer
Choose option 1 to register a new customer.
Provide a unique username and password.
2. Customer Login
Choose option 2 to log in as a customer.
Enter the username and password to access the customer menu.
3. Administrator Login
Use the default admin credentials to log in:
Username: admin
Password: admin123
4. Customer Reservation
After logging in as a customer, you can search for available rooms and make a reservation by selecting the respective menu options.
5. Administrator Room Management
The administrator can add, remove, and update room details using the admin menu.
Limitations
Date parsing and validation are not fully implemented (the program assumes that dates entered are valid).
The system does not handle cancellations or advanced reservation management (this can be expanded in future versions).
No database integration – all data is stored in memory.
Future Enhancements
Implement date parsing and validation for reservations.
Add the ability to cancel reservations.
Implement advanced reservation management features for administrators.
Integrate a database for persistent data storage.
