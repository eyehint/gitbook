# Configuration



## Configuration

Commands to manage DAMDA account information so that you can use functions such as component creation/deletion/deployment by accessing the DAMDA cloud with the DAMDA CLI

### configure

Commands to set up a DAMDA account.

#### Command

```
$ damda configure [OPTIONS]
# OPTIONS:
#   --profile TEXT: [default:default]
```

#### Usage

Case 1) set up an DAMDA account with the default profile

```
$ damda configure
DAMDA ID [default]: <Enter DAMDA ID>
DAMDA P/W[default]: <Enter DAMDA P/W>
```

Case 2) set up an DAMDA account with the default profile

```
$ damda configure --profile test
DAMDA ID [test]: <Enter DAMDA ID>
DAMDA P/W[test]: <Enter DAMDA P/W
```

#### get-configuration

Command to get DAMDA account information for a specific profile.

Command

<pre><code><strong>$ damda get-configuration [OPTIONS]
</strong># OPTIONS:
#    --profile TEXT: [default: default]</code></pre>

#### Usage

Case 1) set up an DAMDA account with the default profile

```
$ damda get-configuration
{'id': '<DAMDA ID>', 'pw': '<DAMDA P/W>'}
```

Case 2)set up an DAMDA account with the default profile

```
$ damda get-configuration --profile test
{'id': '<DAMDA ID>', 'pw': '<DAMDA P/W>'}
```
