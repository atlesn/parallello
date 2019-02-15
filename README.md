# Parallello
Parallello is an engine to run different programming languages and automatically parallelize the execution.

## Why?
Often, order of excecution is not important and tasks in a program may be split on several threads. Parallello aims to make this as the default way of executing a program. Examples of this may be a web server formatting misc. data from an SQL server and sending it to the user. Different queries can be started at the same time.

## TODO
- Write engine. The engine may run many different languages.
- Implement a language module, e.g. Common Lisp.

## Engine
- The engine starts with calling a module to parse the code and create an execution plan
- Some threads are started and held stand by
- Whenever parrallelism is possible, tasks are distributed to the threads

## When parallellism can take place
- A function is called which has no side effects and we do not use its return value
- A loop is run in which order doesn't matter
- A function is to be called with two or more functions as argument, these are called simultaneously. This also goes for operators, while some languages treat operators as functions.
