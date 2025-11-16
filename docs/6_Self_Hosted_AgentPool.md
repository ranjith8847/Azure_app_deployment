## 6. Create Azure Self-Hosted Agent-Pool

The build pipelines we create will run on the Agent Pool (which is nothing but a VM).

So we need to set up the VM for running our build pipelines.

If you have deleted the previously created VM (which is a good practice because we are broke XD), go ahead and create a new VM by referring to the above process.

After creating the VM, SSH into the VM.

*SSH is nothing but accessing the VM (remote resource) from your local machine.*

*Before that, make sure you have downloaded the private_key.*

*And have the public IP of the VM in hand (it can be found in VM overview details).*

![Enter image alt description](../Images/cfv_Image_22.png)

---

Open **cmd**,  
Enter the command:

```
ssh -i <private_key_path> azureuser@<public_ip_of_vm>
```


After running the command, type **yes** if it asks for input.

![Enter image alt description](../Images/YGM_Image_23.png)

---

After SSH-ing into the VM, we should configure it as an agent pool.

Go to your Azure DevOps project  
(In my case: https://dev.azure.com/ranjithchowdary2001/baasic-reactjs)

Navigate to:  
**Project settings → Agent Pools → Add pool**

![Enter image alt description](../Images/RMx_Image_24.png)

Click **Create**.

---

Go to the terminal where you established the SSH connection.

Run:

```
mkdir myagent && cd myagent
```


![Enter image alt description](../Images/lku_Image_25.png)

---

Run the command to download the agent package:

```
wget https://vstsagentpackage.azureedge.net/agent/2.214.1/vsts-agent-linux-x64-2.214.1.tar.gz
```


![Enter image alt description](../Images/Mw1_Image_26.png)

---

Extract the package using:

```
tar zxvf vsts-agent-linux-x64-2.214.1.tar.gz
```


![Enter image alt description](../Images/PvW_Image_27.png)

---

Run:

```
ls -al
```


You should see **config.sh** and **env.sh**.

![Enter image alt description](../Images/Hlq_Image_28.png)

---

Start configuration:

```
./config.sh
```


If you get this error:

![Enter image alt description](../Images/TO1_Image_29.png)

Run:

```
export DOTNET_SYSTEM_GLOBALIZATION_INVARIANT=1
```


And then again run:

```
./config.sh
```


![Enter image alt description](../Images/F2B_Image_30.png)

---

Accept the license agreement by typing **Y**.

It asks for the server URL — enter:

```
https://dev.azure.com/<yourorganization>
```

Example:

![Enter image alt description](../Images/xfT_Image_31.png)

---

When asked for authentication type, choose **PAT (Personal Access Token)**.

![Enter image alt description](../Images/8WX_Image_32.png)

To generate PAT:

Go to:  
**User Settings → Personal Access Token**

![Enter image alt description](../Images/h2k_Image_33.png)

Click **New Token**

Scroll down → click **Show All Scopes**

Enable:

- **Agent Pools → Read & Manage**

Click **Create**.

![Enter image alt description](../Images/8oK_Image_34.png)

---

**Make sure to copy the token** (you won't see it again).

![Enter image alt description](../Images/5R9_Image_35.png)

---

Next, configure the self-hosted agent service:

```
sudo ./svc.sh install &
```


![Enter image alt description](../Images/Kfj_Image_36.png)

---

Start the agent service:

```
./runsvc.sh
```


![Enter image alt description](../Images/Wca_Image_37.png)

---

Now your **self-hosted agent is ready** to run build pipelines!
