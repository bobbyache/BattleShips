

## Use Cases

| Use Case        | Description  |
| ------------- |:-------------|
| Local Player, Remote Player, Computer Player     |  Take Shot |
| Computer Player     |  Guess Next Logical Coordinate |
| Local Player, Remote Player, Computer Player     |  Record Last Shot |
| Local Player, Remote Player, Computer Player     |  Record Opponent Shot |
| Local Player, Remote Player, Computer Player     |  Place Fleet |
| Local Player, Remote Player     |  Start New Game |
| Local Player, Remote Player     |  Suspend Current Game |
| Local Player, Remote Player     |  Resume Game |
| Local Player, Remote Player     |  Concede Game |
| Local Player, Remote Player     |  Cancel Game |

```plantuml
@startuml

actor Player
actor "Local Player" as LocalPlayer
actor "Remote Player" as RemotePlayer
actor "Computer Player" as ComputerPlayer

(Start new game) as start
(Suspend current game) as suspend
(Resume game) as resume
(Concede game) as concede
(Cancel game) as cancel


Player <|-- LocalPlayer
Player <|-- RemotePlayer
Player <|-- ComputerPlayer

Player --up-> (Take a shot)
ComputerPlayer --down-> (Guess next logical coordinate)
Player -up-> (Record last shot)
Player -up-> (Record opponent shot)
Player -up-> (Place fleet)

LocalPlayer --> start
RemotePlayer --> start
LocalPlayer --> suspend
RemotePlayer --> suspend
LocalPlayer --> resume
RemotePlayer --> resume
LocalPlayer --> concede
RemotePlayer --> concede
LocalPlayer --> cancel
RemotePlayer --> cancel

@enduml
```