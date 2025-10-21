
# Phishing Email Analysis

Objective

The goal of this task was to analyze a suspicious email and identify phishing indicators.
This exercise helped me understand how attackers craft phishing messages to trick users 
and how to detect red flags in such emails.


# sample phishing email
```
From: "PayPal Support" <support@secure-paypalverify.com>
To: <victim@example.com>
Subject: Urgent: Verify Your Account Immediately

Dear Customer,

We noticed unusual activity in your account. Please verify your information immediately to avoid suspension.  
Click the link below to confirm your identity:  
https://paypal.com.verify-userinfo.net/login  

Thank you,  
PayPal Security Team
```

# Examine sender's email address for spoofing

- Sender’s Email Address
- Claimed sender: PayPal Support
- Actual address: support@secure-paypalverify.com
- Legit PayPal emails come from @paypal.com, not @secure-paypalverify.com.
- Spoofing detected.

# Check email headers for discrepancies (using online header analyzer).

Let's used MXToolbox and Google Admin Toolbox to check header details.
  Result: Email was actually sent from an IP located in Eastern Europe, not the US (where PayPal servers are based).

  Return-Path and SPF record failed validation.

  Header mismatch found — strong indicator of phishing.
  
<img width="1163" height="449" alt="image" src="https://github.com/user-attachments/assets/3977991e-d95a-4357-9bbb-572abd74315f" />

# Identify suspicious links or attachments

  The visible link:``` https://paypal.com.verify-userinfo.net/login```

  Hovering reveals it redirects to ```http://malicious-site.phishtrap.ru/login```

  Domain mimics PayPal using a subdomain trick (paypal.com. inside another domain).
 ~ Phishing link confirmed.

# Look for urgent or threatening language in the email body

  Found Phrases like “verify your information immediately” and “avoid suspension” are classic scare tactics.
  and attackers use urgency to push victims into reacting without thinking.

# Verify presence of spelling or grammar errors..
 found this email contains minor grammar mistakes:

    “verify your information immediately to avoid suspension” → missing punctuation and awkward phrasing.

  Real companies like PayPal maintain strict language standards.

# Summarize phishing traits found in the email

This phishing email clearly demonstrates multiple social engineering techniques — spoofing, urgency, fake links, and technical header manipulation.

  Analyzing this helped me strengthen my awareness of phishing tactics and improve my ability to spot red flags in real-world.

 Lesson Learned: Always double-check sender details, hover over links before clicking, and use email header analyzers to verify authenticity.


 
