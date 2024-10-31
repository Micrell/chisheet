# Interactive run

```sh
sudo docker run -it <image> bash
```

| OPTION    | ALIAS | VALUE                    | EFFECT                                             |
| --------- | ----- | ------------------------ | -------------------------------------------------- |
| --rm      |       |                          | auto remove the container when it exits            |
| --detach  | -d    |                          | run container in background and print container ID |
| --publish | -p    | HOST_PORT:CONTAINER_PORT | expose port                                        |
