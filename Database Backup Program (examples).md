# Database Backup Program (examples)
## Bash, Database 
### URL: https://www.jesusninoc.com/2014/11/26/database-backup-program-scripts-examples/
```Shell
#!/bin/sh
today=`date +%y-%m-%d-%H`;
mysqldump -h localhost -u user&nbsp;-pass --all-databases | gzip > /home/backups/bd$today.sql.gz ;

```
```Shell
#!/bin/sh
today=`date +%y-%m-%d-%H`;
mysqldump -h localhost -u user -pass --single-transaction \
--ignore-table=database.sessions \
database | gzip > /home/backups/bd$today.sql.gz ;

```
