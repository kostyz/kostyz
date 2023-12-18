[Uploboard = [[' ' for _ in range(3)] for _ in range(3)]
def display_board():
    for row in board:
        print("|".join(row))
        print("-" * 5)
def check_winner():
    for i in range(3):
        if board[i][0] == board[i][1] == board[i][2] != ' ' or board[0][i] == board[1][i] == board[2][i] != ' ':
            return True
    if board[0][0] == board[1][1] == board[2][2] != ' ' or board[0][2] == board[1][1] == board[2][0] != ' ':
        return True
    return False
def check_draw():
    return all(board[i][j] != ' ' for i in range(3) for j in range(3))
current_player = 'X'

while True:
    display_board()
    row = int(input("Введите номер строки (0, 1, 2): "))
    col = int(input("Введите номер столбца (0, 1, 2): "))
    if 0 <= row < 3 and 0 <= col < 3 and board[row][col] == ' ':
        board[row][col] = current_player
        if check_winner():
            display_board()
            print(f"Игрок {current_player} победил!")
            break
        elif check_draw():
            display_board()
            print("Ничья!")
            break
        current_player = 'O' if current_player == 'X' else 'X'
    else:
        print("Некорректный ход. Попробуйте еще раз.")
ading dsa.py…]()
