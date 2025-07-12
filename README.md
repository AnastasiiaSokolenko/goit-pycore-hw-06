# AddressBook

A simple Python Address Book system built using OOP principles.

## Features

- Add new contacts.
- Store multiple phone numbers per contact.
- Edit, remove, or search phone numbers.
- Find or delete contacts by name.
- Phone number validation (must be 10 digits).

## Classes

### Field

- Base class for all fields in a contact.

### Name(Field)

- Stores the name of a contact.

### Phone(Field)

- Stores a phone number.
- Validates that the number contains exactly 10 digits.

### Record

- Represents a single contact.
- Contains a `Name` and a list of `Phone` numbers.
- Methods:
  - `add_phone(phone_number)`
  - `remove_phone(phone_number)`
  - `edit_phone(old_number, new_number)`
  - `find_phone(phone_number)`

### AddressBook (UserDict)

- Stores multiple `Record` instances.
- Methods:
  - `add_record(record)`
  - `find(name)`
  - `delete(name)`

## Example Usage

```python
# Create a new address book
book = AddressBook()

# Create a record for John
john_record = Record("John")
john_record.add_phone("1234567890")
john_record.add_phone("5555555555")

# Add John's record to the book
book.add_record(john_record)

# Find John and edit a phone number
john = book.find("John")
john.edit_phone("1234567890", "1112223333")

print(john)  # Output: Contact name: John, phones: 1112223333; 5555555555

# Search for a phone number
phone = john.find_phone("5555555555")
print(phone)  # Output: 5555555555

# Delete Jane's record
book.delete("Jane")
```
