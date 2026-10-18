I finally finished my transcode of the classic arcade game Asteroids for the Color Computer 3. The compiled sprites, audio samples and game code uses about 195k uncompressed so it requires a CoCo 3 with 512 KB of RAM.

The original arcade game runs on a 6502, so this was a 6502 to 6809 transcode. I started with a disassembly of the arcade code and then used a transcoding tool I wrote to convert it to 6809 assembly. After that I had to work through the weird things about the 6502 that don't translate cleanly. I covered the basics of that process in my "[MOS 6502 to Motorola 6809 Assembly Language Transcoding](https://nowhereman999.wordpress.com/2023/02/15/mos-6502-to-motorola-6809-assembly-language-transcoding/)" post. If you want to see how I approached a similar job on an earlier arcade game, check out my "[PAC MAN z80 to 6809 transcode series](https://nowhereman999.wordpress.com/2017/07/01/zilog-z80-to-motorola-6809-transcode-part-024-pac-man-is-finally-complete-if-you-have-a-coco-3-with-512k-give-it-a-try/)".

The hardest part was the graphics. Asteroids is a vector game, so I had to turn the arcade's vector commands into compiled sprites that draw on the CoCo's 640x200 two colour screen. Getting the sprite sizes right was a real pain and not fun so I stopped the project back in 2023. But these days things like this are easy to do with the help of AI. So with CODEX's help (ChatGPT's coding assistant) I was finally able to draw the sprites at the correct size for the screen, and that was the last piece I needed to finish the game.

I'll be putting it on my GitHub page, and I'll add the link here once it's up.

Have fun!

Glen
