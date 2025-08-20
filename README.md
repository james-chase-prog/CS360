# CS360

WeightSmart

WeightSmart is designed to be a straightforward but robust data driven weight tracking application.  It allows users to create accounts, log weights, and view historical weight data stored within the app.  The app will allow users to transform and analyze their data to gain insight into weight change trends.  SMS notifications can be enabled for reminders and view your weight records in an easy to read sortable table. 

•	Fast logging: Add a weight with date and time (12-hour AM/PM).
•	Goal tracking: See your current weight versus goal with clear labels.
•	Sortable table: View and manage entries in a paginated list (10 per page).
•	Private by design: Data stays on your device. No cloud account is required.
•	Optional reminders: Local notifications help build a daily habit.
•	Upcoming Premium (one-time unlock): CSV export, a trends graph, and visual themes.

Application development is being driven by a used first mindset. We have identified three core user types: beginners, health conscious users, and weight management enthusiasts. The WeightSmart app follows a “simple on the surface, powerful underneath” philosophy. The interface is tailored for users who value both convenience and insight.  Users should be able to flow through WeightSmart intuitively without needing to search for the features they want.  A bottom navigation bar helps users move through the main pages of the app allowing easy access to each core function of WeightSmart.  WeightSmart constantly welcomes, encourages, and engages with the user personally through nicknames, welcome messages, user avatars, and visual customization.  

<img width="975" height="808" alt="image" src="https://github.com/user-attachments/assets/9c803248-76c4-4755-b230-943a8e2897e6" />

Here we can see an early wireframe of WeightSmart.  Most of the UI elements still holds true today.  The user flows froms a login screen to either a create account screen the home screen from where they can navigate between the three core pages of the program.  The table screen uses a Recycler Viewer with pagination to allow the user to comb through their entries and delete accidental logs.  Future iterations will include sorting and filtering logic.  
<img width="975" height="873" alt="image" src="https://github.com/user-attachments/assets/e4acbc65-6e42-42a8-becc-67030dafef65" />
<img width="975" height="864" alt="image" src="https://github.com/user-attachments/assets/047372d2-dceb-40b2-b811-c99783d7c2a7" />

Here we can see the main page to gain a better understanding of the visual design of the application.  Additionally SMS weight alerts were added to the application and that UI is as presented. 

CODING APPROACH
- Hilt was used for dependcy injection.
- Rooms were used for entries and EncryptedSharedPreferences for session data.
- Recycler Viewer was used for the table

Overall development took place focusing on the "skeleton" or core of the project first before switching to developing the code behind the UI/UX.  I wanted a project that was routed in sound design principles and so I built out classes, defined their interaction with each other, and left determining how those classes would interact with the UI till the final stage.  Once my classes were defined I worked on developing a database system; implementing a CRUD module for basic database management.  With the classes already in place I could then succinctly write the components that connected the user classes to the databases to create a working data flow with careful attention to my data sources and sinks.  Finally, I wanted to implement RBAC, authorization, and encryption for sensitive user data as I believe these are critical for scaling the project.  

With everything expect the app logic in place I would begin working towards designing clean code connecting my database, users, and access control with the logic behind the buttons and UI.  I spent some time writing psuedocode and then analyzed the pseudocode for places where I could design reusable helper functions to keep code reading simple.  I built out my helper functions and then back on the happy path I coded my pages one at a time, not focusing on their connections but instead focusing on making each page functional before moving onto the next page. I practiced good coding habits and oop; slowly connecting each UI element to its code logic focusing on developing the code in compartments.  Eventually, once all the screens were developed I focused on connecting the screens with navigation logic. 

Testing prior to Project completion was admittedly at a minimum.  Far more testing is needed, including comphrensive unit testing and boundary testing.  However, testing that was completed included following the happy path and using the app as a user.  An account was created, logged into, and then records were added.  Many records were developed so that the features of the table could be tested.  Pagination was tested, the ability to delete records was performed.  I monitored UI responses such as the TextView user weight and goal weight to make sure they updated appropriately.  Profile screen features that had been implemented were tested.  Additionally, the app was closed and relogged into to confirm that user profiles were successfully saving to the database and accesible after a session ended.

Innovation / Challenges

- Table UX: converting a plain list into a usable “data table” with client-side paging, filters, and a per-row delete action—while maintaining snappy performance.
- DI & Navigation: resolving Hilt injection crashes (ensuring @AndroidEntryPoint where needed) and wiring bottom navigation with a persistent profile overlay.
- Resolving resource AATP2 errors and gradle configuration erros

Where I Demonstrated Strength

The TableFragment is the standout: clean data flow from DB → filtered/sorted list → paginated UI rows, stable formatting for date/time, and safe delete operations that keep pagination indices consistent. It combines user-centered design with robust, maintainable code and platform-correct behavior. I also beleive UI design was done in a strong way trying to adhere to Material3 principles as much as I could.
