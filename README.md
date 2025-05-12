# Python-week-4-assignment

# Ask the user to input the name of the file to read
filename = input("Enter the filename to read: ")

try:
    # Try opening the file in read mode
    with open(filename, 'r') as file:
        # Read the contents of the file
        content = file.read()
        
        # Optional: Modify the content (e.g., convert to uppercase)
        modified_content = content.upper()

        # Create a new file to write the modified content
        new_filename = "modified_" + filename
        with open(new_filename, 'w') as new_file:
            # Write the modified content to the new file
            new_file.write(modified_content)

        print(f"Modified content written to '{new_filename}'.")

# Handle the case where the file doesn't exist
except FileNotFoundError:
    print(f"Error: The file '{filename}' does not exist.")

# Handle other possible I/O errors
except IOError:
    print(f"Error: Could not read the file '{filename}' or write the output file.")

# Catch any other unexpected exceptions
except Exception as e:
    print(f"An unexpected error occurred: {e}")
