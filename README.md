# discord-multiplayer-risk
A Multiplayer RISK-like game where players must get money, buy troops, conquer countries, etc.

## English

This is a multiplayer game where people must get money in order to buy troops to conquer fictional 
countries in a fictional world. Kind of like RISK, but your strength will be determined by the size
of your armies.

The game ends when a player conquers 90% of the conquerable countries, or it may last forever :-)

### Jobs

There are three types of jobs. One legal and two illegal ones:

!work, !narco and !crime. Each one of these will have a different payout but the illegal jobs have
a greater failure rate that will take money off your bank balance.

### Other Triggers

!bank shows your current balance and your inventory.

!shop shows the assets you can purchase (soldier, tank, hellicopter, fighter jet, artillery)

!pay <player> <amount> transfers money from your bank to your friend's

!map  will print a map with the players that have conquered a country. Unconquered countries have
very little defense. Conversely, conquered countries must have troops assigned by the player. 

The defending part will always have a 1000hp extra in the form of garrison.

Attacking side will have an amount of hitpoints defined by the amount of troops that they have.

Values (per assigned unit):
```
soldier: 10hp
artillery: 50hp
hellicopter: 100hp
fighter-jet: 150hp
```

Troops are costly but they can be bought at any time. As long as you have sufficient cash or work frequently any of the jobs explained above.



# Technical 

locale.conf defines the strings for the game. By default is English. 
A spanish locale.conf is also included.

```
shop.py handles the assets a player can buy. More can be added and values can be adjusted here
conquer.py handles the conquering aspect of the game, item strength can be adjusted here, country names too
lexirpg.py the main script. 
```

### Running this on your own discord server

1. Create a bot and obtain a token
2. clone the repository in a machine with python3 
3. edit lexirpg.py and add the obtained token into bot_token('your-token-goes-here')
4. run with nohup /usr/bin/python3 /path/to/lexirpg.py


# EXAMPLE

```
Player: !conquista
LexiRPG: Para iniciar una conquista, asigna tus unidades disponibles. Por favor, especifica el número de cada tipo de unidad que deseas desplegar.
LexiRPG: Soldados disponibles: 5
LexiRPG: Artillería disponible: 3
LexiRPG: Tanques disponibles: 2
Player: Quiero enviar 2 soldados, 1 artillería y 1 tanque.
LexiRPG: ¡Conquista en curso! Simulando batalla...
LexiRPG: Conquista exitosa. Has conquistado el país.
LexiRPG: Tropas perdidas durante la batalla:
LexiRPG: - Soldados perdidos: 1
LexiRPG: - Artillería perdida: 0
LexiRPG: - Tanques perdidos: 1
LexiRPG: Tropas restantes después de la batalla:
LexiRPG: - Soldados restantes: 2
LexiRPG: - Artillería restante: 3
LexiRPG: - Tanques restantes: 1
```
