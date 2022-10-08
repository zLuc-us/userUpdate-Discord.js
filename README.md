```ts
import { TextBasedChannel, EmbedBuilder, Colors } from "discord.js";

    client.on("userUpdate", async (oldMember, newMember) => {
      const channel = <TextBasedChannel>(
        await client.channels.fetch("") //id do canal
      );
      const NewEmbed = new EmbedBuilder()
        .setTitle(`Novo avatar`)
        .setImage(newMember.avatarURL({ size: 2048 }))
        .setColor(Colors.DarkAqua);

      const oldEmbed = new EmbedBuilder()
        .setTitle(`Avatar antigo`)
        .setImage(oldMember.avatarURL({ size: 2048 }))
        .setColor(Colors.Aqua);
      channel!.send({ embeds: [NewEmbed, oldEmbed] });
    });
```
