from random import randint

chance = input("1 先手 2 後手：")
chance = int(chance) % 2 # 0後手 1先手
rows = [ str(i) for i in range(1, 10) ]
turn = chance

def check_win(data):
    for i in range(3):
        if data[i*3] == data[i*3 + 1] and data[i*3+1] == data[i*3 + 2]:
            return data[i]
        if data[i] == data[i+3] and data[i+3] == data[i + 6]:
            return data[i]
    if data[0] == data[4] and data[4] == data[8]:
        return data[0]
    if data[2] == data[4] and data[4] == data[6]:
        return data[2]
    return False

def choose_one(data):
    while True:
        i = randint(0, 8)
        if data[i] == 'O' or data[i] == 'X':
            continue
        return i

def display(data):
    data = [ str(n) for n in data ]
    rows = [ data[i : i + 3] for i in range(0, 9, 3) ]
    print('+-----------+')
    for row in rows:
        print('|', row[0], '|', row[1], '|', row[2], '|')
        print('+-----------+')

display(rows)
while rows.count('O') + rows.count('X') < 9 and not check_win(rows):
    if turn % 2 == 0:
        i = choose_one(rows)
        print("電腦選擇了位置", i + 1)
        rows[i] = 'X'
    else:
        i = int(input("請輸入位置：")) - 1
        rows[i] = 'O'
    display(rows)
    turn += 1

r = check_win(rows)
if r:
    who = "電腦" if r == "X" else "玩家"
    print(who, "獲勝")
else:
    print("平手")
