
# Logger


##### Purpose

This is meant to build a standardized logging mechanism for all of my scripts.  Saving time, and preventing duplication of efforts.

![](https://github.com/ATLUTDVIPs/Logger/blob/b8d388d75a2b97b369cf4b4cda750368b394d8d1/pics/Colors.jpg)

##### Usage

```
logger = CustomLogger( __file__, "Debug" )
```

Call the call, setting the overall logging level.  Levels include: "Debug", "Info", "Warning", "Error", or "Critical"
The script will then take those values and convert them into the logging levels.  ex:  logging.DEBUG.  I do that to prevent the calling script from also having to include logging.

This will also create a log file matching the name of the calling script. 
ex:  If the script is test.py, then a log file will be created in the same directory, under /logs/test.log

All information sent to the Logger is written to the log file.  However, what is outputted to the screen can be adjusted.
![](https://github.com/ATLUTDVIPs/Logger/blob/d4f1b1991421f8d1394ab84984e20fb8b8ab1bc5/pics/Log.jpg)

Based on the default logging level, all logging for that ( and above ) are displayed.  All logging below that level is not printed.
ex:  By setting the logging level to Warning, logging levels of Critical, Error, and Warning are displayed, but Debug is not.  

```
logger = CustomLogger( __file__, "Warning" )
```

Debug info would still be written to the log.  By doing that, you can set a series of messages within your script, from info to Critical.   And have them output at the appropriate time.

```
    # Example usage:
    logger = CustomLogger( __file__, "Debug" )
    logger.Log( f"This is a message without a set type" )
    logger.Log( f"This is a debug message", "Debug" )
    logger.Log( f"This is an info message", "Info" )
    logger.Log( f"This is a warning message", "Warning" )
    logger.Log( f"This is an error message", "Error" )
    logger.Log( f"This is a critical message", "Critical" )
```

![](https://github.com/ATLUTDVIPs/Logger/blob/b8d388d75a2b97b369cf4b4cda750368b394d8d1/pics/Colors.jpg)


##### Requirements
- os
- logging - this is to bring in the different logging types ( DEBUG, INFO, WARNING, ERROR, CRITICAL )
- rich - This is only used for the colored printing.  But it greatly helps the warnings and errors stand out.

