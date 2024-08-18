# gorm-sqlcipher-v4
The existing gorm-sqlcipher modules I tried all threw the same errors when using gorm v1.25.11. I cloned one of the repos, patched the bugs, and created a new working module. Enjoy.

## Installation

go get github.com/gdanko/gorm-sqlcipher-v4

## How to use

```go
import (
	sqlcipher "github.com/gdanko/gorm-sqlcipher-v4"
	"gorm.io/gorm"
)

key := "2DD29CA851E7B56E4697B0E1F08507293D761A05CE4D1B628663F411A8086D99"
dbFile := "/path/to/my.db"
dbName := fmt.Sprintf("%s?_pragma_key=x'%s'&_pragma_cipher_page_size=4096", dbFile, key)
db, err := gorm.Open(sqlcipher.Open(dbName), &gorm.Config{})
```

## More
- https://github.com/mutecomm/go-sqlcipher
- https://github.com/go-gorm/gorm
