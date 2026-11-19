# Member 3 – Message Detection and CSV Import

## 1. Introduction

My responsibility in the Multi-Threaded Threat Detection Desktop Application is implementing message threat detection and CSV file processing.

The objective is to analyze suspicious messages using local rule-based detection and allow users to load multiple inputs from CSV files.

## 2. Implemented Classes

The classes implemented are:

- RiskLevel.java
- ThreatResult.java
- MessageAnalyzer.java
- CsvService.java

## 3. RiskLevel.java

This enum defines four risk levels:

- LOW
- MEDIUM
- HIGH
- NOT_VERIFIED

NOT_VERIFIED is used when an input cannot be evaluated.

## 4. ThreatResult.java

This class stores the result of a threat analysis.

It contains:
- Input: Original message.
- RiskLevel: Detected risk level.
- Score: Accumulated risk score.
- Details: Explanation of detected indicators.

## 5. MessageAnalyzer.java

This class analyzes messages using local detection rules.

It checks for:

1. Urgent language.
2. Account threats.
3. Password and credential requests.
4. Banking information requests.
5. Suspicious links.

Each detected indicator adds points to the total score.

### Risk Classification

- 0–19 points: LOW
- 20–49 points: MEDIUM
- 50 or more points: HIGH
- Empty or null input: NOT_VERIFIED

## 6. CsvService.java

This class reads CSV files from the local computer.

It handles:

- Missing files.
- Incorrect CSV headers.
- Empty inputs.
- Invalid input types.
- Incorrect column counts.
- Unclosed quotation marks.

Invalid rows are marked INVALID and treated as NOT_VERIFIED.

## 7. Testing

Three test classes were created:

- TestMessage.java: Tests message detection.
- TestCsv.java: Tests CSV file reading.
- TestCsvAnalysis.java: Tests CSV reading together with message analysis.

The tests include normal messages, suspicious messages, URLs, empty inputs and invalid rows.

## 8. Current Limitations

- URL analysis is not yet connected.
- Message detection uses simple local rules.
- The CSV parser does not support multiline quoted fields.
- GUI integration and concurrent processing remain part of the complete team application.

## 9. Conclusion

The implemented services provide the foundation for message threat detection and CSV input processing.

The services are separated from the graphical interface, allowing them to be integrated into the complete desktop application.
