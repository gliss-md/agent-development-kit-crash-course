https://google.github.io/adk-docs/callbacks/
# Learnings
- before-callback: state hydration | state setup: 
    - auth
    - user information
    - State anreichern, um den Agenten Kontext zu geben
- after-callback: cleanup / effekte
    - state speichern
    - nebeneffekte like logging
- before-tool-callback: state refresh
    - auth
    - inspect / modify arguments
- after-tool-callback:
    - inspect / modify results
    - effekte
- callbackContext: 
    - Verfügbar in functions; beinhaltet state, welcher angereichert werden kann
    - return none: alles ist fine
    - alternativ: Fehlermeldung an Agent | verhalten | state

# Todos:
- Callbacks werden vmtl das tooling sein, um state herzustellen, mit dem wir Kunden beraten können.
- scope von agents muss geklärt werden. vmtl bekommen wir eine mensa instanz?! Starten können wir hier vmtl mit mocks
- Logging super interesting für das tracking von Kunden-Needs