Collection of **`console mode`** commands --> [ref](https://tools.dathost.net/csgo-commands)

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
