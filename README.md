# Apsara runtime

Builds that [Apsara](https://github.com/EmilMoe/binaries) downloads on demand, separate from
the app's own releases (the same way Laravel Herd fetches PHP).

## PHP

Static PHP CLI builds made with [static-php-cli](https://github.com/crazywhalecc/static-php-cli)
by `.github/workflows/php.yml`, for macOS (Apple Silicon and Intel) and Windows (x64).

- Each version is a release `php-<version>` with one archive per platform.
- [`php.json`](php.json) lists the newest build per minor version, with URL and SHA256.
- Run the workflow from the Actions tab with the minor versions to build, e.g. `["8.4", "8.5"]`.

Extensions on both platforms: bcmath, bz2, calendar, ctype, curl, dom, exif, fileinfo, filter,
ftp, gd, iconv, intl, mbstring, mbregex, mysqli, mysqlnd, opcache, openssl, pdo, pdo_mysql,
pdo_pgsql, pdo_sqlite, pgsql, phar, redis, session, simplexml, soap, sockets, sodium, sqlite3,
tokenizer, xml, xmlreader, xmlwriter, zip, zlib. macOS also has gmp, pcntl, posix, readline,
xsl and imagick.

PHP 8.6 waits for static-php-cli v3.

## Redis

`redis-server` and `redis-cli` for macOS (Apple Silicon and Intel, macOS 12+), built from
Redis' official source releases by `.github/workflows/redis.yml`, so Apsara doesn't have to
compile Redis on the user's Mac. [`redis.json`](redis.json) lists the newest build per major
version. Windows uses the [redis-windows](https://github.com/redis-windows/redis-windows) builds.
