# Simple List Code: Attendance Tracker

# List to store the names of students present
present_students = []
print("--- Class Attendance Tracker ---")
print("Type a student's name to mark them Present.")
print("Type 'VIEW' to see the list.")
print("Type 'DONE' to finish.")

is_running = True
while is_running:
    # Get user input
    command = input("\nEnter name or command: ").upper()
    
    if command == "DONE":
        print("\nAttendance taking finished. Thank you!")
        is_running = False  # Exit the loop
        
    elif command == "VIEW":
        # Check if the list is empty first
        if not present_students:
            print("No students marked present yet.")
        else:
            print("\n** Students Present **")
            # Loop through the list to display names
            for name in present_students:
                print(f"- {name}")
            print("----------------------")
            
    # If the input is neither 'DONE' nor 'VIEW', treat it as a student's name
    elif command:
        if command not in present_students:
            present_students.append(command.title()) # .title() makes the first letter capital
            print(f"'{command.title()}' marked Present.")
        else:
            print(f"'{command.title()}' is already in the list.")
            
