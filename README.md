# HSntubot echo
import sys
import time
import telepot

def handle(msg):
    content_type, chat_type, chat_id = telepot.glance(msg)
    print(content_type, chat_type, chat_id)

    if content_type == 'text':
        bot.sendMessage(chat_id, "Hello, I am Hearthstonebot. I can recommend you decks to play and explain common hearthstone terms. Allow me to recommend you a deck. Would you like to play a fun or competitive deck?")

TOKEN = "274733908:AAFdxj0Rg6v8eIhvk6B4QO11DLcRPzl5UsA"  # get token from command-line

bot = telepot.Bot(TOKEN)
bot.message_loop(handle)
print ('Listening ...')

# Keep the program running.
while 1:
    time.sleep(10)
