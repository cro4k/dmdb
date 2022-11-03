达梦 golang SDK (非官方维护)

[达梦官网](https://eco.dameng.com/document/dm/zh-cn/app-dev/go-go.html)

Usage:
```go
package main

import (
    "database/sql"
    _ "github.com/cro4k/dmdb"
    "log"
)

func main() {
    var db, err = connect("dm", "dm://SYSDBA:SYSDBA@localhost:5236")
    if err != nil {
        log.Fatal(err)
    }
    //TODO
}

func connect(driverName string, dataSourceName string) (*sql.DB, error) {
    var db *sql.DB
    var err error
    
    if db, err = sql.Open(driverName, dataSourceName); err != nil {
        return nil, err
    }
    if err = db.Ping(); err != nil {
        return nil, err
    }
    return db, nil
}
```