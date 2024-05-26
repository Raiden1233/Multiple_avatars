@Raiden.command()
async def avatars(ctx, members: commands.Greedy[discord.Member]):
  ls = []
  for urls in members:
      ls.append(urls.avatar)
      

  if len(ls) > 1:
    for avatarr in members:  
      em = discord.Embed(title=f"{to_upper('avatar')} of {avatarr._user}")
      em.set_image(url= avatarr.avatar)
      
      await ctx.send(embed= em)

  elif len(ls) < 2:
    em = discord.Embed(
                title= 'Error!',
                description= 'Sorry ***This function*** is only to check multiple users avatar at sametime\n use ***>avatar*** to check only **1 person avatar** at a time. <3 Thank you!',
                color= ctx.author.color                      
                        )
    em.set_image(url='https://media.discordapp.net/attachments/1010954815192440935/1125824654033035304/Tumblr_l_108190584885447.gif?width=820&height=10')
    await ctx.send(embed = em)