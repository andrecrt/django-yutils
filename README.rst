=====
Yutils (Yet/Why Another Utility Belt)
=====

Yutils is a collection of utilities for Django.

Quick start
-----------

1. Add "yutils" to your INSTALLED_APPS setting like this:

      INSTALLED_APPS = (
          ...
          'yutils',
      )
      
2. Create a 'logs' folder on your project's folder (if you don't have one already).
      
3. Add logger handler:

      LOGGING = {
          'version': 1,
          'disable_existing_loggers': False,
          'handlers': {
            ...
            'log_file_yutils': {
                'level': 'DEBUG',
                'class': 'logging.handlers.RotatingFileHandler',
                'filename': os.path.join(os.path.join(os.path.dirname( __file__ ), '..'), 'logs/yutils.log'),
                'maxBytes': '16777216', # 16megabytes
            },
        },
        'loggers': {
            ...
            'yutils': {
                'handlers': ['log_file_yutils'],
                'propagate': True,
                'level': 'DEBUG',
            }
        }
    }