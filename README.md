## library of html for Encoding the input which the user enter it 
                                                                                                                                        بتعمل انكودينج للمدخلات اللي اليوزر بيدخلها ##


import html

# Example input that contains XSS payload
user_input = '<script>alert("XSS")</script>'

# Encode it safely
safe_input = html.escape(user_input)

print("Original:", user_input)
print("Escaped:", safe_input)
