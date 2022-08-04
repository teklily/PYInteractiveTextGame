

# -*- coding: utf-8 -*-
"""
Created on Sun Jul 31 14:37:46 2022

@author: Lili
"""

#pyinstaller
from os import system
from random import randint, choice
import random






gametitle = "Castle Dungeouns  - an interactive story game"
#use system module to tell the system what the size of the window should be
system("mode 110,30")
#and add a title
system("title "+gametitle)

#this will clear the screen, like in BASIC, teehee.
#def cls():
#    system('cls')

#Empty character name, this will be entered by the user.
character_name = None
character_race = None
character_class = None
character_strength = None
character_magic = None
character_dexterity = None
character_life = None




#call the clear screen function.
#cls()
print("Castle Dungeons - An interactive fiction game in Python.")

def Intro():
    print("")
    print("In this adventure, you are the hero.")
    print("Your choices, skills, and a bit of luck, will influence the outcome of the game.")
    print("")
    print("An evil sorcerer is holding your fellow adventurers prisoners.")
    print("Will you succeed to free your friends from the castle dungeons, or perish trying?")
    print("")
    #collect input from the user
    input("Press Enter to start...")


#call the function Intro()
Intro()

#Now we create the characters
def create_character():
   # cls()
    #specify global bc we want it to be accessible at any time.
    global character_name
    #a multi line string
    character_name=input("""
        Let's begin by creating your character.
        What is your character name?
        
        > """)
    #print(character_name) just testing to make sure things work here.

    global character_race
    while character_race is None:
        #create local variable to collect race choice.
        race_choice=input("""
        Choose your character race from the list below by entering the relevant number:
            1. -Elf
            2 - Dwarf
            
            > """)
        if race_choice=="1":
            character_race="Elf"
        elif race_choice=="2":
            character_race="Dwarf"
            #incase they enter something else.
        else:
            print("Not a valid choice, try again")
            
            
    #cls()
    global character_class
    while character_class is None:
        class_choice=input("""
        Choose your character class from the list below by entering the relevant number:
            1 - Warrior
            2 - Wizard
            
            >""")
        if class_choice=="1":
            character_class="Warrior"
        elif class_choice=="2":
            character_class="Wizard"
        else:
            print("Not a valid choice, try again")
create_character()


def create_character_skill_sheet():
   # cls()
    global character_name, character_class, character_name, character_strength, character_dexterity, character_magic, character_life
    print("""
    Now let's determine your character's skills, which you will use throughout the game.
    In this game, your character has four skills:
    
    - Strength, which you will use in combat or any strength test
    - Dexterity, which you will use in any ability test
    - Magic, which you will use whenever you need to cast a spell or use/inspect a magical item or place
    - Life, which determines your life energy, points will be lost when hurt, 
      and whenever Life reaches 0, your character dies.

    
    Depending on your race and class, you will have a certain point-base already calculated by the game.
    You will shortly be able to increase your skills by rolling a 6-face die.

    Here is your base Character Skills Sheet:
    """)
    character_strength=5
    character_magic=0
    character_dexterity=3
    character_life=10
    if character_race=="Elf":
        character_strength=character_strength+3
        character_magic=character_magic+6
        character_dexterity=character_dexterity+4
        character_life=character_life+2
    elif character_race=="Dwarf":
        character_strength=character_strength+5
        character_life=character_life+4
    if character_class=="Warrior":
        character_strength=character_strength+3
        character_life=character_life+3
    elif character_race=="Wizard":
        character_magic=character_magic+4
    print("""
    Name:"""+character_name+
    """
    Race:"""+character_race+
    """
    Class:"""+character_class+
    """
    
    Strength: """ +str(character_strength)+#change number to string to print
    """
    Dexterity:"""+str(character_dexterity)+
    """
    Magic:"""+str(character_magic)+
    """
    Life:"""+str(character_life)+"""
    
    """)
    input("Press Enter to apply your skills modifiers")

create_character_skill_sheet()

def modify_skills():
    #cls()
    global character_strength, character_dexterity, character_life
    print("To modify your skills, roll a six face die for each of your skills, and the game will add your score to the relevant skill")
    
    input("Press Enter to roll for Strength")
    roll=randint(1,6)
    print(f"You rolled: {roll}")
    character_strength=character_strength+roll
    input("Press Enter to roll for Dexterity")
    roll=randint(1,6)
    print(f"You rolled: {roll}")
    character_dexterity=character_dexterity+roll
    
    input("Press Enter to roll for Life")
    roll=randint(1,6)
    print(f"You rolled: {roll}")
    character_life=character_life+roll
    input("Press Enter to continue...")
   # cls()
    print("""
    Congratulations! You have completed your character creation!
    Your final character sheet is:

    Name:"""+character_name+
    """
    Race:"""+character_race+
    """
    Class:"""+character_class+
    """
    
    Strength:"""+ (str(character_strength))+
    """
    Dexterity:"""+str(character_dexterity)+
    """
    Magic:"""+str(character_magic)+
    """
    Life:"""+str(character_life)+"""

    """)
    input("Press Enter to begin your adventure, if you dare...")

modify_skills()

def scene_3():
  #  cls()
    choice = None
    while choice is None:
        user_input=input("""
    From the darkness ahead of you.. you hear a strange noise.

    What do you do?

    1 - Continue walking
    2 - Stop to listen

    > """)
        if user_input=="1" or user_input=="continue":
            choice="1"
            random.choice(Combat)()
        elif user_input=="2" or user_input=="stop":
            choice="2"
            random.choice(Skill)()
        else:
            print("""
            Not a valid choice, type a number or - "continue" / "stop"
            """)

def scene_1():
    #cls()
    choice=None
    while choice is None:
        print("Welcome")
        user_input=input("""
        You have entered the Castle Dungeons.. 
        It is dark, however thankfully your torch is lit and you can see up to 20 feet away from you.
        The stone walls are damp, the smell of rats and orcs is strong. 
        You walk down a narrow corridor, until you reach a thick stone wall.

        The corridor continues on the left, and on the right.

        What do you do?

        1 - Turn left
        2 - Turn right    
        > """)
        if user_input=="1" or user_input=="turn left":
            choice="1"
            random.choice(Scene)()
            #choice(Scene)
        elif user_input=="2" or user_input=="turn right":
            choice="2"
            random.choice(Scene)()
            #choice(Scene)
        else:
            print("""
                  Not a valid choice, type a number or "turn left" / "turn right"
                  """)

def combat_2():
   # cls()
    global character_life
    print("An evil Elf finds you and is waiting to kill you with his bow!")
    input("Press Enter to combat...")
    # create a python list, similar to an array. First is strenth,life of orc.
    #this is a simple way to create a monster sheet.
    elf=[2,14]
    #or not and, otherwise it could go on forever!LOL.
   # while orc[1] > 0 or character_life > 0:
    #while elf[1] > 0 or character_life>0:
    while elf[1] > 0:
        char_roll=randint(1,6)
        print(f"You rolled: {char_roll}")
        elf_roll=randint(1,3)
        print(f"The Elf rolled: {elf_roll}")
        if char_roll+character_strength >= elf[0]:
            print("You hit the Elf!")
            #roll die to establish how many life points will be taken away from position 1 of the orc.
            elf[1]= elf[1] - randint(1,6)
            if elf[1] < 0:
                print("The End... or is it?")
            #print("Elf life points left", elf[1])
            
        else:
            print("The Elf hits you!")
            #damage roll for the character
            character_life = character_life - randint(1,6)
        if elf[0] < 0:
            print("You win!")
            input("Press Enter to exit the game")
            #break
    if character_life > 0:
        #adding ability to take character_life from monster defeated.
        character_life = character_life + (elf[0])
        print("You defeated the Elf, Congratulations! Some of the Elf's life points transferred to you!")
        #print("You defeated the Elf, Congratulations! You still have",str(character_life), "Life points! Some of the Elf's life points transferred to you! You may now go to the pub and order some refreshing strawberry lemonade :)")
        random.choice(Scene)()
        input("Press Enter to exit the game")
        #elif orc[1] < 0:
   #     print("You defeated the orc, Woohoo!")
    #    input("Press Enter to exit the game")
    else:
        print("You lost... your friends will never be freed... and you're dead.")
        input("Press Enter to exit the game")

def scene_5():
   # cls()
    choice = None
    while choice is None:
        user_input=input("""
    From the darkness ahead of you.. you hear a strange noise.

    What do you do?

    1 - Continue walking
    2 - Rest at the corner of the room

    > """)
        if user_input=="1" or user_input=="continue":
            choice="1"
            random.choice(Combat)()
        elif user_input=="2" or user_input=="stop":
            choice="2"
            random.choice(Fairy)()
        else:
            print("""
            Not a valid choice, type a number or - "continue" / "stop"
            """)

def fairy_1():
    #cls()
    global character_life
    global character_strength
    global character_magic
    global character_dexterity
    
    character_life = character_life + randint(1, 3)
    character_strength = character_strength + randint(1, 3)
    character_dexterity = character_dexterity + randint(1, 3)
    
    if character_race == "Elf":
        character_magic = character_magic + randint(1, 2)
        print(f"""
    You encounter a beautiful fairy. 
    She tells you her glass of water will refresh you. You reach for the glass and drink it all. You start to feel a little funny. The world starts spinning. You close your eyes.
    When you open them, she tells you your life has been restored and you have gone up a level! 
    """)
    elif character_race == "Wizard":
        character_magic = character_magic + randint(1, 5)
        print(f"""
    You encounter a beautiful fairy. 
    She tells you her glass of water will refresh you. You reach for the glass and drink it all. You start to feel a little funny. The world starts spinning. You close your eyes.
    When you open them, she tells you your life has been restored and you have gone up a level!
    """)
    else:
        print("""
    You encounter a beautiful fairy. 
    She tells you her glass of water will refresh you. You reach for the glass and drink it all. You start to feel a little funny. The world starts spinning. You close your eyes.
    When you open them, she tells you your life has been restored and you have gone up a level!
    """)
    input("Press Enter to exit...")

        
def scene_2():
   # cls()
    choice = None
    while choice is None:
        user_input=input("""
    From the darkness behind you.. you hear a strange noise.

    What do you do?

    1 - Continue walking
    2 - Stop to listen

    > """)
        if user_input=="1" or user_input=="continue":
            choice="1"
            random.choice(Combat)()
            #choice(Combat)()
        elif user_input=="2" or user_input=="stop":
            choice="2"
            random.choice(Skill)()
        else:
            print("""
            Not a valid choice, type a number or "continue" / "stop"
            """)

            
def skill_check_1():
    #cls()
    print("A giant rock falls from the ceiling, roll a die to see if you can dodge it.. or you will be crashed by it!")
    roll=randint(1,6)
    print(f"You rolled: {roll}")
    if roll+character_dexterity > 10:
        print ("""
        You dodge the stone and survive! Danger is not over though..
        The strange noise in the darkness continues, and it feels a lot closer now..""")
        input("Press Enter to continue...")
        random.choice(Combat)()
    else:
        print("You are smashed by the rock.. You die. The game is over.")
        input("Press Enter to exit the game.")

def scene_4():
    #cls()
    choice = None
    while choice is None:
        user_input=input("""
    You feel and hear a sudden woosh! An arrow flies right by your head! 

    What do you do?

    1 - Continue and start running!
    2 - Duck!

    > """)
        if user_input=="1" or user_input=="continue":
            choice="1"
            random.choice(Skill)()
        elif user_input=="2" or user_input=="stop":
            choice="2"
            random.choice(Combat)()
            
        else:
            print("""
            Not a valid choice, type a number or "continue" / "stop"
            """)
            
def skill_check_2():
   # cls()
    print("You continue running and suddenly find yourself at the edge of a giant hole in the dungeoun floor!")
    roll=randint(1,6)
    print(f'You rolled: {roll} ')
    if roll+character_dexterity > 10:
        print ("""
        Phew, you were able to stop in time..
        However, you hear leaves rustling and twigs breaking...""")
        input("Press Enter to continue...")
        random.choice(Combat)()
    else:
        print("You were not able to stop in time, and tumble to your death!")
        input("Press Enter to exit the game.")
        
def combat_1():
    print("this is combat_1")
    #cls()
    global character_life
    print("A horrible orc attacks you!")
    input("Press Enter to combat...")
    # create a python list, similar to an array. First is strenth,life of orc.
    #this is a simple way to create a monster sheet.
    orc=[10,14]
    #or not and, otherwise it could go on forever!LOL.
   # while orc[1] > 0 or character_life > 0:
    #while orc[1] > 0 or character_life>0:
    while orc[1] > 0:
        char_roll=randint(1,6)
        print(f"You rolled: {char_roll}")
        monst_roll=randint(1,6)
        print(f"The monster rolled: {monst_roll}")
        if char_roll+character_strength >= monst_roll+orc[0]:
            print("You hit the monster!")
            #roll die to establish how many life points will be taken away from position 1 of the orc.
            orc[1]= orc[1] - randint(1,6)
            print(f"Orc life points left {orc[1]}")
        else:
            print("The monster hits you!")
            #damage roll for the character
            character_life = character_life - randint(1,6)
            print(f"You have {character_life} remaining")
            if character_life < 0:
                print("You lost... your friends will never be freed... and you're dead.")
                input("Press Enter to exit the game")
            #break
    if character_life > 0:
        #print("You defeated the orc, Congratulations! You still have",str(character_life), "Life points!")
        print("You defeated the orc, Congratulations!" )
        input("Press Enter to continue...")
        random.choice(Scene)()
        #choice(randomscene)()
        #input("Press Enter to exit the game")
        #elif orc[1] < 0:
   #     print("You defeated the orc, Woohoo!")
    #    input("Press Enter to exit the game")
    else:
        print("You lost... your friends will never be freed... and you're dead.")
        input("Press Enter to exit the game")


Combat = [combat_1, combat_2, ]
Scene = [scene_2, scene_3, scene_4, scene_5]
Skill = [skill_check_1, skill_check_2]
Fairy = [fairy_1]
Inventory =[]
Gold = []

scene_1()
