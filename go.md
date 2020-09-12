# Go

## Modules
- 🎥 [Intro to Go Modules and SemVer](https://www.youtube.com/watch?v=aeF3l-zmPsY)

## HTTP Server
- 📝 [How I write HTTP services after eight years.](https://pace.dev/blog/2018/05/09/how-I-write-http-services-after-eight-years.html)
- 💭 [How to create many http servers into one app?](https://stackoverflow.com/questions/31176307/how-to-create-many-http-servers-into-one-app)

#### Creating an HTTP Server
```go
import "fmt"
import "net/http"


func handleIndex(w http.ResponseWriter, r *http.Request){
  fmt.Fprintf(w, "Hello Index!")
}

func main() {
    http.HandleFunc("/", handleIndex)
    http.ListenAndServe(":8000", nil)
}
```

When calling `http.HandleFunc`, handler functions are attached to the `DefaultServeMux` exported by the `net/http` package. You can also create your own ServeMux if you don't want to work directly off of the `DefaultServeMux`

```go
import "fmt"
import "net/http"


func handleIndex(w http.ResponseWriter, r *http.Request){
  fmt.Fprintf(w, "Hello Index!")
}

func main() {
    mux := http.NewServeMux()
    http.HandleFunc("/", handleIndex)
    http.ListenAndServe(":8000", mux)
}
```

This is particularly useful if you want to run multiple HTTP servers.

#### Handling Requests
##### Sending JSON
```go
func foo(w http.ResponseWriter, r *http.Request) {
  profile := Profile{"Alex", []string{"snowboarding", "programming"}}

  js, err := json.Marshal(profile)
  if err != nil {
    http.Error(w, err.Error(), http.StatusInternalServerError)
    return
  }

  w.Header().Set("Content-Type", "application/json")
  w.Write(js)
}
```
##### Sending Templates
##### Getting query params
```go
func main() {
	u, err := url.Parse("https://example.org/?a=1&a=2&b=3")
	if err != nil {
		log.Fatal(err)
	}
	q := u.Query()
	fmt.Println(q["a"]) # [ "1", "2" ]
        fmt.Println(q.Get("a")) # "1"
	fmt.Println(q.Get("b")) # "3"
}
```

https://golang.org/pkg/net/url/#URL.Query

##### Getting path params
The stdlib does not contain path parameter parsing, you either need to use a library, or parse the URL yourself. 
```go
path := "/blog/123"
blogId := strings.TrimPrefix(req.URL.Path, "/blog/")
```
