# Dark_Crawler

**Professional Dark Web Intelligence Platform for Ethical Security Research**

**Version 3 | Enhanced with Marketplace Analysis | Cyber Threat Intelligence Team**


# Table of Contents

- Overview

- Features

- Installation

- Quick Start

- Usage Guide

- Configuration

- Output Formats

- Legal & Ethical Guidelines

- Troubleshooting

- Contributing

- Disclaimer


# Overview

**Dark_Crawler** - is an advanced, stealthy Python-based dark web intelligence platform designed for authorized security professionals and ethical researchers. The tool provides comprehensive dark web crawling capabilities with integrated threat detection, marketplace analysis, and professional reporting features.

Built with privacy and security in mind, **Dark_Crawler** routes all traffic through the Tor network while maintaining operational security standards suitable for sensitive intelligence gathering operations.


# Features

### Core Capabilities

- **Tor Network Integration**: Full anonymity through SOCKS5 proxy routing

- **Stealth Crawling**: Realistic browser headers and intelligent rate limiting

- **BFS Algorithm**: Breadth-first search crawling with configurable depth

- **Multi-format Output**: JSON, CSV, and professional PDF reporting

- **Error Handling**: Robust retry mechanisms with exponential backoff



# Threat Intelligence

- **Three-tier Threat Detection**: High/Medium/Low severity classification

- **Marketplace Analysis**: Automated categorization of illicit goods

- **Pattern Recognition**: Email, phone, cryptocurrency, and credit card detection

- **Content Filtering**: Blacklisted paths and intelligent content parsing


# Analytics & Reporting

- **Comprehensive PDF Reports**: Executive summaries with threat assessments

- **Marketplace Statistics**: Categorized goods analysis with frequency counts

- **Visual Threat Metrics**: Color-coded severity indicators in console output

- **Export Flexibility**: Multiple format support for integration with other tools



# Operational Features

- **Command-line Interface**: Intuitive CLI with comprehensive help system

- **Batch Processing**: Support for URL lists from files

- **Custom Configuration**: Adjustable crawl parameters and output directories

- **Tor Circuit Management**: Automatic identity renewal for enhanced anonymity




# Installation

### Prerequisites

- Python 3.8+

- Tor Browser or Tor Service running on port 9050

- Administrative privileges (for some operating systems)


# Step 1: Manual Installation

- Visit the link below to get the script, then use nano to install it:

**https://gist.github.com/techenthusiast167/e347cd8cfc9de86970b7edf481272ad7**

### Step-by-Step:

- Click on the link below to access the script

- Copy the script content

- Use nano to create and install the tool


# Step 2: Install Dependencies

    pip install requests beautifulsoup4 stem nltk lxml Pillow

# Step 3: Configure Tor

**Ensure Tor is running and accessible**:

# Check Tor service status

    sudo systemctl status tor

# OR start Tor service

    sudo systemctl start tor


# Step 4: Verify Installation

    python darkcrawler.py -h


# Quick Start

**Basic Crawl (Single URL)**


    python darkcrawler.py -u http://example.onion

# Comprehensive analysis with images

    python darkcrawler.py -u http://marketplace.onion --images --all

# JSON only

    python darkcrawler.py -u http://marketplace.onion --json

# CSV only

    python darkcrawler.py -u http://marketplace.onion --csv

# Image-only mode

    python darkcrawler.py -u http://marketplace.onion --images-only

# OR 

    python darkcrawler.py -u http://marketplace.onion --images-only --no-tor-check




# Advanced Crawl with Full Reporting


    python darkcrawler.py -u http://example.onion -d 3 -p 50 --all -o ./reports/


# Batch Processing from File

# Create target list

- echo "http://marketplace1.onion" > targets.txt
- echo "http://forum1.onion" >> targets.txt

# Run batch analysis

    python darkcrawler.py -f targets.txt --images --all -o ./weekly_report/

# Image-Only Evidence Collection

    python darkcrawler.py -u http://marketplace.onion --images-only --image-extensions jpg,png --max-images 50


# Usage Guide


**Command Line Options**


**Option	Short	Description	Default**

--help	-h	Show comprehensive help message	N/A

--url	-u	Single .onion URL to crawl	Required

--file	-f	File containing .onion URLs (one per line)	Required

--depth	-d	Maximum crawl depth	3

--pages	-p	Maximum pages per site	50

--output	-o	Output directory for reports	Current directory

--no-tor-check		Skip Tor connection verification	False

--json		Generate JSON output only	False

--csv		Generate CSV output only	False

--pdf		Generate PDF threat report only	False

--all		Generate all report formats	False


**At least one of --url or --file must be provided**.




# Examples

**Example 1: Basic Intelligence Gathering**


    python darkcrawler.py -u http://examplemarketplace.onion -d 2 -p 25


**Example 2: Comprehensive Threat Assessment**


    python darkcrawler.py -f high_value_targets.txt --all -o /var/reports/threat_intel/




**Example 3: Stealth Operations (No Tor Check)**


    python darkcrawler.py -u http://target.onion --no-tor-check --csv


**Example 4: Academic Research Configuration**


    python darkcrawler.py -u http://academic.onion -d 1 -p 10 --json --output ./research_data/


# URL File Format

**Create a text file with one .onion URL per line**:

# Example targets.txt

http://firsttarget.onion
http://secondtarget.onion
http://commentedout.onion


# Configuration

**Customizing Threat Keywords**

Modify the **DANGEROUS_KEYWORDS** dictionary in the script to add custom threat indicators:

DANGEROUS_KEYWORDS = {
    'high': [
        'your_custom_threat',
        'organization_specific_indicators',
        # Add more high-severity keywords
    ],
    'medium': [
        # Medium severity indicators
    ],
    'low': [
        # Low severity indicators
    ]
}



# Marketplace Categories

**Customize marketplace detection by editing MARKETPLACE_CATEGORIES**:

MARKETPLACE_CATEGORIES = {
    'custom_category': [
        'keyword1',
        'keyword2',
        # Add category-specific keywords
    ]
}



# Crawl Parameters

**Adjust operational parameters for different scenarios**:

**Parameter	Description	Recommended Value**
  
- **CRAWL_DELAY	**Seconds between requests	5-10 seconds
  
- **MAX_DEPTH** Maximum crawl depth	2-3 for stealth
  
- **MAX_PAGES**	Maximum pages per site	20-100 based on target
  
- **RETRY_COUNT**	HTTP retry attempts	3
  
- **BACKOFF_FACTOR** Exponential backoff	4



# Output Formats

**1. JSON Output (darkweb_crawl_results.json)**

{
  "url": "http://target.onion/page",
  "title": "Page Title",
  "text": "Extracted content...",
  "threats": {
    "high": ["keyword1"],
    "medium": ["keyword2"],
    "low": []
  },
  "marketplace_goods": {
    "drugs": {"cocaine": 3},
    "weapons": {"firearm": 1}
  }
}



**2. CSV Output (darkweb_crawl_results.csv)**

**URL	- Title	- Content	- Threats	- Marketplace - Goods**


**3. PDF Threat Report (darkweb_threat_report.pdf)**

**Professional PDF report containing**:

- Executive summary

- Threat statistics

- Marketplace analysis

- Detailed findings

- Recommendations


# Legal & Ethical Guidelines

**Authorized Use Only**

**DarkCrawler Elite is designed EXCLUSIVELY for**:

- Authorized penetration testing

- Security research with proper authorization

- Academic studies with institutional approval

- Corporate threat intelligence with legal clearance

- Law enforcement investigations with appropriate warrants


$ Strict Prohibitions

**NEVER use this tool for**:

- Unauthorized access to systems

- Violation of terms of service

- Illegal surveillance

- Personal vendettas or harassment

- Accessing illegal content



# Compliance Requirements

- Obtain Written Authorization before testing any target

- Document All Activities with timestamps and purposes

- Respect Rate Limits to avoid denial of service

- Report Discovered Vulnerabilities responsibly

- Destroy Sensitive Data after authorized retention periods




# Troubleshooting

**Common Issues & Solutions**

**Issue**: Tor Connection Failed


[WARNING] Tor test failed: Connection refused



# Solution:

# Ensure Tor is running

    sudo systemctl start tor
    
# OR open Tor Browser

# Verify port 9050 is listening

    netstat -tulpn | grep 9050


**ssue**: SSL Certificate Errors


[ERROR] SSL: CERTIFICATE_VERIFY_FAILED

**Solution**:

# Update certificates

    sudo update-ca-certificates
    
# OR run with relaxed SSL (NOT RECOMMENDED for production)

# Modify script to use verify=False (security implications apply)




**Issue**: Memory Consumption High


MemoryError during large crawls

**Solution**:


# Reduce crawl parameters

    python darkcrawler.py -u http://target.onion -d 1 -p 20
    
# Increase system swap space

# Use --csv instead of --all for memory efficiency



**Issue**: Rate Limiting Detected

429 Too Many Requests


**Solution**:


- Increase CRAWL_DELAY in script

- Use --depth 1 to reduce crawl intensity

- Implement rotating user agents (advanced)




# Performance Optimization

**Scenario	Recommended Settings**

- Stealth Operations	-d 1 -p 10 with 10s delay
  
- Comprehensive Analysis	-d 3 -p 100 with 5s delay
  
- Batch Processing	-d 2 -p 30 with 7s delay



# Contributing

**We welcome responsible contributions from security professionals**:

**Contribution Guidelines**

- **Security First**: All contributions must maintain operational security

- **Code Review**: Submit pull requests for review

- **Testing**: Include tests for new features

- **Documentation**: Update relevant documentation

- **Ethical Standards**: Adhere to the tool's ethical guidelines


# Reporting Issues

**Use GitHub Issues to report**:


- Security vulnerabilities (privately)

- Feature requests

- Bug reports

- Documentation improvements



# Disclaimer

**IMPORTANT LEGAL NOTICE**

This tool is provided for educational purposes and authorized security research only. The developers assume NO LIABILITY for misuse of this software. Users are SOLELY RESPONSIBLE for:

- Ensuring they have proper authorization for all activities

- Complying with local, national, and international laws

- Protecting operational security and intelligence sources

- Ethical handling of collected information

- Proper disposal of sensitive data


### By using this tool, you acknowledge that:

- You have read and understand all legal disclaimers

- You accept full responsibility for your actions

- You will use this tool only for lawful purposes

- You have obtained necessary legal permissions


# DarkCrawler Elite | Professional Dark Web Intelligence Platform

**For Authorized Security Research Only | Use Responsibly**

**Report Security Issues | Documentation | Contributing**




- - - 
- - - 

# DarkCrawler V2


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


---

**Darkweb Onion URLs**:

- Decode the hex to get the oinion urls for testing:

68 74 74 70 3a 2f 2f 77 62 7a 32 6c 72 78 68 77 34 64 64 37 68 35 74 32 77 6e 6f 63 7a 6d 63 7a 35 73 6e 6a 70 79 6d 34 70 72 37 64 7a 6a 6d 61 68 34 76 69 36 79 79 77 6e 33 37 62 64 79 64 2e 6f 6e 69 6f 6e 2f 0a 0a 68 74 74 70 3a 2f 2f 69 77 67 67 70 79 78 6e 36 71 76 33 62 32 74 77 70 77 74 79 68 69 32 73 66 76 67 6e 62 79 32 61 6c 62 62 63 6f 74 63 79 73 64 35 66 37 6f 62 72 6c 77 62 64 62 6b 79 64 2e 6f 6e 69 6f 6e 2f 0a 0a 68 74 74 70 3a 2f 2f 73 67 61 35 6e 37 7a 78 36 71 6a 74 79 37 75 77 76 6b 78 70 77 73 74 79 6f 68 37 33 73 68 73 74 36 6d 78 33 6f 6b 6f 75 76 35 33 75 6b 73 37 6b 73 34 37 6d 73 61 79 64 2e 6f 6e 69 6f 6e 2f 0a
