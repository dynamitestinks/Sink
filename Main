import discord
from discord.ext import commands
import random
import os

# Bot setup
intents = discord.Intents.default()
intents.message_content = True

bot = commands.Bot(command_prefix="!", intents=intents)

responses = [
    "yo",
    "hi",
    "thx man",
]

@bot.event
async def on_ready():
    print(f"Logged in as {bot.user}")

@bot.event
async def on_message(message):
    if message.author.bot:
        return

    msg = message.content.lower()

    trigger_phrases = [
        "let that sink in",
        "let this sink in",
        "let him sink in",
        "let her sink in"
    ]

    if any(phrase in msg for phrase in trigger_phrases):
        await message.channel.send(random.choice(responses))

    await bot.process_commands(message)

# Use Render environment variable instead of hardcoding token
bot.run(os.getenv("TOKEN"))
