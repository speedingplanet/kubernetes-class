# Kubernetes Class

## VS Code

Consider adding `.vscode/settings.json` to the project root with the following config:

```json
{
	"vs-kubernetes": {
		// Not using Helm in class, so the warning for this is unneccessary
		"vs-kubernetes.suppress-helm-not-found-alerts": true,
		"disable-linters": [
			// Disabled because the warning is too noisy
			"resource-limits"
		]
	}
}
```

## Demos

### folder-deployment

Demos dploying all the files in a folder.
```shell
cd demos/folder-deployment
kubectl apply -f '*.yaml'
```
The quotes around `*.yaml` are critical to prevent shell expansion
