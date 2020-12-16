# AWS CLI alias

This repository is consolidated collection of AWS cli aliases from several locations on the internet.

An alias - is *shortcut* (for the lack better term that you can use to speed up your day to day work with the CLI

The command is built into the aws cli - you can have a look [here](https://github.com/aws/aws-cli/blob/master/awscli/alias.py) 

Essentially - you create an `alias` file in `.aws/cli/alias` and you populate it with the content you would like and you can see that the support for aliases was added in this [PR](https://github.com/aws/aws-cli/pull/2287) - and if you would like to see exactly what is supported - go through the PR.

Based on the information from the [PR](https://github.com/aws/aws-cli/pull/2287) the `alias` file is an `INI` file, and you define the aliases and their values inside.

- The `~/.aws/cli/alias` file only has support for the `[toplevel]` section. Any other sections, will be ignored.
- Aliases defined under the `[toplevel]` section will only be applied at the service command level.
- Aliases can defined using multiple lines for readability.


You can find more information on the following [blog post](https://blog.technodrone.cloud/2020/12/aws-cli-aliases.html).

## Simple alias

Let's have a look at a simple `alias` file. First you put in a declaration at the top of the file.

```
[toplevel]

whoami = sts get-caller-identity
```

## Functions and commands

Your alias can also contain a function - which is essentially a wrapper for a shell command and looks something like this

```
  !f() {
    <_Enter some shell command here_>
  }; f
```