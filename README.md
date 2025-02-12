# Try Nginx

```bash
# install the example
helm install example example

# port-forward nginx
kubectl port-forward svc/nginx 8080:80

# run the test (using patched warp)
warp mixed --host=test.lcl:8080 \
    --access-key=minioadmin \
    --secret-key=minioadmin \
    --objects=10 \
    --obj.size=1MiB \
    --concurrent=1 \
    --duration=4s
    --header "x-cbt-bucket:bucket1"
```