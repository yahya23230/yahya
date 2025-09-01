## library of html for Encoding the input which the user enter it 

دي مكتبة مدمجة في بايثون علشان تتعامل مع النصوص اللي فيها HTML.

أهم دالة فيها: html.escape( )



```  python
import html

# Example input that contains XSS payload
user_input = "<script>alert(1)</script>"

# Encode it safely
safe = html.escape(user_input)
print(safe)  # &lt;script&gt;alert(1)&lt;/script&gt    ( & → &amp;)   (  > → &gt;  )   ( < → &lt; )


< اتحولت → &lt;

> اتحولت → &gt;

" اتحولت → &quot;


##library of hashlib for e the input which the user enter it
مكتبة مسؤولة عن التشفير (hashing).

بتستخدمها علشان تعمل Hash للبيانات (مش للتشفير reversible).

أشهرها: md5, sha256.
لكن يفضل sha256 بدل md5 لأنه أقوى).

```python
import hashlib

password = "mypassword"
hashed = hashlib.md5(password.encode()).hexdigest()
print(hashed)  # e.g. 34819d7beeabb9260a5c854bc85b3e44   

