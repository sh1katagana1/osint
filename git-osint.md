# Git Threat Intel

## GitRecon

**Description:** OSINT tool to get information from a Github or Gitlab profile and find user's email addresses leaked on commits.
```
python3 gitrecon.py -s <choose either github or gitlab> <username> 
```

## Github Dork

**Description:** This tool lets me search github using github dorks and all through the command line. I can preface my commands with some environment variables to do an authenticated search

Search a single repo
```
github-dork.py -r techgaun/github-dorks
```

Search all repos of a user
```
github-dork.py -u techgaun
```

Search all repos of an organization
```
github-dork.py -u dev-nepal
```

Search as authenticated user
```
GH_USER=techgaun GH_PWD=<mypass> github-dork.py -u dev-nepal
```

Search using auth token
```
GH_TOKEN=<github_token> github-dork.py -u dev-nepal
```

Search a GitHub Enterprise instance
```
GH_URL=https://github.example.com github-dork.py -u dev-nepal
```
