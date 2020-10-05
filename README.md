# Session
#Write Article
a = list(map(str,input().split()))
stack=[]

#Insert_func
def Write(element):
    a.append(element)
    stack.append('w')
#Undo_func
def Undo():
    if len(a)<=0:
        print("List is empty")
    else:
        a.pop()
        stack.append('u')
#Print_func
def print_stack(a):
    if len(a)<=0:
        print("Empty List")
    else:
        for i in range(0,len(a)):
            print(a[i],end=" ")
    return

#Testing
Write("ABC")
Undo()
Undo()
Write("XYZ")
Write("DEF")
Undo() #Running Undo func 4 Times to erase the entire article(Super Undo)
Undo()
Undo()
Undo()

#Super_Undo_Code
for i in range(len(stack)-3):
    if stack[i]=='u' and stack[i+1]=='u' and stack[i+2]=='u' and stack[i+3]=='u':
        a.clear()
        print("You've SUPER UNDO the article")
        break
else:
    print_stack(a)
