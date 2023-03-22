import discord
from discord.ext import commands

client = commands.Bot(command_prefix='!')

@client.event
async def on_ready():
    print('Bot is ready.')

@client.event
async def on_message(message):
    if message.author == client.user:
        return

    if message.content.startswith('hello'):
        await message.channel.send('Hi there!')
    
    await client.process_commands(message)

client.run('MTA4Nzk0Nzk2Mzc5MzQyODQ4MA.G2IKIa._OXl9ddwXY4dpWt8BLymFAepEsZ7XbwbiZyuzc')
