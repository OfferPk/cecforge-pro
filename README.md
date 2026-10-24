\# CECForge Pro (v1.0.0)  
\> \*\*HDMI-CEC (Consumer Electronics Control) Protocol Engineering Studio & Wire Timing Analyzer\*\*

\---

\#\# Overview  
\*\*CECForge Pro\*\* is an open-standard protocol engineering studio, frame builder, and single-wire physical timing analyzer designed for smart home systems integrators, television manufacturers, soundbar developers, and custom AV installers working with HDMI Pin 13 Consumer Electronics Control.

\#\#\# Normative Standards Covered:  
\- \*\*HDMI Specification (HDMI 1.4b / 2.0 / 2.1 Section 8 & Supplement 1):\*\*  
  \- Physical Layer: Single-wire open-collector bidirectional bus on HDMI Pin 13 pulled up to \+3.3V with 27k-ohm resistor.  
  \- Bit Timing:  
    \- Start Bit: 3.7 ms low, 4.5 ms total duration.  
    \- Logic 0: 1.5 ms low, 2.4 ms total duration (sampled at 1.05 ms).  
    \- Logic 1: 0.6 ms low, 2.4 ms total duration (sampled at 1.05 ms).  
  \- Block Structure: 10 bits per block (8 data bits MSB first, 1 EOM bit, 1 ACK bit).  
  \- Logical Addressing: 16 addresses (0=TV, 1/2/9=Recording, 3/6/7/10=Tuner, 4/8/11=Playback, 5=Audio System, 15=Broadcast).  
  \- Opcodes: One Touch Play (0x04 Image View On, 0x82 Active Source), System Standby (0x36), System Audio Control (0x70/0x72), Routing Control (0x80/0x86).

\---

\#\# Key Modules  
1\. \*\*Interactive CEC Frame Builder:\*\*  
   \- Assembles standard multi-block CEC frames: Initiator, Destination, Opcode, and Operands.  
   \- Built-in macros for One Touch Play, System Standby, Audio System Volume/Mute, and Poll pings.  
2\. \*\*Binary Frame Dissector & Semantic Analyzer:\*\*  
   \- Dissects colon-delimited or plain hex strings into logical addresses, opcodes, and operands.  
3\. \*\*HDMI Pin 13 Wire Timing Canvas:\*\*  
   \- Interactive waveform visualizer showing Start Bit, Logic 0, and Logic 1 microsecond pulse widths.  
4\. \*\*10-Point Normative CEC Auditor:\*\*  
   \- Validates Start Bit timing, 10-bit block structure, broadcast opcode permissions, and Signal Free Time quiet periods.  
5\. \*\*Standalone Python 3 CLI Suite:\*\*  
   \- \`build/cec-cli.py\`: Production CLI with JSON export for automated AV control scripting.

\---

\#\# Automated Verification  
Run the unit test suite:  
\`\`\`bash  
python3 test\_cec.py  
\`\`\`  
\*Result: 10/10 unit tests passed (100% pass rate).\*

\---

\#\# License  
Commercial Proprietary License (v1.0.0). Built for Smart Home & Pro-AV Engineers.  
