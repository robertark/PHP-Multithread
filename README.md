    
## Authors & contact


Al-Fallouji Bashar 
    - bashar@alfallouji.com

    
## Documentation and download


Latest version is available on github at :
    - http://github.com/alfallouji/PHP-Multithread/


## License


This Code is released under the GNU LGPL

Please do not change the header of the file(s).

This library is free software; you can redistribute it and/or modify it 
under the terms of the GNU Lesser General Public License as published 
by the Free Software Foundation; either version 2 of the License, or 
(at your option) any later version.

This library is distributed in the hope that it will be useful, but 
WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY 
or FITNESS FOR A PARTICULAR PURPOSE.

See the GNU Lesser General Public License for more details.


## Description


This library provides a lightweight / simple PHP Oriented Object classe to handle multi-threading. Check the sample folder for examples on how to use it. This library requires to have the pcntl (http://php.net/pcntl) extension installed and it will only work with unix distributions.

## Setup 

You can use composer to use this library.

```
{
    "require": {
		"alfallouji/php_multithread": "*"
    }
}
```


## Usage

This client does not rely or depend on any framework and it should be fairly easy to integrate with your own code. You can use composer or your own custom autoloader.

The sample folder contains example on how to use this library.

## Example

### Multi-threading a simple task
```
require(__DIR__ . '/../Threading/Multiple.php');
require(__DIR__ . '/../Threading/Task/Base.php');
require(__DIR__ . '/../Threading/Task/Sample.php');


$maxThreads = 5;
echo 'Example of the multi-thread manager with ' . $maxThreads . ' threads' . PHP_EOL . PHP_EOL;
$params = array();
$exampleTask = new Threading\Task\Example($params);
$multithreadManager = new Threading\Multiple();

$cpt = 0;
while (++$cpt <= 30)
{
    $multithreadManager->start($exampleTask);
}
```
