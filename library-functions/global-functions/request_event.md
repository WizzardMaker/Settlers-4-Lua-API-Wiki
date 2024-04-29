# request_event

## `request_event(Funktion, Eventtyp)`

Jede Funktion, die vom Spiel selbst aufgerufen wird, muss hier angefordert werden. Dies wird meist in new_game() erledigt. Mögliche [Events ](../../api-enums/events.md)sind:

|                                               |                                                                                                  |
| --------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Events.TICK                                   | Funktion wird jeden Tick aufgerufen                                                              |
| Events.FIVE_TICKS                            | Funktion wird alle fünf Ticks aufgerufen                                                         |
| Events.VICTORY_CONDITION_CHECK              | ähnliche wie FIVE_TICKS, aber nur, solange das Spiel nicht gewonnen oder verloren wurde         |
| Events.FIRST_TICK_OF_NEW_OR_LOADED_GAME | Beim Starten oder neu laden eines Spiels                                                         |
| Events.FIRST_TICK_OF_NEW_GAME             | Beim Starten eines neuen Spiels.                                                                 |
| Events.PRODUCTION                             | unbekannt, vermutlich wenn ein Produktionsvorgang beendet wurde.                                 |
| Events.SPACE                                  | unbekannt                                                                                        |
| Events.BUILD_PRIO                            | unbekannt, vermutlich wenn die Gebäudepriorität geändert wird                                    |
| Events.CREATE_FOUNDATION_CART               | unbekannt, vermutlich beim erstellen eines Gründungskarrens.                                     |
| Events.CRUSH_BUILDING                        | unbekannt, vermutlich wenn ein Gebäude abgerissen wird                                           |
| Events.SHOW_WORK_AREA                       | unbekannt, vermutlich wenn der Spieler sich den Arbeitsbereich eines Gebäudes zeigen lässt       |
| Events.MAGIC_SPELL_CAST                     | unbekannt, vermutlich wenn ein Spieler einen Zauber nutzt                                        |
| Events.ZOOM_FACTOR_CHANGED                  | unbekannt, vermutlich wenn der Spieler den Zoom verstellt                                        |
| Events.WARRIOR_SENT                          | unbekannt, vermutlich wenn ein Spieler einer Einheit einen Bewegungsbefehl erteilt               |
| Events.WORK_AREA                             | unbekannt, vermutlich wenn ein Spieler einen Arbeitsbereich neu festlegt                         |
| Events.MENUCLICK                              | unbekannt, vermutlich wenn der Spieler im Menü klickt                                            |
| Events.GOODARRIVE                             | unbekannt, vermutlich wenn ein Siedler eine Ware an ihr Ziel bringt                              |
| Events.WORK_STATUS                           | unbekannt                                                                                        |
| Events.SETTLER_CHANGE_TYPE                  | unbekannt, vermutlich wenn ein Siedler die Rolle wechselt                                        |
| Events.COMMAND                                | unbekannt                                                                                        |
| Events.DRAG_BUILDING                         | unbekannt, vermutlich wenn der Spieler sich die möglichen Bauplätze für ein Gebäude zeigen lässt |

#### Rückgabewert

none

#### Beispiel

```lua
... Funktion Beispiel und VictoryConditionCheck werden hier geschrieben ...

function new_game()
        request_event(VictoryConditionCheck, Events.VICTORY_CONDITION_CHECK)
        request_event(Beispiel, Events.FIVE_TICKS)
end
function register_functions()
        reg_func(VictoryConditionCheck)
        reg_func(Beispiel)
end
```
