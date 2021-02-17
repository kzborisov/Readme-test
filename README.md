The goal of the image uploader tool is to upload the generated images to Azure Storage and make them available in hawkBit.

In order to achieve this, two tools have been developed, Pullify and the HawkBit Image Uploader.

## Pullify

1.Pullify is a tool that generates a pull.json and compressed (.xz) file for a given target file.

2.Usage: 
```bash
pullify.sh <file> <outdir> <description>
```

3.Arguments:

   - file: File to compress and make pullable.
   - outdir: Subdir to store the results in (relative the to file).
   - description: Desctption to include the in the pull.json.

## HawkBit Image Uploader
1. HawkBit Image Uploader is a tool that uploads the generated images to Azure Storage and creates links in hawkBit.

This tool needs azure-cli. How to install
https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-apt?view=azure-cli-latest

Or run it from the test-environment docker image in which it is pre-installed.

2.Usage:
```bash
hawkbit_image_uploader.py [-h] --azure-account AZURE_ACCOUNT --azure-account-key AZURE_ACCOUNT_KEY --artifact-name ARTIFACT_NAME
                                 [--azure-artifact-validity-in-days AZURE_ARTIFACT_VALIDITY_IN_DAYS] --path PATH --hawkbit-server HAWKBIT_SERVER --hawkbit-password HAWKBIT_PASSWORD
                                 --hawkbit-username HAWKBIT_USERNAME [--description DESCRIPTION] [--version VERSION]
```

2.Arguments:
   - --azure-account
   - --azure-account-key
   - --artifact-name
   - --azure-artifact-validity-in-days
   - --path
   - --hawkbit-server
   - --hawkbit-password
   - --hawkbit-username
   - --description
   - --version