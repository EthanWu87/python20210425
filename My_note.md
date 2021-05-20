#題目:判斷閏年平年

##程式碼:

```
form pwn import *	# import pwn library

r = remote('140.110.112.22',2402)	# remote binary

r.recvuntil('year : ')	# receive form linary until the first one 'year :'
r.recvuntil('year : ')	#receive form linary until the second one 'year :'

for i in range(1 ,101):
	r.recvuntil('year :')	# receive form linary until the third 'year :'
	s = r.recvuntil('\n')	# set s as r.recvuntil
	s = s.decode()	# decode s 
	s = s.strip() 	# set s as strip
	s = int(s)	# set s as int 
	
	if s%4 == 0 and %100 !=0 :	#Determine wheather it is a leap year or ordinary year
		r.sendline(b'leap')	#send to server
	elif s%400 == 0 :
		r.sendline(b'leap')
	else :
		r.sendline(b'ordinary')

r.interactive()	#switch to interactive mode

```
