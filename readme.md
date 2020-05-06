# MyBasicWorkItem

A basic workItem, that can be used as a template for your custom workItems.

## Build and Manual Deployment

### Prerequisites

You will need:

- Maven 3.6.2+ installed
- Business Central up & running

### Build a deployable JAR

Clone the current git repository and execute the following command:

```sh
mvn clean package
```

In the **target/** directory, you can find a deployable JAR artifact: my-basic-workitem-1.0.0.jar

### Deploy to Business Central

### Upload JAR artifact to Business Central

1. In Business Central, select the **Admin** icon in the top-right corner of the screen and select **Artifacts**.
2. Click **Upload**.
3. In the **Artifact Upload** window, click the **Choose File** icon.
4. Navigate to the location of the work item handler JAR, my-basic-workitem-1.0.0.jar, select the file and click **Open**.
5. In the pop-up dialog, click the **Upload** icon.

The artifact is uploaded and can now be viewed on the **Artifacts** page and referenced.

### Add workItem Dependency on your process project

In Business Central, select the **Settings** of your process project, and add the dependency to you workItem, as follows: 

![Adding Dependency](https://i.imgur.com/DMFHcZV.png)

Don't forget to **Save** 

### Add workItem Handler class to your process project

In Business Central, select the **Settings** of your process project, and add workItem Handler class to your process project, as follows: 

![Adding workItem Handler](https://i.imgur.com/TlvUGSW.png)

Don't forget to **Save** 

### Update Work Item Definitions (wid) file in your process project

In Business Central, open the **WorkDefinitions.wid** of your process project, and add the following, as follows: 

```
    ,[
        "name" : "MyBasicWorkItem",
        "displayName" : "My Basic WorkItem",
        "category" : "My WorkItems",

        "parameters" : [
            "SampleParam" : new StringDataType()
            ,"SampleParamTwo" : new StringDataType()

        ],
        "results" : [
            "SampleResult" : new StringDataType()

        ],
        "icon" : "defaultservicenodeicon.png"

    ]
```

Refer to following image

![Updating Work Item Definitions](https://i.imgur.com/0mUDPhf.png)


### Your custom workItem is now ready to use !

![Ready to use](https://i.imgur.com/yUVTFIe.png)
