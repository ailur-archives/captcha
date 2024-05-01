> Package captcha provides an easy to use, unopinionated API for captcha generation.

<div>

[![PkgGoDev](https://pkg.go.dev/badge/centrifuge.hectabit.org/HectaBit/captcha)](https://pkg.go.dev/github.com/centrifuge.hectabit.org/HectaBit/captcha)
[![Go Report Card](https://goreportcard.com/badge/centrifuge.hectabit.org/HectaBit/captcha)](https://goreportcard.com/report/centrifuge.hectabit.org/HectaBit/captcha)

</div>

## Why another captcha generator?
Because I can. 

## install
```
go get centrifuge.hectabit.org/HectaBit/captcha
```

## usage
```Go
func handle(w http.ResponseWriter, r *http.Request) {
	// create a captcha of 150x50px
	data, _ := captcha.New(150, 50)

	// session come from other library such as gorilla/sessions
	session.Values["captcha"] = data.Text
	session.Save(r, w)
	// send image data to client
	data.WriteImage(w)
}

```

[documentation](https://pkg.go.dev/centrifuge.hectabit.org/HectaBit/captcha) |
[example](example/basic/main.go) |
[font example](example/load-font/main.go)

## sample image
![image](example/captcha.png)

![image](example/captcha-math.png)

## Compatibility

This package uses embed package from Go 1.16. If for some reasons you have to use pre 1.16 version of Go, reference pre 1.4 version of this module in your go.mod.

## Contributing
If your found a bug, please contribute!
see [contributing.md](contributing.md) for more detail.

## License
[MIT](LICENSE)
