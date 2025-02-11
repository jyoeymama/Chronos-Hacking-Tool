⏳ Chronos - Time Manipulation & Exploitation Tool
Chronos is a unique tool for Kali Linux designed to manipulate time-based security mechanisms. It helps security professionals and penetration testers understand and exploit time-dependent vulnerabilities.

⚡ How It Works
Chronos provides multiple functions, including timestamp manipulation, delayed execution, log poisoning, NTP spoofing, and session hijacking analysis. Here's how each feature works:

1️⃣ Timestamp Spoofing (Anti-Forensics)
📌 Purpose: Modify file timestamps to erase or falsify logs, making forensic tracking harder.
📌 How it Works: Uses the touch command to modify timestamps.
📌 Example Usage:

bash
Copy
Edit
./chronos.sh --spoof /var/log/auth.log "2023-01-01 12:00:00"
🔹 This will set the timestamp of /var/log/auth.log to January 1, 2023, at 12:00 PM.

2️⃣ Delayed Execution (Timed Attacks & Automation)
📌 Purpose: Schedule execution of a command at a specific time.
📌 How it Works: Uses the Linux at command to execute payloads at a scheduled time.
📌 Example Usage:

bash
Copy
Edit
./chronos.sh --execute "echo 'Hacked!'" "23:59"
🔹 This will print "Hacked!" at 11:59 PM.

3️⃣ Log Poisoning (Timestamp Desynchronization)
📌 Purpose: Shift log timestamps to create confusion in forensic analysis.
📌 How it Works: Uses awk to modify timestamps within log files.
📌 Example Usage:

bash
Copy
Edit
./chronos.sh --log-poison /var/log/syslog "-2h"
🔹 This moves all log entries 2 hours into the past.

4️⃣ NTP Spoofing (Network Time Attack)
📌 Purpose: Mislead system clocks by spoofing Network Time Protocol (NTP) responses.
📌 How it Works: Uses ettercap and ntpdate to manipulate time settings on a target.
📌 Example Usage:

bash
Copy
Edit
./chronos.sh --ntp-spoof 192.168.1.100 "+10min"
🔹 This tells the target at 192.168.1.100 that the current time is 10 minutes ahead.

5️⃣ Session Token Hijacking (Experimental)
📌 Purpose: Analyze expired session tokens to hijack active user sessions.
📌 How it Works: Checks session expiration windows and attempts replay attacks.
📌 Example Usage:

bash
Copy
Edit
./chronos.sh --hijack 192.168.1.10
🔹 (Feature still under development).

⚠ Disclaimer: Ethical Use Only
This tool is designed for educational purposes and ethical security testing only. Misusing it for illegal activities is strictly prohibited. The developer is not responsible for any misuse. Always obtain proper authorization before testing security systems.

🔹 Use this tool responsibly and legally. 🚀
