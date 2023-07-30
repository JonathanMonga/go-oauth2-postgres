# Postgres Storage for [OAuth 2.0](https://github.com/go-oauth2/oauth2)

[![GoDoc][godoc-image]][godoc-url] [![License][license-image]][license-url]

## Install

``` bash
$ go get -v github.com/JonathanMonga/go-oauth2-postgres
```

## Usage

``` go
package main

import (
	"github.com/JonathanMonga/go-oauth2-postgres"
	"github.com/go-oauth2/oauth2/v4/manage"

	_ "github.com/lib/pq"
)

func main() {
	manager := manage.NewDefaultManager()

	// use postgres token store
	store := postgres.NewDefaultStore(
		postgres.NewConfig("postgres://postgres:password@localhost/myapp_test?sslmode=disable"),
	)

	defer store.Close()

	manager.MapTokenStorage(store)
	// ...
}

```

## MIT License

```
Copyright (c) 2023 Jonathan Monga
```

[reportcard-url]: https://goreportcard.com/report/github.com/JonathanMonga/go-oauth2-postgres
[reportcard-image]: https://goreportcard.com/badge/github.com/JonathanMonga/go-oauth2-postgres
[godoc-url]: https://godoc.org/gopkg.in/JonathanMonga/go-oauth2-postgres.v1
[godoc-image]: https://godoc.org/gopkg.in/JonathanMonga/go-oauth2-postgres.v3?status.svg
[license-url]: http://opensource.org/licenses/MIT
[license-image]: https://img.shields.io/npm/l/express.svg

