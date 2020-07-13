# How-to-enable-encryption-by-default-for-newly-launched-Instances-volumes-snapshots
How to enable encryption by default for newly launched Instances, volumes, snapshots

![Start-How to Enable encryption by default for newly launched Instances, volumes, snapshots](https://media.giphy.com/media/3xz2Bw12fe9iyG06v6/giphy.gif)


**Issue** :
➜ By default, when you create a new Instance (let say from a public AMI) the volume created is always "unencrypted" and you need to manually apply encryption later following manual steps.

**Solution** :
➜ You can achieve this with a single setting which is specific to individual AWS regions in your account. I'll explain detailed information with an example below.

**References** :
<li><b><a href="https://aws.amazon.com/about-aws/whats-new/2019/05/with-a-single-setting-you-can-encrypt-all-new-amazon-ebs-volumes/" target="_blank">Announcement Link</a></b></li>

<li><b><a href="https://aws.amazon.com/blogs/aws/new-opt-in-to-default-encryption-for-new-ebs-volumes/" target="_blank"> Blog Link</a></b></li>

<li><b><a href="https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html?icmpid=docs_ec2_console" target="_blank"> Amazon EBS encryption </a></b></li>

<p><br></p>
<p><b><u>Basically</u></b></p>
<i>You can now specify that you want all newly created EBS volumes to be created in encrypted form, with the option to use the default key provided by AWS, or a key that you create. Because keys and EC2 settings are specific to individual AWS regions, you must opt-in on a region-by-region basis. Going forward, all EBS volumes that you will create in this region will be encrypted, with no additional effort on your part.</i>

<li>This will also ensure when you launch an Instance, its root volume will be encrypted automatically on launch.</li>

<li>This setting applies to a single AWS region; I will need to repeat the steps above for each region of interest, checking the option and choosing the key.</li>

<p><b><u>Example</u></b></p>
I am applying this setting in a particular region (Ireland). You may choose yourself as per your use case.
Also,I'm using New Console experience view , It may look bit different if you're on older version, you can also change using <b>"New EC2 Experience"</b>

Let's get started....


<p><b>[1] </b>Navigate to EC2 Console --> <b>Account Attributes</b> --> Settings --> <b>“EBS Encryption”</b></p>
<p><img src="https://github.com/dineshrathee12/How-to-enable-encryption-by-default-for-newly-launched-Instances-volumes-snapshots/blob/master/Images/01.jpg" style="width: 836.881px; height: 357.41px;"><b><br></b></p>


<p><b>[2] </b>Click on <b>“Manage”</b></p>
<p><img src="https://github.com/dineshrathee12/How-to-enable-encryption-by-default-for-newly-launched-Instances-volumes-snapshots/blob/master/Images/02.jpg" style="width: 836.881px; height: 357.41px;"><b><br></b></p>

<p><b>[3] </b>Now, you can click on checkbox <b>“Always Encrypt new EBS Volumes”</b>, specify the key, and click <b>“Update EBS Encryption”</b></p>
<p><img src="https://github.com/dineshrathee12/How-to-enable-encryption-by-default-for-newly-launched-Instances-volumes-snapshots/blob/master/Images/03.jpg" style="width: 836.881px; height: 357.41px;"><b><br></b></p>

<p><b>[4] </b>It will look like below:</p>
<p><img src="https://github.com/dineshrathee12/How-to-enable-encryption-by-default-for-newly-launched-Instances-volumes-snapshots/blob/master/Images/04.jpg" style="width: 836.881px; height: 357.41px;"><b><br></b></p>

<p><b>[5] </b>Now, let us try to <b>launch</b> an instance:</p>
<p><img src="https://github.com/dineshrathee12/How-to-enable-encryption-by-default-for-newly-launched-Instances-volumes-snapshots/blob/master/Images/05.jpg" style="width: 836.881px; height: 357.41px;"><b><br></b></p>

<p><b>[6] </b>Now you can see the <b>Volume</b> and click on <b>volume id</b> to check the Encryption details</p>
<p><img src="https://github.com/dineshrathee12/How-to-enable-encryption-by-default-for-newly-launched-Instances-volumes-snapshots/blob/master/Images/06.jpg" style="width: 836.881px; height: 357.41px;"><b><br></b></p>

<p><b>[7] </b><b><i>Now, you can see the volume has been encrypted with a Key for newly launched Instance</b></i></p>
<p><img src="https://github.com/dineshrathee12/How-to-enable-encryption-by-default-for-newly-launched-Instances-volumes-snapshots/blob/master/Images/07.jpg" style="width: 836.881px; height: 357.41px;"><b><br></b></p>


<b>Lastly...</b>
 
<i>"If you want to get information using <b>AWS CLI Commands</b> for your Volumes, Snapshots to know if it is Encrypted or not and If yes, then with which key it is encrypted with (AWS Managed CMK or Customer Manager CMK)", please refer my previous post here:<i>,

<li><b><a href="https://dev.to/dineshrathee12/how-to-get-details-of-an-ami-or-snapshot-if-it-is-encrypted-and-with-which-key-aws-managed-cmk-or-customer-manager-cmk-aws-7b0" target="_blank"> Blog Post</a></b></li>




                       😇 Happy learning 😇

![Happy Learning](https://media.giphy.com/media/8dYmJ6Buo3lYY/giphy.gif)


