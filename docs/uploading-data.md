# Uploading data to the CPD

The CPD is open to uploads from anyone in the catalyst research community. Uploading is done via calls to the CPD application programming interface (API). We have published a [cpd-batch-upload](https://github.com/NREL/cpd-batch-upload) Python library that takes a file as input and makes the necessary API calls. Uploads are subject to the [curation](/curation) process to ensure data quality.

## Installing the Python library

Follow the instructions in the [cpd-batch-upload](https://github.com/NREL/cpd-batch-upload) repository on GitHub to get started. Detailed [documentation](https://github.com/NREL/cpd-batch-upload#building-the-documentation) for the library is included and can be built using Sphinx.

## Formatting data in CSV or JSON for upload

To upload using the [cpd-batch-upload](https://github.com/NREL/cpd-batch-upload) Python library, you will first need a properly formatted comma-separated values (CSV) or JavaScript Object Notation (JSON) file containing the data to be uploaded. Examples of CSV and JSON (JSON coming soon) files can be found [here](https://github.com/NREL/cpd-batch-upload/tree/master/input_examples), and the parameter names in those files correspond to those in the [parameter guide](/parameter-guide).

## Converting computational output files to CSV format

As an example of a workflow to convert computational output files to a format that the cpd-batch-upload library can use, see the [VASP integration example](https://github.com/NREL/cpd-batch-upload/tree/master/integration_examples/VASP) on GitHub. Let us know if you'd like to work with us on another example.

## Obtaining a username and password

In order to authenticate when making upload calls to the API, you will need a username and password on the ChemCatBio [Data Hub](https://datahub.chemcatbio.org/). To sign up, click the "Register" link. You will be contacted by the Energy Materials Network Data Hub team asking which project you are working with; please tell them you would like to upload data to the CPD. Your account will then be activated allowing you to authenticate using the upload script.

## Running the upload scripts from CSV or JSON files

To start uploading once you have completed the steps above, see [running the package](https://github.com/NREL/cpd-batch-upload#running-the-package) instructions on GitHub.

## Need help?

Need help with the upload process? Please send us a message anytime at cpd@nrel.gov and we will be happy to work with you.
