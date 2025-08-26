# ADK Code Completion Instructions

Diese Datei enthält spezifische Anweisungen, um die Code Completion für ADK-Skripte in diesem Repository zu optimieren. Sie basiert auf der offiziellen Dokumentation (https://google.github.io/adk-docs/) und berücksichtigt die Syntax und Struktur dieses Repos.

## 1. Allgemeine Hinweise
- ADK (Agent Development Kit) wird in diesem Repo hauptsächlich in Python verwendet.
- Die Agenten sind in Modulen mit einer klaren Ordnerstruktur organisiert (z.B. `agent.py`, `subagents/`, `tools/`).
- Jeder Agent hat in der Regel eine eigene Klasse, die von einer ADK-Basisklasse erbt oder ADK-Komponenten nutzt.
- Die Benennung folgt dem Muster: `<agent_name>_agent` für Hauptagenten und `subagents/` für Unteragenten.
- Tools und Utilities liegen meist in `tools.py` oder `utils.py`.

## 2. ADK-Syntax und Best Practices
- Importiere ADK-Komponenten immer explizit, z.B.:
  ```python
  from adk.agent import Agent
  from adk.tools import Tool
  ```
- Agenten werden als Klassen implementiert, z.B.:
  ```python
  class MyAgent(Agent):
      def run(self, input):
          # ...
  ```
- Subagenten werden in Unterordnern als eigene Module gehalten und können vom Hauptagenten importiert werden.
- Tools werden als eigene Klassen oder Funktionen implementiert und übergeben.
- Nutze Typhints und Docstrings für bessere Lesbarkeit und Completion.

## 3. Typische ADK-Patterns in diesem Repo
- Jeder Agent hat eine `run`- oder `execute`-Methode als Einstiegspunkt.
- Subagenten werden meist als Attribute im Hauptagenten gehalten.
- Tools werden über eine Liste oder ein Dictionary verwaltet.
- State-Management erfolgt über Attribute oder Hilfsklassen (`utils.py`).
- Persistenz (z.B. SQLite) wird in eigenen Modulen wie `utils.py` oder `main.py` gehandhabt.

## 4. Beispiele
**Agent-Definition:**
```python
from adk.agent import Agent

class GreetingAgent(Agent):
    def run(self, input: str) -> str:
        return f"Hallo, {input}!"
```

**Subagent-Import:**
```python
from .subagents.post_generator import PostGenerator
```

**Tool-Definition:**
```python
from adk.tools import Tool

class MyTool(Tool):
    def execute(self, data):
        # ...
```

## 5. Weitere Hinweise
- Folge der bestehenden Ordner- und Dateistruktur.
- Nutze sprechende Namen für Agenten, Subagenten und Tools.
- Halte dich an PEP8 und die in diesem Repo übliche Formatierung.
- Siehe die offizielle Doku für fortgeschrittene Features und Integrationen.

---

**Weitere Informationen:**
- [ADK Offizielle Dokumentation](https://google.github.io/adk-docs/)
- Siehe README.md und learnings.md in den jeweiligen Modulen für projektspezifische Hinweise.

