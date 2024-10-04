import re

# Step 1: Define Keyword and Link Analysis Functions
def contains_suspicious_keywords(text, keywords):
    for keyword in keywords:
        if re.search(r'\b' + re.escape(keyword) + r'\b', text, re.IGNORECASE):
            return True
    return False

def contains_suspicious_links(text):
    # This is a simplified check; real-world scenarios would require more sophisticated validation
    suspicious_domain_patterns = ['bit.ly', 'tinyurl', 'goo.gl']
    urls = re.findall(r'http[s]?://(?:[a-zA-Z]|[0-9]|[$_@.&+]|[!*\\(\\),]|(?:%[0-9a-fA-F][0-9a-fA-F]))+', text)
    for url in urls:
        if any(domain in url for domain in suspicious_domain_patterns):
            return True
    return False

# Step 2: Simulate Email Input
sample_email = """ 
Dear User, 

We've detected unusual activity in your account. Please verify your account by clicking on the following link: http://bit.ly/fake-url.

Best, 
Your Trusted Bank 
"""

# Step 3: Analyze Email for Phishing
def analyze_email(email_text):
    suspicious_keywords = ['verify your account', 'unusual activity', 'dear user']
    if contains_suspicious_keywords(email_text, suspicious_keywords) or contains_suspicious_links(email_text):
        print("This email is suspicious and might be a phishing attempt.")
    else:
        print("This email does not contain identified phishing indicators.")

if __name__ == "__main__":
    analyze_email(sample_email)
