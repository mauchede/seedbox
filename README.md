### Usage

This image can be used [mauchede/aria2](https://github.com/mauchede/aria2), [mauchede/webui-aria2](https://github.com/mauchede/webui-aria2) and [mauchede/vsftpd](https://github.com/mauchede/vsftpd). An example of usage is provided with `docker-compose`:

```
# Start the project
docker-compose up -d

# Add an user
docker exec -ti seedbox_seedbox_1 adduser-seedbox test pwd

# Go to the URL "localhost" with the credentials "test/pwd"

# Remove an user
docker exec -ti seedbox_seedbox_1 deluser-seedbox test
```

__Note__: Don't forget to change the token used between `aria2` and `webui-aria2`.

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
