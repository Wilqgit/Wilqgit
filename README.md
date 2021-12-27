- 👋 Hi, I’m @Wilqgit
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Wilqgit/Wilqgit is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
# enable/disable checking for application updates on startup

check-for-app-update: true

# same as --fail-on ; upon scanning, if a severity is found at or above the given severity then the return code will be 1

# default is unset which will skip this validation (options: negligible, low, medium, high, critical)

fail-on-severity: ''

# same as -o ; the output format of the vulnerability report (options: table, json, cyclonedx)

output: "table"

# same as -s ; the search space to look for packages (options: all-layers, squashed)

scope: "squashed"

# same as -q ; suppress all output (except for the vulnerability list)

quiet: false

# same as --file; write output report to a file (default is to write to stdout)

file: ""

# a list of globs to exclude from scanning. same as --exclude ; for example:

# exclude:

#   - '/etc/**'

#   - './out/**/*.json'

exclude:

db:

  # check for database updates on execution

  auto-update: true

  # location to write the vulnerability database cache

  cache-dir: "$XDG_CACHE_HOME/grype/db"

  # URL of the vulnerability database

  update-url: "https://toolbox-data.anchore.io/grype/databases/listing.json"

# options when pulling directly from a registry via the "registry:" scheme

registry:

  # skip TLS verification when communicating with the registry

  # GRYPE_REGISTRY_INSECURE_SKIP_TLS_VERIFY env var

  insecure-skip-tls-verify: false

  # use http instead of https when connecting to the registry

  # GRYPE_REGISTRY_INSECURE_USE_HTTP env var

  insecure-use-http: false

  # credentials for specific registries

  auth:

    - # the URL to the registry (e.g. "docker.io", "localhost:5000", etc.)

      # GRYPE_REGISTRY_AUTH_AUTHORITY env var

      authority: ""

      # GRYPE_REGISTRY_AUTH_USERNAME env var

      username: ""

      # GRYPE_REGISTRY_AUTH_PASSWORD env var

      password: ""

      # note: token and username/password are mutually exclusive

      # GRYPE_REGISTRY_AUTH_TOKEN env var

      token: ""

    - ... # note, more credentials can be provided via config file only

log:

  # location to write the log file (default is not to have a log file)

  file: ""

  # the log level; note: detailed logging suppress the ETUI

  level: "error"

  # use structured logging

  structured: false
