# Code Search OSINT

**Description** This is for OSINT resources to search if your company's code is listing anything senstive in public repos 

## Trufflehog
https://github.com/trufflesecurity/trufflehog \
OSINT Tool for secrets scanning. \
Install
```
git clone https://github.com/trufflesecurity/trufflehog.git
```
```
cd trufflehog; go install
```
Scan a repo for only verified secrets
```
trufflehog git https://github.com/trufflesecurity/test_keys --only-verified
```
Scan a Github Org for only verified secrets
```
trufflehog github --org=trufflesecurity --only-verified
```
Scan an S3 bucket for verified keys
```
trufflehog s3 --bucket=<bucket name> --only-verified
```
Scan individual files or directories
```
trufflehog filesystem path/to/file1.txt path/to/file2.txt path/to/dir
```
Scan a Docker image for verified secrets
```
trufflehog docker --image trufflesecurity/secrets --only-verified
```
Help
```
$ trufflehog git --help
usage: TruffleHog git [<flags>] <uri>

Find credentials in git repositories.

Flags:
  -h, --help                Show context-sensitive help (also try --help-long and --help-man).
      --debug               Run in debug mode.
      --trace               Run in trace mode.
      --profile             Enables profiling and sets a pprof and fgprof server on :18066.
  -j, --json                Output in JSON format.
      --json-legacy         Use the pre-v3.0 JSON format. Only works with git, gitlab, and github sources.
      --github-actions      Output in GitHub Actions format.
      --concurrency=8       Number of concurrent workers.
      --no-verification     Don't verify the results.
      --only-verified       Only output verified results.
      --filter-unverified   Only output first unverified result per chunk per detector if there are more than one results.
      --filter-entropy=FILTER-ENTROPY
                                 Filter unverified results with Shannon entropy. Start with 3.0.
      --config=CONFIG            Path to configuration file.
      --print-avg-detector-time
                                 Print the average time spent on each detector.
      --no-update           Don't check for updates.
      --fail                Exit with code 183 if results are found.
      --verifier=VERIFIER ...    Set custom verification endpoints.
      --archive-max-size=ARCHIVE-MAX-SIZE
                                 Maximum size of archive to scan. (Byte units eg. 512B, 2KB, 4MB)
      --archive-max-depth=ARCHIVE-MAX-DEPTH
                                 Maximum depth of archive to scan.
      --archive-timeout=ARCHIVE-TIMEOUT
                                 Maximum time to spend extracting an archive.
      --include-detectors="all"  Comma separated list of detector types to include. Protobuf name or IDs may be used, as well as ranges.
      --exclude-detectors=EXCLUDE-DETECTORS
                                 Comma separated list of detector types to exclude. Protobuf name or IDs may be used, as well as ranges. IDs defined here take precedence over the include list.
      --version             Show application version.
  -i, --include-paths=INCLUDE-PATHS
                                 Path to file with newline separated regexes for files to include in scan.
  -x, --exclude-paths=EXCLUDE-PATHS
                                 Path to file with newline separated regexes for files to exclude in scan.
      --exclude-globs=EXCLUDE-GLOBS
                                 Comma separated list of globs to exclude in scan. This option filters at the `git log` level, resulting in faster scans.
      --since-commit=SINCE-COMMIT
                                 Commit to start scan from.
      --branch=BRANCH            Branch to scan.
      --max-depth=MAX-DEPTH      Maximum depth of commits to scan.
      --bare                Scan bare repository (e.g. useful while using in pre-receive hooks)

Args:
  <uri>  Git repository URL. https://, file://, or ssh:// schema expected.
```




[Searchcode](https://searchcode.com/) \
[Publicwww](https://publicwww.com/) \
[Grep.app](https://grep.app/) \
[Custom Search Engine](https://cipher387.github.io/code_repository_google_custom_search_engines/) \
[explainshell](https://explainshell.com/) \
[Codefinder](https://codefinder.org/) \
[Github Search](https://github.com/search)

