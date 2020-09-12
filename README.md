# Dev Notes

## Back End

- 📖 [**Designing Data-Intensive Applications**](https://dataintensive.net/) - Martin Kleppmann

### HTTP
- 📝 [HTTP Made Really Easy](https://www.jmarshall.com/easy/http/)
- 💭 [Difference between "Cache-Control: max-age=0" and "Cache-Control: no-cache"](http://stackoverflow.com/questions/1046966/whats-the-difference-between-cache-control-max-age-0-and-no-cache)

### Authn/Authz
- 📝 [An Introduction to OAuth 2](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2)

## Web Front-End
- 📝 [THE PAST, PRESENT & FUTURE OF LOCAL STORAGE FOR WEB APPLICATIONS](http://diveintohtml5.info/storage.html)

## [Linux](linux.md)

## Docker
### Dockerfile
#### Example
```dockerfile
FROM golang:alpine d
RUN apk --no-cache add gcc g++ make git
WORKDIR /go/src/app
COPY . .
RUN go get ./...
RUN GOOS=linux go build -ldflags="-s -w" -o ./web-app .

FROM alpine:3.9
RUN apk --no-cache add ca-certificates
COPY --from=build /go/src/app /go
WORKDIR /go
EXPOSE 8080
ENTRYPOINT /go/web-app
```

### CLI
#### Building Images
Docker builds images based on two main pieces of data: A Dockerfile, and a context.
See [dockerfile.md](./dockerfile.md).
The context is a set of files, passed in as an argument to the `docker build` command. The files contained in the context are the files that are available (via for instance a COPY command) to the Dockerfile.

- `docker build .` Build an image using the current folder as context
- `docker build -f config/Dockerfile .` Build an image, specifying a path for the Dockerfile

#### Managing Containers

- `docker ps` List all _running_ containers
- `docker ps -a` List all containers
- `docker ps -q` List all running containers, only outputting numberic IDs
- `docker stop $(docker ps -q)` Stop all running containers
- `docker rm $(docker ps -aq)` Remove all containers

## Object Oriented Programming
- 📝 [Why getter and setter methods are evil](https://www.infoworld.com/article/2073723/why-getter-and-setter-methods-are-evil.html)

## Javascript
- 🎥 [What the heck is the event loop anyway? | Philip Roberts | JSConf EU](https://www.youtube.com/watch?v=8aGhZQkoFbQ)

### Legacy 
These articles aren't too relevant for today's JS, but were helpful at the time and still useful for historical learning.
- 📝 [Overwhelmed by Javascript Dependencies](http://blog.startifact.com/posts/overwhelmed-by-javascript-dependencies.html)

## Typescript
- 📖 [**Effective Typescript**](https://effectivetypescript.com/) - Dan Vanderkam

## C++
- 📝 [C++ Core Guidelines](https://github.com/isocpp/CppCoreGuidelines)

## Rust
- 📝 [Rust via its Core Values](http://designisrefactoring.com/2016/04/01/rust-via-its-core-values/)

## Go
### Modules
- 🎥 [Intro to Go Modules and SemVer](https://www.youtube.com/watch?v=aeF3l-zmPsY)
### HTTP Server
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

## GraphQL
- 📝 [Demystifying the info Argument in GraphQL Resolvers](https://www.prisma.io/blog/graphql-server-basics-demystifying-the-info-argument-in-graphql-resolvers-6f26249f613a)

## Vim
- 💭 [What is the difference between the remap, noremap, nnoremap and vnoremap mapping commands in Vim?](https://stackoverflow.com/questions/3776117/what-is-the-difference-between-the-remap-noremap-nnoremap-and-vnoremap-mapping)

## Git
- 📝 [Understanding git for real by exploring the .git directory](https://www.daolf.com/posts/git-series-part-1/)
- 📝 [Git koans](https://stevelosh.com/blog/2013/04/git-koans/)

### Quick Reference
##### [git clone](http://git-scm.com/docs/git-clone)
+ Clone remote repository
  + `git clone <git url>`
    + e.g. `git clone https://github.com/wwselleck/weston-guides`
+ Clone remote repository into directory with custom name
  + `git clone <git url> [new name]`
    + e.g. `git clone https://github.com/wwselleck/weston-guides programming-guides`

##### [git add](http://git-scm.com/docs/git-add)
+ Add single file to index
  + `git add <file path>`
    + e.g. `git add src/hello-world.js`
+ Add all files in working tree to index
  + `git add -A`
+ Add all changed files in working tree to index, ignoring new files
  + `git add -u`

##### Branches
+ Show branches and their commits
  + `git show-branch`<sup>[[0]](https://git-scm.com/docs/git-show-branch)</sup>
+ Show all local and remote branches
  + `git branch -a` <sup>[[0]](http://gitready.com/intermediate/2009/02/13/list-remote-branches.html)</sup>
+ Rename a local branch
  + `git branch -m <oldname> <newname>`<sup>[[0]](http://stackoverflow.com/questions/6591213/how-to-rename-the-local-branch)</sup>
    + e.g. `git branch -m feature/old-name feature/new-name`
    + If you are already on the branch you want to rename, this can be shortened to
      + `git branch -m <newname>`
+ Delete local branch
  + `git branch -d <branch name>` <sup>[source](http://makandracards.com/makandra/621-git-delete-a-branch-local-or-remote)</sup>
    + e.g. `git branch -d feature/add-navigation`
+ Delete remote branch
  + `git push origin --delete <branch name>` <sup>[source](http://stackoverflow.com/questions/2003505/delete-a-git-branch-both-locally-and-remotely)</sup>
    + e.g. `git push origin --delete feature/add-navigation`
+ Push local branch to remote
  + `git push --set-upstream origin <branch name>`
    + e.g. `git push --set-upstream origin feature/US14933-skeleton-cleanup`

[How to reset/rollback to your last commit](http://stackoverflow.com/questions/927358/how-do-you-undo-the-last-commit)
