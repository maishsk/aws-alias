# AWS CLI alias

This repository is a consolidated collection of AWS cli aliases from several locations on the internet.

An alias - is a *shortcut* (for the lack better term) that you can use to speed up your day to day work with the AWS CLI.

The command is built into the aws cli - you can have a look [here](https://github.com/aws/aws-cli/blob/master/awscli/alias.py) to see how this implemented. 

Essentially - you create an `alias` file in `.aws/cli/alias` and you populate the file with the shortcuts you would like. Support for aliases was added in this [PR](https://github.com/aws/aws-cli/pull/2287) - and if you would like to see exactly what is supported - please go through the PR.

Based on the information from the [PR](https://github.com/aws/aws-cli/pull/2287) the `alias` file is an `INI` file, and you define the aliases and their values in the file.

- The `~/.aws/cli/alias` file only has support for the `[toplevel]` section. Any other sections, will be ignored.
- Aliases defined under the `[toplevel]` section will only be applied at the service command level.
- Aliases can defined using multiple lines for readability.

You can find more information on the following [blog post](https://blog.technodrone.cloud/2020/12/aws-cli-aliases.html).

The file has been divided into sections based on the types of commands that are involved with the aliases.

- general commands
- IAM
- EC2
- CloudWatch
- ECR

## Simple alias
Let's have a look at a simple `alias` file example. First you put in a `[toplevel]` declaration at the top of the file, and your alias below that.

```
[toplevel]

whoami = sts get-caller-identity
```

and when you run `aws whoami` it will replace the command the value `sts get-caller-identity` 
## Functions and commands
Your alias can also contain a function - which is essentially a wrapper for a shell command and looks like this.

```
  !f() {
    <_Enter some shell command here_>
  }; f
```

## Sources
- [https://github.com/awslabs/awscli-aliases/blob/master/alias](https://github.com/awslabs/awscli-aliases/blob/master/alias) ([1](./alias#L7), [2](./alias#L12), [3](./alias#L18), [8](./alias#L65), [9](./alias#L67), [9](./alias#L81), [16](./alias#L155), [17](./alias#L160), [18](./alias#L164), [19](./alias#L175), [20](./alias#L177), [21](./alias#L184), [22](./alias#L189), [23](./alias#L196), [24](./alias#L207), [25](./alias#L212), [26](./alias#L218), [27](./alias#L224), [28](./alias#L229))
- [https://github.com/3-shake/awscli-aliases/blob/master/alias](https://github.com/3-shake/awscli-aliases/blob/master/alias) ([29](./alias#L234))
- [https://github.com/dedelala/awscli-aliases/blob/lambda-last-log/alias](https://github.com/dedelala/awscli-aliases/blob/lambda-last-log/alias) ([52](./alias#L406))
- [https://github.com/faizanbashir/awscli-aliases/blob/master/alias](https://github.com/faizanbashir/awscli-aliases/blob/master/alias) ([30](./alias#L244))
- [https://github.com/Voronenko/dotfiles/blob/b120063fd8531c3b054cf5dda2fdec6bd222bf74/aws/alias](https://github.com/Voronenko/dotfiles/blob/b120063fd8531c3b054cf5dda2fdec6bd222bf74/aws/alias) ([53](./alias#L426))
- [https://github.com/LanikSJ/awscli-aliases/blob/master/alias](https://github.com/LanikSJ/awscli-aliases/blob/master/alias) ([34](./alias#L305), [35](./alias#L310))
- [https://github.com/jameszh/awscli-aliases/blob/master/alias](https://github.com/jameszh/awscli-aliases/blob/master/alias) ([31](./alias#L267), [32](./alias#L289))
- [https://github.com/limed/awscli-aliases/blob/add-list-all-regions/alias](https://github.com/limed/awscli-aliases/blob/add-list-all-regions/alias) ([33](./alias#L300))
- [https://github.com/mbainter/awscli-aliases/blob/personal_aliases/alias](https://github.com/mbainter/awscli-aliases/blob/personal_aliases/alias) ([10](./alias#L97), [11](./alias#L99), [12](./alias#L104))
- [https://github.com/otanner/awscli-aliases/blob/master/alias](https://github.com/otanner/awscli-aliases/blob/master/alias) ([13](./alias#L110), [14](./alias#L121), [36](./alias#L317), [37](./alias#L325), [38](./alias#L333), [39](./alias#L339), [40](./alias#L345), [41](./alias#L350))
- [https://github.com/pwmcintyre/awscli-aliases/blob/master/alias](https://github.com/pwmcintyre/awscli-aliases/blob/master/alias) ([15](./alias#L134))
- [https://gist.github.com/jamesls/3623e9589db175509ec2c61536b6c6b9](https://gist.github.com/jamesls/3623e9589db175509ec2c61536b6c6b9) ([4](./alias#L23), [5](./alias#L30), [6](./alias#L43))
- [https://github.com/skatsuta/awscli-aliases/blob/master/alias](https://github.com/skatsuta/awscli-aliases/blob/master/alias) ([7](./alias#L50))
- [https://github.com/tchia04/awscli-aliases/blob/master/alias](https://github.com/tchia04/awscli-aliases/blob/master/alias) ([42](./alias#L355), [43](./alias#L359), [44](./alias#L363), [45](./alias#L367), [46](./alias#L371), [47](./alias#L375), [48](./alias#L380), [49](./alias#L384))
- [https://github.com/tchia04/awscli-aliases/blob/instance_id_and_dns_conversion/alias](https://github.com/tchia04/awscli-aliases/blob/instance_id_and_dns_conversion/alias) ([50](./alias#L388), [51](./alias#L395))
