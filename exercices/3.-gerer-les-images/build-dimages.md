# Build d'images

```docker
FROM alpine:3.17.3

# CMD ["ping", "--help"]

# ENTRYPOINT ["ping", "--help"]

# ENTRYPOINT ["ping"]
# CMD ["--help"]

ENTRYPOINT ["sleep"]
CMD ["infinity"]
```
