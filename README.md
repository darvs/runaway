# runaway
An SSH remote runner

## Description

runaway is a tiny remote runner not totally unlike the VS Code Remote SSH component.

If it detects the directory it's invoked from has been mounted with sshfs, it will run the following command on the remote host. If it's not, it will run the following command on the local host. 

## Usage

`runaway <command>`

## Example

```bash
cd /tmp
runaway hostname
```

Will print the local host name, for instance `localhost`.

```bash
cd /tmp
mkdir /tmp/project
sshfs remote:/usr/local/src/project /tmp/project
runaway hostname
runaway make
```

Will print the hostname of the remote machine (`remote`) and launch make on the `remote` host.