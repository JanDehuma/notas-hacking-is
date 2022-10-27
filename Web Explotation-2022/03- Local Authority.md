# Local Authority
Can you get the flag?Go to this [website](http://saturn.picoctf.net:49699/) and see what you can discover.

#### Hints
- How is the password checked on this website?

### Solution
```bash
<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<meta http-equiv="X-UA-Compatible" content="ie=edge">

<link rel="stylesheet" href="[style.css](http://saturn.picoctf.net:49699/style.css)">

<title>Login Page</title>

</head>

<body>

<script src="[secure.js](http://saturn.picoctf.net:49699/secure.js)"></script>
```

```bash
  
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}
```