📱 Phone OSINT Tool — Professional Edition
🛡️ Promo Tool Created by VEER

A professional Python-based Phone Number OSINT utility featuring API-based lookups, interactive terminal results, batch processing, and automatic JSON, CSV, and TXT exports.

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
Roadmap
Disclaimer
Legal Notice
License
Author
🧭 About

Phone OSINT Tool is a lightweight command-line application designed for authorized OSINT research, cybersecurity education, and legitimate security investigations.
The application accepts an Indian mobile number and sends a lookup request to a configured third-party API.

Depending on the API response, the tool may display:

📱 Mobile number
👤 Owner name (if returned by the API)
👨 Father's name (if returned by the API)
🏠 Address (if returned by the API)
☎️ Alternate contact (if returned by the API)
📡 Telecom circle / operator
🆔 API-provided identifier
📧 Associated email (if returned by the API)

The application features an interactive terminal interface, making it easy to use without complicated command-line arguments.

⚠️ Use this application only with numbers you own or are explicitly authorized to investigate.

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
⚡ Simple Setup	Easy installation and configuration


📸 Screenshots

Example terminal interface:

text
╔══════════════════════════════════════════════════════════════╗
║                  📱 PHONE OSINT TOOL                         ║
║                    Professional Edition                      ║
║                  Promo Tool Created by VEER                  ║
╚══════════════════════════════════════════════════════════════╝

➤ Enter mobile number (or 'q' to quit): XXXXXXXXXX

⏳ Searching...

══════════════════════════════════════════════════════════════
                      🔍 LOOKUP RESULTS
══════════════════════════════════════════════════════════════

📱 Mobile       : XXXXXXXXXX
👤 Name         : [REDACTED]
🏠 Address      : [REDACTED]
📡 Operator     : [API RESPONSE]
📧 Email        : [REDACTED]

══════════════════════════════════════════════════════════════

✔ Lookup completed successfully

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


Step 1 — Clone the Repository
bash

git clone https://github.com/B5970/osintgram.git
cd osintgram

Step 2 — Create a Virtual Environment (Recommended)

Linux / macOS
bash
python3 -m venv venv
source venv/bin/activate


Windows

bash
python -m venv venv
venv\Scripts\activate

Step 3 — Install Dependencies
bash
pip install -r requirements.txt


Alternatively:

bash
pip install requests colorama tabulate

🚀 Usage
Start the Application
bash
python phone_osint.py

Interactive Example
text
➤ Enter mobile number (or 'q' to quit): XXXXXXXXXX

⏳ Searching...

✔ Lookup completed successfully

↻ Do another lookup? (y/N): y

➤ Enter mobile number (or 'q' to quit): XXXXXXXXXX

↻ Do another lookup? (y/N): n

Accepted Input Formats
Input	Expected Behavior
XXXXXXXXXX	10-digit Indian mobile number
+91XXXXXXXXXX	International prefix
91XXXXXXXXXX	Country code
XXXXX-XXXXX	Formatting characters cleaned
12345	Invalid length
1234567890	Invalid starting digit
Exit the Application

Type:

text
q
quit
exit


Or press Ctrl+C.

📂 Output & Exports

The application automatically saves session results inside the output/ directory.

Generated Files
text
output/
│
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

🔐 Keep exported reports private. They may contain sensitive personal information.
⚙️ How It Works

The application follows this general workflow:

text
       ┌─────────────────────┐
       │      User Input     │
       │    Mobile Number    │
       └──────────┬──────────┘
                  │
                  ▼
       ┌─────────────────────┐
       │     Validation      │
       │    Input Cleaning   │
       └──────────┬──────────┘
                  │
                  ▼
       ┌─────────────────────┐
       │     API Request     │
       │      HTTP GET       │
       └──────────┬──────────┘
                  │
                  ▼
       ┌─────────────────────┐
       │    JSON Parsing     │
       │  Response Handling  │
       └──────────┬──────────┘
                  │
                  ▼
       ┌─────────────────────┐
       │    Pretty Output    │
       │  Colorized Tables   │
       └──────────┬──────────┘
                  │
                  ▼
       ┌─────────────────────┐
       │   Export Results    │
       │   JSON / CSV / TXT  │
       └─────────────────────┘

API Configuration

The application communicates with a configured third-party API.

Example endpoint format:

text
GET https://your-api-host.example/search?mobile=<number>


The actual API endpoint must be configured in the Python application.

Important:

Third-party APIs may change or become unavailable.
API providers may enforce request limits.
Returned information may be inaccurate or incomplete.
Always follow the API provider's terms and applicable privacy laws.
📁 Project Structure
text
phone-osint-tool/
│
├── phone_osint.py          # Main application
├── requirements.txt        # Python dependencies
├── README.md               # Project documentation
├── LICENSE                 # MIT License
│
└── output/                 # Generated reports
    ├── osint_*.json
    ├── osint_*.csv
    └── osint_*.txt

requirements.txt
text
requests>=2.31.0
colorama>=0.4.6
tabulate>=0.9.0

🗺️ Roadmap
Interactive prompt-based input
Mobile number validation
Multi-format export (JSON / CSV / TXT)
Retry handling
Session-based batch lookup
Colorized terminal interface
Improved API configuration
Better rate-limit handling
Web interface (Flask / FastAPI)
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

The author is not responsible for misuse of this software or consequences resulting from unauthorized access, disclosure, or processing of personal information.

⚖️ Legal Notice
⚠️ IMPORTANT — PLEASE READ BEFORE USING THIS SOFTWARE

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

Always obtain appropriate authorization and follow applicable legal requirements.

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
"Promo Tool Created by VEER — Built with ❤️ for the OSINT community."
⭐ Support the Project

If you find this project useful:

⭐ Star the repository.
🔁 Share it with other developers.
🐛 Report bugs and documentation issues.
💡 Suggest improvements.

Your support motivates continued development!

🚀 Quick Start
bash
git clone https://github.com/B5970/osintgram.git

cd osintgram

pip install -r requirements.txt

python phone_osint.py


<p align="center">

🛡️ PROMO TOOL CREATED BY VEER 🛡️

Built with ❤️ using Python

Stay ethical. Respect privacy. Use responsibly.

</p>
