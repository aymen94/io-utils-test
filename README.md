# io-utils test OpenAPI 3.0

This is test for [io-utils](https://github.com/teamdigitale/io-utils) module

## OpenAPI support

The current strategy is to maintain backward compatibility.
With the ability to accept the swagger and oas3 specifications, after automatically detecting the version of the specification.

To support OpenAPI we adopt this strategy:
  - function to detect the version of Spec. in use
  - added different models
  - updated packages
  - added new schemas for support new version

Has been created tests for oas3 based on current tests, added different templates for swagger 2.0 and OpenAPI 3.0.
we are updated `swagger-parser`, because the current version does not support OpenAPI 3.0
Removed `swagger-schema-official` and replace with `openapi-types`, because swagger-schema-official does not support OpenAPI 3.0
Now we are in the testing phase.
