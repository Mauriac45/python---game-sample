# python---game-sample
### importing 

from sys import exit

### Intrducing the game
### welcome to my game called , save the day 

"""
Game :

    A) Introduction:
    This game is called <SAVE THE DAY>. the player has to go through a series 
    stages in which he or she need to save a member of his family at the hospital
    by obtaining the required medcine. If he doesn't complete the stage quickly
    family member dies.
    
    stage 1: Obtain Transportation 
    stage 2: Determine if you need fuel or not to continue the journey
    stage 3: you to determine the the right road that lead to the hospital 
    
    B) Known Bugs and/or Errors:
    None.
    
"""


### defining the game variables

player_name = input(prompt = " Hey\U0001F44B what your name ?")
print("\n")

country = input(prompt = " where are you from ?")
print("\n")

person_of_interest = input(prompt = " who you miss the most in your family? ")
print("\n")

### game start   
def game_start():
    
    print(f"""\033[1;35m Welcome, \033[4;30m{player_name}\033[0;m!, are you ready?""")
   
    print("\n")

    participant_decision = input(prompt = "\033[1;32m Yes \033[0;m / \033[1;31m No \033[0;m")
    
    if participant_decision == "Yes" or participant_decision =="yes":
        print(f""" {player_name} Just came back from his studies after five years out of the country.
At the airport, you notice no one has come to pick you up. Suddenly you receive a call from someone close to your
{person_of_interest} that informs you that,your {person_of_interest} is extremely sick at the hospital and need you
to bring medicines. If not your {person_of_interest} will die""")
        
    else:
        fail_1()

    
    print("\n")

### player need to decide on his mean of transport


    input(prompt = '\n<please press"\033[01;04;91mEnter\033[0;m" to continue>\n')
    
    print(f"""\n at this stage {player_name} need to identify a means of transport on how to get to the hospital.
{player_name} will have to chose between renting a car or taxi Are you ready,let get started !!!""")
    
    input(prompt = '\n<please press"\033[01;04;91mEnter\033[0;m" to continue>\n')
    
    stage_1()
    
    
#defining stage 1 :  Obtain Transportation 
def stage_1():
    

    chances = 2
### looping until a user is out of guesses

    while chances > 0 :
        
        print(f"""{player_name}, how are you planning to get to the hospital ?
    1) renting a car
    2) taxi
    """)
      
        answer = input(prompt = ">")
        
### Applying the conditions   

        if answer == "1" or answer == "rent a car":
            print(f""" excelent choice your a step away from saving your {person_of_interest}.\n """)
            stage_2()
            #break
                
        
        elif answer == "2" or answer == "taxi" :
            print(f"""Am so sorry, you arrived late and your {person_of_interest} died, you may have a better chance next time """)
            
            chances -= 1
            fail()
           
            
        else:
            print(f"\nplease choose how you plan to go to the hospital")
            
            chances -= 1
            fail()
            
print(f"-------------------------------------------------------------------------------------------------------")   

#defining stage 2 :    
def stage_2():
    
    
### looping until a user is out of guesses

    option = 2

    while option > 0:
        print(f""" Hurry!! your {person_of_interest} is waiting .But surprisingly , on your way to the pharmacy to collect the requested drugs, 
        the fuel signal light up in your car. You can either stop to get some fuel or drive straight to the hospital.\n
        
        1) Get fuel
        2) D'ont get fuel """ )
        
        answer = input(prompt = ">")
### Applying the conditions    

        if answer == "1" or answer == "Get fuel":
            print(f"""correct choice, the hospital is far away and this is the last petrol station it would.\n""")
            stage_3()
            #option -= 1
            
        elif answer == "2" or answer == "D'ont get fuel":
            print(f"""oh wrong choice, unfortunately your {person_of_interest} died. Your estimation was wrong, and the car stopped along the way.\n """)
            option -= 1
            fail()
            
            
        else:
            print("please chose whether you need fuel or not.\n")
            option -= 1   
            fail()
    
print(f"--------------------------------------------------------------------------------------------------------------")    
 
#defining stage 3

def stage_3():
    
    print(f""" you've finally reached the pharmacy, good job!, now it time to quickly get to the hospital.
    
    ----------------------------------------------------------------------------------------------------------------
    
    On your way to the hospital, at a road roundabout you notice 3 roads, one of this roads will take you 
    straight to the hospital.\n """)
    
### looping until a user is out of guesses    

    chance = 2

    while chance > 0 :
            
        print(f""" Time is of the essence, so what road are you willing to choose
        1) Road 1
        2) Road 2
        3) Road 3 
        """)
        answer = input(prompt = ">")
            
        if answer == "1" or answer == "Road 1":
            print(f""" sorry, unfortunately this road takes you back to the airport. Try again later.\n""")
            chance -= 1
            fail()
            break

        elif answer == "2" or answer == "Road 2":
            print(f""" Unfortunately you've loss, the road ahead is blocked, there is an accidents""")
            print("\n")
            print(f""" thanks for playing the game""")
            chance -= 1
            fail()
            break


        else:

            print(f""" excelent choice , you've reached the hospital, your {person_of_interest}'s doctor is waiting""")
            print(f""" thanks for playing the game.\n""")
            input(prompt = '<press any key to continue>\n')
            exit(0)
            break

        
        
### defining the fail funtion    

def fail():
    print("\n")
    print(f""" Oh, I'm sorry {player_name}, looks like you've arrived late to the 
    host, unfortunately sha passed away.""")
    
    print(f"""{player_name} would you like to play again? Yes / No""")
    Replay = input(prompt = ">")
    
    if Replay == "Yes" or Replay == "yes":
        game_start()
        
    else:
        print(f"""{player_name}, thanks for playing , see next time)! """)
        input('<Press any key to Exit>\n')
        Exit()
        
def fail_1(): 
    print(f""" Sad! , see you next time""")
    input('<Press any key to Exit>\n')
    Exit()
    
def Exit():
    print(""" Would you like to replay""")
    input('<Press any key to Continue>\n')
    game_start()
    
    
### calling the funtions  
game_start()
#stage_1()
