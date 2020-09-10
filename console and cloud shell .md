#LAB: Console and Cloud Shell

##Objectives

In this lab, you learn how to perform the following tasks:

	-Get access to Google Cloud.

	-Create a Cloud Storage bucket using the Cloud Console.

	-Create a Cloud Storage bucket using Cloud Shell.

	-Become familiar with Cloud Shell features.
	
	
###Task 1: Create a bucket using the Cloud Console

NB: This above task will be completed using command line.
create a new bucket using the below command, replacing the <BUCKET_NAME> to your bucket name.
	`gsutil mb gs://<BUCKET_NAME>`. For example `gsutil mb gs://my_bucket`.

	

###Task 2: Access Cloud Shell
You basically going to get yourself acquainted wih google cloud shell environment.


###Task 3: Create a bucket using Cloud Shell
Same as Task 1.

###Task 4: Explore more Cloud Shell features- Upload a file

-Open Cloud Shell.

-Click the three dots icon in the Cloud Shell toolbar to display further options.

-Click Upload file. Upload any file from your local machine to the Cloud Shell VM. This file will be referred to as [MY_FILE].

-In Cloud Shell, type `ls` to confirm that the file was uploaded.

-Copy the file into one of the buckets you created earlier in the lab. Replace [MY_FILE] with the file you uploaded and [BUCKET_NAME] with one of your bucket names using the below command:
```gsutil cp [MY_FILE] gs://[BUCKET_NAME]``` If your filename has whitespaces, ensure to place single quotes around the filename. For example, `gsutil cp ‘my file.txt' gs://[BUCKET_NAME]`


###Task 5: Create a persistent state in Cloud Shell

Identify available regions

-Open Cloud Shell from the Cloud Console. Note that this allocates a new VM for you.

-To list available regions, execute the following command:

```gcloud compute regions list```

-Select a region from the list and note the value in any text editor. This region will now be referred to as [YOUR_REGION] in the remainder of the lab.


Create and verify an environment variable

-Create an environment variable and replace [YOUR_REGION] with the region you selected in the previous step:

```INFRACLASS_REGION=[YOUR_REGION]```

-Verify it with echo: echo $INFRACLASS_REGION


Append the environment variable to a file

-Create a subdirectory for materials used in this class: `mkdir infraclass`

-Create a file called `config` in the infraclass directory: `touch infraclass/config`

-Append the value of your Region environment variable to the config file: `echo INFRACLASS_REGION=$INFRACLASS_REGION >> ~/infraclass/config`

-Create a second environment variable for your Project ID, replacing [YOUR_PROJECT_ID] with your Project ID. You can find the project ID on the Cloud Console Home page. 

`INFRACLASS_PROJECT_ID=[YOUR_PROJECT_ID]`

-Append the value of your Project ID environment variable to the config file: echo INFRACLASS_PROJECT_ID=$INFRACLASS_PROJECT_ID >> ~/infraclass/config

-Use the source command to set the environment variables, and use the echo command to verify that the project variable was set: 
```source infraclass/config
echo $INFRACLASS_PROJECT_ID
```

-Close and re-open Cloud Shell. Then issue the echo command again then try the following: `echo $INFRACLASS_PROJECT_ID`
There will be no output because the environment variable no longer exists.


