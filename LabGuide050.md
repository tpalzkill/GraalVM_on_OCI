## Introduction

This is the first of several labs that are part of the **GraalVm on Oracle Cloud Infrastructure Workshop** This workshop will walk you through how to improve polyglot application performance using GraalVm within an OCI Compute instance.

**_To log issues_**, click here to go to the [github oracle](https://github.com/oracle/learning-library/issues/new) repository issue submission form.

## Objectives

- Get Started With Oracle Cloud Infrastructure
- Create VCN, compartment and compute instance.
- Install GraalVM on compute instance

## Getting Started

### **STEP 1**: Acquire an Oracle Cloud Trial or Workshop Account

- Wait until you receive the following email before proceeding to the next steps in the lab. Please make note of your temporary password in this email.

    ![](images/050/1.png)

### **STEP 2**: Login to your Oracle Cloud Account

- From any browser, go to the URL:
    `https://cloud.oracle.com`

- click **Sign In** in the upper right hand corner of the browser

    ![](images/050/2.png)


- Enter your identity domain and click **Next**

    **NOTE:** The **Identity Domain** should come from your Trial confirmation email.

    ![](images/050/3.png)

- Once your Identity Domain is set, enter your User Name and the Password you set after your confirmation e-mail and click **Sign In**

    ![](images/050/4.png)

- You will be presented with a Dashboard displaying the various cloud services available to this account.

    ![](images/050/5.png)

### **STEP 3**: Create Compartment

- Click on the hamburger menu on the top left and then scroll to **Identity** and then click **Compartments** .

    ![](images/050/6.png)

- Click on create compartment

    ![](images/050/7.png)

- Fill out the details Name, description and then click **Create Compartment**

    ![](images/050/8.png)

### **STEP 4a**: Create SSH-Keys (Mac/Linux)

- In a `Linux/Mac` client terminal window **Type** the following

  - **type**  mkdir keys

  - **type** cd keys

- Now **Type** the following to generate the OCI Instance key pair (**For this lab we WON'T be using Passphrases**):

  ```
  ssh-keygen -b 2048 -t rsa -f oci_instance_key
  ```

### **STEP 4b**: Create SSH-Keys (Windows)

- If using Windows and your OS does not have the OpenSSH bundle (comes in later versions of Windows 10. `You can open up a Command Prompt and type **ssh** or **ssh-keygen** to see`), download and install from here: [OpenSSH for Windows](http://www.mls-software.com/opensshd.html).

- In a `Windows` client terminal window **Type** the following (**For this lab we WON'T be using Passphrases**)

  - **type**  mkdir keys

  - **type** cd keys

- Now **Type** the following to generate the OCI Instance key pair:

    ```
    ssh-keygen -b 2048 -t rsa -f oci_instance_key
    ```

### **STEP 5**: Create OCI Instance and VCN

- Back on the Oracle Cloud Infrastructure compartments page select the hamburger icon in the top left of the screen. In the menu on the left of the page select **Compute**.

    ![](images/050/9.png)

- Ensure that the compartment you just created is selected, then click **Create Instance**.

    ![](images/050/10.png)

- Name the instance ```graal_compute```. Leave the remaining values in the photo as default and scroll down.

    ![](images/050/11.png)

- In the **Add SSH key** section choose the oci_instance_key.pub that you created in the last step by selecting **Choose File**. You can also open the key in a text editor and paste it in if you prefer.

    ![](images/050/12.png)

- To support networking within the instance you will also provision a Virtual Cloud Network. Give the name ```graal_vcn``` and select create.

    ![](images/050/13.png)

- You will see that your instance is now provisioning and can proceed to the next step.

    ![](images/050/14.png)
