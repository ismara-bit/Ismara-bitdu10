const Discord = require('discord.js')
const bot = new Discord.Cient()
bot.login(NjMzMzAwMzYyNzg2MzczNjQz.XaR9Ag.OWuHwEK2MzIjMBOCx7Rh_1nWyEs)

//debut du code


bot.on('message', message => {

  if (message.content.startsWith('play')) {
    let voiceChannel = message.guild.channels
      .filter(function (channel) { return channel.type === 'voice' })
      .first()
    let args = message.content.split(' ')
    voiceChannel
      .join()
      .then(function (connection) {
        let stream = YoutubeStream(args[1])
        stream.on('error', function () {
          message.reply("Je n'ai pas réussi à lire cette vidéo :(")
          connection.disconnect()
        })
        connection
           .playStream(stream)
            connection.disconnect()
          })
        
      }
  }
)
