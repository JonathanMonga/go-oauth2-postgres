# Postgres Storage for [OAuth 2.0](https://github.com/go-oauth2/oauth2)

[![Build][Build-Status-Image]][Build-Status-Url] [![Codecov][codecov-image]][codecov-url] [![ReportCard][reportcard-image]][reportcard-url] [![GoDoc][godoc-image]][godoc-url] [![License][license-image]][license-url]

## Install

``` bash
$ go get -v github.com/JonathanMonga/go-oauth2-postgres/v4
```

## Usage

``` go
package main

import (
	"github.com/JonathanMonga/go-oauth2-postgres/v4"
	"github.com/go-oauth2/oauth2/v4/manage"

	_ "github.com/go-sql-driver/postgres"
)

func main() {
	manager := manage.NewDefaultManager()

	// use postgres token store
	store := mysql.NewDefaultStore(
		mysql.NewConfig("root:123456@tcp(127.0.0.1:3306)/myapp_test?charset=utf8"),
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

[Build-Status-Url]: https://travis-ci.org/JonathanMonga/go-oauth2-postgres
[Build-Status-Image]: https://travis-ci.org/go-oauth2/mysql.svg?branch=master
[codecov-url]: https://codecov.io/gh/JonathanMonga/go-oauth2-postgres
[codecov-image]: https://codecov.io/gh/JonathanMonga/go-oauth2-postgres/branch/master/graph/badge.svg
[reportcard-url]: https://goreportcard.com/report/gopkg.in/JonathanMonga/go-oauth2-postgres.v3
[reportcard-image]: https://goreportcard.com/badge/gopkg.in/JonathanMonga/go-oauth2-postgres.v3
[godoc-url]: https://godoc.org/gopkg.in/JonathanMonga/go-oauth2-postgres.v3
[godoc-image]: https://godoc.org/gopkg.in/JonathanMonga/go-oauth2-postgres.v3?status.svg
[license-url]: http://opensource.org/licenses/MIT
[license-image]: https://img.shields.io/npm/l/express.svg

