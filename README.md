# HSntubot

import sys
import telepot
from telepot.delegate import pave_event_space, per_chat_id, create_open

class MessageCounter(telepot.helper.ChatHandler):
    def __init__(self, *args, **kwargs):
        super(MessageCounter, self).__init__(*args, **kwargs)
        self._count = 0


    def on_chat_message(self, msg):
        if self._count == 0:
            self.sender.sendMessage("Hello, I am Hearthstonebot. I can recommend you decks to play and explain common hearthstone terms. Allow me to recommend you a deck. Would you like to play a fun or competitive deck?")
            self._count += 1
        elif self._count == 1:
             self.sender.sendMessage("you have chosen...")
             self._count +=1
        else: self.sender.sendMessage("TBD")

       

TOKEN = "274733908:AAFdxj0Rg6v8eIhvk6B4QO11DLcRPzl5UsA" # get token from command-line

bot = telepot.DelegatorBot(TOKEN, [
    pave_event_space()(
        per_chat_id(), create_open, MessageCounter, timeout=10),
])
bot.message_loop(run_forever='Listening ...')
