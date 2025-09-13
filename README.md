# DARKWEB_CRAWLER 2.0 - Advanced Dark Web Intelligence Tool

Darkweb_Crawler is an advanced Python-based OSINT (Open-Source Intelligence) tool designed for ethical security research and threat intelligence gathering on the dark web. This tool enables security professionals to safely crawl .onion sites through the Tor network while analyzing content for potential threats and marketplace activities.


---

# Table of Contents

- Overview

- Key Features

- Importance in OSINT & Cybersecurity

- Installation

- Usage

- Requirements

- Configuration

- Output Samples

- Disclaimer & Legal Notice

- Contributing

---

# Key Features

# Feature	                                              Description

- **Anonymized Crawling**:	Routes all traffic through Tor network with regular circuit renewal

- **Threat Detection**:	Multi-level threat classification (High/Medium/Low severity)

- **Marketplace Analysis**:	Categorizes and counts marketplace goods across 5 categories
  
- **Professional Reporting**:	Generates comprehensive PDF reports with executive summaries

- **Stealth Operation**:	Realistic browser headers and randomized delays between requests

- **Content Analysis**: Advanced text analysis using NLTK for keyword detection

- **Multiple Output**: Formats	JSON, CSV, and PDF reporting capabilities
  
- **Resilient Design**:	Retry mechanism with exponential backoff for reliability

---

# Importance in OSINT & Cybersecurity

**DarkCrawler Elite serves critical functions in modern cybersecurity operations**:


- **Threat Intelligence**: Identifies emerging threats, malware, and attack services being advertised on dark web markets

- **Cyber Crime Investigation**: Gathering evidence from hidden services

- **Illicit Marketplace Monitoring**: Tracking illegal goods and services

- **Brand Protection**: Discovers stolen data, credentials, or intellectual property related to your organization

- **Trend Analysis**: Tracks marketplace trends in cybercrime tools and services

- **Early Warning System**: Provides alerts about potential attacks being planned or sold

- **Incident Respons**e: Supports investigations by gathering intelligence about threat actors

- **Compliance Monitoring**: Helps organizations meet regulatory requirements for monitoring dark web threats

---

# Installation

**Prerequisites**

- Python 3.8 or higher

- Tor service installed and running

---

# Step-by-Step Setup

- Create or activate your virtual environment
  
**1. Manual Installation**:

- Follow the link below, copy and install the tool script manually using nano:
 **https://gist.github.com/techenthusiast167/b3882b59ad0ee36c95aaa2291a1b841e**

**2. Install Python dependencies**:

    pip install requests beautifulsoup4 stem fpdf nltk lxml

---

**3. Install and configure Tor**:

    sudo apt update
    sudo apt install tor
    sudo service tor start

---

**4. Verify Tor is running**:

    curl --socks5 localhost:9050 --socks5-hostname localhost:9050 -s https://check.torproject.org/ | cat | grep -m 1 Congratulations | xargs


---

# Custom Configuration

**Edit the script to add target .onion URLs**:

- onion_start_urls = [
    "http://exampleonionaddress1234567890abcdefghijklmnopqrstuvwxyz234567.onion",

---

# Usage

**Basic Execution**

    python3 darkcrawler.py

# Usage Examples

**Example Onion Sites for Testing**

- **Important**: These are examples for educational purposes. Always ensure you have proper authorization before crawling any sites.
Legitimate .onion Sites (Public Services):


onion_start_urls = [
    "http://duckduckgogg42xjoc72x3sjasowoarfbgcmvfimaftt6twagswzczad.onion",  # DuckDuckGo
    "http://www.nytimes3xbfgragh.onion",  # New York Times
    "http://facebookwkhpilnemxj7asaniu7vnjjbiltxjqhye3mhbshg7kx5tfyd.onion",  # Facebook
]



**Research .onion Sites (Require Authorization)**:


**These would require specific research authorization**

onion_start_urls = [
    "http://examplemarketplace76x7g5j.onion",  # Example marketplace
    "http://researchforum5tg6c2.onion",  # Example research forum
    "http://securityblog32vbr3.onion",  # Example security blog
]


---

**Example Outputs**



**JSON Output Example (darkweb_crawl_results.json)**:

{
  "url": "http://examplemarketplace76x7g5j.onion/products",
  "title": "Marketplace Products | Example Marketplace",
  "text": "Welcome to our marketplace. We offer various digital products... Bitcoin: 1A1zP1eP5QGefi2DMPTfTL5SLmv7DivfNa... Credit cards available for purchase...",
  "threats": {
    "high": ["credit card fraud", "stolen data"],
    "medium": ["drugs for sale", "fake documents"],
    "low": ["premium accounts", "bypass security"]
  },
  "marketplace_goods": {
    "digital_goods": {
      "credit cards": 5,
      "accounts": 3
    },
    "fraud": {
      "fake documents": 2
    },
    "drugs": {
      "weed": 0
    },
    "weapons": {
      "firearm": 0
    },
    "services": {
      "hacking": 1
    }
  }
}


---

**CSV Output Example (darkweb_crawl_results.csv)**:

URL	Title	Content	Threats	Marketplace Goods
http://examplemarketplace76x7g5j.onion/products	Marketplace Products	Welcome to our marketplace. We offer various digital products... Bitcoin: 1A1zP1eP5QGefi2DMPTfTL5SLmv7DivfNa... Credit cards available for purchase...	{'high': ['credit card fraud', 'stolen data'], 'medium': ['drugs for sale', 'fake documents'], 'low': ['premium accounts', 'bypass security']}	digital_goods: credit cards(5), accounts(3); fraud: fake documents(2); services: hacking(1)
http://researchforum5tg6c2.onion/discussion	Security Discussions	Latest cybersecurity threats and research discussions... Ransomware detection techniques...	{'high': [], 'medium': ['ransomware'], 'low': ['hacking tutorial']}	services: hacking(2)


---

**PDF Report Example (darkweb_threat_report.pdf)**

**Page 1: Cover Page**

╔══════════════════════════════════════════════════════════════╗
║                  DARKWEB THREAT INTELLIGENCE REPORT         ║
║                                                              ║
║  Generated on: 2024-01-15 14:30:22                          ║
║                                                              ║
║  Tool: DarkCrawler Elite v2.2                               ║
║  Scan Duration: 2 hours, 15 minutes                         ║
║  Pages Crawled: 47                                          ║
║  Threats Detected: 18                                       ║
╚══════════════════════════════════════════════════════════════╝

**Page 2: Executive Summary**

**EXECUTIVE SUMMARY**

This report contains findings from a dark web crawl conducted on 2024-01-15 14:30:22.

Total threats detected: 18
High severity threats: 5
Medium severity threats: 8  
Low severity threats: 5

**MARKETPLACE GOODS OVERVIEW**
Total marketplace goods detected: 42
Digital goods: 18 items detected
Fraud: 12 items detected
Services: 8 items detected
Drugs: 3 items detected
Weapons: 1 item detected

**RECOMMENDATIONS**
1. Review high severity threats immediately with security team.
2. Monitor medium severity threats for potential escalation.
3. Document all marketplace findings for intelligence gathering.
4. Consider law enforcement notification for illegal activities.
5. Implement monitoring for detected marketplace categories.
6. Update security protocols based on threat findings.

---

**Page 3: Detailed Finding Example**

**THREAT FINDING: Marketplace Products | Example Marketplace**

URL: http://examplemarketplace76x7g5j.onion/products

**CONTENT EXCERPT**:
Welcome to our marketplace. We offer various digital products... 
Bitcoin: 1A1zP1eP5QGefi2DMPTfTL5SLmv7DivfNa... 
Credit cards available for purchase... 
Database leaks... Premium accounts...

**IDENTIFIED THREAT**S:
HIGH severity threats:
- credit card fraud
- stolen data

**MEDIUM severity threats**: 
- drugs for sale
- fake documents

**LOW severity threats**:
- premium accounts  
- bypass security

**MARKETPLACE GOODS ANALYSIS**:
Digital Goods:
- credit cards (found 5 times)
- accounts (found 3 times)

**Fraud**:
- fake documents (found 2 times)

**Services**:
- hacking (found 1 time)

---

**Page 4: Statistical Analysis**

**STATISTICAL ANALYSIS**

**THREAT DISTRIBUTION**:
High Severity: 28% (5/18)
Medium Severity: 44% (8/18) 
Low Severity: 28% (5/18)

**TOP THREAT CATEGORIES**:
1. Financial Fraud: 6 occurrences
2. Data Theft: 4 occurrences  
3. Illegal Services: 3 occurrences
4. Drug-related: 3 occurrences
5. Weapon-related: 2 occurrences

**MARKETPLACE CATEGORY DISTRIBUTION**:
Digital Goods: 43% (18/42)
Fraud: 29% (12/42)
Services: 19% (8/42)
Drugs: 7% (3/42)
Weapons: 2% (1/42)

**CRYPTO CURRENCY FINDINGS**:
Bitcoin addresses detected: 3
Payment requests identified: 5

---

**Page 5: Action Plan**

**ACTION PLAN & NEXT STEPS**

**IMMEDIATE ACTIONS (0-24 hours)**:
- [ ] Review high severity threats with legal team
- [ ] Notify financial institutions about credit card findings
- [ ] Document all cryptocurrency addresses for tracking
- [ ] Isolate and analyze any discovered data samples

**SHORT-TERM ACTIONS (1-7 days)**:
- [ ] Enhance monitoring for detected threat patterns
- [ ] Update security controls based on findings
- [ ] Conduct threat intelligence sharing with partners
- [ ] Implement additional dark web monitoring

**LONG-TERM STRATEGY (1-4 weeks)**:
- [ ] Develop comprehensive dark web monitoring program
- [ ] Establish formal incident response procedures
- [ ] Create ongoing threat intelligence reporting
- [ ] Implement regular dark web assessment schedule

**CONTACT INFORMATION**:
Security Team: security@yourcompany.com
Incident Response: ir@yourcompany.com  
Legal Department: legal@yourcompany.com
Law Enforcement Liaison: le@yourcompany.com

---

# Real-World Use Case Example

**Scenario: A financial institution suspects customer data has been compromised and is being sold on dark web marketplaces**.

**DarkCrawler Implementation**:

**Target specific marketplace sections**

onion_start_urls = [
    "http://knownmarketplace76x7g5j.onion/credit-cards",
    "http://knownmarketplace76x7g5j.onion/data-dumps",
    "http://knownmarketplace76x7g5j.onion/bank-accounts"
]

**Add company-specific keywords to watch for**
DANGEROUS_KEYWORDS['high'].extend([
    'yourbankname', 
    'yourbank customers',
    'yourbank database'
])

---

# Expected PDF Report Output:

- Executive summary highlighting data breach evidence

- Specific pages where company data was found

- Bitcoin addresses used for transactions

- Recommended immediate actions for customer protection

- Legal documentation for law enforcement engagement

**The PDF report becomes crucial evidence for incident response, regulatory compliance reporting, and law enforcement engagement.**

---

# System Requirements

- Tor service running on port 9050

- 4GB RAM minimum (8GB recommended for large crawls)

- 5GB free disk space for data storage

- Stable internet connection

---

# Configuration

**Tor Control Setup (Optional)**

**For advanced anonymity with circuit renewal**:

- **1. Edit Tor configuration file (/etc/tor/torrc or torrc in Tor Browser directory)**

- **2. Add the following line**:


- **ControlPort 9051
HashedControlPassword 16:872860B76453A77D60CA2BB8C1A7042072093276A3D701AD684053EC4C**

---

- **3. Restart Tor service**

- **Set the password in the script: TOR_CONTROL_PASSWORD = "your_password"**

**Customization Options**:

- Adjust CRAWL_DELAY for rate limiting

- Modify MAX_DEPTH and MAX_PAGES for crawl scope

- Update threat keywords in DANGEROUS_KEYWORDS

- Add marketplace categories in MARKETPLACE_CATEGORIES

---

# Output Samples

**The tool generates three types of outputs**:

 **1. JSON File**: Complete structured data of all crawled content

**2. CSV File**: Summary data for analysis in spreadsheet applications

**3. PDF Report**: Professional threat intelligence report with:

**Executive summary**

- Threat severity analysis

- Marketplace goods categorization

- Detailed findings per page

- Recommendations for action

---

# Disclaimer & Legal Notice

**This tool is designed for ethical security research and authorized penetration testing only.**


- **Legal Compliance**: Ensure you have proper authorization before using this tool

- **Jurisdictional Laws**: Dark web crawling may be illegal in some countries

- **Unauthorized Use**: Do not use this tool against sites you don't own or have permission to test

- **Data Handling**: Properly secure any collected data according to privacy regulations

- **Risk Awareness**: Dark web environments contain potentially harmful content

 I am not responsible for misuse of this tool. Users assume all legal responsibility for their actions.

 ---

# Contributing

 **I welcome contributions to enhance DarkCrawler**:

- Fork the repository

- Create a feature branch (git checkout -b feature/amazing-feature)

- Commit your changes (git commit -m 'Add amazing feature')

- Push to the branch (git push origin feature/amazing-feature)

- Open a Pull Request

---

# Areas for Contribution

- Additional output formats

- Enhanced stealth techniques

- Machine learning for threat classification

- Graphical user interface

- Integration with threat intelligence platforms




- - - 
- - - 

# DarkCrawler V2:1


# Table of Contents

- Features
- Installation
- Usage
- GUI
- Important note 

- - - 

# Features

- **Anonymized Crawling**: Routes all traffic through Tor network
  
- **Threat Detection**: Identifies dangerous content with severity levels
  
- **Marketplace Analysis**: Categorizes illicit goods and services
  
- **Multi-format Reporting**: JSON, CSV, and professional PDF reports
  
- **GUI Dashboard**: Interactive threat intelligence interface

- **Content Analysis**: Advanced text processing with NLTK

- **Stealth Operation**: Randomized delays and circuit renewal

- - - 

# Installation

**Prerequisites**

- Python 3.8+

- Tor service installed and running


- Create or activate your virtual environment

**Install Python Packages**:

    pip3 install requests beautifulsoup4 stem nltk fpdf feedparser lxml

**Manual Installation**:

- Follow the link below, copy and install the tool script manually using nano:

**https://gist.github.com/techenthusiast167/63ed3e74ad5cec0ad0a62d932d8a3b70**


**Start Tor service**:

    Refer to version 2:0 above for support on how to configure Tor


**Configure Target URLs**:

Edit the **onion_start_urls** list in the main function with actual .onion addresses - Or refer to the V2:0 above for clarification. 


# Usage

**Basic Command Line**:


    python3 darkcrawler.py


# GUI Usage

**The interactive GUI provides**:

- **Dashboard Overview**: Summary of findings and threat levels

- **Results Browser**: Navigate through crawled pages with threat assessment

- **Detailed Analysis**: View content excerpts and threat classifications

- **New Scan Interface**: Configure and launch new crawls

- **Threat Intelligence Feed**: Latest cybersecurity news integration


# GUI Features:

- Color-coded threat severity (High/Medium/Low)

- Marketplace goods categorization
One-click export functionality

- Interactive results filtering
Real-time scan progress monitoring



# Important Note:

- Maintain Tor anonymity best practices

- Ensure Tor is properly installed and running

- Verify all dependencies are installed correctly



For additional support, do well to reach out via my email address: preciousvincentct@gmail.com
