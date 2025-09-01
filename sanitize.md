## html.escape ( )   prevent from XSS
## re.sub ( )      Replace symbol  to spaces 
### sanitize_input that name of function , you name it anything if you like 
 
   اسم دالة تقدر تسميها زي ما انت عايز .

```python
import re
import html

def sanitize_input(user_input):
   
    cleaned = re.sub(r"[^a-zA-Z0-9\u0600-\u06FF\s@._-]", "", user_input)     # Replace symbol  to spaces 
    return html.escape(cleaned)

print("Enter your name :")
name = sanitize_input(input("Your Name : "))  # for user to  enter your name 
print("Sanitized:", name)

### html.escape prevent from XSS 
# convert      < → &lt;   
# convert      > → &gt;
# convert     & → &amp;
