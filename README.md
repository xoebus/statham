# statham

*statham is the per-domain transporter*

## installation

``` sh
go get github.com/xoebus/statham
```

## usage

``` go
defaultTransport := &http.Transport{...}
tr1 := &http.Transport{...}
tr2 := &http.Transport{...}

tr := statham.NewTransport(defaultTransport, statham.Mapping{
  "github.com": tr1,
  "google.com": tr2,
})

client := &http.Client{Transport: tr}
```
