# Go Modules - Belajar Go Modules

Go Modules adalah sistem manajemen dependency di Go yang memungkinkan pengelolaan paket secara lebih fleksibel dan terstruktur.

## 📌 Struktur Folder

```
/go-say-hello
├── go.mod        # File module Go
├── README.md     # Dokumentasi proyek
└── say_hello.go  # File utama dengan fungsi SayHello
```

## 📖 Deskripsi

Project ini adalah contoh sederhana penggunaan Go Modules. Modul ini menyediakan satu fungsi sederhana:

```go
package go_say_hello

func SayHello(name string) string {
    return "Hello" + name
}
```

## 🚀 Cara Menggunakan

### 1️⃣ Inisialisasi Module

Di dalam folder project, jalankan perintah berikut untuk menginisialisasi module:

```sh
go mod init github.com/rizkycahyono97/go-say-hello
```

### 2️⃣ Menggunakan Module di Project Lain

Buat project baru, lalu jalankan:

```sh
go mod init github.com/rizkycahyono97/app-say-hello
```

Tambahkan dependency dengan:

```sh
go get github.com/rizkycahyono97/go-say-hello@latest
```

### 3️⃣ Buat File `main.go`

Di dalam project yang ingin menggunakan module ini, buat file `main.go` seperti berikut:

```go
package main

import (
    "fmt"
    "github.com/rizkycahyono97/go-say-hello"
)

func main() {
    fmt.Println(go_say_hello.SayHello("Parameter"))
}
```

### 4️⃣ Jalankan Program

```sh
go run main.go
```

**Output yang diharapkan:**

```
Hello Parameter
```

## 🛠 Troubleshooting

* *   Jika terjadi error module path, pastikan **path di `go.mod` sesuai dengan repository GitHub**.
* *   Jika ingin menggunakan versi lokal tanpa push ke GitHub, gunakan:

```sh
go mod edit -replace github.com/rizkycahyono97/go-say-hello=../go-say-hello
```

## 📌 Referensi

* *   [Official Go Modules Guide](https://go.dev/doc/modules)

* * *

Happy coding! 🚀