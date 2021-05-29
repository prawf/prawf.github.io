# Configuring Tests

> To start, open the `prawf.json` file in your project folder. If you do not have a `prawf.json` file, run-

```
prawf init
```

The `prawf.json` config file will contain all your tests. You can define tests by specifying the endpoints request details and provide the expected responses to test with.

See the [Quick Start](#quick-start) guide for more details on getting started.

Once you have the `prawf.json` file initialised, open it on a text editor.

## Available Configurations

The following could be configured in the `prawf.json` file. See the [example below](#example-prawf.json-file)-

`current`- Represents the focused test. Users can define multiple tests and the test mentioned in `current` will be used for running tests.

`tests` - Array of tests. Users can define multiple tests here with a test name as mentioned below.

    `test-name`- Name of the test. Its value contains the test.

        `url`- The URL the current test is interested in.

        `methods`- Array of methods to test the URL on.
            
            `name`- Name of the method.
            
            `path`- The path which will be added to the URL.
            
            `method`- Type of HTTP request.
            
            `query`- The query to add to the request.
            
            `header`- The header to add to the request.
            
            `body`- The body to add to the request.
            
            `expect`- Represents what to look for in the response for testing.
            
                `keys`- To check if the keys mentioned are present in the response.
                
                `contain`- To check if the key-value pairs are present in the response.
                
                `equal`- To check if the response if exactly equal to the present value.

## Example prawf.json file

> An example json file created when you run `prawf init`

```json
{
  "current": "sample-test",
  "tests": {
    "sample-test": {
      "url": "https://jsonplaceholder.typicode.com",
      "methods": [
        {
          "name": "get-pass",
          "path": "/posts",
          "method": "get",
          "query": {
            "id": 1
          },
          "expect": {
            "contain": {
              "id": 1
            }
          }
        },
        {
          "name": "get-fail",
          "path": "/posts",
          "method": "get",
          "query": {
            "id": 3
          },
          "expect": {
            "keys": [
              "uuid"
            ]
          }
        },
        {
          "name": "post-pass",
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
          "expect": {
            "equal": {
              "body": "If you haven't already, check out prawf to test your REST API endpoints",
              "title": "prawf is amazing!",
              "userId": 1
            }
          }
        },
        {
          "name": "put-pass",
          "path": "/posts/1",
          "method": "put",
          "header": {
            "Content-type": "application/json; charset=UTF-8"
          },
          "body": {
            "body": "Give us a star on GitHub/prawf!",
            "id": 1,
            "title": "prawf is awesome!",
            "userId": 1
          },
          "expect": {
            "contain": {
              "title": "prawf is awesome!"
            }
          }
        }
      ]
    }
  }
}
```

This is an example `prawf.json` config file that is generated when you run `prawf init`.

You can use this config file as a template to write your own tests.