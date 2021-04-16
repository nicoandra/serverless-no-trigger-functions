# serverless-ignore-triggers

A simple serverless plugin to remove all events bound to a function upon deployment. The goal is to avoid the function to be called.

## Install

```sh
npm install --save-dev serverless-ignore-triggers
```

Add the plugin to your serverless.yml file:

```yaml
plugins:
  - serverless-ignore-triggers
```

## Usage

Add the parameter `ignoreTriggers: false` to a function to remove all events.


```
functions:
  hello:
    handler: handler.hello
    ignoreTriggers: true
```

In case you need to parse a `string` as `bool` for example if you are using `env`; you need to use `strToBool`:

```
functions:
  hello:
    handler: handler.hello
    ignoreTriggers: strToBool(${env:SAY_HELLO_ENABLED})
```
