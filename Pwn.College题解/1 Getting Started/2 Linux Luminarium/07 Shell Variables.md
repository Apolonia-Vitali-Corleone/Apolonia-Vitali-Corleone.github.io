# 1-Printing Variables

env



```
设置变量什么都不需要定义，shell真牛逼
```

# 2-Setting Variables

```shell
hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{4WYybmefpmFzngihIQPMvomBvLs.QXwYTN0wCO5IzW}

hacker@variables~multi-word-variables:~$ 
```



娃娃教程

# 3-Multi-word Variables 

```shell
hacker@variables~exporting-variables:~$ export PWN=COLLEGE
You've set the PWN variable to the proper value!

hacker@variables~exporting-variables:~$ COLLEGE=PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!

hacker@variables~exporting-variables:~$ /challenge/run 
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great 
job! Here is your flag:
pwn.college{4FekZ0BZDmCEQbKcI2ihY6MLgUq.QXyYTN0wCO5IzW}
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!

hacker@variables~exporting-variables:~$ 
```



这题跟父子shell间variables传递没有关系

# 4-Exporting Variables

Try the `env` command: it'll print out every *exported* variable set in your shell

```
env
```



# 5-Printing Exported Variables 



# 6-Storing Command Output

题目的一些提示：

```sh
Trivia: You can also backticks instead of $(): FLAG=`cat /flag` instead of FLAG=$(cat /flag) in the example above. This is an older format, and has some disadvantages (for example, imagine if you wanted to nest command substitutions. How would you do $(cat $(find / -name flag)) with backticks? The official stance of pwn.college is that you should use $(blah) instead of `blah`.
```

解释了我的一些困惑。

---



```bash
$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out 
and submit it!

$ echo $PWN
pwn.college{Uhx8hQsaH3gKDYwljr2zDZy8I7m.QX1cDN1wCO5IzW}

$ 
```

the picture：

![image-20241119135924316](./07%20Shell%20Variables.assets/image-20241119135924316.png)

# 7-Reading Input

```shell
hacker@variables~reading-input:~$ read PWN
COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{g923jnxk-8tL-0THOtdafIsomZs.QX4cTN0wCO5IzW}
hacker@variables~reading-input:~$ 
```

如图所示：

![image-20241119135703194](./07%20Shell%20Variables.assets/image-20241119135703194.png)



# 8-Reading Files

```sh
~$ read PWN < /challenge/read_me 
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{4WfwXwa0dgP9GqcvcHGzZUCbVY4.QXwIDO0wCO5IzW}

~$ 
```

如图所示：

![image-20241119134704260](./07%20Shell%20Variables.assets/image-20241119134704260.png)
