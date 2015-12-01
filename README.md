### Usage

This image uses [mauchede/aria2](https://github.com/mauchede/aria2), [mauchede/cakebox](https://github.com/mauchede/cakebox), [mauchede/webui-aria2](https://github.com/mauchede/webui-aria2) and [mauchede/vsftpd](https://github.com/mauchede/vsftpd). An example of usage is provided with `docker-compose`:

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
* [image "mauchede/aria2"](https://hub.docker.com/r/mauchede/aria2/)
* [image "mauchede/cakebox"](https://hub.docker.com/r/mauchede/cakebox/)
* [image "mauchede/seedbox"](https://hub.docker.com/r/mauchede/seedbox/)
* [image "mauchede/vsftpd"](https://hub.docker.com/r/mauchede/vsftpd/)
* [image "mauchede/webui-aria2"](https://hub.docker.com/r/mauchede/webui-aria2/)
* [mauchede/aria2](https://hub.docker.com/r/mauchede/aria2/)
* [seedboxes/pibox](https://github.com/seedboxes/pibox)
