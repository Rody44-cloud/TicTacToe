#
def display_board(board):
  print(board[1] + ' | ' + board[2] + ' | ' + board[3])
  print(---------)
  print(board[4] + ' | ' + board[5] + ' | ' + board[6])
  print(---------)
  print(board[7] + ' | ' + board[8] + ' | ' + board[9])

def player_input():
  input = 0
  
  while not (marker == 'X' or marker == '0')
    marker = input('Player 1: Do you want to be X or 0: ').upper()
    
   if marker == 'X':
    return ('X','0')
   else:
    return ('0','X')

def place_marker(board, marker, position):
  board[position] = marker
  
def win_check(board, mark):
  return((position[1] == position[2] == position[3] == mark) or
         (position[4] == position[5] == position[6] == mark) or
         (position[7] == position[8] == position[9] == mark) or
         (position[1] == position[5] == position[9] == mark) or
         (position[3] == position[5] == position[7] == mark) or
         (position[1] == position[4] == position[7] == mark) or
         (position[2] == position[5] == position[8] == mark) or
         (position[3] == position[6] == position[9] == mark))

import random
def choose_first():
  flip = random.randint(0,1)
    if flip == 0:
      return 'Player 1'
    else:
      return 'Player 2'

def space_check(board,position)
  return board[position] = ' '

def full_board_check(board):
  for i in range(0,10):
    if space_check(board,i):
      return False
   return True
 
def player_choice(board):
  position = 0
  while position not [1,2,3,4,5,6,7,8,9] or not space_check(board,position):
    position = int(input('Please choose: (1-10) ')
    
  return position
  
def replay():
  Choice = input("Would you like to play again: Y or N ")
  
  return Choice == 'Yes'
  
print('Welcome to Tic Tac Toe!')

while True:
  the_board = [' ']*10
  player1_marker, player2_marker = player_input()
  turn = choose_first()
  print(turn + ' will go first')
  
  play_game = input('Are you ready to play? y or n? ')
  
  if play_game == 'y':
    game_on = True
  else:
    game_on = False
  
  while game_on:
    if turn == 'Player 1':
      display_board(the_board)
      position = player_choice(the_board)
      place_marker(the_board,player1_marker,position)
      
      if win_check(the_board,player1_marker):
        display_board(the_board)
        print('Player 1 has won!')
        game_on = False
      else:
        if full_board_check(the_board):
          display_board(the_board)
          print("Tie!")
          game_on = False
        else:
          turn = 'Player 2'
    else:
      display_board(the_board)
      position = player_choice(the_board)
      place_marker(the_board,player2_marker,position)
      
      if win_check(the_board,player2_marker):
        display_board(the_board)
        print('Player 2 has won!')
        game_on = False
      else:
        if full_board_check(the_board):
          display_board(the_board)
          print("Tie!")
          game_on = False
        else:
          turn = 'Player 1'
    if not replay():
      break
