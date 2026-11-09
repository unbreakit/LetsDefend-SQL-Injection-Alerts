# LetsDefend Alert: SQL Injection

## SQL Injection

When a web application has fields for user input and is vulnerable to SQL injection, attackers can sometimes pass SQL into those fields and get authenticated without having the correct credentials.

## Alert 1

This alert was generated because the requested URL contained a common SQL Injection payload "OR 1 = 1".


<img width="1190" height="502" alt="Screenshot 2026-11-09 125121" src="https://github.com/user-attachments/assets/4f9fa349-7272-463d-9d19-d57654009595" />

After searching up the source IP address, I found a few entries including the one that generated the alert.  This one is kind of tricky because the attacker used percent encoding so it's harder for analysts to detect.

<img width="1352" height="636" alt="Screenshot 2026-11-09 125544" src="https://github.com/user-attachments/assets/89ba323d-5935-4e6b-841e-73754be1900d" />

After decoding the URL in a decoder, we can see that it indeed held a SQL Injection payload.  However, the response code was 500 so this attack was unsuccessful.

<img width="822" height="422" alt="Screenshot 2026-11-09 125420" src="https://github.com/user-attachments/assets/a62c4d00-8c8e-4713-ad96-49d7bd9b92b0" />


