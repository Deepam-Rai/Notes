# Basic
Library import:
```python
import logging
```

Basic use:
```python
import logging

logger = logging.getLogger(__name__)

logger.error("message")
```

Customizing the log-records(more format specifies below):
```python
import logging  
  
  
logging.basicConfig(  
    level=logging.NOTSET,  
    format='%(asctime)s:%(levelname)s:%(name)s:%(lineno)s: %(message)s'  
)  
logger = logging.getLogger(__name__)
```


---
# Notes

>*Multiple calls to `logging.getLogger('someLogger')` return a reference to the same logger object. This is true not only within the same module, but also across modules as long as it is in the same Python interpreter process. It is true for references to the same object; additionally, application code can define and configure a parent logger in one module and create (but not configure) a child logger in a separate module, and all logger calls to the child will pass up to the parent*
~ [reference](https://docs.python.org/3/howto/logging-cookbook.html#using-a-context-manager-for-selective-logging)


----
# Docs
- https://docs.python.org/3/library/logging.html
- https://docs.python.org/3/howto/logging.html
- https://docs.python.org/3/howto/logging-cookbook.html#using-a-context-manager-for-selective-logging
- https://docs.python.org/3/library/logging.html#logrecord-attributes

---
# Logging levels

|Level|Numeric value|What it means / When to use it|
|---|---|---|
|logging.NOTSET[](https://docs.python.org/3/library/logging.html#logging.NOTSET "Link to this definition")|0|When set on a logger, indicates that ancestor loggers are to be consulted to determine the effective level. If that still resolves to `NOTSET`, then all events are logged. When set on a handler, all events are handled.|
|logging.DEBUG[](https://docs.python.org/3/library/logging.html#logging.DEBUG "Link to this definition")|10|Detailed information, typically only of interest to a developer trying to diagnose a problem.|
|logging.INFO[](https://docs.python.org/3/library/logging.html#logging.INFO "Link to this definition")|20|Confirmation that things are working as expected.|
|logging.WARNING[](https://docs.python.org/3/library/logging.html#logging.WARNING "Link to this definition")|30|An indication that something unexpected happened, or that a problem might occur in the near future (e.g. ‘disk space low’). The software is still working as expected.|
|logging.ERROR[](https://docs.python.org/3/library/logging.html#logging.ERROR "Link to this definition")|40|Due to a more serious problem, the software has not been able to perform some function.|
|logging.CRITICAL[](https://docs.python.org/3/library/logging.html#logging.CRITICAL "Link to this definition")|50|A serious error, indicating that the program itself may be unable to continue running.|

---
# log-record attributes

|Attribute name|Format|Description|
|---|---|---|
|args|You shouldn’t need to format this yourself.|The tuple of arguments merged into `msg` to produce `message`, or a dict whose values are used for the merge (when there is only one argument, and it is a dictionary).|
|asctime|`%(asctime)s`|Human-readable time when the [`LogRecord`](https://docs.python.org/3/library/logging.html#logging.LogRecord "logging.LogRecord") was created. By default this is of the form ‘2003-07-08 16:49:45,896’ (the numbers after the comma are millisecond portion of the time).|
|created|`%(created)f`|Time when the [`LogRecord`](https://docs.python.org/3/library/logging.html#logging.LogRecord "logging.LogRecord") was created (as returned by [`time.time()`](https://docs.python.org/3/library/time.html#time.time "time.time")).|
|exc_info|You shouldn’t need to format this yourself.|Exception tuple (à la `sys.exc_info`) or, if no exception has occurred, `None`.|
|filename|`%(filename)s`|Filename portion of `pathname`.|
|funcName|`%(funcName)s`|Name of function containing the logging call.|
|levelname|`%(levelname)s`|Text logging level for the message (`'DEBUG'`, `'INFO'`, `'WARNING'`, `'ERROR'`, `'CRITICAL'`).|
|levelno|`%(levelno)s`|Numeric logging level for the message ([`DEBUG`](https://docs.python.org/3/library/logging.html#logging.DEBUG "logging.DEBUG"), [`INFO`](https://docs.python.org/3/library/logging.html#logging.INFO "logging.INFO"), [`WARNING`](https://docs.python.org/3/library/logging.html#logging.WARNING "logging.WARNING"), [`ERROR`](https://docs.python.org/3/library/logging.html#logging.ERROR "logging.ERROR"), [`CRITICAL`](https://docs.python.org/3/library/logging.html#logging.CRITICAL "logging.CRITICAL")).|
|lineno|`%(lineno)d`|Source line number where the logging call was issued (if available).|
|message|`%(message)s`|The logged message, computed as `msg % args`. This is set when [`Formatter.format()`](https://docs.python.org/3/library/logging.html#logging.Formatter.format "logging.Formatter.format") is invoked.|
|module|`%(module)s`|Module (name portion of `filename`).|
|msecs|`%(msecs)d`|Millisecond portion of the time when the [`LogRecord`](https://docs.python.org/3/library/logging.html#logging.LogRecord "logging.LogRecord") was created.|
|msg|You shouldn’t need to format this yourself.|The format string passed in the original logging call. Merged with `args` to produce `message`, or an arbitrary object (see [Using arbitrary objects as messages](https://docs.python.org/3/howto/logging.html#arbitrary-object-messages)).|
|name|`%(name)s`|Name of the logger used to log the call.|
|pathname|`%(pathname)s`|Full pathname of the source file where the logging call was issued (if available).|
|process|`%(process)d`|Process ID (if available).|
|processName|`%(processName)s`|Process name (if available).|
|relativeCreated|`%(relativeCreated)d`|Time in milliseconds when the LogRecord was created, relative to the time the logging module was loaded.|
|stack_info|You shouldn’t need to format this yourself.|Stack frame information (where available) from the bottom of the stack in the current thread, up to and including the stack frame of the logging call which resulted in the creation of this record.|
|thread|`%(thread)d`|Thread ID (if available).|
|threadName|`%(threadName)s`|Thread name (if available).|
|taskName|`%(taskName)s`|[`asyncio.Task`](https://docs.python.org/3/library/asyncio-task.html#asyncio.Task "asyncio.Task") name (if available).|


----
# Adding colors to log-output

## using external library

Tutorial: https://pythonhowtoprogram.com/logging-in-python-3-how-to-output-logs-to-file-and-console/?utm_source=dev.to&utm_medium=cp&utm_campaign=ctalink&utm_term=logging-in-python-3-how-to-output-logs-to-file-and-console


```python
import logging, coloredlogs  
  
 
LOGGER_FIELD_STYLE = {  
    'asctime': {'color': 'green'},  
    'levelname': {'bold': True, 'color': 'black'},  
    'filename': {'color': 'cyan'},  
    'funcName': {'color': 'magenta'}  
}  
  
LOGGER_LEVEL_STYLES = {  
    'critical': {'bold': True, 'color': 'red'},  
    'debug': {'color': 'green'},  
    'error': {'color': 'red'},  
    'info': {'color': 'blue'},  
    'warning': {'color': 'yellow'}  
}


logging.basicConfig()  
logger = logging.getLogger(__name__)  
coloredlogs.install(  
    level=logging.NOTSET,  
    logger=logger,  
    fmt='%(asctime)s:%(levelname)s:%(filename)s:%(funcName)s():%(lineno)s: %(message)s',  
    field_styles=LOGGER_FIELD_STYLE,  
    level_styles=LOGGER_LEVEL_STYLES  
)


logger.error("error")  
logger.warning("warning")  
logger.critical("critica")  
logger.info("info")
```

