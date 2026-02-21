## Windows Investigation 2 - Key Tools

**Procmon (Process Monitor)**
A Windows utility for detailed process monitoring during forensic investigations.
Key details it captures: process name, command line, process path, and parent process ID.
Useful for identifying malicious processes hiding in normal Windows activity.

**Loki**
A digital forensics scanner that analyzes files and processes on a system.
Uses preloaded YARA rules to detect known malicious patterns and activity.
Generates logs when suspicious matches are found - useful for incident triage.

**Autoruns**
A utility that shows everything configured to run automatically on system startup.
Key details: scheduled tasks, startup paths, and commands being executed.
Attackers abuse autoruns for persistence - always check this during investigation.
