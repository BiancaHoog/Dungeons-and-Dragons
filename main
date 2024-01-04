import random

def get_name():
    name = input("Enter your character's name: ")
    return name

def sum_of_four_six_sided_dice_with_lowest_dropped():
    dice_rolls = [random.randint(1, 6) for _ in range(4)]
    dice_rolls.sort()
    return sum(dice_rolls[1:])

def get_ability_modifier(ability_score):
    modifier = (ability_score - 10) // 2
    return modifier

def menu():
    print("Actions:")
    print("1. Attack")
    print("2. Negotiate")
    print("3. Search")
    print("4. Eat")
    choice = int(input("Choose an action (1-4): "))
    return choice

def attack(ability_modifier):
    attack_roll = random.randint(1, 20)
    total = attack_roll + ability_modifier
    if total >= 12:
        print("You hit!")
        damage_roll = random.randint(1, 6)
        damage = max(0, damage_roll + ability_modifier)
        print("You deal {} damage.".format(damage))
    else:
        print("You missed.")

def negotiate(ability_modifier):
    negotiate_roll = random.randint(1, 20)
    total = negotiate_roll + ability_modifier
    if total >= 15:
        print("You successfully negotiated a truce.")
    else:
        print("Negotiation failed.")

def search(ability_modifier):
    search_roll = random.randint(1, 20)
    total = search_roll + ability_modifier
    if total >= 12:
        print("You found some treasure!")
        treasure = get_random_treasure()
        print("You obtained: {}".format(treasure))
    else:
        print("You found nothing.")

def eat(constitution_modifier):
    print("Your food was rancid.")
    eat_roll = random.randint(1, 20)
    total = eat_roll + constitution_modifier
    if total >= 10:
        print("You were able to handle the rancid food without getting sick.")
    else:
        print("You got sick and need to stay in bed.")

def get_random_treasure():
    treasures = ["gems", "gold", "jade figurine", "other type"]
    return random.choice(treasures)

def main():
    results = []

    name = get_name()
    print("Character's Name:", name)

    strength = sum_of_four_six_sided_dice_with_lowest_dropped()
    dexterity = sum_of_four_six_sided_dice_with_lowest_dropped()
    constitution = sum_of_four_six_sided_dice_with_lowest_dropped()
    intelligence = sum_of_four_six_sided_dice_with_lowest_dropped()
    wisdom = sum_of_four_six_sided_dice_with_lowest_dropped()
    charisma = sum_of_four_six_sided_dice_with_lowest_dropped()

    print("Strength:", strength)
    print("Dexterity:", dexterity)
    print("Constitution:", constitution)
    print("Intelligence:", intelligence)
    print("Wisdom:", wisdom)
    print("Charisma:", charisma)

    ability_scores = [strength, dexterity, constitution, intelligence, wisdom, charisma]
    ability_modifiers = [get_ability_modifier(score) for score in ability_scores]

    for _ in range(4):
        choice = menu()
        if choice == 1:
            attack(ability_modifiers[0])
        elif choice == 2:
            negotiate(ability_modifiers[5])
        elif choice == 3:
            search_modifier = max(ability_modifiers[3], ability_modifiers[4])
            search(search_modifier)
        elif choice == 4:
            eat(ability_modifiers[2])

    results.append("Character: {}".format(name))
    results.append("Strength: {}".format(strength))
    results.append("Dexterity: {}".format(dexterity))
    results.append("Constitution: {}".format(constitution))
    results.append("Intelligence: {}".format(intelligence))
    results.append("Wisdom: {}".format(wisdom))
    results.append("Charisma: {}".format(charisma))

    return results


game_results = main()
for result in game_results:
    print(result)
