---
title: prawf Docs

toc_footers:
  - Made with ❤️ by <a href='https://github.com/navendu-pottekkat' target="_blank">Navendu Pottekkat</a>
  - <a href='https://github.com/prawf/prawf-cli/blob/master/LICENSE' target="_blank">GNU General Public License v3.0</a>

includes:
  - quick_start
  - installation
  - configuring
  - sending_requests
  - running_tests
  - contributing

search: true

code_clipboard: true
---

# Introduction

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

🧪 <a href="https://github.com/prawf/prawf-cli">prawf</a> is a lightweight and easy-to-use HTTP API testing framework.

You can easily define your tests in a `prawf.json` file and use the `prawf` CLI to run tests with it.

Try the [Quick Start](#quick-start) guide to run prawf without any configurations.

Here are some reasons why you might want to use prawf-

🏋️‍♂️ Lightweight- Does not add any overhead to your software

🧰 Cross platform- Compiled to a binary and works on Windows, Mac and Linux
 
📝 Declarative tests- Forget all those flags you use to send a request and write your tests in a file

🧱 Structured logs- Get structured logs so you do not have to spend hours debugging

🚰 Built-in CI/CD support- Ship your applications bug free by adding to your CI/CD pipelines

🔓 Free and open-source- It is and it always will be