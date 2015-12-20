### Usage

This image uses [timonier/aria2](https://github.com/timonier/aria2), [timonier/cakebox](https://github.com/timonier/cakebox), [timonier/webui-aria2](https://github.com/timonier/webui-aria2) and [timonier/vsftpd](https://github.com/timonier/vsftpd). An example of usage is provided with `docker-compose`:

```bash
# Copy the default configuration
cp docker-compose.yml.dist docker-compose.yml

# Start the project
docker-compose up -d

# Add an user
docker exec -ti seedbox_seedbox_1 adduser-seedbox test pwd

# Go to the URL "localhost" with the credentials "test/pwd"

# Remove an user
docker exec -ti seedbox_seedbox_1 deluser-seedbox test
```

__Note__: Don't forget to change the token used between `aria2` and `webui-aria2`. Use `bin/generate-secret` if you want to generate a strong token.

### Contributing

1. Fork it.
2. Create your branch: `git checkout -b my-new-feature`.
3. Commit your changes: `git commit -am 'Add some feature'`.
4. Push to the branch: `git push origin my-new-feature`.
5. Submit a pull request.

__Note__: Use the script `bin/build` to test your modifications locally.

### Links

* [docker-compose](https://docs.docker.com/compose/)
* [image "mauchede/seedbox"](https://hub.docker.com/r/mauchede/seedbox/)
* [image "timonier/aria2"](https://hub.docker.com/r/timonier/aria2/)
* [image "timonier/cakebox"](https://hub.docker.com/r/timonier/cakebox/)
* [image "timonier/vsftpd"](https://hub.docker.com/r/timonier/vsftpd/)
* [image "timonier/webui-aria2"](https://hub.docker.com/r/timonier/webui-aria2/)
* [seedboxes/pibox](https://github.com/seedboxes/pibox)
