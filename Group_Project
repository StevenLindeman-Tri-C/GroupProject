import random
import string
import requests
import bs4
import re
import os

# Container for the password generation function
def passwordMenu():


    def generatePassword(length, upper, lower, nums, symbols):
        # Create local variables for the set of characters that can be used
        # and the new password that will be returned from the function
        chars = ""
        newPassword = ""
   
        if upper:
            chars = chars + string.ascii_uppercase

        if lower:
            chars = chars + string.ascii_lowercase

        if nums:
            chars = chars + string.digits

        if symbols:
            chars = chars + string.punctuation

    # Loop that adds a random character from the set to the new passsword
        for i in range(length):
            newPassword = newPassword + random.choice(chars)
    # Return the new password as the function's return value
        return newPassword
    
   

    # Loop that asks the user for the password length and 
    # checks that it is within the correct range. 
    while True:
        os.system('cls')
         # Password Generator welcome message
        print('====================================================')
        print('==== WELCOME TO THE ULTIMATE PASSWORD GENERATOR ====')
        print('====================================================')
        print()

        pw_length = int(input('How long should the password be? (3-18) '))
        if pw_length < 3 or pw_length > 18:
            print()
            print('***Password length must be between 3-18***')
            print()
            input('Press any key to continue...')
            continue
        if pw_length >= 3 and pw_length <= 18:
            break    
        print()
    
    # Loop that asks the user What parameters they would like to use in creating
    # their passord. If none are used, the user is prompted to select at lease one  
    while True:
        os.system('cls')
        print('====================================================')
        print('==== WELCOME TO THE ULTIMATE PASSWORD GENERATOR ====')
        print('====================================================')
        print()
        print('-------------------- Settings ----------------------')
        print()
        pw_upper = bool(int(input('Use UPPERcase letters? 1 = Yes, 0 = No: ')))
        pw_lower = bool(int(input('Use lowercase letters? 1 = Yes, 0 = No: ')))
        pw_nums = bool(int(input('Use numbers? 1 = Yes, 0 = No: ')))
        pw_symbols = bool(int(input('Use symbols? 1 = Yes, 0 = No: ')))
        print()
        if pw_upper is False and pw_lower is False and pw_nums is False and pw_symbols is False:
            
            print('***Please select as least one password parameter***')
            print()
            input('Press any key to continue...')
        if pw_upper or pw_lower or pw_nums or pw_symbols:
            break    

    # Call the generatePassword function and pass in the user's choices
    # and display the return value to the user

    print('----------------------------------------------------')
    print('Generating password...')
    print('----------------------------------------------------')

    print("Your new password is: "
          + generatePassword(pw_length, pw_upper,
           pw_lower, pw_nums, pw_symbols))
    print('====================================================')
    print()
    input('Press any key to continue...')

def phoneMenu():

    def webscrape(webpage):
        # Passes the webpage entered by the user into a request object then                    
        # parses the text from the request object into a BeautifulSoup
        # object using the 'html.parser'
        res = requests.get(str(webpage)) 
        res.raise_for_status() 
        catalogPage = bs4.BeautifulSoup(res.text, 'html.parser')
        # Create a Regex for different phone number formats and matches
        # them againse the text from the BeautifulSoup object,
        # placing them in a list.
        textphoneRegex = re.compile(r'\d{3}-\d{3}-\d{4}|\(\d{3}\)\d{3}-\d{4}|\d{3}\.\d{3}\.\d{4}|\(\d{3}\)\s\d{3}-\d{4}')
        textmatch = textphoneRegex.findall(catalogPage.get_text())
        # Loop throuth the list of phone numberss and prints them to screen
        for x in textmatch:
            print('Phone Number: ', x)
            print()
        
        input('Press any key to continue...')
   
    while True:
        print('====================================================')
        print('=========== Webpage Phone Number Scraper============')
        print('====================================================')
        print()
        pageURL = input('Please enter the URL of the webpage: ')
        print()
        if pageURL[0:7] != 'http://' and pageURL[0:8] != 'https://':
            
            print('***Please enter a valid URL***')
            print()
            print('e.g. "http://" or "https://"')
            print()
            input('Press any key to continue...')
            os.system('cls')
        if pageURL[0:7] == 'http://' or pageURL[0:8] == 'https://':
            break
    webscrape(pageURL)        

# Print a welcome message
ans = True
# Loop that uses a boolean value to detect the end of the program
while ans:
    os.system('cls')
    print('====================================================')
    print('========THE TEAM ONE SECURITY APPLICATION===========')
    print('====================================================')
    print()

    print('1. Password Generator')
    print('2. Webpage Phone Number Scraper')
    print('3. Exit')
    print()
    menuChoice = input('Please select a menu item: ')
    # Checks user input and calls the propper procedure
    # Also checks if user input is valid
    if menuChoice == '1':
        os.system('cls')
        passwordMenu()
    elif menuChoice == '2':
        os.system('cls')
        phoneMenu()
    elif menuChoice == '3':
        ans = False
    else:
        print()
        print('***Please select a valid menu choice***')
        print()
        input('press any key to continue...')
        os.system('cls')
        continue