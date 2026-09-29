main.py
import os
import telebot

TOKEN = os.environ["BOT_TOKEN"]
bot = telebot.TeleBot(TOKEN)

@bot.message_handler(commands=["start"])
def start(message):
    bot.reply_to(
        message,
        "📊 Besno EUR/USD Bot\n\n"
        "স্বাগতম!\n"
        "/signal - সিগন্যাল\n"
        "/status - বটের অবস্থা"
    )

@bot.message_handler(commands=["signal"])
def signal(message):
    bot.reply_to(message, "⏳ EUR/USD সিগন্যাল প্রস্তুত করা হচ্ছে...")

@bot.message_handler(commands=["status"])
def status(message):
    bot.reply_to(message, "✅ Besno Signal Bot চালু আছে।")

bot.infinity_polling()
