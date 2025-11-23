# cesp

Code Execution &amp; Structure Profiler for PHP

## Overview

`cesp_log` is a lightweight single-function **Code Execution &amp; Structure Profiler**
for PHP that collects detailed execution metrics, including:

* Memory usage
* Allocated memory
* Peak memory usage
* Execution time
* Included files
* Declared classes, interfaces, traits
* User-defined functions and constants

It is designed for micro-benchmarking, architectural analysis, and research on software complexity.
Moreover, it can be used for studying structural overhead of any PHP framework or library.
It works in any PHP environment without dependencies.

Count and list of:

  * Included files
  * User-defined classes
  * User-defined interfaces
  * User-defined traits
  * User-defined functions
  * User-defined constants

Returns a PHP array with complete metrics or optional JSON output for easy logging.


## Example

```php
<?php
require 'cesp_log.php';

// Start profiling
cesp_log('start');

// your code here
echo "Hello World";

// End profiling
cesp_log('end');

// print JSON
cesp_log('print');

// or retrieve the data
// $data = cesp_log();

```

Output format example:

```
cesp_log--{ ... JSON DATA ... }--cesp_log
```

This bounded format makes it easy to extract logs from web output or CLI tools.

## Returned Data Structure

`cesp_log()` returns an associative array with the following fields:

```php
[
  'version' => '2025.2',
  'memory_usage_start' => int,
  'memory_usage_end'   => int,
  'memory_usage_delta' => int,
  'memory_allocated_start' => int,
  'memory_allocated_end'   => int,
  'memory_allocated_delta' => int,
  'memory_peak_start'  => int,
  'memory_peak_end'    => int,
  'memory_real_peak_start' => int,
  'memory_real_peak_end'   => int,
  'microtime_start' => float,
  'microtime_end'   => float,
  'microtime_delta' => float,
  'num_included_files' => int,
  'num_declared_classes' => int,
  'num_declared_interfaces' => int,
  'num_declared_traits' => int,
  'num_defined_functions' => int,
  'num_defined_constants' => int,
  'included_files' => [...],
  'declared_classes' => [...],
  'declared_interfaces' => [...],
  'declared_traits' => [...],
  'defined_functions' => [...],
  'defined_constants' => [...]
]
```

## License

Licensed under the **Mozilla Public License 2.0**.
See: [https://www.mozilla.org/en-US/MPL/2.0/](https://www.mozilla.org/en-US/MPL/2.0/)


## Contributing

Bug reports, feature requests, and pull requests are welcome.
Please open an issue to discuss significant changes.
