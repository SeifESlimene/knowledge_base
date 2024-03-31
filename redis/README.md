## Some Useful Postgres Commands:

| Command     | Description |
| ----------- | ----------- |
| `redis-cli` | Open Redis Client |
| `ping` | Test Connection |
| `clear` | Clear Screen |
| `dbsize` | Show Number Of Keys |
| `keys '*'` | Get All Keys In Redis |
| `KEYS *image-cach*` | Get Keys With A Specific Pattern (Or Get Multiple Keys) |
| `set mykey "Seif"` | Set a key named ==Seif== |
| `get mykey` | Get The Value Of The Key Named ==mykey== |
| `expire mykey 10` | Set Expiration Date For A Key For 10 Seconds |
| `ttl mykey` | Show Time To Live For A Key |
| `KEYS "image-cache" | xargs redis-cli DEL` | Delete Keys |
| `flushdb` | Flush The Database
