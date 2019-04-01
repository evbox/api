# Everon public APIs
Welcome to the start page of Everon public APIs! Here you can find a quick introduction guide to get on board using our public APIs in the fastest and easiest way possible.

## Few words about OpenAPI
The central element of our APIs is the [OpenAPI specification](https://github.com/OAI/OpenAPI-Specification) and the related toolset that makes it easier to use the APIs. These tools let you generating static documentation, running an interactive API browsing UI and last but not least generating high level clients for various programming languages that enables interaction with these APIs in a more convenient and - most of the time - type-safe way.

## Accessing the specification
In order to ensure that the public API specification is always in sync with the actual service available the service itself exposes the specification that has been used for the implementation. We encourage using this single source of truth unless you are interested in some previous version of the API that you can find in the specification archive in the [api](api) folder of this repository.

To fetch the current specification you can use the endpoints in the following format: `https://api.everon.io/api/[module]/v[version]?openapi` - for example https://api.everon.io/api/billing/v1?openapi. Here you will get back a description of the API that is compliant with the OpenAPI specification and can be used for further steps. The specification is available in YAML format as it's conscise and easy to read.

## Browsing the specification
Probably the most popular tool to browse OpenAPI specifications is [Swagger UI](https://swagger.io/tools/swagger-ui/). The easiest way to try out is to check out the [live demo](https://petstore.swagger.io/) and enter the URL of the API specification to be explored in the top bar. If you want to run it yourself then pull and run the Docker image as described [here](https://github.com/swagger-api/swagger-ui/blob/master/docs/usage/installation.md) in the Docker section.

## First interaction with the APIs
Note that Swagger UI not only allows you to browse the API but you can also try it out. Select the _Authorize_ option and setup your authorization key in order to use the service. You will see the request and response details and on top of that a [Curl](https://curl.haxx.se/) command that let's you try it out from the command line too.

If your preference is [Postman](https://www.getpostman.com/) to try the API out it's also simple, just don't forget to setup the _Authorization_ header to execute your requests.

## Generating clients
Depending on your architecture context it might be desirable to take advantage of automatically generated clients for these APIs. We recommend using the generator tools from [OpenAPITools](https://github.com/OpenAPITools/openapi-generator) that provides both a large set of supported languages and a good documentation how to get started.

## About API versioning
We follow the rules of [semantic versioning](https://semver.org/). As a consequence all major version changes imply also a URL change to be able to run new and old APIs in parallel that are not backwards compatible. This is the version that you see next to the module name, prefixed with a _v_, e.g. _v1_. All version numbers are present in the specification itself and the services always expose the latest deployed version as described above.