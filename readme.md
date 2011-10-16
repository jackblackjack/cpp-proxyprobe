# cpp-proxyprobe

Proxy Probe is a suite of proxy scripts started in Python, that have been partially converted (proxy checker, proxy importer tool) to C++. (Note: this was created few years ago, but felt like open sourcing it now). Usage code for [nextgen](https://github.com/ericmuyser/nextgen).

## Features

* Identifies different types of proxies: http (transparent, anonymous, elite), socks (socks4, socks5).
* Validate many proxies in parallel.
* Performance optimized code. 
* Database of proxies. (Currently more than 99% of the 200,000 are invalid or dead.)

## Requirements

Proxy Probe has been compiled/tested (a few years ago) with:

* Compiler: GCC 4.5
* Platform: Ubuntu 9.1 with Code::Blocks 8.02
* Libraries: Boost 1.40, Asio 1.4.1

## Getting Started

* Clone the repo: `git clone git@github.com:ericmuyser/cpp-proxyprobe.git`
* Restore the `db/proxies.sql` file to MySQL to database: `proxies`.
* Set your database configuration in the `src/proxy_checker.cpp` file.
* Build the project from the `mk` folder and run the resulting binary in the `bin` folder.

## Roadmap

* Identify different states: CoDeen, agency, etc.
* Improve invalid handling: cannot connect, 0 transfer time, odd responses.
* Remove dead proxies and restart with a fresh set.
* Detect if the proxy is browser compatible (cookies, etc).
* Maintain a reliability/performance rating attributes for the proxy.

## Notes

On Linux/Mac OS X you need to increase your file descriptor/socket limit. In the **same** terminal tab before you run the script, run this command: `ulimit -n 1024`

## Disclaimer

Distributed under the free and open source MIT license. Provided without warranty of any kind, express or implied. In no event shall we be held liable for any claim, damages or other liability.