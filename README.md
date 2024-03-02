# sara
# Function to add two numbers
def add_numbers(num1, num2):
    return num1 + num2

# Main function
def main():
    # Get input from user
    num1 = float(input("Enter the first number: "))
    num2 = float(input("Enter the second number: "))

    # Call the function to add numbers
    result = add_numbers(num1, num2)

    # Display the result
    print("The sum of", num1, "and", num2, "is:", result)

# Call the main function to execute the code
