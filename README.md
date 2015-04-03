# Go URL Lengthener
Lengthens URLs

#### Usage
Input must have 1 arguments:

1.  -url

#### Example Input - Output
-
Input:
```
go run main.go http://t.co/xqc8YUzCMT
```
Output (Success):
```
{"result":"http://store.steampowered.com/search/?developer=Phoenix%20Online%20Studios"}
```
-
Output (Failure):
```
{
  "error":"<error message>"
}
```

#### How to build docker image
Requirements:

1. Golang environment set up
2. Git
3. boot2docker running

```
go get github.com/cloudspace/Go_URL_Lengthener
cd <Go_URL_Lengthener>/Go_URL_Lengthener
docker run --rm -v $(pwd):/src centurylink/golang-builder
docker build -t <username>/go_url_lengthener:0.1 ./

```

In order for `docker run --rm -v $(pwd):/src centurylink/golang-builder` to work you need to have the github url on the top line of main.go. It should look like this:
```
package main // import "github.com/cloudspace/Go_URL_Lengthener"
```
You also must *push your code* to github *before building* the docker image.
