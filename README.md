# README

## Usage

This image uses [timonier/aria2](https://github.com/timonier/aria2), [timonier/cakebox](https://github.com/timonier/cakebox), [timonier/webui-aria2](https://github.com/timonier/webui-aria2) and [timonier/vsftpd](https://github.com/timonier/vsftpd). An example of usage is provided with `docker-compose`:

```sh
# Override docker-compose
cat > docker-compose.override.yml << "EOF"
version: '2'

services:
    aria2:
        command:
            - --dir=/var/lib/seedbox
            - --enable-dht=false
            - --enable-rpc
            - --log=-
            - --log-level=notice
            - --max-concurrent-downloads=10
            - --quiet
            - --rpc-listen-all=true
            - --rpc-secret=$RPC_SECRET
            - --rpc-save-upload-metadata=false
    webui-aria2:
        environment:
            - "RPC_SECRET=$RPC_SECRET"
EOF

# Prepare the project
export RPC_SECRET="0fd9094d-76ca-4a76-be82-eaf513a1ccd2"

# Start the project
docker-compose up -d

# Add an user
docker-compose run seedbox adduser-seedbox test pwd

# Go to the URL "localhost" with the credentials "test/pwd"

# Remove an user
docker-compose run seedbox deluser-seedbox test
```

__Note__: Don't forget to change the token used between `aria2` and `webui-aria2`. Use `bin/generate-secret` if you want to generate a strong token.

## Contributing

1. Fork it.
2. Create your branch: `git checkout -b my-new-feature`.
3. Commit your changes: `git commit -am 'Add some feature'`.
4. Push to the branch: `git push origin my-new-feature`.
5. Submit a pull request.

__Note__: Use the script `bin/build` to test your modifications locally.

## Links

* [docker-compose](https://docs.docker.com/compose/)
* [image "mauchede/seedbox"](https://hub.docker.com/r/mauchede/seedbox/)
* [image "timonier/aria2"](https://hub.docker.com/r/timonier/aria2/)
* [image "timonier/cakebox"](https://hub.docker.com/r/timonier/cakebox/)
* [image "timonier/vsftpd"](https://hub.docker.com/r/timonier/vsftpd/)
* [image "timonier/webui-aria2"](https://hub.docker.com/r/timonier/webui-aria2/)
* [s6-overlay](https://github.com/just-containers/s6-overlay)
* [syslog-stdout](https://github.com/timonier/syslog-stdout)
* [seedboxes/pibox](https://github.com/seedboxes/pibox)
