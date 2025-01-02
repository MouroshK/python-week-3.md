Create a program that reads a file and writes a modified version to a new file.

def read_and_write_file():
    # Ask the user for the file to read
    input_filename = input("Enter the name of the file to read: ").strip()
    output_filename = input("Enter the name of the new file to write to: ").strip()

    try:
        # Open the input file and read its content
        with open(input_filename, 'r') as input_file:
            content = input_file.readlines()

        # Modify the content (example: convert to uppercase)
        modified_content = [line.upper() for line in content]

        # Write the modified content to the output file
        with open(output_filename, 'w') as output_file:
            output_file.writelines(modified_content)

        print(f"Modified content written to {output_filename} successfully.")

    except FileNotFoundError:
        print("Error: The file does not exist. Please check the filename and try again.")
    except PermissionError:
        print("Error: Permission denied. You do not have access to this file.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

# Run the program
read_and_write_file()


Ask the user for a filename and handle errors if it doesn’t exist or can’t be read.

def read_file_with_error_handling():
    filename = input("Enter the filename to read: ").strip()

    try:
        # Attempt to open the file for reading
        with open(filename, 'r') as file:
            content = file.read()
            print("\nFile content:")
            print(content)
    except FileNotFoundError:
        print("Error: The file does not exist. Please check the filename and try again.")
    except PermissionError:
        print("Error: Permission denied. You do not have access to this file.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

# Run the program
read_file_with_error_handling()
