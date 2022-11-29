# Image Library

## Introduction

This lab walks you through the steps to organize an image library in OCI Object Storage and upload X-Ray images to the the library.

Estimated Time: 20 minutes

### About OCI Object Storage
The Oracle Cloud Infrastructure Object Storage service is an internet-scale, high-performance storage platform that offers reliable and cost-efficient data durability. 

The Object Storage service can store an unlimited amount of unstructured data of any content type, including analytic data and rich content, like images and videos.

### Objectives

In this lab, you will:

* Create a new bucket
* Set bucket visibility
* Setup required folder structure
* Load images

### Prerequisites

This lab assumes you have:

* An Oracle Cloud account

## Task 1: Create a new Bucket

You will organize your image library in a new object storage bucket.

1. Step 1: Login into OCI

    Login as a user who will manage your image library and also will perform the rest of activities in this workshop.

    Select your Identity Provider, **oracleidentitycloudservice** in this case, ...

    ![](./images/lab1_001.jpg =50%x*)

    ... and provide your user's credentials. For example, Candy.Sweets.

    ![](./images/lab1_002.jpg =50%x*)

2. Step 2: Navigate to **Buckets** page

    From the **Navigator** menu (top-left cornent) select **Storage** and then **Buckets**.

    ![Navigate to Buckets page](./images/lab1_004.png " ")

3. Step 3: Create a new bucket

    Please pay attention that you've selected correct compartment, *Box-of-Chocolates* in our case.

    Then click **Create Bucket**

    ![Click Create Buckets](./images/lab1_005.jpg " ")

4. Step 4: Define bucket

    When creating a new bucket, provide a **Bucket Name** of your choosing and then leave everything else as default:
    * choose Standard for **Default Storage Tier**, 
    * use Encrypt using Oracle managed keys for **Encryption** and 
    * provide some **Tags**.

    ![Define a new bucket](./images/lab1_006.png " ")

    Finally click **Create** to create a new bucket.

## Task 2: Set visibility

In order to make your image library visible to other users/service, you have to update its visibility. One way of doing it is to set visibility to **Public**.

1. Step 1: Change visibility to Public.

    From your bucket list choose your newly created bucket.

    ![Buckets List](./images/lab1_007.jpg " ")

2. Step 2: Edit Visibility

    In the Bucket Details page, click **Edit Visibility**.

    ![Bucket Details Page](./images/lab1_008.jpg " ")

3. Step 3: Update Visibility

    Check **Public** radio button and click **Save Changes**

    ![Update visibility](./images/lab1_009.jpg =50%x*)

4. Step 4: (optional) Set Pre-Authenticated Request

    Please note that you have an option to set **Pre-Authentication Request** instead of changing visibility to **Public**.

    In this case click **Pre-Authentication Requests** link under **Resources** and then **Create Pre-Authenticated Request**.

    ![PAR](./images/lab1_010.png " ")

    Fill required field in PAR definition and finally click **Create Pre-Authenticated Request**.

    ![Create PAR](./images/lab1_011.png " ")

    Pre-Authenticated Request details popup window is shown. Please copy URL for your reference as it won't be shown again.

    ![PAR URL](./images/lab1_012.png " ")

    Click **Close** to return to the **Bucket Details** page.

    ![Bucket Details Page](./images/lab1_013.png " ")

## Task 3: Set required folder structure

This workshop is using [Chest X-Ray Images (Pneumonia)](https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia) dataset.

In this task you will setup the folder structure and load images into proper folders in the next. 

Start with the library folder structure. Image library is organized in two folders:

* PNEUMONIA, which contains images of bacteria or virus infected lungs, and
* NORMAL, which contains images of normal, unaffected lungs

1. Step 1: Create a new folder

    Make sure you've clicked **Objects** under **Resources** in the Bucket Details page of you new bucket. 

    Click **More Actions** and choose **Create New Folder** from the menu.
    
    ![Create folder](./images/lab1_014.png " ")

2. Step 2: Define folder

    Name your new folder **PNEUMONIA** and click **Create**

    ![Pneumonia folder](./images/lab1_015.jpg " ")

    Repeat this step for another new folder **NORMAL**.
    
    ![Normal folder](./images/lab1_016.png " ")

3. Step 3: Verify your folder structure

    Please verify that you've created two folders, PNEUMONIA and NORMAL, under the *root*.

    ![Verify folders](./images/lab1_017.jpg " ")

## Task 4: Load images

We are now ready to load images into appropriate folders. The following steps might seem a bit long and far from being optimal as all images will be loaded using **Upload** utility provided on **Bucket Details** page. More elegant way of uploading would be to upload programmatically. 

The main issue with **Upload** is that you can only load approx. 200 images in one attempt. This means repeating the upload step several times to upload all 5000 images. This step can take approx 20-30 minutes to complete.

1. Step 1: Initiate images Upload

    You should still be located in the **Objects** sub-page of the **Bucket Details** page of your bucket.

    Navigate to the **PNEUMONIA** folder first.

    ![Pneumonia folder](./images/lab1_018.png " ")

    And click **Upload**.

2. Step 2: Upload images for PNEUMONIA

    In the dialog window leave **Object Name Prefix** empty, and leave **Storage Tier** unchanged.

    Then **drag image files** or **select files** from your computer onto **Choose Files from your Computer Area**. When ready, **Upload** button will become enabled (blue). Please note that you can upload approx. 200 images in one upload job.

    Click **Upload** and wait all images are uploaded.

    ![Upload pneumonia images](./images/lab1_019.png " ")

    Repeat this step for all 3000+ images for PNEUMONIA.

3. Step 3: Upload images for NORMAL

    Repeat the previous step, except this time navigate to NORMAL folder and upload images for NORMAL.

    ![Upload normal images](./images/lab1_020.png " ")

    There should be approx. 1000+ images for NORMAL.

4. Step 4: Verify images are correctly loaded

    Before you continue to the next lab, just make sure that you've uploaded all images and that images are correctly placed into PNEUMONIA and NORMAL folders:

    ![Verify loaded images](./images/lab1_022.png " ")

    You should see and review all details of uploaded images in corresponding folders.

    ![Verify loaded images](./images/lab1_021.png " ")

## Learn More

* [OCI Object Storage](https://docs.oracle.com/en-us/iaas/Content/Object/home.htm)


## Acknowledgements
* **Author** - Žiga Vaupot, Oracle ACE Pro, Qubix
* **Contributors** -  Grega Dvoršak, Qubix
* **Last Updated By/Date** - Žiga Vaupot, November 2022