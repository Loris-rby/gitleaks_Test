git commit -m "test"
Detect hardcoded secrets.................................................Failed
- hook id: gitleaks
- exit code: 1

○
    │╲
    │ ○
    ○ ░
    ░    gitleaks

Finding:     GITHUB_TOKEN=REDACTED
DATABASE_URL=postgr...
Secret:      REDACTED
RuleID:      generic-api-key
Entropy:     5.003258
File:        flag1.txt
Line:        4
Fingerprint: flag1.txt:generic-api-key:4

Finding:     API_KEY=REDACTED
AWS_ACCESS_KEY_ID=A...
Secret:      REDACTED
RuleID:      stripe-access-token
Entropy:     4.175736
File:        flag1.txt
Line:        1
Fingerprint: flag1.txt:stripe-access-token:1

Finding:     AWS_ACCESS_KEY_ID=REDACTED
Secret:      REDACTED
RuleID:      aws-access-token
Entropy:     3.684184
File:        flag1.txt
Line:        2
Fingerprint: flag1.txt:aws-access-token:2

8:56PM INF 1 commits scanned.
8:56PM INF scan completed in 50.1ms
8:56PM WRN leaks found: 3
