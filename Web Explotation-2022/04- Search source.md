# Search source
The developer of this website mistakenly left an important artifact in the website source, can you find it?The website is [here](http://saturn.picoctf.net:50761/)

#### Hints
- How could you mirror the website on your local machine so you could use more powerful tools for searching?

### Solution
```bash
/** banner_main picoCTF{1nsp3ti0n_0f_w3bpag3s_ec95fa49} **/
 .carousel-indicators li {
     width: 20px;
     height: 20px;
     border-radius: 11px;
     background-color: #070000;
```

