## Description
Xdebug does not work.

## Solution
1. Ensure that Xdebug is enabled in `deploy.*.yml`:
```
```yaml
docker:
...
    debug:
      xdebug:
        enabled: true
```
2. Ensure that IDE is listening to the port 9000.
3. Check if the host is accessible from the container:
```bash
docker/sdk cli -x bash -c 'nc -zv ${SPRYKER_XDEBUG_HOST_IP} 9000'
```