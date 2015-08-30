# anvil-server

```
sudo npm install -g anvil-connect-cli

> spawn-sync@1.0.13 postinstall /usr/lib/node_modules/anvil-connect-cli/node_modules/yeoman-generator/node_modules/cross-spawn/node_modules/spawn-sync
> node postinstall

/usr/bin/nvl -> /usr/lib/node_modules/anvil-connect-cli/bin/nvl
anvil-connect-cli@0.1.8 /usr/lib/node_modules/anvil-connect-cli
├── async@1.4.2
├── chalk@1.1.1 (escape-string-regexp@1.0.3, supports-color@2.0.0, ansi-styles@2.1.0, has-ansi@2.0.0, strip-ansi@3.0.0)
├── mkdirp@0.5.1 (minimist@0.0.8)
├── underscore.string@3.2.0
├── update-notifier@0.5.0 (is-npm@1.0.0, string-length@1.0.1, repeating@1.1.3, configstore@1.2.1, semver-diff@2.0.0, latest-version@1.0.1)
├── fs-extra@0.22.1 (graceful-fs@4.1.2, jsonfile@2.2.1, rimraf@2.4.3)
├── request@2.61.0 (aws-sign2@0.5.0, forever-agent@0.6.1, stringstream@0.0.4, caseless@0.11.0, tunnel-agent@0.4.1, oauth-sign@0.8.0, form-data@1.0.0-rc3, isstream@0.1.2, json-stringify-safe@5.0.1, extend@3.0.0, node-uuid@1.4.3, combined-stream@1.0.5, qs@4.0.0, mime-types@2.1.5, http-signature@0.11.0, bl@1.0.0, tough-cookie@2.0.0, hawk@3.1.0, har-validator@1.8.0)
├── nash@2.0.3 (minimist@1.2.0, flat-arguments@1.0.2, lodash@3.10.1)
├── inquirer@0.9.0 (strip-ansi@3.0.0, ansi-regex@2.0.0, figures@1.3.5, cli-width@1.0.1, through@2.3.8, run-async@0.1.0, readline2@0.1.1, rx-lite@2.5.2, lodash@3.10.1)
├── yeoman-generator@0.20.3 (path-is-absolute@1.0.0, path-exists@1.0.0, read-chunk@1.0.1, detect-conflict@1.0.0, yeoman-welcome@1.0.1, yeoman-assert@2.0.0, rimraf@2.4.3, text-table@0.2.0, xdg-basedir@2.0.0, mime@1.3.4, user-home@2.0.0, dargs@4.0.1, debug@2.2.0, istextorbinary@1.0.2, nopt@3.0.3, run-async@0.1.0, shelljs@0.5.3, pretty-bytes@2.0.1, through2@2.0.0, cli-table@0.3.1, dateformat@1.0.11, diff@2.1.0, glob@5.0.14, findup-sync@0.2.1, mem-fs-editor@2.0.4, cross-spawn@2.0.0, github-username@2.0.0, class-extend@0.1.1, download@4.2.0, sinon@1.16.1, html-wiring@1.2.0, gruntfile-editor@1.0.0, lodash@3.10.1, inquirer@0.8.5)
└── yeoman-environment@1.2.7 (escape-string-regexp@1.0.3, log-symbols@1.0.2, diff@1.4.0, text-table@0.2.0, untildify@2.1.0, debug@2.2.0, mem-fs@1.1.0, globby@2.1.0, grouped-queue@0.3.0, lodash@3.10.1, inquirer@0.8.5)
```

```
cd projects/
~/projects mkdir myauthserver
~/projects cd myauthserver/
~/projects/myauthserver nvl

                                           _ _
                          /\              (_) |
                         /  \   _ ____   ___| |
               _____    / /\ \ | '_ \ \ / / | | _
              / ____|  / ____ \| | | \ V /| | || |
             | |     _/_/ _ _\_\_|_|_|\_/_|_|_|| |_
             | |    / _ \| '_ \| '_ \ / _ \/ __| __|
             | |___| (_) | | | | | | |  __/ (__| |_
              \_____\___/|_| |_|_| |_|\___|\___|\__|



http://anvil.io

A modern authorization server built to
authenticate your users and protect your APIs.
```

```
~/projects/myauthserver nvl init
? What would you like to name your Connect instance? myauthserver
? What (sub)domain will you use? connect.example.com
? Would you like to use Docker? Yes
? Would you like to run Redis? Yes
? Would you like to run nginx? Yes
? Would you like to create a self-signed SSL cert? Yes
? Country Name (2 letter code) US
? State or Province Name (full name) California
? Locality Name (eg, city) Los Angeles
? Organization Name (eg, company) Internet Widgits Pty Ltd
Initialized empty Git repository in /home/oren/projects/myauthserver/.git/
Generating RSA private key, 4096 bit long modulus
......................++
..............................++
unable to write 'random state'
e is 65537 (0x10001)
writing RSA key
Generating a 4096 bit RSA private key
..........................................................++
.......................................................++
unable to write 'random state'
writing new private key to '/home/oren/projects/myauthserver/nginx/certs/nginx.key'
-----
   create .gitignore
   create README.md
   create docker-compose.yml
   create connect/server.js
   create connect/config/production.json
   create connect/package.json
   create connect/.bowerrc
   create connect/bower.json
   create connect/Dockerfile
   create nginx/nginx.conf
   create nginx/conf.d/default.conf
   create nginx/conf.d/upstream.conf
   create nginx/Dockerfile
   create redis/etc/redis.conf
   create redis/Dockerfile
Connect all the things :)
```

```
docker-compose up
```

```
curl https://localhost -k
{"Anvil Connect":"Welcome","issuer":"https://connect.example.com","version":"0.1.50"}
```

Add to .gitignore
```
connect/config/keys/*
nginx/certs/*
redis/data/*
```
