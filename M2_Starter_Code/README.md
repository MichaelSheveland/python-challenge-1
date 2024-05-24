# python-challenge-1
python-challenge-1

# Menu dictionary


# 1. Set up order list. Order list will store a list of dictionaries for
# menu item name, item price, and quantity ordered
order_list = [] 
"""order list created"""

# Launch the store and present a greeting to the customer
print("Welcome to the variety food truck.")

"""greeting to the customer"""

place_order = input("Make Your Selection: Snacks, Meals, Desserts, Drinks? ")
# Customers may want to order multiple items, so let's create a continuous
# loop
place_order = True
while place_order:
    # Ask the customer from which menu category they want to order
    print("From which menu would you like to order? ")

    # Create a variable for the menu item number
    i = 1
    # Create a dictionary to store the menu for later retrieval
    menu_items = {}

    """creating a variable to store the menu item number used later"""

    # Print the options to choose from menu headings (all the first level
    # dictionary items in menu).
    for key in menu.keys():
        print(f"{i}: {key}")
        # Store the menu category associated with its menu item number
        menu_items[i] = key
        # Add 1 to the menu item number
        i += 1


    # Get the customer's input
    menu_category = input("Type menu number: ")

    # Check if the customer's input is a number
    if menu_category.isdigit():
        # Check if the customer's input is a valid option
        if int(menu_category) in menu_items.keys():
            # Save the menu category name to a variable
            menu_category_name = menu_items[int(menu_category)]
            # Print out the menu category name they selected
            print(f"You selected {menu_category_name}")

            # Print out the menu options from the menu_category_name
            print(f"What {menu_category_name} item would you like to order?")
            i = 1
            menu_items = {}
            print("Item # | Item name                | Price")
            print("-------|--------------------------|-------")
            for key, value in menu[menu_category_name].items():
                # Check if the menu item is a dictionary to handle differently
                if type(value) is dict:
                    for key2, value2 in value.items():
                        num_item_spaces = 24 - len(key + key2) - 3
                        item_spaces = " " * num_item_spaces
                        print(f"{i}      | {key} - {key2}{item_spaces} | ${value2}")
                        menu_items[i] = {
                            "Item name": key + " - " + key2,
                            "Price": value2
                        }
                        i += 1
                else:
                    num_item_spaces = 24 - len(key)
                    item_spaces = " " * num_item_spaces
                    print(f"{i}      | {key}{item_spaces} | ${value}")
                    menu_items[i] = {
                        "Item name": key,
                        "Price": value
                    }
                    i += 1
            # 2. Ask customer to input menu item number
            menu_selection = input("Can you enter a Menu Item Number?")
            if menu_selection == 'q':
                break
            # 3. Check if the customer typed a number
            if menu_selection.isdigit():
                menu_selection = int(menu_selection)
        else:
            print("You didn't input a valid number") 
            
                # 4. Check if the menu selection is in the menu items
                if int(menu_selection) in menu_items.keys():
                    # Store the item name as a variable
                    menu_selection_name = menu_items[int(menu_selection)]
                    # Ask the customer for the quantity of the menu item
                    quantity_menu_item =input(" How many items do you want?")

                    # Check if the quantity is a number, default to 1 if not
                    if menu_selection.isdigit(): 
                        quantity_menu_item = int(quantity_menu_item)
                        print(f"Input{quantity_menu_item}is a number!")
                        else quantity_menu_item = 1

                        """"checking item Quantity matches and is a valid number"""
                      

                ###Quantity_menu_item in menu_items.keys():

                    # Add the item name, price, and quantity to the order list
                order.append({"Item_name" : item_name, "Price" : price, "Quantity" : quantity})

                    # Tell the customer that their input isn't valid
                    print(f"{menu_selection} is not a valid menu item ")

                # Tell the customer they didn't select a menu option
                  print(f"{menu_category} was not a menu option.")
        else:
            # Tell the customer they didn't select a menu option
            print("Your item selection is not a menu option")
    else:
        # Tell the customer they didn't select a number
         print("You didn't select a number.")

    while True:
        # Ask the customer if they would like to order anything else
        keep_ordering = input("Would you like to keep ordering? (Y)es or (N)o ")

        # 5. Check the customer's input
        match keep_ordering.Upper():
            case "Y":

                # Keep ordering
                if continue_ordering == 'Y':
                    place_order = True
                
                # Exit the keep ordering question loop
                break
                # Complete the order
                 case "N"
                # Since the customer decided to stop ordering, thank them for
                # their order
                place_order = False
                # Exit the keep ordering question loop
                break

                # Tell the customer to try again
                print("try ordering once more")

"""allowing customer to order more to stop with a break 'N" """"

# Print out the customer's order
print("This is what we are preparing for you.\n")

# Uncomment the following line to check the structure of the order
#print(order)

print("Item name                 | Price  | Quantity")
print("--------------------------|--------|----------")

# 6. Loop through the items in the customer's order
 for i in range(len(order_list)):
    # 7. Store the dictionary items as variables
    item_name = order_list[List]["item"]
    item_price = order_list[List]["price"]
    item_quantity = order_list[List]["quantity"]

    # 8. Calculate the number of spaces for formatted printing
    num_item_spaces = 60 - len(item_name)

    # 9. Create space strings
        print("-" * 60)

    # 10. Print the item name, price, and quantity
    print(item_name + item_spaces + "|"+ item_price+ price_spaces+ "|" + item_quantity+ quantity_spaces + "|")

# 11. Calculate the cost of the order using list comprehension
print(f"{rides[i]} costs ${prices[i]:.2f} to ride.")
# Multiply the price by quantity for each item in the order list, then sum()
order_cost= sum(order ['price'] * ['quantity'] for order in order_list)

"""formula to calc total price based on item,price and quantity""""

# and print the prices.
print(f"Total is: $ {total:.2f}")

"""total price displayed 2 decimal places"""