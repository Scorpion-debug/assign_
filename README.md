class Smartphone:
    def __init__(self, brand, model, storage, color):
        self.brand = brand
        self.model = model
        self._storage = storage
        self.color = color

    def get_storage(self):
        return f"{self._storage} GB"

    def make_call(self, number):
        print(f"Calling {number} from {self.brand} {self.model}...")

    def __str__(self):
        return f"{self.brand} {self.model} ({self.color}, {self._storage}GB)"

class iPhone(Smartphone):
    def __init__(self, model, storage, color, ios_version):
        super().__init__("Apple", model, storage, color)
        self.ios_version = ios_version

    def make_call(self, number):
        print(f"Using FaceTime Audio to call {+2541234567} on your iPhone {self.model}.")

    def update_ios(self, new_version):
        if new_version > self.ios_version:
            print(f"Updating iOS from {self.ios_version} to {new_version}...")
            self.ios_version = new_version
        else:
            print(f"Your iPhone already has the latest iOS version: {self.ios_version}")

    def __str__(self):
        return f"iPhone {self.model} ({self.color}, {self._storage}GB, iOS {self.ios_version})"


phone1 = Smartphone("Samsung", "Galaxy S22", 128, "Black")
phone2 = iPhone("14 Pro", 256, "Silver", 20.0)

print(phone1)
phone1.make_call("+123456789")

print("\n" + "-"*40 + "\n")

print(phone2)
phone2.make_call("+987654321")
phone2.update_ios(23.0)
