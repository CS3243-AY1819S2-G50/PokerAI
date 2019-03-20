## Term Project

### Set up environment
using the conda or pyenv

- conda create -n cs3243 python=2.7
- source activate cs3243

replace the cs3243 with whatever name you want
https://conda.io/docs/index.html

pip install PyPokerEngine  
https://ishikota.github.io/PyPokerEngine/



testing installmement:

```
import pypokerengine   
print("hello world")
```



### Create your own player
#### Example player

```

class RaisedPlayer(BasePokerPlayer):

  def declare_action(self, valid_actions, hole_card, round_state):
    #Implement your code
    return action

  def receive_game_start_message(self, game_info):
    pass

  def receive_round_start_message(self, round_count, hole_card, seats):
    pass

  def receive_street_start_message(self, street, round_state):
    pass

  def receive_game_update_message(self, action, round_state):
    pass

  def receive_round_result_message(self, winners, hand_info, round_state):
    pass
```
#### Example Game
The example game is in the example.py

#### Information for the game
```valid_actions```: vaild action list


```
[
    { "action" : "fold"  },
    { "action" : "call" },
    { "action" : "raise" }
]
OR 
[
    {"action": "fold"},
    {"action": "call"}
]
```
   
In each street (preflop,flop,turn,river), each player only allowed to raise for four times. So for a game, 
each player can raise a maximum of 16 times.

Other information is similar to the PyPokerEngine,please check the detail about the parameter [link](https://github.com/ishikota/PyPokerEngine/blob/master/AI_CALLBACK_FORMAT.md)
