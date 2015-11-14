### Usage

This image can be used [mauchede/aria2](https://github.com/mauchede/aria2), [mauchede/webui-aria2](https://github.com/mauchede/webui-aria2) and [mauchede/vsftpd](https://github.com/mauchede/vsftpd). An example of usage is provided with `docker-compose`:

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

It is also possible to start this image in [rancher](http://rancher.com/rancher/) via [rancher-compose](https://github.com/rancher/rancher-compose):

```bash
# Copy the default configuration
cp docker-compose.yml.dist docker-compose.yml
cp rancher-compose.yml.dist rancher-compose.yml

# Start the project
RANCHER_URL="..." RANCHER_ACCESS_KEY="..." RANCHER_SECRET_KEY="..." rancher-compose -p seedbox up -d
```

### Contributing

1. Fork it.
2. Create your branch: `git checkout -b my-new-feature`.
3. Commit your changes: `git commit -am 'Add some feature'`.
4. Push to the branch: `git push origin my-new-feature`.
5. Submit a pull request.

### Links

* [docker-compose](https://docs.docker.com/compose/)
* [image "mauchede/aria2"](https://hub.docker.com/r/mauchede/aria2/)
* [image "mauchede/vsftpd"](https://hub.docker.com/r/mauchede/vsftpd/)
* [image "mauchede/webui-aria2"](https://hub.docker.com/r/mauchede/webui-aria2/)
* [mauchede/aria2](https://hub.docker.com/r/mauchede/aria2/)
* [rancher](http://rancher.com/rancher/)
* [rancher/compose](https://github.com/rancher/rancher-compose)
