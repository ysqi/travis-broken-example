+++
title = "study golang"
draft = false
date = "2016-11-02T21:01:21+08:00"

+++

你应该去询问 Ysqi ,他写的一段代码
```Go
import fmt 

func main(){
    fmt.Println("Hello Gopher!")
}
```

### Beego

```Go

// show error string as simple text message.
// if error string is empty, show 503 or 500 error as default.
func exception(errCode string, ctx *context.Context) {
	atoi := func(code string) int {
		v, err := strconv.Atoi(code)
		if err == nil {
			return v
		}
		if ctx.Output.Status == 0 {
			return 503
		}
		return ctx.Output.Status
	}

	for _, ec := range []string{errCode, "503", "500"} {
		if h, ok := ErrorMaps[ec]; ok {
			executeError(h, ctx, atoi(ec))
			return
		}
	}
	//if 50x error has been removed from errorMap
	ctx.ResponseWriter.WriteHeader(atoi(errCode))
	ctx.WriteString(errCode)
}
```
