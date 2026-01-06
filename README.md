# 1. Dataset in Big Query: 
chunks table: https://console.cloud.google.com/bigquery?project=summestorm-1754711636&ws=!1m5!1m4!4m3!1ssummestorm-1754711636!2srag_pds!3schunks

# 2. MCP Toolbox – Configuration
## For deployment: 
'''bash
gcloud run deploy mcp-toolbox \
  --image us-central1-docker.pkg.dev/database-toolbox/toolbox/toolbox:latest \
  --service-account toolbox-identity@summestorm-1754711636.iam.gserviceaccount.com \
  --region us-east4 \
  --allow-unauthenticated \
  --set-secrets "/app/tools.yaml=tools:latest" \
  --args="--tools-file=/app/tools.yaml","--address=0.0.0.0","--port=8080"

------------

## Service URL: https://toolbox-817503285740.us-east4.run.app

This repository contains MCP Toolbox configuration (primarily `tools.yaml`).
The `toolbox` binary is not stored in Git (GitHub blocks large binaries and it may be internal).

## Get the toolbox binary (internal)
Download the Linux x86_64 binary from GCS:

```bash
gsutil cp gs://pds_database_useast4/RAG/TOOLBOX/toolbox-linux-x86_64 ./toolbox
chmod +x ./toolbox

# 3. ADK
## For re-deployment:
'''bash
gcloud run services update neptune2 \
  --region us-east4 \
  --set-env-vars \
GOOGLE_GENAI_USE_VERTEXAI=1,\
GOOGLE_CLOUD_PROJECT=summestorm-1754711636,\
GOOGLE_CLOUD_LOCATION=us-east4,\
MODEL=gemini-2.5-pro,\
TOOLBOX_URL=https://mcp-toolbox-817503285740.us-east4.run.app

-------------
# 4. Testing here: https://neptune2-817503285740.us-east4.run.app/
