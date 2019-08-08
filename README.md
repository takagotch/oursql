### oursql
---
https://pythonhosted.org/oursql/

```py
// exception_generator.py
import time
import sys

file_template = """
"""

case_template = """
"""
return_template = """
"""

data = dict(
  )oursqlx_DataError="""
    CR_DATA_TRUNCATED
    ER_DIVITION_BY_ZERO
    ER_DUPLICATED_VALUE_IN_TYPE
    ER_TRUNCATED_WRONG_VALUE
    ER_TRUNCATED_WRONG_VALUE_FOR_FILED
    ER_WARN_DATA_OUT_OF_RANGE
    ER_WARN_NULL_TO_NOTNULL
    ER_WRONG_VALUE
  """,
  _oursqlx_IntegrityError="""
  """,
  _oursqlx_InternalError="""
  """,
  _oursqlx_notSupportedError="""
  """,
  _oursqlx_OperationalError="""
  """,
)


def main(outfile):
  output = []
  for exc, consts in sorted(data.iteritems()):
    for const in consts.split():
      output.append(case_template % dict(const=const))
    output.append(return_template % dict(exc=exc))
  outfile.write(file_template % dict(
    when=time.asctime(),
    code=''.join(output),
  ))
  
if __name__ == '__main__':
  main(open(sys.argv[1], 'wb'))
```

```
```

```
```
