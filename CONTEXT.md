# Subagents

Delegation of work from a parent Pi session to child agents, running in the parent process or in detached background processes.

## Language

**Background runner**:
The detached process that hosts one asynchronous launch and its child Pi sessions. Foreground children do not use one.
_Avoid_: Worker, daemon

**Runner launcher**:
A named, user-defined argv prefix that wraps the background runner's command, typically to run it in an OS sandbox. An agent selects one by name with `launcher`; only the user's own config defines what it executes.
_Avoid_: Sandbox (the launcher is the mechanism, not the sandbox), wrapper, runner command

**Runner type**:
The agent's `runner` field, which chooses between native Pi and an external CLI or job. Unrelated to the background runner process or the runner launcher.
_Avoid_: Launcher
