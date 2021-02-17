The goal of the image uploader tool is to ... TODO
In order to achieve this, two tools have been developed, the Pullify tool and the HawkBit Image Uploader further described below.

## Pullify

1.Pullify is a tool that generates a pull.json and xz file for a given target file.

2.Usage: 
```bash
pullify.sh <file> <outdir> <description>
```

3.Arguments:
   file: File to compress and make pullable.
   outdir: Subdir to store the results in (relative to file).
   description: Desctption to include the in the pull.json.

## HawkBit Image Uploader
