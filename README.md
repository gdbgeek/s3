# s3

A Windows command-line utility for Amazon's S3 web services that requires no installation, is a single .EXE file with no DLLs, and requires only .NET 2.0, so will work on a plain vanilla Windows installation.

Forked from code on https://s3.codeplex.com/ to fix some bugs.

## Things I've fixed;

1. Correctly handling folders within buckets when doing a recursive "get"
2. Added ListBuckets and ListKeys commands which just creates a plain list (i.e. no attributes) in order to pipe output to other command line functions (eg write list of keys to text file and then filter list to another text file).
3. Ignore checksum for multi-part uploads (anything over 15728640 bytes or 15mb) as the S3 doesnt report the correct checksum.

## Things I still need to fix;

1. Still only works on S3 buckets in US Standard region (other regions give an access denied error). This is a known issue with the original source code.
