# bash-backup
Simple backup shell script by bash v4.*.

## Usage
```
$ git clone git@github.com:newsdict/bash-backup.git
$ cd bash-backup
$ cp env-example .env
```
 edit `.env` file
```
$ sh backup.sh
```
### Multiple Targets
```
$ git clone git@github.com:newsdict/bash-backup.git
$ cd bash-backup
$ cp env-example .env-sample1
```
edit `.env-sample1` file
```
$ cp env-example .env-sample2
```
edit `.env-sample2` file
```
$ sh backup.sh sample1
$ sh backup.sh sample2
```

## Environments

### Temporary Directory
```
temporary_directory=tmp
```

### log name
```
log_name=logs/backup.$now.log
```

### backup filename
```
backup_filename=backup
```

### display messages
```
display_messages=1
```

### Execute archive
```
archive=1
```

### Archive paths or files
```
declare -a archive_paths=(
	"/var/www/html"
	"/etc/nginx"
)
```


### Compression type of backup
```
commpression_type=gzip
```
*_gzip: *.tar.gz_
*_zip: *.zip_
*_bzip2: *.tar.bz2_

### Execute database
```
database=1
```

### Database Type for Dump
```
declare -A database_conf=(
	["engine"]="mysql" # mysql only
	["name"]="sample1_database" # database name
	["username"]="user1" # username
	["password"]="pass" # password
	["host"]="127.0.0.1" # host
	["port"]=3306 # port
)
```

### Storage type for backup files
```
storage_type=s3
```

*_`s3` only_

### s3 info
```
declare -A s3_conf=(
	["keep"]=5
	["access_key"]=""
	["secret"]=""
	["bucket"]="backup"
	["path"]="test"
	["region"]="ap-northeast-1"
)
```