# Data ops

Code for blog at http://www.startdataengineering.com/post/cicd-dbt

## 1. Fill in connection details

Fill in [profiles.yml](./profiles.yml) with your snowflake credentials

## 2. Develop dbt locally

Run the following commands from your terminal

```bash
docker run --rm -v $(pwd):/usr/app -v $(pwd):/root/.dbt fishtownanalytics/dbt:0.19.0 deps
docker run --rm -v $(pwd):/usr/app -v $(pwd):/root/.dbt fishtownanalytics/dbt:0.19.0 compile -- optionally, if you want to see the compiled SQL before running
docker run --rm -v $(pwd):/usr/app -v $(pwd):/root/.dbt fishtownanalytics/dbt:0.19.0 run
docker run --rm -v $(pwd):/usr/app -v $(pwd):/root/.dbt fishtownanalytics/dbt:0.19.0 test
docker run --rm -v $(pwd):/usr/app -v $(pwd):/root/.dbt fishtownanalytics/dbt:0.19.0 docs generate
docker run --rm -ip 8080:8080 -v $(pwd):/usr/app -v $(pwd)/:/root/.dbt fishtownanalytics/dbt:0.19.0 docs serve
docker run --rm -ip 8080:8080 -v $(pwd):/usr/app -v $(pwd)/:/root/.dbt fishtownanalytics/dbt:0.19.0 clean
```
