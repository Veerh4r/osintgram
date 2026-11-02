📱 Phone OSINT Tool — Professional Edition
🛡️ Promo Tool Created by VEER

A professional, interactive Python-based Phone Number OSINT utility featuring API-based lookups, formatted terminal results, batch processing, automatic JSON/CSV/TXT exports, and optional Python source-code obfuscation.

<p align="center">
<img src="https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white" alt="Python">
<img src="https://img.shields.io/badge/License-MIT-green" alt="License">
<img src="https://img.shields.io/badge/Status-Active-brightgreen" alt="Status">
<img src="https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20macOS-lightgrey" alt="Platform">
<img src="https://img.shields.io/badge/Author-VEER-purple" alt="Author">
</p>

📖 Table of Contents
About
Features
Screenshots
Installation
Usage
Output & Exports
How It Works
Project Structure
Python Script Protection
Why Obfuscate Python?
Obfuscation Methods
PyArmor Installation
Obfuscating Your Script
Building a Windows EXE
Linux & macOS
Nuitka Alternative
Security Best Practices
Roadmap
Disclaimer
Legal Notice
License
Author
🧭 About

Phone OSINT Tool is a lightweight command-line application designed for authorized OSINT research, cybersecurity education, and legitimate security investigations.

The application accepts an Indian mobile number and sends a lookup request to a configured third-party API.

Depending on the API's response, the tool can display structured information such as:

📱 Mobile number
👤 Name (if returned by the API)
👨 Father's name (if returned by the API)
🏠 Address (if returned by the API)
☎️ Alternate contact (if returned by the API)
📡 Telecom circle / operator
🆔 API-provided identifier
📧 Associated email (if returned by the API)

The application features an interactive terminal interface, so users don't need to remember complicated command-line arguments.

⚠️ Use this application only with numbers you own or are explicitly authorized to investigate. Third-party API availability and data accuracy are not guaranteed.
✨ Features
Feature	Description
🎯 Interactive Prompt	Simple mobile number input
✅ Smart Validation	Supports Indian mobile number formats
🎨 Colorized Output	Terminal interface powered by Colorama
📊 Table Formatting	Professional tables using Tabulate
🔁 Batch Mode	Multiple lookups in one session
💾 Multi-Format Export	JSON, CSV, and TXT
🔄 Retry Logic	Retry handling for temporary network failures
🛡️ Error Handling	Handles invalid input, timeouts, and API errors
🏷️ Branded Exports	VEER branding in generated reports
⚡ Simple Setup	No local API key configuration required when using a public API
🔒 Source Protection Guide	Optional Python obfuscation and executable packaging
📸 Screenshots

Example terminal interface:

text
╔══════════════════════════════════════════════════════════════╗
║             📱 PHONE OSINT TOOL                              ║
║                 Professional Edition                         ║
║             Promo Tool Created by VEER                       ║
╚══════════════════════════════════════════════════════════════╝

  ➤ Enter mobile number (or 'q' to quit): XXXXXXXXXX

  ⏳ Searching...

══════════════════════════════════════════════════════════════
                    🔍 LOOKUP RESULTS
══════════════════════════════════════════════════════════════

  📱 Mobile       : XXXXXXXXXX
  👤 Name         : [Redacted]
  🏠 Address      : [Redacted]
  📡 Operator     : [API response]
  📧 Email        : [Redacted]

══════════════════════════════════════════════════════════════

  ✔ Lookup completed

  ↻ Do another lookup? (y/N): n

  📦 Saving session results...

  💾 JSON → output/
  💾 CSV  → output/
  💾 TXT  → output/

  ✦ Promo Tool Created by VEER ✦

🛠️ Installation
Prerequisites
Python 3.8+
pip package manager
Internet connection
Access to a compatible third-party API
Step 1 — Clone the repository
bash
git clone https://github.com/B5970/osintgram.git
cd osintgram

Step 2 — Create a virtual environment (Recommended)

Linux / macOS

bash
python3 -m venv venv
source venv/bin/activate


Windows

bash
python -m venv venv
venv\Scripts\activate

Step 3 — Install dependencies
bash
pip install -r requirements.txt


Alternatively:

bash
pip install requests colorama tabulate

🚀 Usage
Start the application
bash
python phone_osint.py

Interactive example
text
➤ Enter mobile number (or 'q' to quit): XXXXXXXXXX

⏳ Searching...

✔ Lookup completed successfully

↻ Do another lookup? (y/N): y

➤ Enter mobile number (or 'q' to quit): XXXXXXXXXX

↻ Do another lookup? (y/N): n

Accepted input formats
Input	Expected behavior
XXXXXXXXXX	10-digit Indian mobile number
+91XXXXXXXXXX	International prefix
91XXXXXXXXXX	Country code
XXXXX-XXXXX	Formatting characters cleaned
Invalid length	Rejected
Invalid starting digit	Rejected
Exit

Type any of the following:

text
q
quit
exit


Or press Ctrl+C.

📂 Output & Exports

The application automatically saves session results in the output/ directory.

Generated files
text
output/
├── osint_YYYYMMDD_HHMMSS.json
├── osint_YYYYMMDD_HHMMSS.csv
└── osint_YYYYMMDD_HHMMSS.txt

JSON Example
json
[
  {
    "mobile": "XXXXXXXXXX",
    "name": "[REDACTED]",
    "fname": "[REDACTED]",
    "address": "[REDACTED]",
    "alt": "[REDACTED]",
    "circle": "[API RESPONSE]",
    "id": "[REDACTED]",
    "email": "[REDACTED]"
  }
]

CSV Example
csv
mobile,name,fname,address,alt,circle,id,email
XXXXXXXXXX,[REDACTED],[REDACTED],[REDACTED],[REDACTED],[API RESPONSE],[REDACTED],[REDACTED]

TXT Example
text
PHONE OSINT TOOL
Promo Tool Created by VEER

Generated: YYYY-MM-DD HH:MM:SS

mobile  : XXXXXXXXXX
name    : [REDACTED]
fname   : [REDACTED]
address : [REDACTED]
circle  : [API RESPONSE]

🔐 Keep exported reports private. They may contain personal information.
⚙️ How It Works

The application's general workflow:

text
       ┌──────────────────┐
       │    User Input    │
       │  Mobile Number   │
       └────────┬─────────┘
                │
                ▼
       ┌──────────────────┐
       │    Validation    │
       │  Input Cleaning  │
       └────────┬─────────┘
                │
                ▼
       ┌──────────────────┐
       │   API Request    │
       │  HTTP GET Call   │
       └────────┬─────────┘
                │
                ▼
       ┌──────────────────┐
       │   JSON Parsing   │
       │ Response Handling│
       └────────┬─────────┘
                │
                ▼
       ┌──────────────────┐
       │  Pretty Output   │
       │ Colorized Tables │
       └────────┬─────────┘
                │
                ▼
       ┌──────────────────┐
       │  Export Results  │
       │ JSON / CSV / TXT │
       └──────────────────┘

API Configuration

The application uses a third-party API endpoint.

Example format:

text
GET https://your-api-host.example/search?mobile=<number>


The actual endpoint should be configured in the Python application.

Important: A public API can change, become unavailable, impose rate limits, or return inaccurate information. Verify that you are authorized to use the service and that its terms permit your intended use.

📁 Project Structure
text
phone-osint-tool/
│
├── phone_osint.py
├── requirements.txt
├── README.md
├── LICENSE
│
├── output/
│   ├── osint_*.json
│   ├── osint_*.csv
│   └── osint_*.txt
│
└── protected/
    └── obfuscated application files

requirements.txt
text
requests>=2.31.0
colorama>=0.4.6
tabulate>=0.9.0

🔒 Python Script Protection

Want to distribute your Python application without exposing its original source code?

This section explains optional source-code obfuscation and executable packaging.

🤔 Why Obfuscate Python?

Normally, Python scripts are readable:

text
phone_osint.py


Anyone who receives the original source file can open it using a text editor.

Obfuscation transforms the source code into a less readable format, making casual inspection and copying more difficult.

Benefits
🔒 Makes source code harder to read.
🛡️ Helps protect proprietary application logic.
📦 Supports executable distribution.
⚙️ Offers optional licensing features.
💻 Helps prepare applications for commercial distribution.
⚠️ No obfuscation technique can guarantee complete protection against reverse engineering.
📊 Obfuscation Methods
Tool	Main Purpose
PyArmor	Python source-code obfuscation
PyInstaller	Executable packaging
Nuitka	Native compilation
Cython	Compiling Python modules
Base64	Encoding only, not security
Recommended combination

PyArmor + PyInstaller

PyArmor provides code obfuscation.
PyInstaller packages the protected application.
Together, they make casual source inspection more difficult and simplify distribution.
🛠️ Step 1 — Install PyArmor

Install the required packages:

bash
pip install pyarmor pyinstaller


Verify:

bash
pyarmor --version
pyinstaller --version


Official documentation:

PyArmor: https://pyarmor.readthedocs.io/
PyInstaller: https://pyinstaller.org/
🔐 Step 2 — Obfuscate Your Script

Make sure your project contains:

text
phone-osint-tool/
├── phone_osint.py
└── requirements.txt


Run:

bash
pyarmor gen -O obfuscated phone_osint.py


The generated directory contains the protected script and its required runtime files.

Example:

text
obfuscated/
├── phone_osint.py
└── pyarmor_runtime_*/


Test the generated script:

bash
python obfuscated/phone_osint.py


Make sure the application works before packaging it.

📦 Step 3 — Build a Windows Executable

Install PyInstaller if you haven't already:

bash
pip install pyinstaller


Navigate to the obfuscated directory:

bash
cd obfuscated


Build:

bash
pyinstaller --onefile --console --name PhoneOSINT phone_osint.py


Your executable will be generated inside:

text
dist/
└── PhoneOSINT.exe


<details>
<summary>Windows executable build with custom icon</summary>

bash
pyinstaller --onefile --console --name PhoneOSINT --icon=icon.ico phone_osint.py


Make sure icon.ico exists in your current working directory.

</details>

Important
Build and test on the target operating system.
Include required dependencies and runtime components.
Check that the executable can reach its configured API.
Test on a clean machine before distribution.
🐧 Linux & 🍎 macOS

PyInstaller supports Linux and macOS as well.

Build on the operating system for which you want to distribute the executable.

Linux
bash
pyinstaller --onefile --console --name PhoneOSINT phone_osint.py


Run:

bash
./dist/PhoneOSINT

macOS
bash
pyinstaller --onefile --console --name PhoneOSINT phone_osint.py


Run:

bash
./dist/PhoneOSINT

Note: A Windows executable cannot normally be produced by running a standard PyInstaller build on Linux or macOS. Use the appropriate target build environment.
⚡ Alternative: Nuitka

Nuitka compiles Python applications into native executable code.

Installation
bash
pip install nuitka

Build
bash
python -m nuitka --onefile --standalone phone_osint.py

Advantages
Native compilation.
Standalone executable support.
No need to distribute ordinary Python source files.
Potential performance improvements in some applications.
Limitations
Compilation may take longer.
Build dependencies may be required.
Native binaries can still be reverse-engineered.
🛡️ Security Best Practices

Obfuscation is not a substitute for proper application security.

Follow these recommendations:

1. Never Hardcode API Secrets

Avoid:

python
API_KEY = "your-secret-api-key"


Use environment variables or secure server-side configuration instead.

2. Protect Personal Information

Avoid including real people's names, addresses, telephone numbers, or email addresses in public screenshots and repository examples.

3. Use HTTPS

Use secure HTTPS connections when communicating with external services.

4. Keep Dependencies Updated

Regularly update Python libraries and check for known security vulnerabilities.

5. Protect Exported Files

Generated JSON, CSV, and TXT files may contain sensitive information. Do not commit them to a public repository.

Consider adding this to .gitignore:

gitignore
venv/
__pycache__/
*.pyc
output/
build/
dist/
*.spec
.env

6. Don't Trust Client-Side Licensing Alone

If you distribute commercial software, perform important license validation on a server you control. Local validation can be modified or bypassed.

🗺️ Roadmap
Interactive prompt-based input
Mobile number validation
Multi-format export (JSON / CSV / TXT)
Retry handling
Session-based batch lookup
Colorized terminal interface
Python obfuscation documentation
Executable packaging documentation
Improved API configuration
Better rate-limit handling
Web interface
Bulk import with authorization checks
HTML report generation
Docker support
Automated testing
⚠️ Disclaimer

This software is provided "AS IS", without warranties of any kind, express or implied.

The author makes no guarantees regarding:

Third-party API availability.
Accuracy or completeness of returned information.
Compatibility with future API changes.
Uninterrupted application operation.

Users are responsible for ensuring that their activities comply with applicable laws, API terms, and privacy requirements.

The author is not responsible for misuse of this software or any consequences resulting from unauthorized access, disclosure, or processing of personal information.

⚖️ Legal Notice
IMPORTANT — PLEASE READ BEFORE USING THIS SOFTWARE

This project is intended for:

🎓 Educational purposes.
🔬 Authorized security research.
🛡️ Lawful OSINT investigations.
✅ Testing with your own information or information you are explicitly authorized to process.

Phone numbers and associated personal information are sensitive data.

Unauthorized collection, disclosure, or processing of personal information may violate applicable privacy and cybersecurity laws.

Depending on jurisdiction, relevant laws may include:

🇮🇳 Information Technology Act, 2000 (India).
🇮🇳 Digital Personal Data Protection Act, 2023 (India), subject to applicable commencement and rules.
🇪🇺 General Data Protection Regulation (GDPR).
🇺🇸 Computer Fraud and Abuse Act (CFAA), where applicable.

Always obtain appropriate authorization and follow the applicable legal requirements.

📜 License

This project is distributed under the MIT License.

Copyright (c) 2025 VEER

See the LICENSE file for complete license terms.

👤 Author

VEER 🛡️

🐙 GitHub: @B5970
📂 Repository: Phone OSINT Tool
📧 Email: Add your contact email.
💬 Telegram: Add your Telegram username.
⭐ Support the Project

If you find this project useful:

⭐ Star the repository.
🔁 Share it with other developers.
🐛 Report bugs and documentation issues.
💡 Suggest improvements.

Your support helps improve the project!

🚀 Quick Start
bash
git clone https://github.com/B5970/osintgram.git

cd osintgram

pip install -r requirements.txt

python phone_osint.py


<div align="center">

🛡️ PROMO TOOL CREATED BY VEER 🛡️

Built with ❤️ using Python

Protect your code. Respect privacy. Use technology responsibly.

</div>
