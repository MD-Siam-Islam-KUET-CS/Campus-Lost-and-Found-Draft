## Using the Application

After launching the program, a menu appears with the following options:

text
CAMPUS LOST & FOUND INTELLIGENCE SYSTEM

1. Report Lost Item
2. Report Found Item
3. Display Reports
4. Search Reports
5. Update Report
6. Delete Report
7. Find Possible Matches
8. Record Item Return
0. Save and Exit


Enter the corresponding option and follow the prompts.

When adding a report, provide the requested item details, including its name, category, colour, location, date, description, reporter information, and contact information.

To identify possible matches, select option 7 and enter the ID of an existing report. The system calculates similarity scores and displays qualifying matches.

Select option 0 to save the latest changes and exit.

## Data Storage and Reliability

The application stores records locally in items.dat.

The storage module includes:

- A file signature to identify the expected data format.
- Validation of record counts and stored records.
- Duplicate-ID checks.
- Temporary-file writing before replacing the existing data file.
- Error handling for common file-reading and file-writing failures.

*Important:* The binary data format is intended for compatible builds using the same structure layout and platform assumptions. It is not a portable interchange format between arbitrary compilers or platforms. Keep a backup of important records before changing the data format or modifying the structure definitions.

The application does not require a remote database or internet connection for its core functionality.

## Build Commands

| Command | Purpose |
|---|---|
| make | Compile and link the application |
| make run | Build if necessary and launch the application |
| make clean | Remove object files and the generated executable |

If make is unavailable, compile the source files directly with GCC:

bash
gcc -std=c11 -Wall -Wextra -Wpedantic -O2 \
    main.c items.c matching.c storage.c \
    -o campus_lost_found


Then run the generated executable using the command appropriate for your operating system.

## Concepts Demonstrated

This project demonstrates practical applications of fundamental C programming concepts:

- Structures (struct) for representing item records.
- Functions and modular programming.
- Arrays and string processing.
- Conditional statements, loops, and menu-driven interaction.
- Searching, sorting, and score-based matching.
- File handling and binary data storage.
- Input validation and error handling.
- Header files and multi-file compilation.
- Makefiles and basic build automation.

## Limitations

- The application runs in a terminal rather than a graphical interface.
- Records are stored locally and are not automatically shared across computers.
- Match scores depend on the information entered by users.
- The system does not independently verify item ownership.
- The application is designed for a limited number of records, with a maximum capacity defined in the source code.
- The current implementation does not provide a multi-user web interface or centralized database.

## Future Improvements

Potential extensions include:

- A graphical user interface or web-based frontend.
- Centralized database storage for campus-wide access.
- User authentication and administrative roles.
- More advanced matching using normalized text and additional item attributes.
- Notifications when a likely match is found.
- Report timestamps and audit history.
- Image uploads for item identification.
- Improved portability through a versioned, platform-independent storage format.

## Academic Purpose

This project was developed as a practical exercise in C programming, data structures, modular software development, searching, sorting, file handling, and error management. It models a campus lost-and-found workflow and demonstrates how fundamental programming concepts can be combined to solve a practical problem.

## License

No license has been specified yet. Unless a license is added to this repository, others should not assume that they have permission to redistribute or modify the project.

---

*Project:* Campus Lost & Found Intelligence System  
*Language:* C  
*Application Type:* Menu-driven terminal application  
*Storage:* Local binary file
