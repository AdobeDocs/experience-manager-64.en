---
uuid: 5f3744e1-a544-4088-a431-4e97845b671d
index: y
internal: n
snippet: y
translate: y
---

# Command Line Start and Stop

---

## Starting Adobe Experience Manager from the Command Line

The `start` script is available under *the &lt;cq-installation&gt;/bin* directory. Both Unix and Windows versions are provided. The script starts the instance installed in *&lt;cq-installation&gt;* directory.

Those two versions support a list of environement variables that could be used to start and tune the AEM instance.

| **Environment variable ** |**Description ** |
|---|---|
| CQ_PORT |TCP port used for stop and status scripts  |
| CQ_HOST |Host name  |
| CQ_INTERFACE |Interface that this server should listen to  |
| CQ_RUNMODE |Runmode(s) separated by comma  |
| CQ_JARFILE |Name of the jarfile  |
| CQ_USE_JAAS |Use of JAAS (if true)  |
| CQ_JAAS_CONFIG |Path of the JAAS configuration  |
| CQ_JVM_OPTS |Default JVM options  |

>[!CAUTION]
>
><p>Note that some run modes, among them author and publish, need to be set before first starting AEM and can not be changed afterwards. Before setting up an AEM instance that is supposed to be used in production, please see the <a href="/content/help/en/experience-manager/6-4/sites/deploying/using/configure-runmodes.html">run modes documentation</a> for details.</p>

#### Windows platform start.bat script example

```shell
SET CQ_PORT=1234 & ./start.bat
```

#### Unix platform start script example

```shell
CQ_PORT=1234 ./start
```

>[!NOTE]
>
><p>The start script launches the AEM Quickstart installed under <i>the &lt;cq-installation&gt;/app</i> folder.<br> </p>

---

## Stopping Adobe Experience Manager

To stop AEM, do one of the following:

* Depending on the platform you are using:

    * If you started AEM from either a script or the command line, press **Ctrl+C **to shut down the server.    
    * If you have used the start script on UNIX, you must use the stop script to stop AEM.

* If you started AEM by double-clicking the jar file, click the **On** button on the startup window (the button then changes to **Off**) to shut down the server.
  ![](assets/chlimage_1.png)

---

## Stopping Adobe Experience Manager from the Command Line

The `stop` script is available under *the &lt;cq-installation&gt;/bin* directory. Both Unix and Windows versions are provided. The script stops the running instance installed in *&lt;cq-installation&gt;* directory.

#### Unix platform stop script example

```shell
./stop
```

#### Windows platform stop.bat script example

```shell
./stop.bat
```

If you just want to preconfigure the repository (without relocating it) you only have to:

* extract `repository.xml` to the required location
* update `repository.xml` as required
* create `bootstrap.properties` and define `repository.config`

Again, before starting the actual installation. 
