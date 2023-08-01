# File
class Repository:
    def __init__(self):
        self.data = {}

    def add_item(self, key, value):
        if key not in self.data:
            self.data[key] = value
            print(f"Added {key} to the repository.")
        else:
            print(f"{key} already exists in the repository. Use 'update_item' to modify it.")

    def update_item(self, key, new_value):
        if key in self.data:
            self.data[key] = new_value
            print(f"Updated {key} in the repository.")
        else:
            print(f"{key} does not exist in the repository. Use 'add_item' to add it.")

    def get_item(self, key):
        if key in self.data:
            return self.data[key]
        else:
            return None

    def remove_item(self, key):
        if key in self.data:
            del self.data[key]
            print(f"Removed {key} from the repository.")
        else:
            print(f"{key} does not exist in the repository.")

    def list_items(self):
        print("Repository items:")
        for key, value in self.data.items():
            print(f"{key}: {value}")


# Example usage:
repo = Repository()

repo.add_item("item1", 100)
repo.add_item("item2", 200)
repo.list_items()

repo.update_item("item1", 150)
print(f"item1 value: {repo.get_item('item1')}")

repo.remove_item("item2")
repo.list_items()
