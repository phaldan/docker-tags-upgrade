# Docker tags upgrade

`upgrade.sh` is a bash-script to create aliases for a tag and push this tag with all aliases to a docker registry. Aliases are configured within a `v...` file. Each line of this file contains a single alias.

## Usage

```
upgrade.sh image tag
```

## Example

In this example we have a docker image `phaldan/example` with a tag `1.2.3.4` and a file `v1.2.3` with the following content:

```
1.2.3
1.2
1
latest
```

With the following command the bash-script detects the existens of `v1.2.3` (full internal search: `v1.2.3.4`, `v1.2.3.`, `v1.2.3`, `v1.2.`, `v1.2`, `v1.`, `v1` and `v`) and executes the previous described procedure:

```
$ ./upgrade.sh phaldan/example 1.2.3.4
```