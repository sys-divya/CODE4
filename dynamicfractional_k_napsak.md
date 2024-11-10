class Item:
    def __init__(self, value, weight):
        self.value = value
        self.weight = weight
        self.ratio = value / weight  # Value-to-weight ratio

def fractional_knapsack(capacity, items):
    items.sort(key=lambda x: x.ratio, reverse=True)  # Sort items by ratio
    total_value = 0

    for item in items:
        if capacity <= 0:
            break
        if item.weight <= capacity:
            total_value += item.value  # Take the whole item
            capacity -= item.weight
        else:
            total_value += item.ratio * capacity  # Take the fraction
            capacity = 0  # Knapsack is full

    return total_value

# Dynamic input
if __name__ == "__main__":
    capacity = float(input("Enter the capacity of the knapsack: "))
    n = int(input("Enter the number of items: "))
    items = [Item(float(input(f"Enter the value of item {i + 1}: ")), 
                   float(input(f"Enter the weight of item {i + 1}: "))) for i in range(n)]

    max_value = fractional_knapsack(capacity, items)
    print(f"Maximum value in Knapsack = {max_value}")
