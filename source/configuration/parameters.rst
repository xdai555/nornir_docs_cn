配置参数详解
===============

Nornir 的五个配置块及其对应参数的默认值和环境变量值。

core
----

``raise_on_error``
__________________

.. list-table::
   :widths: 15 85

   * - **描述**
     - 如果配置为 ``True``，在至少有一台主机执行任务失败时， (:obj:`nornir.core.Nornir.run`) 方法会抛出异常 :obj:`nornir.core.exceptions.NornirExecutionError` 
   * - **数据类型**
     - ``boolean``
   * - **默认值**
     - ``False``
   * - **是否需要该配置**
     - ``False``
   * - **系统环境变量**
     - ``NORNIR_CORE_RAISE_ON_ERROR``

runner
---------

``plugin``
__________

.. list-table::
   :widths: 15 85

   * - **描述**
     - 任务运行的线程插件，分为两种： ``Threaded`` （多线程）和 ``Serial`` （单线程）；必须注册该插件
   * - **数据类型**
     - ``string``
   * - **默认值**
     - ``Threaded``，默认线程数为 ``num_worker=20``
   * - **是否需要该配置**
     - ``False``
   * - **系统环境变量**
     - ``NORNIR_RUNNER_PLUGIN``

``options``
___________

.. list-table::
   :widths: 15 85

   * - **描述**
     - 需要给插件传递的参数，默认为空字典
   * - **数据类型**
     - ``object``
   * - **默认值**
     - ``{}``
   * - **是否需要该配置**
     - ``False``
   * - **系统环境变量**
     - ``NORNIR_RUNNER_OPTIONS``

inventory
---------

``plugin``
__________

.. list-table::
   :widths: 15 85

   * - **描述**
     - 要使用的主机清单插件名；必须注册该插件
   * - **数据类型**
     - ``string``
   * - **默认值**
     - ``SimpleInventory``
   * - **是否需要该配置**
     - ``False``
   * - **系统环境变量**
     - ``NORNIR_INVENTORY_PLUGIN``

``options``
___________

.. list-table::
   :widths: 15 85

   * - **描述**
     - 需要给插件传递的参数，默认为空字典
   * - **数据类型**
     - ``object``
   * - **默认值**
     - ``{}``
   * - **是否需要该配置**
     - ``False``
   * - **系统环境变量**
     - ``NORNIR_INVENTORY_OPTIONS``

``transform_function``
______________________

.. list-table::
   :widths: 15 85

   * - **描述**
     -  要使用的传输函数插件名；必须注册该插件
   * - **数据类型**
     - ``string``
   * - **默认值**
     - 
   * - **是否需要该配置**
     - ``False``
   * - **系统环境变量**
     - ``NORNIR_INVENTORY_TRANSFORM_FUNCTION``

``transform_function_options``
______________________________

.. list-table::
   :widths: 15 85

   * - **描述**
     - 需要给插件传递的参数，默认为空字典
   * - **数据类型**
     - ``object``
   * - **默认值**
     - ``{}``
   * - **是否需要该配置**
     - ``False``
   * - **系统环境变量**
     - ``NORNIR_INVENTORY_TRANSFORM_FUNCTION_OPTIONS``





ssh
---

``config_file``
_______________

.. list-table::
   :widths: 15 85

   * - **描述**
     - 指定 ``ssh`` 配置文件的路径，可以用来配置相关参数
   * - **数据类型**
     - ``string``
   * - **默认值**
     - ``~/.ssh/config``
   * - **是否需要该配置**
     - ``False``
   * - **系统环境变量**
     - ``NORNIR_SSH_CONFIG_FILE``





logging
-------

默认情况下，当调用 InitNornir 时，Nornir 会自动配置日志记录。

日志记录的配置可以根据以下选项进行修改。

如果想使用 Python 的 logging 模块配置日志，需要确保此配置中 ``enable`` 参数值为 False，以免发生冲突（Python 中日志配置为一次性的配置，只有第一次调用的配置会生效，随后的调用不会产生生效）。

``enabled``
___________

.. list-table::
   :widths: 15 85

   * - **描述**
     - 是否启用日志记录功能
   * - **数据类型**
     - ``boolean``
   * - **默认值**
     - ``None``
   * - **是否需要该配置**
     - ``False``
   * - **系统环境变量**
     - ``NORNIR_LOGGING_ENABLED``

``level``
_________

.. list-table::
   :widths: 15 85

   * - **描述**
     - 日志记录的级别（CRITICAL > ERROR > WARNING > INFO > DEBUG）
   * - **数据类型**
     - ``string``
   * - **默认值**
     - ``INFO``
   * - **是否需要该配置**
     - ``False``
   * - **系统环境变量**
     - ``NORNIR_LOGGING_LEVEL``

``log_file``
____________

.. list-table::
   :widths: 15 85

   * - **描述**
     - 保存到日志文件的名称
   * - **数据类型**
     - ``string``
   * - **默认值**
     - ``nornir.log``
   * - **是否需要该配置**
     - ``False``
   * - **系统环境变量**
     - ``NORNIR_LOGGING_LOG_FILE``

``format``
__________

.. list-table::
   :widths: 15 85

   * - **描述**
     - 日志信息的格式
   * - **数据类型**
     - ``string``
   * - **默认值**
     - ``%(asctime)s - %(name)12s - %(levelname)8s - %(funcName)10s() - %(message)s``
   * - **是否需要该配置**
     - ``False``
   * - **系统环境变量**
     - ``NORNIR_LOGGING_FORMAT``

``to_console``
______________

.. list-table::
   :widths: 15 85

   * - **描述**
     - 日志是否输出到控制台
   * - **数据类型**
     - ``boolean``
   * - **默认值**
     - ``False``
   * - **是否需要该配置**
     - ``False``
   * - **系统环境变量**
     - ``NORNIR_LOGGING_TO_CONSOLE``

``loggers``
___________

.. list-table::
   :widths: 15 85

   * - **描述**
     - 默认使用的 ``logger`` 对象
   * - **数据类型**
     - ``array``
   * - **默认值**
     - ``['nornir']``
   * - **是否需要该配置**
     - ``False``
   * - **系统环境变量**
     - ``NORNIR_LOGGING_LOGGERS``


``user_defined``
----------------

用户可以自行配置需要的 ``<k, v>`` 键值对， 使用时必须在 ``Config`` 对象下才能调用到该配置，例如： ``nr.config.user_defined.my_app_option`` 。