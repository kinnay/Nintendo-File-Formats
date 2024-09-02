[SNES Online](/formats.md#snes-nso) > SFROM Files
---

An SFROM file contains the code and data of an emulated SNES game. It has the following structure:

* Unknown
* [Configuration info](#configuration-info)
* [Footer](#footer)

## Configuration Info
This section contains an array of configuration chunks. Every configuration chunk starts with a single character that indicates its type, which is followed by the configuration value.

If the character is lowercase, the value contains exactly one byte:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Chunk type (`a-z`) |
| 0x1 | 1 | Value |

If it is uppercase, the next three bytes specify the size of the value:

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 1 | Chunk type (`A-Z`) |
| 0x1 | 3 | Value size (N) |
| 0x4 | N | Value |

The following configuration types are valid:

| Type | Description |
| --- | --- |
| `A` | Unknown |
| `D` | Unknown |
| `G` | [Game id](#game-ids) |
| `P` | Unknown |
| `S` | Unknown |
| `U` | Unknown |
| `a` | Unknown |
| `c` | Unknown |
| `e` | Unknown |
| `h` | Unknown |
| `j` | Unknown |
| `m` | Unknown |
| `p` | Unknown |
| `r` | Unknown |
| `t` | Unknown |
| `v` | Audio volume |

### Game IDs
The game id is used to load game-specific patches. The following game ids are currently known:

| ID | Game |
| --- | --- |
| `1003` | Super Ghouls'n Ghosts |
| `1011` | Super Mario World |
| `1016` | Mario's Super Picross |
| `1018` | F-Zero |
| `101D` | The Legend of Zelda: A Link to the Past |
| `1022` | Donkey Kong Country |
| `1040` | Super Metroid |
| `1058` | Kirby's Dream Course |
| `105D` | Donkey Kong Country 2: Diddy's Kong Quest |
| `1068` | Breath of Fire II |
| `106E` | Earthbound |
| `1074` | Panel de Pon |
| `1077` | Donkey Kong Country 3: Dixie Kong's Double Trouble |
| `107A` | Kirby's Avalanche |
| `109F` | Kirby Super Star |
| `10A2` | Kirby's Dream Land 3 |
| `10A9` | Super Punch-Out |
| `10BA` | Pilotwings |
| `10BD` | Super Mario Kart |
| `10C7` | Super Earth Defense Force |
| `10CA` | Rival Turf |
| `10CD` | Brawl Brothers |
| `10D0` | The Ignition Factor |
| `10E7` | Super Mario All-Stars |
| `10FB` | Wild Guns |
| `1107` | Natsume Championship Wrestling |
| `112F` | Pop'n TwinBee |
| `1144` | Breath of Fire |
| `1146` | Demon's Crest |
| `123B` | Star Fox |
| `123D` | Super Mario World 2: Yoshi's Island |
| `123E` | Stunt Race FX |
| `1241` | Super Soccer |
| `1245` | Star Fox 2 |
| `1247` | Super Puyo Puyo 2 |
| `124A` | Smash Tennis |
| `1262` | Joe & Mac 2: Lost in the Tropics |
| `1266` | Super Tennis |
| `126E` | Fighter's History |
| `1270` | Caveman Ninja |
| `1276` | Doomsday Warrior |
| `1278` | Operation Logic Bomb |
| `127A` | Psycho Dream |
| `127C` | The Peace Keepers |
| `127E` | Tuff E Nuff |
| `1280` | Super Valid IV |
| `1282` | Congo's Caper |
| `1284` | Magical Drop 2 |
| `12A2` | Prehistorik Man |
| `12A4` | Earthworm Jim 2|
| `12A6` | Claymates |
| `12B0` | Super Baseball Simulator 1.000 |
| `12D2` | Bombuzal |
| `12D6` | Spanky's Quest |
| `12D8` | Jelly Boy |

## Footer

| Offset | Size | Description |
| --- | --- | --- |
| 0x0 | 4 | Configuration info size |
| 0x4 | 4 | Magic number (`Can1`) |