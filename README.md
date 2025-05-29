# ragflow-dev-debug-container

1. build and start dev-debug container:
   	```shell
    ./build.sh $ragflow_version $dev_debug_version $http_proxy_on_host $container_external_sshServer_port $root_pwd
	  ```
    example:
    ```shell 
    ./build.sh v0.19.0 v0.19.0 http://192.168.0.161:7890 2222 root
    ```
2. start dependent services:

	```shell
 	cd ragflow
 	docker compose -f docker/docker-compose.yml down -v
	docker compose -f docker-compose.yml up -d
	```
3. connect to the container using vs code remote
4. `docker logs --tail 100 -f $container_id` , wait for ouptput: "dev debug container ready!"
5. source code absolute path: `/ragflow`
6. entrypoints: 
   - `api/ragflow_server.py`
   - `rag/svr/task_executor.py`
