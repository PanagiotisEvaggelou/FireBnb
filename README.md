# Room Rental Management System

## Description
This application was developed as a university project for the "Distributed Systems" course. The application is a room rental management system that allows users to perform manager and tenant operations. The system uses the MapReduce framework for processing large volumes of data and consists of a backend implemented in Java and a mobile application in Android.

## Project Requirements
### Manager Functions:
- Add accommodations.
- Add available dates for rental for these accommodations.
- Display bookings for the accommodations they own.
- Manage these functions via a console application.

### Tenant Functions:
- Filter accommodations based on:
  - Area of interest.
  - Desired dates.
  - Number of people.
  - Price.
  - Rating (stars).
- Book an accommodation.
- Rate the accommodation (1-5 stars).
- Perform these actions via an Android UI.
  - A `search()` function sends the filter to the Master asynchronously and displays the search results.
  - A `book()` function allows the user to book an accommodation from the search results.

### System Requirements:
- The system should run distributed across multiple machines.
- Use MapReduce for processing data.
- Implement Master and Worker nodes communication using TCP sockets.
- Ensure thread synchronization using `synchronized`, `wait`, and `notify`.
- Data should be stored in memory (except for photos).

### Backend Implementation Requirements:
- The Master must be a multi-threaded TCP Server implemented in Java.
- Workers should also be multi-threaded to handle multiple requests from the Master.
- Workers should be dynamically specified during the Master initialization.
- Implement active replication to ensure data redundancy and fault tolerance.
- Synchronize data across multiple nodes to prevent data loss if a worker node fails.

### Frontend Implementation Requirements:
- Develop an Android application for the user interface.
- Communication between the Application and Master must use TCP sockets.
- Implement asynchronous communication to keep the application interactive.

## How to Run the Application

### Backend Setup
1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/room-rental-management-system.git
    ```
2. Navigate to the backend directory:
    ```bash
    cd room-rental-management-system/backend
    ```
3. Compile the Java files:
    ```bash
    javac -d bin src/**/*.java
    ```
4. Run the Master server:
    ```bash
    java -cp bin MasterServer <number_of_workers>
    ```
5. In separate terminals, run the Worker servers, the Reducer and the Backup server:
    ```bash
    java -cp bin WorkerServer <worker_id>
    ```

### Frontend Setup (Android Application)
1. Open Android Studio.
2. Import the project by selecting the root directory of the cloned repository.
3. Build and run the application on an emulator or a physical device.

### Usage
- **Manager Console Application**: Use the console application to add accommodations, set available dates, and view bookings.
- **Tenant Android Application**: Use the Android app to filter and book accommodations, as well as to rate them.

