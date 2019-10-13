Collection of **`console mode`** commands --> [CS:GO references](https://tools.dathost.net/csgo-commands) + [Weapon list](https://steamcommunity.com/sharedfiles/filedetails/?id=570025313)

```groovy
Mode 	                  game_type 	game_mode
Classic Casual               0              0
Classic Competitive	     0	            1
Arms Race 	             1	            0
Demolition                   1	            1
Deathmatch	             1	            2
```

- mp_weapons_allow_zeus 
```groovy
Default: 1
Determines whether the Zeus is purchasable or not.
Client only command
```

- mp_ct_default_melee 
```groovy
Default: weapon_knife
The default melee weapon that the CTs will spawn with.
Even if this is blank, a knife will be given. 
To give a taser, it should look like this: 'weapon_knife weapon_taser'.  
Remember to set mp_weapons_allow_zeus to 1 if you want to give a taser!
Client only command
```

- mp_t_default_grenades 
```groovy
Default: 
The default grenades that the Ts will spawn with.  
To give multiple grenades, separate each weapon class with a space like this: 'weapon_molotov weapon_hegrenade'
Client only command
```

- mp_hostages_takedamage 
```groovy
Default: 0
Whether or not hostages can be hurt.
Client only command
```

- mp_hostages_max 
```groovy
Default: 2
Maximum number of hostages to spawn.
Server only
```

- mp_ignore_round_win_conditions 
```groovy
Default: 0
Ignore conditions which would end the current round
Server only
```

- mp_limitteams 0 
```groovy
disables limitations on the number of players in both teams.
```

- bot_quota [number]
```groovy
Default: 10
Determines the total number of bots in the game.
Server only
```

- bot_quota_mode 
```groovy
Default: normal
Determines the type of quota.
Allowed values: 'normal', 'fill', and 'match'.
If 'fill', the server will adjust bots to keep N players in the game, where N is bot_quota.
If 'match', the server will maintain a 1:N ratio of humans to bots, where N is bot_quota.
Server only
```

- buddha 
```groovy
Toggle.  Player takes damage but won't die. (Shows red cross when health is zero)
Requires sv_cheats 1
Server only
```

- bot_autodifficulty_threshold_high 
```groovy
Default: 5.0
Min: -20, Max: 20
Upper bound above Average Human Contribution Score that a bot must be above to change its difficulty
Client only command
Modified in v1.34.5.6
```
