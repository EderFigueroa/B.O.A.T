---
name: code-explorer
description: Describe what this code base do
license: MIT
compatibility: opencode
metadata:
  audience: maintainers
  workflow: github
---


##  Workflow
- [] 1. survery the repo
- [] 2. Identify purpose 
- [] 3. Identify entry points
- [] 4. Map main components and relationships
- [] 5. Trace up to three important flows end to end
- [] 6. Write results in html
- [] 7. Report short summary



##  1. Survey

Read first, in this order: README*, docs/, top-level manifests (package.json, pyproject.toml, requirements*.txt, go.mod, pom.xml, build.gradle, Cargo.toml, Gemfile), Makefile/justfile,

• github/workflows/, Dockerfile*, docker-compose*. List the top two directory levels, skipping node_modules, venv, dist, build, vendor, and git.

For large repos, launch parallel explore subagents (one per top-level area instead of reading everything yourself.

##  2. Purpose and entry points

Find where execution starts: main, CLI definitions, server bootstrap, HTTP route registration, job/DAG definitions, Lambda/function handlers, exported library API. Describe the purpose in 2 - 3 plain sentences: who uses this, and what it does for them.


##   3. Components and relationships

Pick the 5-12 classes/modules that matter most (high fan-in, entry points, core domain models).

For each one, record its responsibility, its file path, and what it depends on. Skip utilities and boilerplate.

##  4. Key flows

Trace the one or two most important paths (e.g. an HTTP request reaching the DB, a job going from trigger to output) using real function names.

##  5. Infrastructure

Look for: Terraform (*.tf), Helm charts, k&s manifests, CloudFormation/CDK/SAM, Pulumi, serverless.yml, Databricks bundles (databricks. yml), Dockerfiles, CI/CD deploy steps, and env/config files. Record the cloud provider, compute, data stores, queues, external services, environments (dev/stage/prod), and how deploys get triggered.

If nothing is declared in the repo, say so explicitly. Don't guess.

  
##  6. Write the HTML

Use the template below. Rules:

- ﻿﻿Every claim cites a file path (path/to/file.py), so the reader can verify it.
- ﻿﻿Use Mermaid for diagrams. Keep each diagram under ~15 nodes.
- ﻿﻿Mark anything inferred rather than confirmed as (inferred).
- ﻿﻿Put unknowns in "Open questions" instead of inventing answers.

##  7. Finish

Open the file (open repo-overview.html on macOS) and give the user a 3-5 sentence summary in chat.

