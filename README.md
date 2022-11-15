# learn-python-list

Click the snake to see the code and explanation about my code
<!-- 
<details><summary>:snake: </summary>
<p>

```python

```
</p>
</details>

*******************************************
-->


<details><summary>:snake: nested list</summary>
<p>

```python
board = [['A','B','C'],['D','E','F'],['G','H','I'],['J','K','L']]
#print C
print(board[0][2])
#print H
print(board[2][1])
 # change L to be Z
board[3][2] = 'Z'
print(board)

# add the list ['M','N','O'] to board
board.append(['M','N','O'])
print(board)
board[0].append('Q')
print(board)

for i in range(len(board)):

	print(board[i])

#print  G H I
print()
for i in range(len(board[2])):
	print(board[2][i])

# print every letter
print()
for i in range(len(board)):
	for k in range(len(board[i])):
		print(board[i][k])

```
</p>
</details>
<details><summary>:snake: String manipulation </summary>
<p>

```python
'''
S = "Hello World"
print(S[0:5])
S2 = S[6:9]
print(S2) 
print(S)
print(S[:7])
print(S[3:])

print(S[:])
print(S.lower())
print(S.upper())
print(S)
print(S.replace("o","i"))
print(S.replace(" ", "-"))
print(S.replace("Hello","Goddbye"))
print(S.replace("h","j"))

print(S[4:-1:-1])
print(S[10::-1])
print(S[::-1])
print(S.strip())

S2 = " Foo Bar	"
print(f"{S2}!")
S3 = S2.strip()
print(f"{S3}!")
words = S.split(" ")
print(words)
a = S.split("e")
print(a)
b = S.split('o')
print(b) 
print(b[2])
c = S.split('Wo')
print(c)
d = S.split('l')
print(d)
e = S.split('Q')
print(e)
'''
S = "Hello World"
a = S[:6]
b = a.strip()
c = b.replace('H','J')
d = c.upper()
print(d)
e= S[:6].strip().replace('H','J').upper()
print(e)
f = S.split(' ')[1].replace('W','H').replace('o','i')[:2].lower()
print(f)

```
</p>
</details>

<details><summary>:snake: Append list with index</summary>
<p>

```python
#1 list common element with no duplication
#list_alpha = [4,7,3,2,4,6,8,1,7,6]
#list_beta = [7,9,1,4,5,2,3,2,5,9]
list_beta = "abcd"
list_alpha = "abcde"
newList = []

'''
for i in range(len(list_alpha)):
	if  list_alpha[i] not in list_beta:
	#newList.append(list_beta[i])
		newList.append(list_alpha[i])
print(newList)
'''
for i in range(len(list_alpha)):
	if list_alpha[i] not in list_beta:
		newList.append(list_alpha[i])
print(newList)
```
</p>
</details>

<details><summary>:snake: a string as a list </summary>
<p>

```python
S = "Hello World"
print(S[0])

print(f"{S[4]}{S[2]}{S[10]}")
for i in range(len(S)):
	print(S[i])
if "o" in S:
	print("contains an o")
if "h" not in S:
	print("no h")

#S.append("!")
S += "!"

print(S) 
```
</p>
</details>


<details><summary>:snake: No duplication list</summary>
<p>

```python
  numbers = [-3,4,4,1,-3,4,7,1,-2]
negList = []
newList = []
for i in range(len(numbers)):
	print(numbers[i])

print()

for number in numbers:	

	if number< 0:
		print(number)
		negList.append(number)
		
	if number not in newList:
		newList.append(number)

print(negList)
print(newList)
print("the end")

'''
newList = []	
for i in range(len(numbers)):
	if i not in newList:
		newList.append(numbers[i])
print(newList)

the looping id by index, so the statement ---if i not in newList, that's mean :
0 is not in newList, then newlist will be appended by newList element, so the result it will be:
[-3,
1 is not in the newList, then the list will be appended with : 4
2 is not in the newList, then the list will be append with : 4
etc, so it will not eliminate the duplication.

'''    
```
</p>
</details>


<details><summary>:snake: Random list</summary>
<p>

```python
import random

list_a = []
list_b = []
list_c = []

number_count = random.randrange(5,15)
for i in range(number_count):
    list_a.append(random.randrange(0,11))
print(list_a)
number_count = random.randrange(5,15)
for i in range(number_count):
    list_b.append(random.randrange(0,11))
print(list_b)

for k in list_b :
    if k in list_a and k not in list_c:
        list_c.append(k)
print(list_c)
extra_list = []
for i in list_a:
    if i not in list_b and i not in extra_list:
        extra_list.append(i)
for k in list_b:
    if k not in list_a and k not in extra_list:
        extra_list.append(k)
print(extra_list)

av_list = {}
sum_a = 0
for i in list_a:
    sum_a += i
av_a = sum_a/len(list_a)
av_list['list_a'] = av_a
sum_b = 0
for k in list_c:
    sum_b += k
av_b = sum_b/len(list_b)
av_list['list_b'] = av_b
sum_c = 0
for j in list_c:
    sum_c += j
av_c = sum_c/len(list_c)
av_list['list_c'] = av_c
sum_extra = 0
for d in extra_list:
    sum_extra += d
av_d = sum_extra/len(extra_list)
av_list['extra_list'] = av_d

if av_b > av_a:
    print("list B has bigger average than list A")
else:
    print(("list A has bigger average than list B"))

biggest_av = 0
for i in av_list:
    if av_list[i] > biggest_av:
        biggest_av = av_list[i]
        biggest_list = i
print(f"the biggest average is {biggest_list}")

#find a biggest number
#solution 1
big_num = 0
for  num in list_a:
    if num > big_num :
        big_num = num
for num in list_b:
    if num > big_num:
        big_num = num
for num in list_c:
    if num > big_num:
        big_num = num
for num in extra_list:
    if num > big_num:
        big_num = num
print(f"the biggest number: {big_num}")

#solution2
big_list =[]
for i in list_a:
    if i not in big_list:
        big_list.append(i)
for i in list_b:
    if i not in big_list:
        big_list.append(i)
for i in list_c:
    if i not in big_list:
        big_list.append(i)
for  i in  extra_list:
    if i not in big_list:
        big_list.append(i)

big_num2 = 0
for num in big_list:
    if num > big_num2:
        big_num2 = num
print(f"big list: {big_list}")

print(big_num2)
#3
comb_list =[]
comb_list.extend(list_a)
comb_list.extend(list_b)
comb_list.extend(list_c)
comb_list.extend(extra_list)
comb_list.sort()
print(f"biggest number: {comb_list[-1]}")
#4
comb_list2 = list_a + list_b + list_c + extra_list
big = max(comb_list2)
print(f" the biggest number: {big}")

   
```
</p>
</details>

<details><summary>:snake: List comprehension</summary>
<p>

```python
numbers = [-4,6,-7,-5,2,9,-8]
#make  new list only the positive number
pos_numbers =[]
for number in numbers:
    if number >0:
        pos_numbers.append(number)
print(pos_numbers)

#build single list from 4 lines code

#list = [what you append your_loop your_if]
pos_numbers2 = [number for number in numbers if number > 0]
print( pos_numbers2)

squares = [number * number for number in numbers]
print(squares)   
```
</p>
</details>


<details><summary>:snake: Append list </summary>
<p>

```python
#print each color
colors=["red","blue","green","red","yellow","orange","green","red","blue","white"]
'''
for color in colors:
	print(color)

#print out only the primary color (red , blue, yellow)
print()
for color in colors:
	if color == "red" or color == "blue" or color == "yellow":
		print(color)

# print out red

red = 0
for color in colors:
	if color == "red":
		red +=1
print(" total red color in the list: ") 
print(red)

#total color in the list
print()

print("what kind color you look for: ")

input = input()
count = 0
for color in colors:
	if input == color:
		count +=1
if count == 1:
	print(f"there is {count} {input} in the list")
elif count > 1:
	print(f"there are {count} {input} in the list")
else:
	print("that color is not in the list")

# second color list
'''
list2 = []
for color in colors:
	if color == "orange":
		list2.append("orange")
	if color == "purple":
		list2.append("purple")
	if color == "green":
		list2.append("green")
print(list2)
print()

# no duplication
print(colors)
newList = []
for color in colors:
	if color not in newList:
		newList.append(color)

print(newList)

   
```
</p>
</details>

<details><summary>:snake: phrase  </summary>
<p>

```python
first = ["Hello", "Foo", "Shooting"]
last = ["World", "Bar","Star"]

words = ""
for i in range(len(first)):

	phrase=f"{first[i]} {last[i]}"
	words = words + phrase 
	if i < len(last) -2:
		words = words + ", "
	elif i < len(last) -1:
		words = words + " and "
	
print(words)   
```
</p>
</details>

<details><summary>:snake: No duplication</summary>
<p>

```python
#1 list common element with no duplication  

list_alpha = [4,7,3,2,4,6,8,1,7,6]
list_beta = [7,9,1,4,5,2,3,2,5,9]
newList = []


for i in range(len(list_alpha)):
	if list_alpha[i]  in list_beta and list_alpha[i] not in newList:
		newList.append(list_alpha[i])

print(newList)   
```
</p>
</details>

<details><summary>:snake: Best average student score</summary>
<p>

```python
#2 best average student score
print()

steve = [85, 73, 90, 94, 82]
john = [82, 71, 72, 96, 98]
phil = [99, 91, 88,90,45]
sumS = 0
sumJ = 0
sumP = 0

for i in range(len(steve)):
	sumS = sumS + steve[i]

avSteve = sumS/len(steve)

for i in range(len(john)):
	sumJ = sumJ + john[i]
avJohn = sumJ/len(john)

for i in range(len(phil)):
	sumP = sumP + phil[i]
avPhil = sumP/len(phil)

if avSteve > avJohn and avSteve > avPhil:
	print("steve has best average")

elif avJohn > avPhil:
	print("John has best average")
else:
	print("Phil has best average")
   
```
</p>
</details>

<details><summary>:snake: Palindrome </summary>
<p>

```python
 #3 palindrome
print()
letters1 = ['a','b', 'c','c','b','a']
letters2 = ['a','b', 'c','d','e','f']
letters3 = ['a','b', 'c','b','a']	
letters4 = ['a','b', 'b','c','a']

a = len(letters1)
b= len(letters2)
c = len(letters3)
d= len(letters4)
bol1=[]
bol2=[]
bol3=[]
bol4=[]

# Print out letters2 in reverse order
for i in range(len(letters1)):
	
	if letters1[i]==letters1[(a-1-i)]:
		bol1.append('T')
	else:
		bol1.append('F')

if 'F' in bol1:
	print("letters1 is not palindrome")
else:
	print("letters1 is palindrome")
for i in range(len(letters2)):

	if letters2[i]==letters2[(b-1-i)]:
		bol2.append('T')
	else:
		bol2.append('F')
if 'F' in bol2:
	print("letters2 is not palindrome")
else:
	print("letters2 is palindrome")

for i in range(len(letters3)):

	if letters3[i]==letters3[(c-1-i)]:
		bol3.append('T')
	else:
		bol3.append('F')
if 'F' in bol3:
	print("letters3 is not palindrome")
else:
	print("letters3 is palindrome")

for i in range(len(letters4)):
	
	if letters4[i]==letters4[(d-1-i)]:

		bol4.append('T')
	else:
		bol4.append('F')

if 'F' in bol4:
	print("letters4 is not palindrome")
else:
	print("letters4 is palindrome")
#
if letter1[0]==letter1[5] and letter1[1] == letter1[4] and letter1[2] == letter1[3]:
		print(" letter1 is palidrome")
else:
		print("letter1 is not palindrome")

if letter2[0]==letter2[5] and letter2[1] == letter2[4] and letter2[2] == letter2[3]:
		print(" letter2 is palidrome")
else:
		print("letter2 is not palindrome")

if letter3[0]==letter3[4] and letter3[1] == letter3[3]:
		print(" letter3 is palidrome")
else:
		print("letter3 is not palindrome")

if letter4[0]==letter4[4] and letter4[1] == letter4[3]:
		print("eletter4 is palidrome")
else:
		print("letter4 is not palindrome")

	  
```
</p>
</details>


<details><summary>:snake: List with loop </summary>
<p>

```python
 fruits =["apple", "banana", "cherry","apple"]
#for fruits in fruits:
#	print(fruits)

for i in range(3):
	print(fruits[i])

for i in range(len(fruits)):
	print(fruits[i])

print()

first_names=["Harrison","John","Susan"]
last_names=["Newkirk", "Doe","Smith"]

for i in range(len(first_names)):
	#print(first_names[i])
	#print(last_names[i])

	print(f"{first_names[i]} {last_names[i]}")
  
```
</p>
</details>

<details><summary>:snake: List practices </summary>
<p>

```python

numbers = [3,5,-6,2,-7,1]
# becareful modifiying(append, delete) a list while looping through it

for number in numbers:
	print(number)

numbers.extend([6,-3])
print(numbers)

print()

for number in numbers:
	if number>0:

		print(number)
    
print()
print("total numbers in the list")
print(len(numbers))

print()
print(numbers)

sum = 0
for number in numbers:
	sum = sum + number
print("the total sum is: ")
print(sum)

numbers = [-3,-5,-6,-2,-7,-11, -1]

smallest = numbers[0]

for number in numbers:
	if number< smallest:

		smallest = number
		
print("the smallest number from the list is: ")
print(smallest)
for i in range(len(numbers)):
	if numbers[i] > numbers[i+1]:
		numbers[i]=numbers[i+1]
		numbers[i+1] = numbers[i]
print(numbers)

# A

colors = ["Red", "Green", "Blue", "Black","White", "Yellow"]
print(colors)

#B

for color in colors:
	if color == "Red" or color == "White" or color == "Blue":
		print(color)



colors[3] = "Purple"
colors[4] = "Orange"
print(colors)
colors.extend(["Black", "White"])


colors = ["Red", "Green", "Blue", "Purple","Orange", "Yellow","Black","White"]
print(colors)
colors.pop(6)
colors.pop(2)
colors.pop(0)

print(colors)

  
```
</p>
</details>
