---
layout:     post
title:      Converting email to data field value
date:       2017-08-24
categories: [ICO]
lang: en 
permalink: /email-to-data-field/
---

You can use JavaScript converter from this page to convert your email to hex without spaces (and newlines). Or you can use this command in your shell:

```bash
echo -n "example@example.org" | od -A n -t x1 | tr -d '\r\n' | sed "s/ //g"
```

    
{% include tools/emailhex.html %}
