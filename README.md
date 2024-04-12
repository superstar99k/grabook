# Installation

1. Add the host setting to /etc/hosts
```
127.0.0.1 grabook.local
127.0.0.1 api.grabook.local
```
1. Clone source code
```sh
git clone git@github.com:dragon99k/grabook.git
cd shino.shinobiz
git clone git@github.com:dragon99k/grabook-server.git src/server
git clone git@github.com:dragon99k/grabook-client.git src/client
```
2. Run docker `docker-compose up`
3. Init server source: `./tools/init.sh`
4. Launch npm dev server: `./tools/launch-client.sh`

## Note

### Test Account

```
email: admin@admin.com
password: 11111111
```

### Remote Container

We recommend you to use VSCode Remote Container to develop in this project.<br />
Please look at the following example.<br />
You can also open the server side project as the same with this example.
```sh
# open the client side project
cd src/client
code .
# then, push "Reopen in Container" button.
# or push left bottom button and choose "Reopen in Container".
```

### メモAn error occured setting up the containerが出てしまう時
An error occured setting up the containerが出てしまう時<br />
0.245.2にダウングレードして解消できました。<br />
https://github.com/microsoft/vscode-remote-release/issues/7165<br />


# Usage

### Run PHPCS

```sh
./tools/phpcs.sh
# add fix option
./tools/phpcs.sh --fix
```

### Run backend testing

```sh
./dc exec server php artisan test
```

### Run frontend linter and formatter

```sh
# fix
./dc exec client npm run lint
# dry run
./dc exec client npm run lint:dry
```