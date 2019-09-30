# WSDL to Go
[![Gitter](https://badges.gitter.im/Join Chat.svg)](https://gitter.im/hooklift/gowsdl?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![GoDoc](https://godoc.org/github.com/reillywatson/gowsdl?status.svg)](https://godoc.org/github.com/reillywatson/gowsdl)
[![Build Status](https://travis-ci.org/hooklift/gowsdl.svg?branch=master)](https://travis-ci.org/hooklift/gowsdl)

Generates Go code from a WSDL file.

### Features
* Supports only Document/Literal wrapped services, which are [WS-I](http://ws-i.org/) compliant
* Attempts to generate idiomatic Go code as much as possible
* Generates Go code in parallel: types, operations and soap proxy
* Supports: 
	* WSDL 1.1
	* XML Schema 1.0
	* SOAP 1.1
* Resolves external XML Schemas recursively, up to 5 recursions.
* Supports providing WSDL HTTP URL as well as a local WSDL file

### Not supported
* Setting SOAP headers
* SOAP 1.2 and HTTP port bindings
* WS-Security
* WS-Addressing
* MTOM binary attachments
* UDDI

### Caveats
* Please keep in mind that the generated code is just a reflection of what the WSDL is like. If your WSDL has duplicated type definitions, your Go code is going to have the same and will not compile.

### Usage
```
gowsdl [OPTIONS]

Application Options:
  -v, --version     Shows gowsdl version
  -p, --package=    Package under which code will be generated (myservice)
  -o, --output=     File where the generated code will be saved (myservice.go)
  -i, --ignore-tls  Ignores invalid TLS certificates. It is not recomended for production. Use at your own risk
                    (false)

Help Options:
  -h, --help        Show this help message
```
