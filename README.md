# pail-credential-archdev

A [pail](https://pail.build) credential provider: your ArchDev login (pail.archdev.ai).

```sh
pail auth install archdev
pail auth use archdev --for https://pail.archdev.ai --global
```

pail credential provider: your ArchDev login. ArchDev serves your organization's pail
repositories at https://pail.archdev.ai/<org>/<repo> and checks the token on every request;
archdev only hands the token to stores under its own pail URLs.

  pail auth install archdev
  pail auth use archdev --for https://pail.archdev.ai --global
  pail clone "$(archdev pail url team/app)"     # https://pail.archdev.ai/<your org>/team/app

It speaks `pail-credential/1`: `pail-credential-archdev get` reads `{"protocol","store","scheme"}` on stdin and prints
`{"token","expires_at"}`. `pail-extension.json` tells `pail auth install` which file to install.
