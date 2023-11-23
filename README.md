# Retail-shop-
# Sample item list with prices
items = {
    'soap'  : 30,
    'shampo': 5,
    'rice'  : 75,
    'oil'   : 125,
    'water' : 15,
    'maggie': 10,
    'biscuts=':20
    # Add more items as needed
}

# Initialize variables for the shopping cart and total cost
cart = {}
total_cost = 0.0

# Display available items,
print("Available items:")
for item, price in items.items():
    print(f"{item}: ₹{price}")

# Shopping loop
while True:
    item = input("Enter item name to add to cart (or 'done' to finish shopping): ").lower()

    if item == 'done':
        break

    if item in items:
        quantity = int(input(f"Enter quantity of {item} to purchase: "))
        if quantity <= 0:
            print("Please enter a valid quantity.")
        else:
            if item in cart:
                cart[item] += quantity
            else:
                cart[item] = quantity
            total_cost += items[item] * quantity
    else:
        print("Item not found. Please choose an available item.")

# Display the items in the cart and the total cost
print("\nItems in your cart:")
for item, quantity in cart.items():
    print(f"{item}: {quantity}")
print(f"Total cost: ₹{total_cost:.2f}")

# Handle payment
payment = float(input("Enter payment amount: ₹"))
if payment < total_cost:
    print("Insufficient payment. Please provide enough funds.")
else:
    change = payment - total_cost
    print(f"Thank you for your purchase! Your change: ₹{change:.2f}")
