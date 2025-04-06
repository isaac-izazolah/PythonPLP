def read_and_write_file():
    try:
        # Ask the user for the input file name
        input_filename = input("Enter the name of the file to read: ")
        
        # Open the input file for reading
        with open(input_filename, "r") as infile:
            content = infile.readlines()  # Read file line by line
        
        # Modify the content (e.g., add line numbers)
        modified_content = [f"{idx + 1}: {line}" for idx, line in enumerate(content)]
        
        # Ask for the output file name
        output_filename = input("Enter the name of the output file: ")
        
        # Write the modified content to a new file
        with open(output_filename, "w") as outfile:
            outfile.writelines(modified_content)
        
        print(f"✅ Successfully written modified content to '{output_filename}'")

    except FileNotFoundError:
        print("❌ Error: The file does not exist. Please check the filename and try again.")
    except IOError:
        print("❌ Error: Unable to read or write to the file. Please check permissions.")
    except Exception as e:
        print(f"⚠️ Unexpected error: {e}")

# Run the function
read_and_write_file()
