# python-简单代码实现密码检测
~~~python
#!/usr/bin/python3
'''
@jzb
'''
import re
password = str(input('您输入的密码是：'))
def lencheck(pwd):
    if(len(password)<=5):
        print('您的密码长度过短')
    elif(len(password)<=9):
        print('您的密码长度适中')
    else:
        print('您的密码长度达到要求')
        return True
def numbercheck(pwd):
    pattern = re.compile('[0-9]+')
    match = pattern.findall(pwd)
    if match:
        print('安全系数较低')
        return True
    else:
        print('Waring:the password security of your password is low')
        return False
def lowcheck(pwd):
    pattern = re.compile('[a-z]+')
    match = pattern.findall(pwd)
    if match:
        print('安全系数较高')
        return True
    else:
        print('Waring:the password security of your password is low')
        return False
def middlecheck(pwd):
    pattern = re.compile('[A-Z]+')
    match = pattern.findall(pwd)
    if match:
        print('安全系数较高')
        return True
    else:
        print('Waring:the password security of your password is low')
        return False
def highcheck(pwd):
    pattern = re.compile('^[a-z0-9A-Z]+')
    match = pattern.findall(pwd)
    if match:
        print('安全系数极高哦')
        return True
    else:
        print('Waring:the password security of your password is low')
        return False
def checkpassword(pwd):
    check = lencheck(pwd) and numbercheck(pwd) and lowcheck(pwd)and middlecheck(pwd)and highcheck(pwd)
    if check:
        print('您的密码安全系数高')
    else:
        print('您的密码安全系数低')
checkpassword(password) 
~~~
