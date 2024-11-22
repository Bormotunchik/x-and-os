def print_board(board):
    print("\n".join([" | ".join(row) for row in board]))
    print()

def check_winner(board):
    for row in board:
        if row[0] == row[1] == row[2] != " ":
            return row[0]

    for col in range(3):
        if board[0][col] == board[1][col] == board[2][col] != " ":
            return board[0][col]

    if board[0][0] == board[1][1] == board[2][2] != " ":
        return board[0][0]
    if board[0][2] == board[1][1] == board[2][0] != " ":
        return board[0][2]

    return None

def is_board_full(board):
    return all(cell != " " for row in board for cell in row)

def tic_tac_toe():
    board = [[" " for _ in range(3)] for _ in range(3)]
    current_player = "1"

    while True:
        print_board(board)
        print(f"Игрок {current_player}, Твой ход! Введите строку и столбец (например, 1 1 чтобы поставить в центр):")
        
        try:
            row, col = map(int, input().split())
            if board[row][col] != " ":
                print("Эта клетка уже занята.")
                continue
        except (ValueError, IndexError):
            print("Пожалуйста, введите два числа от 0 до 2.")
            continue

        board[row][col] = current_player
        
        winner = check_winner(board)
        if winner:
            print_board(board)
            print(f"Игрок {winner} выиграл!")
            break
        
        if is_board_full(board):
            print_board(board)
            print("Ничья!")
            break

        current_player = "O" if current_player == "X" else "X"

if __name__ == "__main__":
    tic_tac_toe()
