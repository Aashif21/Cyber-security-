import re

def check_password_strength(password):
    strength_score = 0
    
    
    if len(password) >= 8:
        strength_score += 1
    if len(password) >= 12:
        strength_score += 1
    
    
    if re.search(r"[A-Z]", password) and re.search(r"[a-z]", password):
        strength_score += 1
    

    if re.search(r"\d", password):
        strength_score += 1
    

    if re.search(r"[@$!%*?&]", password):
        strength_score += 1
    
  passwords (basic example)
    common_passwords = ["123456", "password", "qwerty", "abc123", "password1"]
    if password in common_passwords:
        return "Very Weak (Common Password)"
    

    if strength_score <= 2:
        return "Weak"
    elif strength_score == 3:
        return "Moderate"
    elif strength_score == 4:
        return "Strong"
    else:
        return "Very Strong"

password = input("Enter a password to check its strength: ")
print("Password Strength:", check_password_strength(password))
