﻿Over the Wire's **Leviathan** Walkthrough by AlbertoSpinella.

Don't be sly! Try to solve the challenges on your own before comparing with my solutions.

# Index
1. [leviathan 0](https://github.com/AlbertoSpinella/over-the-wire-leviathan#leviathan-0)
2. [leviathan 0 -> 1](https://github.com/AlbertoSpinella/over-the-wire-leviathan#leviathan-0---1)
3. [leviathan 1 -> 2](https://github.com/AlbertoSpinella/over-the-wire-leviathan#leviathan-1---2)
4. [leviathan 2 -> 3](https://github.com/AlbertoSpinella/over-the-wire-leviathan#leviathan-2---3)
5. [leviathan 3 -> 4](https://github.com/AlbertoSpinella/over-the-wire-leviathan#leviathan-3---4)
6. [leviathan 4 -> 5](https://github.com/AlbertoSpinella/over-the-wire-leviathan#leviathan-4---5)
7. [leviathan 5 -> 6](https://github.com/AlbertoSpinella/over-the-wire-leviathan#leviathan-5---6)
8. [leviathan 6 -> 7](https://github.com/AlbertoSpinella/over-the-wire-leviathan#leviathan-6---7)
9. [leviathan 7 -> 8](https://github.com/AlbertoSpinella/over-the-wire-leviathan#leviathan-7---8)

## leviathan 0
Run the command:
```
ssh leviathan.labs.overthewire.org -p 2223 -l leviathan0
```
**Password**: leviathan0

## leviathan 0 -> 1
Run the commands:
```
ls -la
cd .backup
cat bookmarks.html | grep password
```
**Password**: rioGegei8m

## leviathan 1 -> 2
Run the commands:
```
ssh leviathan.labs.overthewire.org -p 2223 -l leviathan1
ls -la
./check
```
Try the first password that comes to mind and it will fail.
Then run the commands:
```
ltrace ./check
```
Press Enter a few times, and you'll find the password is `sex`.
After that, it will prompt to a new shell.
Run the command ``` whoami ``` to verify you're leviathan2.
Then run the commands:
```
cat /etc/leviathan_pass/leviathan2
```
**Password**: ougahZi8Ta

## leviathan 2 -> 3
Run the commands: 
```
ssh leviathan.labs.overthewire.org -p 2223 -l leviathan2
ls -la
./printfile /etc/leviathan_pass/leviathan3
```
You don't have the permissions to read that file.
Run the commands:
```
ltrace ./printfile /etc/leviathan_pass/leviathan3
mkdir /tmp/lev3
cd /tmp/lev3
touch pass temp.txt
ltrace ~/printfile temp.txt
touch password\ temp.txt
ln -s /etc/leviathan_pass/leviathan3 /tmp/lev3/password
./printfile "password temp.txt"
```
**Password**: Ahdiemoo1j

## leviathan 3 -> 4
Run the commands: 
```
ssh leviathan.labs.overthewire.org -p 2223 -l leviathan3
ls -la
./level3
ltrace ./level3
```
You'll find that it compares your input with the string "snlprintf". So, run the command `./level3` and then enter that string as the password.
Then run the commands:
```
whoami
cat /etc/leviathan_pass/leviathan4
```
**Password**: vuH0coox6m

## leviathan 4 -> 5
Run the commands:
```
ssh leviathan.labs.overthewire.org -p 2223 -l leviathan4
ls -la
cd .bin
ls -la
./bin
```
Find an online tool for converting binary to ASCII.
**Password**: Tith4cokei

## leviathan 5 -> 6
Run the commands:
```
ssh leviathan.labs.overthewire.org -p 2223 -l leviathan5
ls -la
./leviathan5
 ln -s /etc/leviathan_pass/leviathan6 /tmp/file.log
./leviathan5
```
**Password**: UgaoFee4li

## leviathan 6 -> 7
Run the commands:
```
ssh leviathan.labs.overthewire.org -p 2223 -l leviathan6
ls -la
./leviathan6
./leviathan6 1234
for i in {0000..9999}; do ~/leviathan6 $i; done
```
Wait few seconds, then you'll be prompted to a new shell.
Run the commands:
```
whoami
cat /etc/leviathan_pass/leviathan7
```
**Password**: ahy7MaeBo9

## leviathan 7 -> 8
Run the commands:
```
ssh leviathan.labs.overthewire.org -p 2223 -l leviathan7
ls -la
cat CONGRATULATIONS
```
**Password**: Congratulations! You have finished Leviathan!
