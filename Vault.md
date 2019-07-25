# Vault

#### Initialization

```
vault operator init
```
#### Unseal

```
vault operator unseal
```

#### Export Token

available through init

```
export VAULT_TOKEN=s.xxxxxxxxxxxxxx
```

#### Login
```
vault login
```

#### Enable secrets 

```
vault secrets enable -path=kv kv
Success! Enabled the kv secrets engine at: kv/
```

#### Put 

```
vault kv put kv/hello foo=world
Success! Data written to: kv/hello
```

#### List

```
vault secrets list
Path          Type         Accessor              Description
----          ----         --------              -----------
cubbyhole/    cubbyhole    cubbyhole_fb8565a6    per-token private secret storage
identity/     identity     identity_77bfb1d1     identity store
kv/           kv           kv_0e879e5b           n/a
sys/          system       system_fd4254e7       system endpoints used for control, policy and debugging
```
