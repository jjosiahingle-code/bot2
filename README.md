@bot.command()
async def joined(ctx, member: discord.Member):
    """Says when a member joined."""
    # Joined at can be None in very bizarre cases so just handle that as well
    if member.joined_at is None:
        await ctx.send(f'{member} has no join date.')
    else:
        await ctx.send(f'{member} joined {discord.utils.format_dt(member.joined_at)}')
        
@client.event
async def on_message(message):
    if message.author == client.user:
        return
    if message.content.startswith('weeee'):
        await message.channel.send("wooooo!")
        
client.run("MTUyNjk4MDAzMTczMTk5MDY0Mg.Godwi3.H5p9s5YGYJD1WRwLSR2lkWBD5oFOvLDqQ6AiXw")
