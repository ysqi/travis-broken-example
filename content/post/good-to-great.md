+++
title = "good to great"
draft = false
date = "2016-11-02T20:42:55+08:00"

+++

I read **Good to Great in January 2016**. An awesome read sharing detailed analysis on how good companies became great.

```html
<section id="main">
  <div>
   <h1 id="title">{{ .Title }}</h1>
        <ul id="list">
            {{ range .Data.Pages }}
                {{ .Render "li"}}
            {{ end }}
        </ul>
  </div>
</section>
```