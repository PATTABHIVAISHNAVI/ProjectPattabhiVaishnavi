from IPython.display import clear_output


def player_choice():
    i=0    # inorder to initially enter into the loop hence we r taking i=0
    E=0#By using this expression we are  seeing that after the end of this game it should not iterate this while loop again  hence even at the end() func we r taking it to be E=1 
    R=0
    print("Welcome! to Tic-Tac-Toe")
    
    while i not in ['O','X','o','x'] and E!=1:
        i=input("Player1 : please choose your option 'X' or 'O' ")
        print("Player-1 your option is : ",i)
        
        while R==0:
            M=input("Do you want to start the game : Yes='Y' or No='N'")
        
            if M=='Y' or M=='y':
            
            
                if i in ['O','X','o','x']:
                    R=1
                    if i=='X' or i=='x':
                        return 'X','O'
                    else:
                        return 'O','X'
                
                
                if i not in ['X','O','o','x']:
                    print("Please enter the valid option i.e, 'O' or 'X'")
            
        
            elif M=='N' or M=='n':
                end()
            else:
                print("Enter the valid option")
                R=0
            
def game_on(p1,p2):
    
    l=[1,2,3,4,5,6,7,8,9]
    P=0
    v=0
    a=['  ','  ','  ','  ','  ','  ','  ','  ','  ']
    
    print("\nTic-Tac-Toe  Board is here...!✨ along with their corresponding positions")
    
    print("      |      |      ")
    print("  {}  |  {}  |  {}  ".format(str(1)+' ',str(2)+' ',str(3)+' '))
    print("______|______|______")
    print("      |      |      ")
    print("  {}  |  {}  |  {}  ".format(str(4)+' ',str(5)+' ',str(6)+' '))
    print("______|______|______")
    print("      |      |      ")
    print("  {}  |  {}  |  {}  ".format(str(7)+' ',str(8)+' ',str(9)+' '))
    print("      |      |      ")
    
    while v<9 and P==0:
        
        if v%2==0:
            k=p1
            j=int(input("\nPlayer-1 enter the position  from 1 to 9"))
        else:
            k=p2
            j=int(input("\nPlayer-2 enter the position  from 1 to 9"))
         
        
        #j=int(input("Enter the position of the number from 1 to 9"))
        
        clear_output()
        
        
                
            
        if j in l:
            
            a[int(j)-1]=k+' '
            print("      |      |      ")
            print("  {}  |  {}  |  {}  ".format(a[0],a[1],a[2]))
            print("______|______|______")
            print("      |      |      ")
            print("  {}  |  {}  |  {}  ".format(a[3],a[4],a[5]))
            print("______|______|______")
            print("      |      |      ")
            print("  {}  |  {}  |  {}  ".format(a[6],a[7],a[8]))
            print("      |      |      ")
        
            l.remove(j)
        
            v=v+1
            
            if (a[0]==a[1]==a[2]==p1+' ' or a[3]==a[4]==a[5]==p1+' '  or a[6]==a[7]==a[8]==p1+' ' or a[0]==a[3]==a[6]==p1+' ' or a[2]==a[5]==a[8]==p1+' ' or a[0]==a[4]==a[8]==p1+' ' or a[2]==a[4]==a[6]==p1+' ' or a[1]==a[4]==a[7]==p1+' '):
                print("\nPLAYER-1 👑 WON THE GAME 🎆💥")
                cont()
                P=1
                
            elif(a[0]==a[1]==a[2]==p2+' ' or a[3]==a[4]==a[5]==p2+' '  or a[6]==a[7]==a[8]==p2+' ' or a[0]==a[3]==a[6]==p2+' ' or a[2]==a[5]==a[8]==p2+' ' or a[0]==a[4]==a[8]==p2+' ' or a[2]==a[4]==a[6]==p2+' ' or a[1]==a[4]==a[7]==p2+' '):
                print("\nPLAYER-2 👑 WON THE GAME 🎆💥")
                cont()
                P=1
                
            
            else:
                pass
            
            
            
            
            
        else:
            print("      |      |      ")
            print("  {}  |  {}  |  {}  ".format(a[0],a[1],a[2]))
            print("______|______|______")
            print("      |      |      ")
            print("  {}  |  {}  |  {}  ".format(a[3],a[4],a[5]))
            print("______|______|______")
            print("      |      |      ")
            print("  {}  |  {}  |  {}  ".format(a[6],a[7],a[8]))
            print("      |      |      ")
            print("Enter the valid option from 0 to 9")
        
        
    if v==9:
        tie()
    
    
    
def cont():
    
    
    Q=0
    while Q==0:
        n=input(("\nDo you want to continue the game ! \nIf YES ✅ enter 'Y' \nIf NO ❌ enter 'N'"))
        if n in ['Y','y','N','n']:
        
            if n=='Y' or n=='y':
                tic()
                Q=1
        
            elif n=='N' or n=='n':
                end()
                Q=1
        else :
        
            print("\nEnter the valid option")
            Q=0
        
        
        
def tic():
    p1,p2=player_choice()
    
    game_on(p1,p2)
    
def end():
    print("\n🚩The game ended 🚩 ")
    print()
    E=0
    
def tie():
    print("\nIt is tie !..  🤝🧑‍🤝‍🧑")
    cont()
