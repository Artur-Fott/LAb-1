def what_to_wear(temperature, is_rainy, is_raining_heavily):
    if temperature >= 20:
        return "Футболка, шорты и дождевик" if is_rainy else "Футболка и шорты"
    elif temperature < 20:
        if 8 < temperature < 20:  
            if is_rainy:
                return "Пальто, резиновые сапоги и зонт" if is_raining_heavily else "Пальто и дождевик"
            return "Пальто"
        return "Пуховик"
    else:
        return "Пальто"

temperature = int(input("Введите температуру: "))
is_rainy = False
is_raining_heavily = False
if temperature >= 20 or (8 < temperature < 20):
    is_rainy = input("Идет дождь? (да/нет): ").strip().lower() == "да"
    if 8 < temperature < 20 and is_rainy:
        is_raining_heavily = input("Сильный дождь? (да/нет): ").strip().lower() == "да"

print(what_to_wear(temperature, is_rainy, is_raining_heavily))
