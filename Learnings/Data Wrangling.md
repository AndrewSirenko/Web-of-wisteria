
## Unix Pipes & Redirects
## Regex

## Grep

- Negate match:
	- `grep -v 'not' text.txt`
- Get x lines After/Before/Context around match:
	- `grep 'test' text.txt -A 3`

## Ripgrep

Great for searching through source code

`rg 'error: some message'`

## Awk

## xargs 

xargs

- Provide only one line of input at a time:
	- `cat hostnames | xargs -n host -t A`
- Provide placeholder of where to put each line:
	- `cat hostnames | xargs -I{} host -t A {} 8.8.8.8`
- Run in parallel (4 here):
	- `cat hostnames | xargs -P4 host -t A`
- `sh -c` trick -- get last line of each command:
	- `cat hostnames | xargs sh -c "host -t A | tail -n1"`


