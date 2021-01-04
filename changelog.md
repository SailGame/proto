## 1.0.0

[Cookbook-for-Provider-Dev](https://github.com/SailGame/Core/wiki/Cookbook-for-Provider-Dev)

### Codenames
Protocol for game codenames between core side and provider side.
- When core sends a start game signal it should specify the hourglass, which is used to count the deadline when user chooses its word.
- For `UserOperation`, it holds `LeaderWord` which means leader says a keyword for its partner to guess and `FollowerWord` which stands for some follower chooses a word.
- `NotifyMsg` is a message that provider wants to send to client.
  - At Game starts, it will send the whole card table to every player. Besides, the player's role and current turn.
  - When Game running, after every message is processed by provider, it sends the `ProcessStateMsg` including current keyword or guess word and current state(which team wins or not) and next turn.
- `CardInfo` is the structure for 5x5 matrix of word, party pair.