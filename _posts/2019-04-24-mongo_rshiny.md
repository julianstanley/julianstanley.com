---
layout: post
title: Connecting a remote MongoDB database with R/Shiny
date: '2019-04-24'
draft: false
categories:
  - R
tags: [
    "projects",
    "R",
    "shiny",
    "technical"
]
---

While making a Shiny App for a lab project (Sensor Overlord), I wanted to create 
a feature where users could input sensor data into a database, where it could
be accessible to other users. 

I decided to give MongoDB a shot, mostly becuase of the free hosting services
available on [MongoDB's website](https://mongodb.com). 

And it was actually extremely straightforward. There are great resources 
available online, like 
[the mongolite user manual](https://jeroen.github.io/mongolite/) and the
[shiny persistent data storage page](https://shiny.rstudio.com/articles/persistent-data-storage.html).

But it still took some troubleshooting on my part, so I wanted to share
my mongodb.com-specific guide.


# MongoDB.com free cluster setup and configuration 

1. Create an account on cloud.mongodb.com.
2. Set up a basic (free) cluster, give it a name. I named mine SensorOverlordCluster.
3. On the main cluster page, navigate to the "Security" tab and add a user.
    * I'll give mine the username *myself* and the password *letmein*.
4. Back on the "Overview" tab, click the name of your cluster. 
5. In the new screen that appears, click the "Collections" tab.
6. Create a new database and write down the database and collection name.
For mine, the database name was *sensordb* and the collection name was *responses*.

# Writing and reading MongoDB from R

1. Install the mongolite package
     * I'm running Ubuntu and had to run 
     `sudo apt-get install libssl-dev libsasl2-dev` to get the dependencies I 
     needed for my system. See the 
     [the mongolite user manual](https://jeroen.github.io/mongolite/) for 
     more info specific to your system.
     * `install.packages("mongolite")` for the CRAN version or `devtools::install_
     github("jeroen/mongolite")` for the development version.
2. Save some data to your database. I'll put the code below.
    * Note that the host should me mnopd.mongodb.net if you're using mongodb.net's
    hosting service. If that doesn't work, check the base url that's given when
    you click "connect" on the main overviewpage on cloud.mongodb.com,
    and then click "Connect Your Application" and set your driver as C
    version 1.9 or later. Your eventual url input should mimic that
    "connection string only" field.
    
```{r}
options(mongodb = list(
    "cluster" = "sensoroverlordcluster",
    "host" = "mnopd.mongodb.net",
    "username" = "myself",
    "password" = "letmein"
))

databaseName <- "sensordb"
collectionName <- "responses"

saveData <- function(data) {
    # Connect to the database
    db <- mongo(collection = collectionName,
                url = sprintf(
                    "mongodb+srv://%s:%s@%s-%s/%s?retryWrites=true",
                    options()$mongodb$username,
                    options()$mongodb$password,
                    options()$mongodb$cluster,
                    options()$mongodb$host,
                    databaseName))
    
    # Insert the data into the mongo collection as a data.frame
    data <- as.data.frame(data)
    db$insert(data)
}
```

 
&nbsp;

3. Once you use the `saveData(data)` function to save some data, you can
load it right back up!

```{r}
loadData <- function() {
    # Connect to the database
    db <- mongo(collection = collectionName,
                url = sprintf(
                    "mongodb+srv://%s:%s@%s/%s",
                    options()$mongodb$username,
                    options()$mongodb$password,
                    options()$mongodb$host,
                    databaseName))
    
    # Read all the entries
    data_output <- db$find()
    data_output
}
```
