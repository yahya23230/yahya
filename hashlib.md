### library of hashlib for Encrypting the input which the user enter it


مكتبة مسؤولة عن التشفير (hashing).

بتستخدمها علشان تعمل Hash للبيانات (مش للتشفير reversible).

أشهرها: md5, sha256.
لكن يفضل sha256 بدل md5 لأنه أقوى).

```python
import hashlib

password = "mypassword"
hashed = hashlib.md5(password.encode()).hexdigest()
print(hashed)  # e.g. 34819d7beeabb9260a5c854bc85b3e44  
