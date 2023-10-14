# Azure OpenAI ARO Application

Repository for Deploy A Gradio App with Azure OpenAI as a backend LLM


## Usage

* First, set your environment variables with the plain text values in your terminal:

```md
export BASE_URL="https://MY_FANCY_URL.openai.azure.com/"
export API_KEY="your-api-key"
```

* create a Secret YAML file with base64-encoded values using echo and base64:
```
echo -n "$BASE_URL" | base64
echo -n "$API_KEY" | base64
```

* Deploy the secret in the namespace
```
envsubst < manifests/overlays/secret.yaml > /tmp/k8s-aoiaro-secret.yaml
kubectl apply -n -f /tmp/k8s-aoiaro-secret.yaml
```