# ParsEVTX: Simplifying EVTX Analysis

**Workshop:** FSEC-SS Pre BOH Workshop  
**Host:** Eric Hendryani (Cofastic)

## Overview

This repository contains materials and resources for the **ParsEVTX** workshop, focused on simplifying Windows Event Log (EVTX) analysis for digital forensics and incident response investigations. Learn how to efficiently parse and analyze EVTX files using Eric Zimmerman's powerful tools: **EvtxECmd** and **Timeline Explorer**.

## Why This Workshop?

Traditional Event Viewer becomes extremely slow with large log files and can only display one log at a time. This workshop teaches you how to:

- Convert all EVTX files into a single CSV file in minutes using EvtxECmd
- Analyze events in Timeline Explorer with powerful filtering and search capabilities
- Work across all logs simultaneously instead of one at a time
- Transform investigations from hours/days of manual work into just minutes of efficient analysis

## What Are EVTX Files?

EVTX files are Windows Event Log files that store event records in a structured binary format. Unlike normal text files, they require special applications (Event Viewer or EvtxECmd) to parse and read their contents.

### Windows EVTX Categories

**System**  
Captures events related to Windows components like drivers, system services, and hardware issues.

**Security**  
Tracks authentication events, login attempts, file access, and other security-related activities (requires enabled auditing policies).

**Application**  
Records events from installed programs and software applications.

**Operational**  
Provides detailed diagnostic information for specific Windows features and services.

## Tools Covered

### EvtxECmd

A command-line tool created by Eric Zimmerman for parsing Windows Event Log files into CSV format for analysis.

**Key Commands:**

```bash
# Converting Single EVTX File Into CSV
EvtxECmd.exe -f "location of .evtx file" --csv "output location" --csvf Filename.csv

# Converting ALL EVTX Files In A Directory Into A Single CSV
EvtxECmd.exe -d "directory location" --csv "output location" --csvf Filename.csv

# Filtering To Include Only Specific Event IDs In CSV Output
EvtxECmd.exe -d "directory location" --csv "output location" --csvf Filename.csv --inc "eventid"
```

**Pro Tip:** Redirect output to a text file for easier analysis by adding `> filename.txt` at the end of your command.

### Timeline Explorer

A digital forensics tool that analyzes event logs by organizing them into chronological timelines. It works perfectly with EvtxECmd by importing the CSV files, making event log analysis fast and efficient.

**Key Features:**
- Chronological timeline organization
- Powerful filtering and search capabilities
- Helps identify suspicious activities and security incidents
- Efficient analysis across multiple logs simultaneously

## What You'll Learn

1. Understanding Windows Event Log structure and EVTX file formats
2. Parsing EVTX files efficiently using EvtxECmd
3. Analyzing parsed logs with Timeline Explorer
4. Understanding and working with Event IDs
5. Identifying suspicious activities and security incidents
6. Utilizing AI (like ChatGPT) to enhance your analysis workflow
7. Practical incident response techniques through hands-on challenges

## Event IDs

Event IDs are unique numerical identifiers assigned to specific types of events recorded in Windows Event Logs. Each Event ID corresponds to a particular action or occurrence in the system.

When you parse EVTX files, EvtxECmd provides a count of each Event ID occurrence, which you can use to prioritize your investigation.

## Utilizing AI in Your Analysis

### AI-Enhanced Workflow

When analyzing EVTX files, you can leverage AI to work more efficiently:

1. Parse your EVTX files using EvtxECmd (redirect output to a text file)
2. Copy the Event ID counts into an AI tool like ChatGPT
3. Ask which Event IDs to prioritize based on your investigation goals

### Suggested AI Prompt

```
"Based on the provided text file, classify each Event ID and briefly explain what type of event each one corresponds to. Additionally, identify which Event ID is the most significant or worth investigating further in relation to the given challenge description: [insert challenge description here]."
```

**Note:** Make sure to attach the text file containing the output from EvtxECmd's EVTX to CSV conversion.

## Prerequisites

- Basic understanding of Windows operating systems
- Familiarity with command-line interfaces
- Interest in digital forensics or incident response
- Windows machine (or VM) for running the tools

## Getting Started

1. Clone this repository
2. Download EvtxECmd and Timeline Explorer from [Eric Zimmerman's Tools](https://ericzimmerman.github.io/)
3. Follow along with the workshop materials
4. Practice with the provided sample EVTX files
5. Complete the hands-on challenges

## About Eric Zimmerman - The DFIR Goat! 🐐

Eric Zimmerman is widely considered one of the most influential contributors in Digital Forensics and Incident Response (DFIR). He is:

- A SANS Institute instructor teaching FOR508: Advanced Digital Forensics, Incident Response and Threat Hunting
- Former FBI Special Agent
- Two-time winner of the SANS DFIR NetWars Tournament (2014, 2015)
- Creator of world-class, open-source forensic tools including:
  - EvtxECmd
  - Timeline Explorer
  - Registry Explorer
  - ShellBags Explorer
  - And many more!

## Resources

- [Eric Zimmerman's Tools](https://ericzimmerman.github.io/)
- [EvtxECmd GitHub Repository](https://github.com/EricZimmerman/evtx)
- [SANS FOR508 Course](https://www.sans.org/cyber-security-courses/advanced-incident-response-threat-hunting-training/)
- [Windows Event Log Reference](https://docs.microsoft.com/en-us/windows/security/threat-protection/auditing/audit-policy-recommendations)

## Workshop Structure

- Hands-on demonstrations and tutorials
- Real-world log analysis scenarios
- Practical challenges to test your skills
- AI-enhanced analysis techniques

**Note:** This workshop is for educational purposes. Always ensure you have proper authorization before analyzing systems or logs that don't belong to you.

**Ready to simplify your EVTX analysis? Let's get started! 🚀**
