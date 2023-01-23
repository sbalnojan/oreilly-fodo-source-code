
# Resources
https://docs.python.org/3/library/ast.html
https://greentreesnakes.readthedocs.io/en/latest/tofrom.html


https://github.com/dbt-labs/jaffle_shop


# Setup 

```bash
./batect setup
```

Make sure you have two environment variables exported:
- KENSU_INGESTION_TOKEN
- KENSU_API_TOKEN

# Enter env



# Enter env
```bash
./batect dev
(inside the new container: )$ source dbt_env/bin/activate

... $ cd jaffle_shop; dbt debug
```
this should work out just fine, all inside docker compose.

```

```

 
# RUN

```bash
# git clone https://github.com/dbt-labs/jaffle_shop.git
cd jaffle_shop
export KSU_CONF_FILE="conf.ini"
dbt seed
dbt run
```

# Developer tool
Dumping AST code from python code into injection code :D

```bash
pip3 install astpretty
```

Then run for example
```python
import ast
import astpretty
example_code = '''

from dbt.task.kensu_reporting import maybe_report_postgres
maybe_report_postgres(conn_mngr=self, cursor=cursor, sql=sql)

'''

def pp(code = example_code):
  astpretty.pprint(ast.parse(code, mode="exec"), show_offsets=False, indent='  ')

pp()
```
