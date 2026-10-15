# unraid-docker-icons

Public icon assets for Unraid Docker tiles. Point the `<Icon>` field in a container
template at a raw URL below and Unraid will fetch and cache it.

## Icons

| Container        | Icon                                              |
| ---------------- | ------------------------------------------------- |
| `llama-cpp`      | `icons/llama-cpp.png` (official llama.cpp logo)   |
| `postgresql` / `nuq-postgres` | `icons/postgresql.png`              |
| `rabbitmq`       | `icons/rabbitmq.png`                              |
| `redis`          | `icons/redis.png`                                 |

All icons are 256x256 PNG on a dark rounded tile (`#1b1f20`), matching the
llama.cpp icon style.

## Usage

Replace `BRANCH` with `main` (or a pinned commit SHA for stability) and set the
template `<Icon>` to the raw URL:

```xml
<Icon>https://raw.githubusercontent.com/bryann816a/unraid-docker-icons/main/icons/llama-cpp.png</Icon>
```

Other containers:

```xml
<Icon>https://raw.githubusercontent.com/bryann816a/unraid-docker-icons/main/icons/postgresql.png</Icon>
<Icon>https://raw.githubusercontent.com/bryann816a/unraid-docker-icons/main/icons/rabbitmq.png</Icon>
<Icon>https://raw.githubusercontent.com/bryann816a/unraid-docker-icons/main/icons/redis.png</Icon>
```

After editing the template, refresh Docker Manager and rebuild the container so
the `net.unraid.docker.icon` label updates:

```bash
php -q /usr/local/emhttp/plugins/dynamix.docker.manager/scripts/dockerupdate -v nonotify
php -q /usr/local/emhttp/plugins/dynamix.docker.manager/scripts/rebuild_container <NAME>
```

## Sources

- `llama-cpp.png` — official logo from [ggml-org/llama.cpp](https://github.com/ggml-org/llama.cpp) `media/llama1-icon-transparent.png`
- `postgresql.png`, `rabbitmq.png`, `redis.png` — brand marks from [Simple Icons](https://simpleicons.org/), rendered to PNG and placed on a dark tile

## License

MIT (icons remain subject to their respective brand guidelines).
