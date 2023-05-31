# Lab2
from random import randint


def get_intersection(set_a: set, set_b: set):

 #   Отримує перетин двох множин

    if not isinstance(set_a, set) or not isinstance(set_b, set):
        raise TypeError("Аргументи повинні бути наборами.")
    return set_a & set_b


def get_union(set_a: set, set_b: set):

#   Отримує перетин двох множин

    if not isinstance(set_a, set) or not isinstance(set_b, set):
        raise TypeError("Аргументи повинні бути наборами.")
    return set_a.union(set_b)


def add_element_to_set(set_data: set, element):

# Додає елемент у множину

    if not isinstance(set_data, set):
        raise TypeError("Перший аргумент має бути набором.")
    set_data.add(element)
    return set_data


def remove_element_from_set(set_data: set, element):

 # Видаляє елемент із множини

    if not isinstance(set_data, set):
        raise TypeError("Перший аргумент має бути набором.")
    set_data.discard(element)
    return set_data


def create_random_list(length: int):

# Створює перелік випадкових цілих чисел заданої довжини

    if not isinstance(length, int) or length < 1:
        raise ValueError("Довжина має бути додатним цілим числом.")
    return [randint(0, 100) for _ in range(length)]


def add_element_to_list(lst: list, element):

 # Додає елемент у список   Добавляет элемент в список

    lst.append(element)
    return lst


def remove_element_from_list(lst: list, value):

#    Видаляє елемент із списка

    if not isinstance(lst, list):
        raise TypeError("Перший аргумент має бути списком.")
    try:
        lst.remove(value)
    except ValueError:
        pass
    return lst


def sort_list_in_ascending_order(lst: list):

 #   Сортує список за зростанням

    if not isinstance(lst, list):
        raise TypeError("Аргумент має бути списком.")
    return sorted(lst)


def create_dictionary_from_lists(keys: list, values: list):

# Створює словник на основі списків ключів та значень

    return dict(zip(keys, values))


def add_element_to_dict(d: dict, key, value):

# Додає елемент до словника

    if isinstance(key, int):
        d[key] = value
    return d


def remove_element_from_dict(d: dict, key):

# Видаляє елемент зі словника

    if isinstance(key, int) and key in d:
        del d[key]
    return d


def iterate_over_dict(d: dict):
    
# Ітерується за словником і виводить на екран усі ключі та відповідні значення
    
    for key, value in d.items():
        print(f"{key}: {value}")


set_data_1 = {1, 3, 4, 5, 6}
set_data_2 = {1, 2, 3, 7, 8}

print(get_intersection(set_data_1, set_data_2))
print(get_union(set_data_1,set_data_2))
print(add_element_to_set(set_data_1, 100))
print(remove_element_from_set(set_data_1, 1))

list_data_1 = create_random_list(11)
list_data_2 = create_random_list(11)

print(list_data_1)
print(add_element_to_list(list_data_1, 111))
print(remove_element_from_list(list_data_1, 111))
print(sort_list_in_ascending_order(list_data_1))

dict_data = create_dictionary_from_lists(list_data_1, list_data_2)

print(dict_data)
print(add_element_to_dict(dict_data, 120, 100))
print(remove_element_from_dict(dict_data, 120))
iterate_over_dict(dict_data)
