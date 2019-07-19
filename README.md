[![CircleCI](https://circleci.com/gh/aymen94/io-utils-test.svg?style=svg)](https://circleci.com/gh/aymen94/io-utils-test)

# io-utils test OpenAPI 3.0

This is test for [io-utils](https://github.com/teamdigitale/io-utils) module
## OpenAPI 3 support

Our goal is to implement support of OAS3 specifications 
while maintaining a backward compatibility with the current swagger2 implementation.

The strategy is the following:

- [x] identify an updated version of Swagger-Parser library which now
   supports OAS3 via the OpenAPI-Types which replaces the old
   Swagger-Schema-Official library;

- [x] move the actual Swagger2 code to the new OpenAPI-Types so that
   all io-utils, io-functions, io-functions-commons test works. 
   To ensure that related projects work, we set up some circleci
   builds linked to the io-utils github branch instead of the
   version distributed on npm;

- [x] plan OAS3 tests based on the existing testlist

- [x] create a function to detect the spec version (OAS3 or Swagger2):
   all old functions now receive the spec version as an input parameter;

- [x] create two different njk models: one unchanged for Swagger2, so 
   that we retain compatibility with the previous code, and a new one
   for OAS3 where we are free to modify anything that is needed to 
   implement new features;

We think that this strategy gives us enough specification agility and
can be applied iteratively to other specifications, as you just have to:

- modify the detect-version function;
- provide a new njk model for the new spec kind.
