## library of html for Encoding the input which the user enter it 

دي مكتبة مدمجة في بايثون علشان تتعامل مع النصوص اللي فيها HTML.

أهم دالة فيها: html.escape()

بتحول < → &lt;

> → &gt;

& → &amp;
                                                                                                                                     
```python
import html

# Example input that contains XSS payload
user_input = "<script>alert(1)</script>"

# Encode it safely
safe = html.escape(user_input)
print(safe)  # &lt;script&gt;alert(1)&lt;/script&gt;

