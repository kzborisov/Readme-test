Another new line from main

The goal of the image uploader tool is to upload the generated images to Azure Storage and make them available in hawkBit. In order to achieve this, two tools have been developed, Pullify and HawkBit Image Uploader.

## Pullify

Pullify is a tool that generates a pull.json and compressed (*.xz) file for a given target file.

The pull.json file contains all the metadata for the *.xz file.

### Usage: 
```bash
pullify.sh <file> <outdir> <description>
```
New file from newbranch
### Arguments:
   - file: File to compress and make pullable.
   - outdir: Subdir to store the results in (relative the to file).
   - description: Desctption to include the in the pull.json.

## HawkBit Image Uploader

The purpose of the HawkBit Image Uploader tool is to upload the generated images to Azure Storage and then modify hawkBit to show that version by creating links.

The tool needs azure-cli. [How to install](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-apt?view=azure-cli-latest).
It can be also run from the test-environment docker image in which it is pre-installed.

### Usage:

```bash
hawkbit_image_uploader.py [-h] --azure-account AZURE_ACCOUNT
                               --azure-account-key AZURE_ACCOUNT_KEY
                               --artifact-name ARTIFACT_NAME
                               [--azure-artifact-validity-in-days AZURE_ARTIFACT_VALIDITY_IN_DAYS]
                               --path PATH
                               --hawkbit-server HAWKBIT_SERVER
                               --hawkbit-password HAWKBIT_PASSWORD
                               --hawkbit-username HAWKBIT_USERNAME
                               [--description DESCRIPTION]
                               [--version VERSION]
```

### Arguments:
All of the arguments will be provided by the Lely IT department.

   - Required:
      - --azure-account
      - --azure-account-key
      - --artifact-name
      - --azure-artifact-validity-in-days
      - --path
      - --hawkbit-server
      - --hawkbit-password
      - --hawkbit-username
   - Optional:
      - --description  - product name followed by the git hash.
      - --version      - branch name (by default).

## Mender Image Uploader - Deprecated.
The mender storage is no longer in use.
