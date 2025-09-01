



```python
import re
import html

def sanitize_input(user_input):
   
    cleaned = re.sub(r"[^a-zA-Z0-9\u0600-\u06FF\s@._-]", "", user_input)
    return html.escape(cleaned)

print("Enter your name :")
name = sanitize_input(input("Your Name : "))
print("Sanitized:", name)

# convert      < → &lt;   
convert      > → &gt;
convert     & → &amp;
