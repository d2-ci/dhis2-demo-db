# dhis2-demo-db

### DHIS 2 demo databases

This repository contains PostgreSQL dumps of demo databases.

To work with the database you can gunzip and restore it using psql:

gunzip dhis2-db-sierra-leone.sql.gz

psql -d dhis2 -U dhis -f dhis2-db-sierra-leone.sql

After modifying it you can create a dump using pg_dump. Please gzip and exclude the analytics and resource tables as they will be generated:

pg_dump dhis2 -U dhis -T analytics* -T _* | gzip > dhis2-db-sierra-leone.sql.gz

