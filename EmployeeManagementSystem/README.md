# **REST API with MongoDB with Loopback Connector**

## _This is an REST API application based on Employee Management System_
This project uses MongoDB to perform database operations.

Ace connects MongoDB using Loopback Request Node but using before we need to make few installations and changes:
1. **Install and configure the required LoopBack connector for use with IBM App Connect Enterprise.**
   
    a. Open the IBM App Connect Enterprise Command Console and change to the node_modules subdirectory of the work path directory (which is defined by the MQSI_WORKPATH environment variable).
    > cd %MQSI_WORKPATH%\node_modules
    
    b. rom the node_modules subdirectory, run the npm command, specifying the name of your chosen LoopBack connector.
    For example, to install the MongoDB LoopBack connector:
    > npm install loopback-connector-mongodb

2. **Configuring the data source and models(optional not done in this project) for your LoopBack connector**

    a. Create or update a LoopBack datasources.json file adn this file must be saved in either of the below locations:
    >    workpath/integration_node/integration_server/connectors/loopback (specific to the integration Server)
        workpath/integration_node/connectors/loopback (specific to the integration node)
         workpath/connectors/loopback(specific to the independent integration node)
    **Note:** _datasources.json files added to this project._

3. Specifying security credentials for connecting to a secured data source
    a. You can use the mqsicredentials or mqsisetdbparms command to specify the security credentials used by a LoopBackRequest node to connect to a secured data source. I used mqsisetdbparms command
    ```sh
    mqsisetdbparms INODE -n loopback::lbreqid1 -u myLoopBackUserID -p myLoopBackPassword
    ```
    here,
    >    -n loopback::lbreqid1 - The name of the security identity that is used to authenticate a connection to a LoopBack connector, where securityIdentity is the value of the Security identity property in the LoopBackRequest node.
    -u myLoopBackUserID - The user ID for connecting to the LoopBack connector application.
    -p myLoopBackPassword - The password for accessing the LoopBack connector application.

