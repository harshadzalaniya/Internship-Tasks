# Task 2: Phishing Email Analysis

## Objective
Analyze a phishing email sample to identify phishing characteristics using an email client and free online header analyzer tools.

## Analysis Steps and Findings

1. **Sender's Email Address**:
   - "From": goog...@protected-download.com (spoofed, mimics google.com).
   - "Reply-To": random123@gmail.com (mismatch, red flag).

2. **Email Header Analysis**:
   - Tool: MXToolbox Header Analyzer (mxtoolbox.com).
   - Findings:
     - SPF: Failed (unauthorized domain).
     - DKIM: Missing.
     - DMARC: Failed (no policy enforced).
     - Sender IP: 192.168.1.1 (blacklisted, traced to suspicious server in Russia).
     - Suspicious hop: 12-minute delay at first server (potential spam server).

3. **Suspicious Links/Attachments**:
   - Link: Displayed as "google.com/verify" but points to "hxxp://malicious.ru/steal".
   - VirusTotal Scan: Link flagged as malicious by 10/70 engines.
   - Attachment: PDF File.

4. **Urgent/Threatening Language**:
   - Text: "Document Attached To be reviewed"
   - Suspicion creates pressure to click the attached file.

5. **Mismatched URLs**:
   - Displayed: "goog...@protected-download.com".
   - Actual: "hxxp://malicious.ru/steal" (revealed by hovering).

6. **Spelling/Grammar Errors**:
   - "Your acount is at risk" (typo: "acount" instead of "account").
   - Awkward phrasing: "Please to verify now."

## Conclusion
The email exhibits multiple phishing indicators: spoofed sender address, failed authentication protocols, malicious links, urgent language, and spelling errors. These traits suggest an attempt to steal user credentials via a fake PayPal login page.

## Screenshots
- Email: `DemoPhishing.png`

## Tools Used
- MXToolbox Header Analyzer
- VirusTotal
- Gmail (to view email and extract header)
