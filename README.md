import telebot

# conexión con nuestro Bot
TOKEN = '7862120369:AAH4BmLUGSi0X17OrXCHW9lDEMxRCmqGBGw'
bot = telebot.TeleBot(TOKEN)

# creación de comandos simples como '/start' y el comando '/help'

@bot.message_handler(commands=['start'])
def send_welcome(message):
    bot.reply_to(message, '¡Hola! Bienvenidos a footbot')

@bot.message_handler(commands=['help'])
def send_help(message):
    bot.reply_to(message, 'Puedes interactuar conmigo usando comandos. Por ahora, solo respondo a /start y /help.')

@bot.message_handler(func=lambda m: True)
def echo_all(message):
    bot.reply_to(message, message.text)

print("Bot iniciado...")



if __name__ == '__main__':
    bot.infinity_polling(None_stop=True)  # Mantén el bot en ejecución


