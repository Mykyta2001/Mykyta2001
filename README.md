import telebot
bot = telebot.TeleBot('1427003407:AAH9L-oy36syhxOuaz54JLgceyxLAOfGt7M')
@bot.message_handler(commands=['start'])
def start_message(message):
    bot.send_message(message.chat.id, 'Напиши  привет ' )

@bot.message_handler(content_types=['text'])
def send_text(message):
    if message.text.lower() == 'привет':

        bot.send_message(message.chat.id, 'Привет, я бот Стефаний, стараюсь показать дату :);спроси: покажи дату  ')
    elif message.text.lower() == 'покажи дату':
       bot.send_message(message.chat.id, 'Посмотрите у себя в календаре ')
    elif message.text.lower() == '/help':
       bot.send_message(message.chat.id, 'Кроме даты ничего нет  ')
    elif message.text.lower() == 'пока':
        bot.send_message(message.chat.id, 'Прощай, ')

bot.polling()
