# fhir-questionnaireresponse-validation
Basic example of validating a FHIR QuestionnaireResponse against a Questionnaire using the FHIR validator.

### Prerequisites

[Download the latest FHIR Validator CLI](https://github.com/hapifhir/org.hl7.fhir.core/releases/latest/download/validator_cli.jar) and move `validator_cli.jar` to the root of this project.

### Example

Running `sh validate.sh` will run an example script which validates the `qr-pass.json` QuestionnaireResponse resource. This resource should pass validation.

Running `sh validate-fail.sh` will run an example script which validates the `qr-fail.json` QuestionnaireResponse resource. This resource should fail validation as it is missing a required property which is defined in the Questionnaire, which is in the example `ig` folder.

### Gotchas

1) The FHIR Validator does not appear to include resources which are listed as `example` usage as part of it's validation process, so ensure that all Questionnaire resources are NOT `example` type. You can check this by downloading the `pacakge.tgz` of the Implementation Guide and ensuring you resource is not in the `examples` directory once unarchived.

2) The validator does not attempt to 'resolve' the questionnaire resource over http, it must find the canonical url as part of the Implementation Guide used for validation.


