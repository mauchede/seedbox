# README

Uploading and downloading files

## Usage

This image uses [timonier/aria2](https://github.com/timonier/aria2), [timonier/cakebox](https://github.com/timonier/cakebox) and [timonier/webui-aria2](https://github.com/timonier/webui-aria2). An example of usage is provided with `docker-compose`:

```sh
# Prepare the project

export RPC_SECRET="0fd9094d-76ca-4a76-be82-eaf513a1ccd2"

# Start the project

docker-compose up -d

# Add a user

docker-compose exec seedbox adduser-seedbox test pwd

# Go to "http://localhost/" with the credentials "test/pwd"

# Remove a user

docker-compose exec seedbox deluser-seedbox test
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
* [image "timonier/webui-aria2"](https://hub.docker.com/r/timonier/webui-aria2/)
* [just-containers/6-overlay](https://github.com/just-containers/s6-overlay)
* [seedboxes/pibox](https://github.com/seedboxes/pibox)
* [timonier/syslog-stdout](https://github.com/timonier/syslog-stdout)
* [timonier/version-lister](https://github.com/timonier/version-lister)
