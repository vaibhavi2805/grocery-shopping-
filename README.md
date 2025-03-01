#grocery shopping 
# Grocery Shopping List Application
# Grocery Shopping List Application

class GroceryList:
    def __init__(self):
        self.grocery_list = {}

    def add_item(self, item, quantity):
        if item in self.grocery_list:
            self.grocery_list[item] += quantity
        else:
            self.grocery_list[item] = quantity
        print(f"Added {quantity} of {item} to the list.")

    def remove_item(self, item):
        if item in self.grocery_list:
            del self.grocery_list[item]
            print(f"Removed {item} from the list.")
        else:
            print(f"{item} not found in the list.")

    def update_quantity(self, item, quantity):
        if item in self.grocery_list:
            self.grocery_list[item] = quantity
            print(f"Updated {item} to {quantity}.")
        else:
            print(f"{item} not found in the list.")

    def view_list(self):
        if not self.grocery_list:
            print("The grocery list is empty.")
        else:
            print("\nYour Grocery List:")
            for item, quantity in self.grocery_list.items():
                print(f"{item}: {quantity}")

    def mark_as_purchased(self, item):
        if item in self.grocery_list:
            print(f"{item} has been purchased.")
            del self.grocery_list[item]
        else:
            print(f"{item} is not in the list.")

def main():
    shopping_list = GroceryList()

    while True:
        print("\nGrocery Shopping List Menu:")
        print("1. Add Item")
        print("2. Remove Item")
        print("3. Update Quantity")
        print("4. View List")
        print("5. Mark as Purchased")
        print("6. Exit")

        choice = input("Enter your choice (1-6): ")

        if choice == '1':
            item = input("Enter item name: ")
            quantity = int(input("Enter quantity: "))
            shopping_list.add_item(item, quantity)

        elif choice == '2':
            item = input("Enter item name to remove: ")
            shopping_list.remove_item(item)

        elif choice == '3':
            item = input("Enter item name to update: ")
            quantity = int(input(f"Enter new quantity for {item}: "))
            shopping_list.update_quantity(item, quantity)

        elif choice == '4':
            shopping_list.view_list()

        elif choice == '5':
            item = input("Enter item name to mark as purchased: ")
            shopping_list.mark_as_purchased(item)

        elif choice == '6':
            print("Exiting the grocery list application.")
            break

        else:
            print("Invalid choice. Please choose between 1 and 6.")

if __name__ == "__main__":
    main()
