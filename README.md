# Unit-6-HASH-TABLES
"""
====================================================
UNIT 6 DISCUSSION: Python Dictionaries as Hash Tables
====================================================

This program demonstrates how Python dictionaries behave
like hash tables by performing insert, lookup, update,
and delete operations. It also explores several edge cases.
"""

def main():
    print("=== UNIT 6: DICTIONARIES AS HASH TABLES ===")

    # ===============================
    # CREATE A HASH TABLE
    # ===============================
    #
    # Python dictionaries use a hashing mechanism to store
    # key-value pairs. Each key is hashed to determine where
    # the value is stored internally, allowing fast access.

    inventory = {}

    # Insert key-value pairs into the dictionary
    inventory["Apples"] = 25
    inventory["Bananas"] = 18
    inventory["Milk"] = 12
    inventory["Bread"] = 15
    inventory["Eggs"] = 30

    print("\n=== INSERT OPERATIONS ===")
    print("Initial inventory (dictionary/hash table):")

    for item, quantity in inventory.items():
        print(f"{item}: {quantity}")

    # ===============================
    # LOOKUP OPERATIONS
    # ===============================
    #
    # Dictionary lookups use the key to locate the value.
    # Hashing allows Python to find items quickly without
    # searching through every entry.

    print("\n=== LOOKUP OPERATIONS ===")

    print(f"Milk quantity: {inventory['Milk']}")
    print(f"Eggs quantity: {inventory['Eggs']}")

    # ===============================
    # UPDATE OPERATIONS
    # ===============================
    #
    # Assigning a new value to an existing key replaces
    # the previous value while keeping the same key.

    print("\n=== UPDATE OPERATIONS ===")

    print("Inventory before update:")
    print(inventory)

    inventory["Milk"] = 20

    print("Inventory after updating Milk quantity:")
    print(inventory)

    # ===============================
    # DELETE OPERATIONS
    # ===============================
    #
    # Removing a key deletes both the key and its associated
    # value from the dictionary.

    print("\n=== DELETE OPERATIONS ===")

    print("Inventory before deletion:")
    print(inventory)

    del inventory["Bread"]

    print("Inventory after deleting Bread:")
    print(inventory)

    # ===============================
    # EDGE CASES
    # ===============================
    #
    # Demonstrate behavior when working with missing keys
    # and empty dictionaries.

    print("\n=== EDGE CASES ===")

    # Edge Case 1: Lookup a missing key safely
    print("\nEdge Case 1: Lookup a missing key")

    result = inventory.get("Cheese")

    if result is None:
        print("Cheese not found in inventory.")
    else:
        print(f"Cheese quantity: {result}")

    # Edge Case 2: Delete a missing key safely
    print("\nEdge Case 2: Delete a missing key")

    removed_value = inventory.pop("Juice", None)

    if removed_value is None:
        print("Juice was not found, so nothing was deleted.")
    else:
        print("Juice removed successfully.")

    # Edge Case 3: Update a missing key
    print("\nEdge Case 3: Update a missing key")

    inventory["Cheese"] = 10

    print("Adding a new key by assigning a value:")
    print(inventory)

    # Edge Case 4: Empty dictionary
    print("\nEdge Case 4: Empty dictionary")

    empty_table = {}

    print("Empty dictionary contents:")
    print(empty_table)

    print("\nProgram complete. Dictionaries provide efficient")
    print("storage and retrieval through hash table behavior.")


if __name__ == "__main__":
    main()
