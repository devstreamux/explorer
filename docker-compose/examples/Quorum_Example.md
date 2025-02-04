

### Connecting Sirato to Quorum 7 Node Example 

Get Quorum 7 node example 

```
git clone https://github.com/jpmorganchase/quorum-examples
cd quorum-examples
docker-compose up
```

You should see the following happening in the terminal window.

![image](images/7NodesDocker.png)

#### Set up Sirato-Free

```
git clone https://github.com/blk-io/Sirato-free.git
cd Sirato-free
```

In order to start Sirato you need to run the following command:

`NODE_ENDPOINT=http://quorum-examples_node1_1:8545 docker-compose -f docker-compose.yml -f Sirato-extensions/docker-compose-quorum.yml up`

The command above does two things :
* It sets up the node endpoint 
* Tells docker to run by using the two docker compose files provided.

The first docker-compose file in the command is the contains all the services required for Sirato.

The second file named docker-compose-quorum contains the network settings required to start Sirato on the same network as quorum.

> Note: we are connecting to node 1 - you will only see private transactions for that node.

You should see the following happening in the terminal window. This means that everything has started successfully.

![img](images/SiratoDocker.png)

> Note: The logs are verbose and you will see various errors before all services are started. The important logs to look at are on the api. You can access them with the following
> 
>`docker-compose logs -f api`


Navigate to [localhost](http://localhost) and you should see the loading page:

![image](images/Loading.png)

After a few minutes Sirato should display the following information:

![img](../images/Blocks.png)

Sirato has successfully connected to a Quorum node and is ingesting data. Depending on your machine specs this can take a long time to get to this point (20 mins on a macbook air).

To close Sirato or Quorum you can execute the following line in your terminal:

`docker-compose down` 


#### Help & Additional Information

For more information on Sirato you can go [here](https://github.com/blk-io/Sirato-free).

For more information Quorum 7 Nodes example you can go [here](https://github.com/jpmorganchase/quorum-examples/blob/master/README.md).

