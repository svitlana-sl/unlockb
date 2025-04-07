#### Export/Import for DB
```shell
git clone repo_URL
```

```shell
ddev start
```

#### On a old machine from the project folder:
```shell
ddev export-db --file=./db.sql.gz
```
#### On a new machine from the project folder:
```shell
ddev import-db --src=./db.sql.gz
```

```shell
ddev composer require drupal/feeds
```

```shell
ddev composer require drupal/feeds_tamper
```