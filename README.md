# mdl-gen-midway

forked from [Kononnable/typeorm-model-generator](https://github.com/Kononnable/typeorm-model-generator)

通过已存在的数据库生成用于 `Midway` 的 `TypeORM` 实体。

其他详细文档和用法请参考 [Kononnable/typeorm-model-generator](https://github.com/Kononnable/typeorm-model-generator)

Supported db engines:
* Microsoft SQL Server
* PostgreSQL
* MySQL
* MariaDB
* Oracle Database
* SQLite


## Installation

```shell
npm i mdl-gen-midway
```

## Usage 

```shell
# 推荐
# 请替换配置信息
npx mdl-gen-midway -h localhost -p 3306 -d yourdbname -u root -x yourpassword -e mysql --noConfig --case-property none
```

There are two way to use this utility:
- Use step by step wizard which will guide you though the process - just type `npx mdl-gen-midway` in your console.
- Provide all parameters through command line(examples below)


Use `npx mdl-gen-midway --help` to see all available parameters with their descriptions. Some basic parameters below:
```shell
Usage: npx mdl-gen-midway -h <host> -d <database> -p [port] -u <user> -x
[password] -e [engine]

Options:
  --help                 Show help                                     [boolean]
  --version              Show version number                           [boolean]
  -h, --host             IP address/Hostname for database server
                                                          [default: "127.0.0.1"]
  -d, --database         Database name(or path for sqlite)            [required]
  -u, --user             Username for database server
  -x, --pass             Password for database server              [default: ""]
  -p, --port             Port number for database server
  -e, --engine           Database engine
          [choices: "mssql", "postgres", "mysql", "mariadb", "oracle", "sqlite"]
                                                              [default: "mssql"]
  -o, --output           Where to place generated models
                            [default: "./output"]
  -s, --schema           Schema name to create model from. Only for mssql
                         and postgres. You can pass multiple values
                         separated by comma eg. -s scheme1,scheme2,scheme3
  --ssl                                               [boolean] [default: false]

  --noConfig             Doesn't create tsconfig.json and
                         ormconfig.json         [布尔] [默认值: false]

  --cp, --case-property  Convert property names to specified case
                  [可选值: "pascal", "camel", "snake", "none"] [默认值: "camel"]
```
### Examples

* Creating model from local MySQL database
