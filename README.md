# creationofCE

This sample implemntion for Compute engine instance for GCP
By GUI
In the Navigation menu (Navigation menu), click Compute Engine > VM instances.
Click Create.
On the Create an Instance page, for Name, type my-vm-1
For Region and Zone, select the region and zone assigned by Qwiklabs.
For Machine type, accept the default.
For Boot disk, if the Image shown is not Debian GNU/Linux 9 (stretch), click Change and select Debian GNU/Linux 9 (stretch).
Leave the defaults for Identity and API access unmodified.
For Firewall, click Allow HTTP traffic.
Leave all other defaults unmodified.
To create and launch the VM, click Create.


By command line:

n GCP console, on the top right toolbar, click the Open Cloud Shell button.

Cloud Shell icon

Click Continue. cloudshell_continue.png

To display a list of all the zones in the region to which Qwiklabs assigned you, enter this partial command gcloud compute zones list | grep followed by the region that Qwiklabs or your instructor assigned you to.

Your completed command will look like this:

gcloud compute zones list | grep us-central1
Choose a zone from that list other than the zone to which Qwiklabs assigned you. For example, if Qwiklabs assigned you to region us-central1 and zone us-central1-a you might choose zone us-central1-b.

To set your default zone to the one you just chose, enter this partial command gcloud config set compute/zone followed by the zone you chose.

Your completed command will look like this:

gcloud config set compute/zone us-central1-b


To create a VM instance called my-vm-2 in that zone, execute this command:

gcloud compute instances create "my-vm-2" \
--machine-type "n1-standard-1" \
--image-project "debian-cloud" \
--image "debian-9-stretch-v20190213" \
--subnet "default"
Note: The VM can take about two minutes to launch and be fully available for use.

To close the Cloud Shell, execute the following command:

exit
