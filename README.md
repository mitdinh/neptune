# MCP Toolbox – Configuration

This repository contains MCP Toolbox configuration (primarily `tools.yaml`).
The `toolbox` binary is not stored in Git (GitHub blocks large binaries and it may be internal).

## Get the toolbox binary (internal)
Download the Linux x86_64 binary from GCS:

```bash
gsutil cp gs://pds_database_useast4/RAG/TOOLBOX/toolbox-linux-x86_64 ./toolbox
chmod +x ./toolbox

