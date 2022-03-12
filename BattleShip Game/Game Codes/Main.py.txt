
# Ultimate Battleships
from turtledemo.penrose import f


def print_ships_to_be_placed():
    print("Ships to be placed:", end=" ")
    if FILE_OUTPUT_FLAG:
        f.write("Ships to be placed: ")


# elem expected to be a single list element of a primitive type.
def print_single_element(elem):
    print(str(elem), end=" ")
    if FILE_OUTPUT_FLAG:
        f.write(str(elem) + " ")


def print_empty_line():
    print()
    if FILE_OUTPUT_FLAG:
        f.write("\n")


# n expected to be str or int.
def print_player_turn_to_place(n):
    print("It is Player {}'s turn to place their ships.".format(n))
    if FILE_OUTPUT_FLAG:
        f.write("It is Player {}'s turn to place their ships.\n".format(n))


def print_to_place_ships():
    print("Enter a name, coordinates and orientation to place a ship (Example: Carrier 1 5 h) :", end=" ")
    if FILE_OUTPUT_FLAG:
        f.write("Enter a name, coordinates and orientation to place a ship (Example: Carrier 1 5 h) : \n")
        # There is a \n because we want the board to start printing on the next line.


def print_incorrect_input_format():
    print("Input is in incorrect format, please try again.")
    if FILE_OUTPUT_FLAG:
        f.write("Input is in incorrect format, please try again.\n")


def print_incorrect_coordinates():
    print("Incorrect coordinates given, please try again.")
    if FILE_OUTPUT_FLAG:
        f.write("Incorrect coordinates given, please try again.\n")


def print_incorrect_ship_name():
    print("Incorrect ship name given, please try again.")
    if FILE_OUTPUT_FLAG:
        f.write("Incorrect ship name given, please try again.\n")


def print_incorrect_orientation():
    print("Incorrect orientation given, please try again.")
    if FILE_OUTPUT_FLAG:
        f.write("Incorrect orientation given, please try again.\n")


# ship expected to be str.
def print_ship_is_already_placed(ship):
    print(ship, "is already placed, please try again.")
    if FILE_OUTPUT_FLAG:
        f.write(ship + " is already placed, please try again.\n")


# ship expected to be str.
def print_ship_cannot_be_placed_outside(ship):
    print(ship, "cannot be placed outside the board, please try again.")
    if FILE_OUTPUT_FLAG:
        f.write(ship + " cannot be placed outside the board, please try again.\n")


# ship expected to be str.
def print_ship_cannot_be_placed_occupied(ship):
    print(ship, "cannot be placed to an already occupied space, please try again.")
    if FILE_OUTPUT_FLAG:
        f.write(ship + " cannot be placed to an already occupied space, please try again.\n")


def print_confirm_placement():
    print("Confirm placement Y/N :", end=" ")
    if FILE_OUTPUT_FLAG:
        f.write("Confirm placement Y/N : \n")


# n expected to be str or int.
def print_player_turn_to_strike(n):
    print("It is Player {}'s turn to strike.".format(n))
    if FILE_OUTPUT_FLAG:
        f.write("It is Player {}'s turn to strike.\n".format(n))


def print_choose_target_coordinates():
    print("Choose target coordinates :", end=" ")
    if FILE_OUTPUT_FLAG:
        f.write("Choose target coordinates : ")


def print_miss():
    print("Miss.")
    if FILE_OUTPUT_FLAG:
        f.write("Miss.\n")


# n expected to be str or int.
def print_type_done_to_yield(n):
    print("Type done to yield your turn to player {} :".format(n), end=" ")
    if FILE_OUTPUT_FLAG:
        f.write("Type done to yield your turn to player {} : \n".format(n))


def print_tile_already_struck():
    print("That tile has already been struck. Choose another target.")
    if FILE_OUTPUT_FLAG:
        f.write("That tile has already been struck. Choose another target.\n")


def print_hit():
    print("Hit!")
    if FILE_OUTPUT_FLAG:
        f.write("Hit!\n")


# n expected to be str or int.
def print_player_won(n):
    print("Player {} has won!".format(n))
    if FILE_OUTPUT_FLAG:
        f.write("Player {} has won!\n".format(n))


def print_thanks_for_playing():
    print("Thanks for playing.")
    if FILE_OUTPUT_FLAG:
        f.write("Thanks for playing.\n")


# my_list expected to be a 3-dimensional list, formed from two 2-dimensional lists containing the boards of each player.
def print_3d_list(my_list):
    first_d = len(my_list[0])
    for row_ind in range(first_d):
        second_d = len(my_list[0][row_ind])
        print("{:<2}".format(row_ind+1), end=' ')
        for col_ind in range(second_d):
            print(my_list[0][row_ind][col_ind], end=' ')
        print("\t\t\t", end='')
        print("{:<2}".format(row_ind+1), end=' ')
        for col_ind in range(second_d):
            print(my_list[1][row_ind][col_ind], end=' ')
        print()
    print("", end='   ')
    for row_ind in range(first_d):
        print(row_ind + 1, end=' ')
    print("\t\t", end='   ')
    for row_ind in range(first_d):
        print(row_ind + 1, end=' ')
    print("\nPlayer 1\t\t\t\t\t\tPlayer 2")
    print()

    if FILE_OUTPUT_FLAG:
        first_d = len(my_list[0])
        for row_ind in range(first_d):
            second_d = len(my_list[0][row_ind])
            f.write("{:<2} ".format(row_ind + 1))
            for col_ind in range(second_d):
                f.write(my_list[0][row_ind][col_ind] + " ")
            f.write("\t\t\t")
            f.write("{:<2} ".format(row_ind + 1))
            for col_ind in range(second_d):
                f.write(my_list[1][row_ind][col_ind] + " ")
            f.write("\n")
        f.write("   ")
        for row_ind in range(first_d):
            f.write(str(row_ind + 1) + " ")
        f.write("\t\t   ")
        for row_ind in range(first_d):
            f.write(str(row_ind + 1) + " ")
        f.write("\nPlayer 1\t\t\t\t\t\tPlayer 2\n")
        f.write("\n")


def print_rules():
    print("Welcome to Ultimate Battleships")
    print("This is a game for 2 people, to be played on two 10x10 boards.")
    print("There are 5 ships in the game:  Carrier (occupies 5 spaces), Battleship (4), Cruiser (3), Submarine (3), and Destroyer (2).")
    print("First, the ships are placed. Ships can be placed on any unoccupied space on the board. The entire ship must be on board.")
    print("Write the ship's name, followed by an x y coordinate, and the orientation (v for vertical or h for horizontal) to place the ship.")
    print("If a player is placing a ship with horizontal orientation, they need to give the leftmost coordinate.")
    print("If a player is placing a ship with vertical orientation, they need to give the uppermost coordinate.")
    print("Player 1 places first, then Player 2 places. Afterwards, players take turns (starting from Player 1) to strike and sink enemy ships by guessing their location on the board.")
    print("Guesses are again x y coordinates. Do not look at the board when it is the other player's turn.")
    print("The last player to have an unsunk ship wins.")
    print("Have fun!")
    print()

    if FILE_OUTPUT_FLAG:
        f.write("Welcome to Ultimate Battleships\n")
        f.write("This is a game for 2 people, to be played on two 10x10 boards.\n")
        f.write(
            "There are 5 ships in the game:  Carrier (occupies 5 spaces), Battleship (4), Cruiser (3), Submarine (3), and Destroyer (2).\n")
        f.write(
            "First, the ships are placed. Ships can be placed on any unoccupied space on the board. The entire ship must be on board.\n")
        f.write(
            "Write the ship's name, followed by an x y coordinate, and the orientation (v for vertical or h for horizontal) to place the ship.\n")
        f.write("If a player is placing a ship with horizontal orientation, they need to give the leftmost coordinate.\n")
        f.write("If a player is placing a ship with vertical orientation, they need to give the uppermost coordinate.\n")
        f.write(
            "Player 1 places first, then Player 2 places. Afterwards, players take turns (starting from Player 1) to strike and sink enemy ships by guessing their location on the board.\n")
        f.write("Guesses are again x y coordinates. Do not look at the board when it is the other player's turn.\n")
        f.write("The last player to have an unsunk ship wins.\n")
        f.write("Have fun!\n")
        f.write("\n")


# Create the game
board_size = 10
f = open('UltimateBattleships.txt', 'w')
FILE_OUTPUT_FLAG = True  # You can change this to True to also output to a file so that you can check your outputs with diff.

print_rules()



try:# The entire code is in this try block, if there ever is an error during execution, we can safely close the file.
    # DO_NOT_EDIT_ANYTHING_ABOVE_THIS_LINE
    # Defining ship lists
    elem = ['Carrier', 'Battleship', 'Cruiser', 'Submarine', 'Destroyer']
    elem2 = ['Carrier', 'Battleship', 'Cruiser', 'Submarine', 'Destroyer']
    # Defining for placement turns
    Player1Turn = True
    Player2Turn = True

    #Defining and creating list
    emptyplayer1 = [["-" for c in range(10)] for r in range(10)]
    emptyplayer2 = [["-" for c in range(10)] for r in range(10)]
    player1 = [["-" for c in range(10)] for r in range(10)]
    player2 = [["-" for c in range(10)] for r in range(10)]
    my_list = [player1,player2]


    #All game starts
    game = True

    while game == True:
        while Player1Turn:
            print_3d_list(my_list)

            # checking if all the ships have placed or not and then asking is it ready to battle
            if elem == []:
                yesno = 'a'
                while yesno not in ['Y','y','n','N']:
                    print_confirm_placement()
                    yesno = input()

                if yesno == 'y' or yesno == 'Y':
                    realplayer1 = player1.copy()
                    elem = ['Carrier', 'Battleship', 'Cruiser', 'Submarine', 'Destroyer']
                    yesno = 'a'
                    Player1Turn = False
                    break

                if yesno == 'n' or yesno == 'N':
                    player1 = []
                    for i in range(10):
                        row = []
                        for a in range(10):
                            row.append('-')
                        player1.append(row)
                my_list = [player1, player2]
                print_3d_list(my_list)
                elem = ['Carrier', 'Battleship', 'Cruiser', 'Submarine', 'Destroyer']
                yesno = 'a'

            print_ships_to_be_placed()

            #taking input from user to place ship
            for a in (elem):
                print_single_element(a)
            print_empty_line()
            n = 1
            print_player_turn_to_place(n)

            print_to_place_ships()

            given = input()
            given = given.split()

            # chechking whether input is int or not
            try:
                givenint_1 = int(given[1])
                givenint_2 = int(given[2])

            except:
                print_incorrect_input_format()
                continue
            # chechking the input's lenght
            if (len(given) != 4):
                print_incorrect_input_format()
                continue
            #chechking the inputs cordinates
            if givenint_1 <= 0 or givenint_1 > 10 or givenint_2 <= 0 or givenint_2 > 10:
                print_incorrect_coordinates()
                continue

            shipname = given[0].capitalize()

            if shipname in elem2:
                pass
            else:
                print_incorrect_ship_name()
                continue
            #checking horizontal and vertical inputs
            if given[3] != 'h' and given[3] != 'H' and given[3] != 'v' and given[3] != 'V':
                print_incorrect_orientation()
                continue

            ship_dict = {
                "Carrier": 5,
                "Battleship": 4,
                "Cruiser": 3,
                "Submarine": 3,
                "Destroyer": 2
            }

            #checking the presence of shipname in ship list
            if shipname in elem:
                pass
            else:
                print_ship_is_already_placed(shipname)
                continue

            #trying to place ship
            if given[3] == 'h' or given[3] == 'H':
                if givenint_1 - 1 + ship_dict[shipname] > 10 :
                    print_ship_cannot_be_placed_outside(shipname)
                    continue

            elif given[3] == 'v' or given[3] == ' V':
                if givenint_2 - 1 + ship_dict[shipname] > 10:
                    print_ship_cannot_be_placed_outside(shipname)
                    continue

            occupycheck = False
            if given[3] == 'v' or given[3] == 'V':
                lastcheck = givenint_2-1 + ship_dict[shipname]
                for i in range(givenint_2-1,lastcheck):
                    if my_list[0][i][givenint_1-1] == '#':
                        print_ship_cannot_be_placed_occupied(shipname)
                        occupycheck = True
                if occupycheck:
                    continue

            if given[3] == 'h' or given[3] == 'H':
                lastcheck = givenint_1-1 + ship_dict[shipname]
                for i in range(givenint_1-1,lastcheck):
                    if my_list[0][givenint_2-1][i] == '#':
                        print_ship_cannot_be_placed_occupied(shipname)
                        occupycheck = True
                        break
                if occupycheck == True:
                    continue
            #removing the ship which is placed
            for a in elem:
                if shipname == a:
                    elem.remove(a)
                    continue

            #placing ship virtually to list cordinates
            if given[3] == 'h' or given[3] == 'H':
                for i in range(ship_dict[shipname]):
                    my_list[0][(givenint_2)-1][(givenint_1)-1+i] ='#'

                continue
            if given[3] == 'V' or given[3] == 'v':
                for i in range(ship_dict[shipname]):
                    my_list[0][(givenint_2-1+i)][(givenint_1-1)] ='#'
                continue
        # Player 2's turn

        while Player1Turn == False and Player2Turn == True:

            my_list = [emptyplayer1,player2]
            print_3d_list(my_list)

            # checking if all the ships have placed or not and then asking is it ready to battle
            if elem == []:
                yesno = 'a'
                while yesno not in ['Y','y','n','N']:
                    print_confirm_placement()
                    yesno = input()

                if yesno == 'y' or yesno == 'Y':
                    realplayer2 = player2.copy()
                    Player1Turn = False
                    Player2Turn = False
                    break

                if yesno == 'n' or yesno == 'N':
                    player2 = []
                    for i in range(10):
                        row = []
                        for a in range(10):
                            row.append('-')
                        player2.append(row)
                my_list = [emptyplayer1, player2]
                print_3d_list(my_list)
                elem = ['Carrier', 'Battleship', 'Cruiser', 'Submarine', 'Destroyer']
                yesno = 'a'

            print_ships_to_be_placed()


            for a in (elem):
                print_single_element(a)
            print_empty_line()
            n = 2
            print_player_turn_to_place(n)

            print_to_place_ships()

            given = input()
            given = given.split()

            # chechking whether input is int or not
            try:
                givenint_1 = int(given[1])
                givenint_2 = int(given[2])

            except:
                print_incorrect_input_format()
                continue

            # chechking the input's lenght
            if (len(given) != 4):
                print_incorrect_input_format()
                continue
            #chechking the inputs cordinates
            if givenint_1 <= 0 or givenint_1 > 10 or givenint_2 <= 0 or givenint_2 > 10:
                print_incorrect_coordinates()
                continue

            shipname = given[0].capitalize()

            if shipname in elem2:
                pass
            else:
                print_incorrect_ship_name()
                continue
            #checking horizontal and vertical inputs
            if given[3] != 'h' and given[3] != 'H' and given[3] != 'v' and given[3] != 'V':
                print_incorrect_orientation()
                continue

            ship_dict = {
                "Carrier": 5,
                "Battleship": 4,
                "Cruiser": 3,
                "Submarine": 3,
                "Destroyer": 2
            }

            #checking the presence of shipname in ship list
            if shipname in elem:
                pass
            else:
                print_ship_is_already_placed(shipname)
                continue

            #trying to place ship
            if given[3] == 'h' or given[3] == 'H':
                if givenint_1 - 1 + ship_dict[shipname] > 10 :
                    print_ship_cannot_be_placed_outside(shipname)
                    continue

            elif given[3] == 'v' or given[3] == ' V':
                if givenint_2 - 1 + ship_dict[shipname] > 10:
                    print_ship_cannot_be_placed_outside(shipname)
                    continue

            occupycheck = False
            if given[3] == 'v' or given[3] == 'V':
                lastcheck = givenint_2-1 + ship_dict[shipname]
                for i in range(givenint_2-1,lastcheck):
                    if my_list[0][i][givenint_1-1] == '#':
                        print_ship_cannot_be_placed_occupied(shipname)
                        occupycheck = True
                if occupycheck == True:
                    continue

            if given[3] == 'h' or given[3] == 'H':
                lastcheck = givenint_1-1 + ship_dict[shipname]
                for i in range(givenint_1-1,lastcheck):
                    if my_list[0][givenint_2-1][i] == '#':
                        print_ship_cannot_be_placed_occupied(shipname)
                        occupycheck = True
                        break
                if occupycheck == True:
                    continue
            #removing the ship which is placed
            for a in elem:
                if shipname == a:
                    elem.remove(a)
                    continue

            #placing ship virtually to list cordinates
            if given[3] == 'h' or given[3] == 'H':
                for i in range(ship_dict[shipname]):
                    my_list[1][(givenint_2)-1][(givenint_1)-1+i] ='#'

                continue
            if given[3] == 'V' or given[3] == 'v':
                for i in range(ship_dict[shipname]):
                    my_list[1][(givenint_2-1+i)][(givenint_1-1)] ='#'
                continue

        battleFaze1or2 = 1
        # Starting to battle for 1.player

        while battleFaze1or2 == 1:

            my_list = [realplayer1, emptyplayer2]
            print_3d_list(my_list)

            totalhit1 = 0
            # checking if all the ship cordinates have been hit
            for row in emptyplayer2:
                totalhit1 += row.count('!')

            # finishing the game if all the cordinates have been hit
            if totalhit1 == 17:
                print_player_won(1)
                print_thanks_for_playing()
                game = False
                battleFaze1or2 = 'a'
                break

            # getting coordinates
            print_player_turn_to_strike(1)
            print_choose_target_coordinates()

            boom = input()
            boom = boom.split()
            # checking coordinate formats
            try:
                boom1 = int(boom[0]) - 1
                boom2 = int(boom[1]) - 1

            except:
                print_incorrect_input_format()
                continue

            if (len(boom) != 2):
                print_incorrect_input_format()
                continue

            if boom1 < 0 or boom1 >= 10 or boom2 < 0 or boom2 >= 10:
                print_incorrect_coordinates()
                continue
            # checking if the coordinate has been already struck
            if realplayer2[boom2][boom1] == 'O':
                print_tile_already_struck()
                continue

            if realplayer2[boom2][boom1] == '!':
                print_tile_already_struck()
                continue

            # checking if the coordinates hitting or missing the ship and typing it to the list
            if realplayer2[boom2][boom1] == '-':
                print_miss()
                emptyplayer2[boom2][boom1] = 'O'
                realplayer2[boom2][boom1] = 'O'

                doneornot = 'a'
                # giving turn the 2.player
                while doneornot != 'done':
                    print_type_done_to_yield(2)
                    doneornot = input()
                    doneornot = doneornot.lower()

                if doneornot == 'done':
                    battleFaze1or2 = 2
                    break

            if realplayer2[boom2][boom1] == '#':
                print_hit()
                emptyplayer2[boom2][boom1] = '!'
                realplayer2[boom2][boom1] = '!'
                continue

        # Starting to battle for 2.player
        while battleFaze1or2 == 2:

            my_list = [emptyplayer1, realplayer2]
            print_3d_list(my_list)

            totalhit = 0
            # checking if all the ship cordinates have been hit
            for row in emptyplayer1:
                totalhit += row.count('!')

            # finishing the game if all the cordinates have been hit
            if totalhit == 17:
                print_player_won(2)
                print_thanks_for_playing()
                game = False
                battleFaze1or2 = 'a'
                break

            #getting coordinates
            print_player_turn_to_strike(2)
            print_choose_target_coordinates()

            boom = input()
            boom = boom.split()
            #checking coordinate formats
            try:
                boom1 = int(boom[0]) - 1
                boom2 = int(boom[1]) - 1

            except:
                print_incorrect_input_format()
                continue



            if (len(boom) != 2):
                print_incorrect_input_format()
                continue

            if boom1 < 0 or boom1 >= 10 or boom2 < 0 or boom2 >= 10:
                print_incorrect_coordinates()
                continue

            # checking if the coordinate has been already struck
            if realplayer1[boom2][boom1] == 'O':
                print_tile_already_struck()
                continue

            if realplayer1[boom2][boom1] == '!':
                print_tile_already_struck()
                continue

            #checking if the coordinates hitting or missing the ship and typing it to the list
            if realplayer1[boom2][boom1] == '-':
                print_miss()
                emptyplayer1[boom2][boom1] = 'O'
                realplayer1[boom2][boom1] = 'O'

                doneornot = 'a'
                # giving turn the 1.player
                while doneornot != 'done':
                    print_type_done_to_yield(1)
                    doneornot = input()
                    doneornot = doneornot.lower()

                if doneornot == 'done':
                    battleFaze1or2 = 1
                    break

            if realplayer1[boom2][boom1] == '#':
                print_hit()
                emptyplayer1[boom2][boom1] = '!'
                realplayer1[boom2][boom1] = '!'
                continue

    # DO_NOT_EDIT_ANYTHING_BELOW_THIS_LINE
except:
    f.close()

