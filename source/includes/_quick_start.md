# Quick Start

> Create a new `prawf.json` config file-

```shell
prawf init
```

> This will create the file in your current directory-

```shell
prawf.json file not found. Would you like to create one? [y/n]? y
INFO[0002] File created.                                 file=prawf.json
INFO[0002] File loaded.                                  file=prawf.json
```
> Default `prawf.json` file-

```json
{
  "current": "sample-test",
  "tests": {
    "sample-test": {
      "url": "https://jsonplaceholder.typicode.com",
      "methods": [
        {
          "name": "get-post",
          "path": "/posts",
          "method": "get",
          "query": {
            "id": 1
          },
          "expect": {
            "contain": {
              "id": 22
            },
            "keys": [
              "id"
            ],
            "equal": {
              "id": 22
            }
          }
        },
        {
          "name": "post-post",
          "path": "/posts",
          "method": "post",
          "header": {
            "Content-type": "application/json; charset=UTF-8"
          },
          "body": {
            "body": "If you haven't already, check out prawf to test your REST API endpoints",
            "title": "prawf is amazing!",
            "userId": 1
          },
          "expect": {}
        }
      ]
    }
  }
}
```

> Send requests to endpoints specified in the `prawf.json` file-

```shell
prawf run

INFO[0000] File loaded.                                  file=prawf.json
INFO[0000] Running test.                                 test=sample-test url="https://jsonplaceholder.typicode.com"

INFO[0000] Creating request.                             method=GET name=get-post path=/posts
INFO[0000] Response received.                            status code="200 OK"
INFO[0000] [
  {
    "userId": 1,
    "id": 1,
    "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
    "body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto"
  }
] 

INFO[0000] Creating request.                             method=POST name=post-post path=/posts
INFO[0001] Response received.                            status code="201 Created"
INFO[0001] {
  "body": "If you haven't already, check out prawf to test your REST API endpoints",
  "title": "prawf is amazing!",
  "userId": 1,
  "id": 101
}
```

> Test the endpoints as specified in the `prawf.json` file-

```shell
prawf test

INFO[0000] File loaded.                                  file=prawf.json
INFO[0000] Running test.                                 test=sample-test url="https://jsonplaceholder.typicode.com"

INFO[0000] Creating request.                             method=GET name=get-post path=/posts
INFO[0000] Response received.                            status code="200 OK"
INFO[0000] [
  {
    "userId": 1,
    "id": 1,
    "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
    "body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto"
  }
] 

ERRO[0000] Expected response.                            contain=yes equal=yes keys=yes test=fail
ERRO[0000] {
  "id": 22
  }                              type=equal
ERRO[0000] {
  "id": 22
  }                              type=contain
ERRO[0000] [id]                                          type=keys

INFO[0000] Creating request.                             method=POST name=post-post path=/posts
INFO[0001] Response received.                            status code="201 Created"
INFO[0001] {
  "body": "If you haven't already, check out prawf to test your REST API endpoints",
  "title": "prawf is amazing!",
  "userId": 1,
  "id": 101
} 
```

<aside class="notice">
  Check the window on the right for step by step walkthrough on the commands.
</aside>

* Install prawf- See the [Installation](#installation) guide.

* Open up your project folder. If you do have a project yet and is just testing prawf, you can create an empty folder.

* Create a new `prawf.json` config file.

<aside class="notice">
    By default, prawf will initialise the <code>prawf.json</code> configuration file with the API endpoints from <a href="https://jsonplaceholder.typicode.com/" target="_blank">jsonplaceholder.typicode.com</a>.

    You can use this for testing out the capabilities of prawf. 
</aside>


* Edit the `prawf.json` configuration file if you are testing a custom application. You can leave it as it is if you are just testing out prawf. See [Configuring prawf.json](#configuring-prawf.json) for more details.

* Send requests to endpoints specified in the `prawf.json` file.

* Test the endpoints as specified in the `prawf.json` file.

<aside class="success">
    Awesome! You have successfully run a prawf test. See the <a href="http://" target="_blank">Tutorials</a> for specific tutorials on how to use prawf.
</aside>