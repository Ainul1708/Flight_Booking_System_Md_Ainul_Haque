# Flight_Booking_System_Md_Ainul_Haque

Documentation for the Project FlightBookingSystemMdAinulHaque for package flightbooking.models

In Package flightbooking.models-:

Class: Flight
Purpose:
Represents an airline flight with details such as flight number, origin, destination, base price, 
and available seats. It also provides methods for seat booking and releasing, as well as displaying 
flight details.

Attributes:
- flightNumber (String): Unique identifier for the flight.
- origin (String): Starting location of the flight.
- destination (String): Ending location of the flight.
- basePrice (double): Base cost of the flight ticket.
- availableSeats (int): Number of seats currently available for booking.

Methods:
- getFlightNumber(): Returns the flight number.
- getOrigin(): Returns the origin of the flight.
- getDestination(): Returns the destination of the flight.
- getBasePrice(): Returns the base price of the flight ticket.
- getAvailableSeats(): Returns the number of available seats.
- bookSeat(): Reduces the available seat count by 1 if a seat is available and returns true; 
			  otherwise returns false.
- releaseSeat(): Increases the available seat count by 1.
- displayFlightDetails(): Prints flight details such as flight number, origin, destination, base price, 
                          and available seats.

Class: Passenger
Purpose:
Represents a passenger who can book a flight. Contains attributes related to personal information 
and category of the passenger (e.g., VIP, Regular).

Attributes:
- name (String): Name of the passenger.
- age (int): Age of the passenger.
- category (String): Special category of the passenger (e.g., "Senior Citizen", "Army", "VIP", etc.).

Key Methods:
- getName(): Returns the passenger's name.
- getAge(): Returns the passenger's age.
- getCategory(): Returns the passenger's category.
- displayPassenger(): Prints the passenger's details (name, age, and category).

Class: Ticket
Purpose:
Represents a ticket booked by a passenger for a flight. Includes the flight details, 
passenger details, and the final price of the ticket.

Attributes:
- flight (Flight): The flight associated with the ticket.
- passenger (Passenger): The passenger who booked the ticket.
- finalPrice (double): The final price of the ticket after applying discounts or additional charges.

Key Methods:
- getFlight(): Returns the flight details.
- getPassenger(): Returns the passenger details.
- getFinalPrice(): Returns the final price of the ticket.
- displayTicket(): Prints the ticket details, including the passenger name, flight number, and final price.


Documentation for the Project FlightBookingSystemMdAinulHaque for package flightbooking.services

Package flightbooking.services-:

Class: BookingService
Purpose:
Manages the flight booking system, including booking tickets, listing bookings, finding bookings,
and canceling bookings.
Attributes:
- bookings (ArrayList<Ticket>): Stores the list of all tickets/bookings made.

Key Methods:
- bookFlight(Flight flight, Passenger passenger):
Books a flight for a passenger if seats are available. Calculates the final price using discounts and 
creates a ticket. Returns the created Ticket object, or null if booking fails.
- listBookings():
Displays all current bookings with ticket details. If no bookings exist, prints a message.
- findBookingByPassenger(Passenger passenger):
Searches for and returns the ticket associated with a specific passenger. Prints a message 
if no booking is found.
- findBookingsByFlight(Flight flight):
Returns a list of all bookings associated with a specific flight.
- cancelBooking(Ticket ticket):
Cancels a specific booking, releases the flight seat, and removes the ticket from the bookings list. 
Returns true if successful, false otherwise.

Class: FlightService
Purpose:
Manages and maintains a list of all available flights. Allows adding and listing flights.
Attributes:
- flights (ArrayList<Flight>): Stores the list of all available flights.

Key Methods:
- addFlight(Flight flight):
Adds a new flight to the list of flights.
- getFlights():
Returns the list of all flights.
- listFlights():
Displays details of all flights by invoking the displayFlightDetails() method of the Flight class.

Class: PassengerService
Purpose:
Manages passengers, including adding, removing, finding, and listing passengers. Provides additional 
functionality to list passenger categories.
Attributes:
- passengers (List<Passenger>): Stores the list of all passengers.

Key Methods:
- addPassenger(Passenger passenger):
Adds a new passenger to the list.
- removePassenger(String name):
Removes a passenger from the list based on their name (case-insensitive).
- findPassengerByName(String name):
Searches for and returns a passenger by name. Returns null if no match is found.
- listPassengers():
Displays details (name, age, category) of all passengers in the list. If no passengers exist, 
prints a message.
- listCategories():
Displays the categories of all passengers. If no passengers exist, prints a message.



Documentation for the Project FlightBookingSystemMdAinulHaque for package flightbooking.utils

In Package flightbooking.utils-:

1. DiscountUtil
- Purpose: Handles discount calculation for passengers based on their category.
- Functionality:- The calculateDiscount method takes a Passenger object and determines the 
				  discount percentage based on predefined categories.
- Different passenger categories (Senior Citizen, Army, VIP, Celebrity, Flying Personnel) receive
 different discounts, with Regular


2. FlightBookingSystem
- Purpose: Serves as the main entry point for the flight booking application.
- Functionality:- Manages flight services, passenger services, and booking services.
- Provides an interactive menu for users to:- Add/Delete passengers.
- View available flights and passengers.
- Book/Cancel tickets.
- View existing bookings and passenger categories.
- Includes error handling to manage invalid user inputs.


3. PrintUtil
- Purpose: Provides utility methods for printing standardized messages.
- Functionality:- printMessage(String message): Prints a formatted informational message
				  prefixed with [INFO].
- printError(String errorMessage): Prints an error message prefixed with [ERROR], 
								   using System.err for visibility.


4. ValidationUtil
- Purpose: Offers validation methods to ensure data integrity.
- Functionality:- isValidString(String str): Checks whether a given string is non-null and not empty.
- isPositiveNumber(int number): Verifies if a number is positive.


