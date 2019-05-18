# Google-Assistant

from Adafruit_IO import Client, RequestError, Feed
import os
import webbrowser
import urllib.request as url
import random
ADAFRUIT_IO_KEY = '*******************************'

ADAFRUIT_IO_USERNAME = '************'

# Create an instance of the REST client.
aio = Client(ADAFRUIT_IO_USERNAME, ADAFRUIT_IO_KEY)

try:
    foo = aio.feeds('happy')
except RequestError: # Doesn't exist, create a new feed
    feed = Feed(name="happy")
    foo = aio.create_feed(feed)


# Send a string value 'bar' to the feed 'Foo'.
aio.send_data(foo.key, random.randint(0,10))

flag=''
while 1:
  
    data = aio.receive(foo.key)
    data=data.value
    if not flag==data:
        print(data)
        if data=='opennote':
            os.startfile('notepad.exe')
        elif data=='closenote':
            os.system('TASKKILL /F /IM notepad.exe')
        elif data=='openiot':    
            webbrowser.open('http://v3svimal.co.nf') # Go to example.com
        elif data=='closeiot':    
            os.system('TASKKILL /F /IM chrome.exe')    
        elif data=='1':
            url.urlopen('http://v3svimal.co.nf/my_data_write.php?a_data=on')
        elif data=='0':
            url.urlopen('http://v3svimal.co.nf/my_data_write.php?a_data=off')
        elif data=='shutlap':    
            os.system("shutdown /r /t 1");
        elif data=='open calci':
            os.startfile('Calc.exe')
        elif data=='close calci':
            os.system('TASKKILL /F /IM Calculator.exe')
        elif data=='urvashi rautela':
            webbrowser.open('https://en.wikipedia.org/wiki/Urvashi_Rautela')
        elif data=='close urvashi rautela':
            os.system('TASKKILL /F /IM /chrome.exe')
            
        flag=data


