

# PEcAn Unconstrained Ecological Forecast Course

## Written by [Christopher Tate](https://www.computate.org/)

- Red Hat Principal Software Engineer in Red Hat Research 
- Creator of the Smart Village Operator and Smart Village Platform 
- Architect of the Red Hat Social Innovation Program 
- Founder of the Smarta Byar Smart Village Community FIWARE Innovation Hub 
- Principal Software Engineer for the New England Research Cloud

# Red Hat OpenShift Developer Sandbox

This is a course showing you how to try out the PEcAn Ecological Forecasting platform for free in the Red Hat OpenShift Developer Sandbox. 

## How to start an OpenShift Developer Sandbox

Start a [free Red Hat OpenShift Developer Sandbox
here](https://developers.redhat.com/developer-sandbox).

<img src="pictures/10000201000002EC000000B797470F50FAD9B503.png" />

Click on the
<img src="pictures/100002010000002A00000016F8A31816B66F52D8.png" />
button in the top right corner.

<img src="pictures/10000201000000C20000004B778672F45D986E77.png" />

### Register for a free Red Hat account

If you do not already have a free Red Hat account, click
<img src="pictures/100002010000011D000000194F39C6CC5D1A0EA6.png" />.

Log in if you already have a free Red Hat account:

<img src="pictures/10000201000001A4000000F06DFE281142C79837.png" />

### Start your OpenShift Developer Sandbox

After you are logged into your Red Hat account, return to the page to
start a [free Red Hat OpenShift Developer Sandbox
here](https://developers.redhat.com/developer-sandbox).

Click
<img src="pictures/10000201000000DF000000245838DB81DC18462A.png" />

Then click
<img src="pictures/100002010000008A000000248AC83F9D6A153747.png" />

Before you can access your new sandbox, you will need to request an
activation code by phone. Click on the link.

Be sure to enter your country code, and phone number correctly, then
check your phone for the activation code.

<img src="pictures/1000020100000359000000CB3CE9E1A39B080DE6.png" />

Enter your activation code in the box .

After a few moments, you should be able to start your Red Hat OpenShift
Developer Sandbox. Click the button to start your sandbox for free.

<img src="pictures/100002010000027E0000008072F673BF670FECCA.png" />

If you see a message
<img src="pictures/10000201000001EA0000001EB1A61FBC1D9C353B.png" />,
then click
<img src="pictures/1000020100000048000000243F3A75341A965DC4.png" />

You can get started in the Red Hat OpenShift platform by clicking on the
button.

<img src="pictures/10000201000000740000007DED7012DEEE29A8D6.png" />

Log in by clicking on the
<img src="pictures/100002010000006C0000001DABF5B58FF6B1D253.png" />
button to log into the new sandbox with your Red Hat account.

Explore your new sandbox with a tour, or get started now.

<img src="pictures/1000020100000220000000A7B122DE8EA79F44F2.png" />

## Using the OpenShift Developer Sandbox

### Download the oc command
- Click the
<img src="pictures/10000201000000180000001946A6B15A7F8D3A9C.png" />
button in the top right of the Developer Sandbox.

- Click
<img src="pictures/100002010000010400000025591A5F602949BE11.png" />.
- Click the download link for your operating system.

<img src="pictures/1000020100000168000000AC979C70CCF932ABC5.png" />
- You'll need to extract the `oc` command and place it in your path,
for example in a `bin` directory in your `$HOME` directory.

```bash
mkdir -p ~/bin
tar xvf ~/Downloads/oc.tar -C ~/bin/
```

### Log into the OpenShift CLI in your terminal

<img src="pictures/10000201000000DA000000A925DC020844A89E01.png" />
- Click your username in the top right corner of the Developer Sandbox.
- Click
<img src="pictures/10000201000000BD00000025748AE357F93DE9CB.png" />.
- Click
<img src="pictures/10000201000000740000002333EFEF0BE6991D9D.png" />.
- Click
<img src="pictures/100002010000006A000000156B50A1A3B5B867E3.png" />.
- Copy the line to the clipboard that looks like this:

<img src="pictures/100002010000024F0000004C0CDBE88B1D849CC9.png" />
- Paste the command into your terminal to log in to the Developer Sandbox in the terminal.

<img src="pictures/10000201000003AC000000BE7CE02563432523F1.png" />

### Try the built-in OpenShift Command Line Terminal

If you would rather use the built-in OpenShift Command Line Terminal,
you can click the
<img src="pictures/10000201000000300000002141D4B84667B12CDC.png" />
button at the top.

Start your terminal with the
<img src="pictures/100002010000003F000000219314E9C10310EE58.png" />
button.

<img src="pictures/10000201000001DB000000F8A368C4DDD19862FB.png" />

### Grant default service account edit role in namespace

To grant the default service account edit role privileges, you will use
either your own terminal where you have logged in to OpenShift, or use
the built-in OpenShift Terminal. We will grant edit privileges on the
default service account, as well as edit privileges on roles and
rolebindings in the namespace so that the default service account can
deploy resources in your namespace.

```
oc create rolebinding python-edit --clusterrole=edit \
  --serviceaccount=$(oc get project -o \
  jsonpath={.items[0].metadata.name}):python

oc create role python-edit-rolebindings \
  --verb=get,list,watch,create,update,patch,delete \
  --resource=roles,rolebindings

oc create rolebinding python-edit-rolebindings --role=python-edit-rolebindings \
  --serviceaccount=$(cat /var/run/secrets/kubernetes.io/serviceaccount/namespace):python
```

# OpenShift AI

## Set up an OpenShift AI Workbench

### Accessing OpenShift AI

In your OpenShift Sandbox, click on the apps button
<img src="pictures/100002010000003000000024AAAC041571052865.png" />
at the top,

then click
<img src="pictures/100002010000012600000028AA3F546B7EAF857C.png" />
to log into OpenShift AI.

Click the button to
<img src="pictures/10000201000000A000000020B028AB197DEBE3A3.png" />.

Log into OpenShift AI by clicking on the
<img src="pictures/100002010000006C0000001DABF5B58FF6B1D253.png" />
button.

Once you are in OpenShift AI, click on the menu button
<img src="pictures/100002010000002E000000216426608B65255A13.png" />,
then click
<img src="pictures/10000201000000B200000027F58611BB363F3154.png" />.

Then click on the name of your data science project
<img src="pictures/100002010000008F00000034E5BB257B3DE6397F.png" />,
for my Red Hat user it’s computate-dev.

### Create a new OpenShift AI Workbench

To create a new workbench, click
<img src="pictures/100002010000009100000021A1D82C0B6349F1C3.png" />.

To stay consistent with the rest of the course, enter the workbench name
“python”
<img src="pictures/1000020100000043000000446EA181997A7346B6.png" />.

For Image selection, choose “Minimal Python”
<img src="pictures/100002010000007B0000003FA29A900E8890D587.png" />.

You can leave the rest of the fields as the default. At the very bottom,
click
<img src="pictures/1000020100000091000000211148800178F97C50.png" />.

After a minute or two, you should see the workbench change from
<img src="pictures/10000201000000460000002FDF0FBBBC61A6E1C5.png" />
to
<img src="pictures/100002010000003A00000030BD8223197D20CCFD.png" />.

### Access your OpenShift AI Workbench

In OpenShift AI, click on the
<img src="pictures/100002010000004200000023E46306A5CE3ADC98.png" />
link to open your new OpenShift AI Workbench.

Log into OpenShift AI by clicking on the
<img src="pictures/100002010000006C0000001DABF5B58FF6B1D253.png" />
button.

You will need to authorize yourself access to your workbench. Click
<img src="pictures/10000201000000CD0000001AA11D3D36B96FAA42.png" />.

## Using an OpenShift AI Python Workbench

### Using a Workbench Terminal to load course resources

You will want to open a Terminal inside your OpenShift AI Workbench to
load the course resources. There are many ways to open a terminal, but
here is one that always works.

At the top, click
<img src="pictures/100002010000002300000017A7751A2F8CB5671D.png" />
→
<img src="pictures/100002010000002800000016B63989EE943480F7.png" />
→
<img src="pictures/100002010000004D00000018604E6A830090C94F.png" />.

### Clone the pecan-unconstrained-forecast-course course

With git, clone the course materials to the default home directory
(/opt/app-root/src) of your workbench.

```bash
git clone https://github.com/computate-org/pecan-unconstrained-forecast-course.git ~/pecan-unconstrained-forecast-course
```

### Open the course Jupyter Notebook

A Jupyter Notebook is an interactive, online notebook, and the rest of
the course be found in the Jupter Notebooks. 

## Next...
If you have successfully ran all of the commands above, congratulations, you are ready to move on to the next notebook in the course. 
- In your workbench, make sure your left sidebar is open. If it’s not,
press \[ Ctrl \] + \[ b \].
- Navigate to `pecan-unconstrained-forecast-course`. 
- Open the first Notebook [01-ecological-forecasting-in-the-cloud.ipynb](01-ecological-forecasting-in-the-cloud.ipynb) and follow the instructions from there. 

- If you have additional questions or issues, please [create an issue for the course here](https://github.com/computate-org/pecan-unconstrained-forecast-course/issues). 