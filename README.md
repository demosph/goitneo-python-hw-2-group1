# Домашнє завдання №2

## Приклади:
### Завдання №1

Обробка ValueError
```
Enter a command: add Eugene
Invalid command format. Use '[name] [phone]' as command arguments.
Enter a command: change Julia
Invalid command format. Use '[name] [phone]' as command arguments.
Enter a command: add John +380 647882145
Invalid command format. Use '[name] [phone]' as command arguments.
```
Обробка KeyError
```
Enter a command: phone Tanya
Contact with the name 'Tanya' doesn't exists. Use 'add [name] [new_phone]' to add.
```

Обробка IndexError
```
Enter a command: phone
Invalid command format. Use 'phone [name]' to get contact number.
```


### Завдання №2

```python
# Створення нової адресної книги
book = AddressBook()

# Створення запису для John
john_record = Record("John")
john_record.add_phone("1234567890")
john_record.add_phone("5555555555")

# Додавання запису John до адресної книги
book.add_record(john_record)
# Створення та додавання нового запису для Jane
jane_record = Record("Jane")
jane_record.add_phone("9876543210")
book.add_record(jane_record)
# Виведення всіх записів у книзі
for name, record in book.data.items():
    print(record)
# Знаходження та редагування телефону для John
john = book.find("John")
john.edit_phone("1234567890", "1112223333")
print(john)  # Виведення: Contact name: John, phones: 1112223333; 5555555555
# Пошук конкретного телефону у записі John
found_phone = john.find_phone("5555555555")
print(f"{john.name}: {found_phone}")  # Виведення: 5555555555
# Видалення запису Jane
book.delete("Jane")
```