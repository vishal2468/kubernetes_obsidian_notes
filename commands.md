```yaml
spec:
  containers:
  - name: simple-webapp
    image: kodekloud/webapp-color
    command: ["python", "app.py"]
    args: ["--color", "pink"]
```

defined under [[spec]].[[container]]s 
this is equivalent to ENTRYPOINT in [[dockerfile]]
