# GameEngiLab
labActivity

Leux Mattheus Yap 100928496
Game title: "mario64 at home"

Gameplay loop is basically collecting coins and parkouring through the stage to get to the end and get the "star", this resets the game, also touching the white floor will kill you.

Blueprints:
![image alt](https://github.com/Matt-Yap/GameEngiLab/blob/37339fb851ff3179e5196b66df1ca5bb0f4f610b/Screenshot%202026-09-29%20231447.png)
![image alt](https://github.com/Matt-Yap/GameEngiLab/blob/d6775f160437c94fc497c43a7270cf3a3c00ef8a/Screenshot%202026-09-29%20231435.png)

Pseudocode for blueprints:

on overlap with player character:
    gameInstance.Coins += 1
    else:
          Overlapping actor is not the player — ignore
return


and for the widget blueprint:
GetText() -> Text:
    return ToText(GameInstance.Coins)

The element of the game that adopts the singleton pattern is the coin collecting part. Globally accessible piece of state that two unrelated objects share (coin pickup blueprint and the UI hud widget)

I used the Game Instance because there's only one coin count in the game, and both the coin pickup and the HUD need to use it without having to know about the other. It also persists for the whole game so the player doesn't lose their coins when the level changes.
