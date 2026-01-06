# Dataset in Big Query: 

Chunks table: https://console.cloud.google.com/bigquery?project=summestorm-1754711636&ws=!1m5!1m4!4m3!1ssummestorm-1754711636!2srag_pds!3schunks

# MCP Toolbox – Configuration

This repository contains MCP Toolbox configuration (primarily `tools.yaml`).
The `toolbox` binary is not stored in Git (GitHub blocks large binaries and it may be internal).

## Get the toolbox binary (internal)
Download the Linux x86_64 binary from GCS:

```bash
gsutil cp gs://pds_database_useast4/RAG/TOOLBOX/toolbox-linux-x86_64 ./toolbox
chmod +x ./toolbox

