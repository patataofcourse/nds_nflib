# Nightfox's Lib for Nintendo DS - edited by patataofcourse
(the original readme for NightFox's Lib is located at readme_nflib.txt)

This version of the library adds support for loading tiled BGs, sprites, and sprite palettes from char arrays in the code. It's meant to be used with DS Download Play or other instances where neither FAT nor NitroFS are available.

For each function, you'll need to supply an array per file required, plus the size of that array.

The new functions are:

```c
void NF_LoadTiledBgFromSource(const char* img, u16 img_length, const char* map, u16 map_length, const char* pal, u16 pal_length, const char* name, u16 width, u16 height);
```
- `const char* img`: the background's .img file.
- `u16 img_length`: the length of the .img array.
- `const char* map`: the background's .map file.
- `u16 map_length`: the length of the .map array.
- `const char* pal`: the background's .pal file.
- `u16 pal_length`: the length of the .pal array.
- `const char* name`: a name for the background, to be later referred to.
- `u16 width`: the width of the background - has to be a multiple of 256.
- `u16 height`: the height of the background - has to be a multiple of 256.

```c
void NF_LoadSpriteGfxFromSource(const char* file, u16 file_length, u16 id, u16 width, u16 height);
```
- `const char* file`: the sprite's .img file.
- `u16 file_length`: the length of the file array.
- `u16 id`: an id for the sprite gfx (in RAM), to be later referred to.
- `u16 width`: the width of the sprite - has to be a multiple of 8, and no bigger than 64.
- `u16 height`: the height of the sprite - has to be a multiple of 8, and no bigger than 64.

```c
void NF_LoadSpritePalFromSource(const char* pal, u16 pal_size, u8 id);
```
- `const char* pal`: the palette file.
- `u16 pal_size`: the length of the file array.
- `u16 id`: an id for the palette (in RAM), to be later referred to.