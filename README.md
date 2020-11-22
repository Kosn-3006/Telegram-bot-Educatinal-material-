# Telegram-bot-Educatinal-material-

CODE FOR BOT

import telebot
from telebot import types
bot = telebot.TeleBot("1464825390:AAEGdQWXSTa8HWRVj3J97stAIK1rb-jbvDM")

@bot.message_handler(commands=['start', 'help'])
def send_welcome(message):
   # keyboard
   markup = types.ReplyKeyboardMarkup(resize_keyboard=True)
   item1 = types.KeyboardButton("С++")
   item2 = types.KeyboardButton("ICT")
   item3 = types.KeyboardButton("Calculus 1")

   markup.add(item1, item2, item3)
   bot.reply_to(message, "Привет, по каким предметам нужна помощь ?",reply_markup=markup)

@bot.message_handler(content_types=['text'])
def bort(message):
   if message.chat.type == 'private':
      if message.text == 'С++':
         # keyboard
         markup = types.InlineKeyboardMarkup(row_width=1)
         item1 = types.InlineKeyboardButton("Week 1", url='https://code-live.ru/post/cpp-if-else/')
         item2 = types.InlineKeyboardButton("Week 2",  url='https://code-live.ru/post/cpp-loops/')
         item3 = types.InlineKeyboardButton("Week 3", url='https://code-live.ru/post/cpp-loops/')
         markup.add(item1, item2,item3)
         bot.send_message(message.chat.id, "Choose which week", reply_markup=markup)
      elif message.text == 'ICT':
         # keyboard
         markup = types.InlineKeyboardMarkup(row_width=1)
         item1 = types.InlineKeyboardButton("Week 1", url= 'https://www.ictlounge.com/html/database_structures.htm')
         item2 = types.InlineKeyboardButton("Week 2", url='https://www.guru99.com/difference-system-software-application-software.html')
         item3 = types.InlineKeyboardButton("Week 3", url='https://www.zeluslugi.ru/info-czentr/it-glossary/term-sql#:~:text=SQL%20%E2%80%94%20%D0%BF%D1%80%D0%BE%D1%81%D1%82%D1%8B%D0%BC%D0%B8%20%D1%81%D0%BB%D0%BE%D0%B2%D0%B0%D0%BC%D0%B8%2C%20%D1%8D%D1%82%D0%BE%20%D1%8F%D0%B7%D1%8B%D0%BA,%D0%B8%D0%B7%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8F%20%D0%B8%D0%B7%20%D0%B1%D0%B0%D0%B7%D1%8B%20%D0%B8%20%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F.')
         markup.add(item1, item2, item3)
         bot.send_message(message.chat.id, "Choose which week", reply_markup=markup)
      elif message.text == 'Calculus 1':
         # keyboard
         markup = types.InlineKeyboardMarkup(row_width=1)
         item1 = types.InlineKeyboardButton("Week 1", url='http://mathportal.net/index.php/matematicheskaya-logika-i-teoriya-mnozhestv/mnozhestva-operatsii-nad-mnozhestvami')
         item2 = types.InlineKeyboardButton("Week 2", url='https://artemarakcheev.com/2018-01-17/limits_and_continuous_functions')
         item3 = types.InlineKeyboardButton("Week 3", url='https://www.berdov.com/docs/fluxion/rules/')
         markup.add(item1, item2, item3)
         bot.send_message(message.chat.id, "Choose which week", reply_markup=markup)

bot.polling()
