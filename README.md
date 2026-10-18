I finally finished my transcode of the classic arcade game Asteroids for the Color Computer 3. The compiled sprites, audio samples and game code uses about 224k uncompressed so it requires a CoCo 3 with 512 KB of RAM.

I started with a disassembly of the arcade code and then used a transcoding tool I wrote to convert the 6502 instructions to similar 6809 assembly instructions. After that I had to work through the weird things about the 6502 that don't translate cleanly.  I covered the basics of that process in my "[MOS 6502 to Motorola 6809 Assembly Language Transcoding](https://nowhereman999.wordpress.com/2023/02/15/mos-6502-to-motorola-6809-assembly-language-transcoding/)" post. If you want to see how I approached a similar job on an earlier arcade game, check out my "[PAC MAN z80 to 6809 transcode series](https://nowhereman999.wordpress.com/2017/07/01/zilog-z80-to-motorola-6809-transcode-part-024-pac-man-is-finally-complete-if-you-have-a-coco-3-with-512k-give-it-a-try/)".

Asteroids is a vector game, so I had to turn the arcade's vector commands into compiled sprites that draw on the CoCo 3's 640x200 two colour screen (highest resolution screen on the CoCo 3). Getting all the sprite sizes correct was a real pain as there are 8 pre bit aligned versions of each sprite and the players ship has 64 rotational shapes, so I stopped the project back in 2023. These days things like this are easy to do with the help of AI. With CODEX's help (ChatGPT's coding assistant) I was finally able to draw the sprites at the correct size for the screen, which was the last piece I needed to finish the game.

Have fun!

Glen

## Game instructions

From the `README.TXT` included in the ZIP.

### Loading the game

```text
LOADM"ASTEROID"
```

The game starts automatically after loading.

### Inserting coins and starting

| Key | Action |
| --- | --- |
| `5` | Insert one coin. Release the key before inserting another. |
| `1` | Start a one-player game (requires one coin). |
| `2` | Start a two-player game (requires two coins). |

In a two-player game, players take turns using the same controls.

### Playing controls

| Key | Action |
| --- | --- |
| `Z` | Rotate left |
| `X` | Rotate right |
| `/` | Thrust |
| `SHIFT` | Fire |
| `SPACE` | Hyperspace |

### High-score initials

If your score qualifies, enter your three initials when prompted:

| Key | Action |
| --- | --- |
| `Z` | Select the next letter (A, B, C, ...) |
| `X` | Select the previous letter |
| `SPACE` | Accept the current letter and move to the next initial |

Press and release `SPACE` for each initial. After accepting the third letter, your entry is complete. Finish before the entry timer expires.
