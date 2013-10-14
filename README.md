shareAMI
========


usage: shareAMI.py [-h] -k KEY -s SECRET [-t TARGET] [-a AMI] [-f FILE]

This script will share one or several AMI's from your account to a target account, it can share AMI's on several regions at the same time.

arguments:
  -h, --help            show help message and exit

  -k KEY, --key KEY     Access Key ID of your AWS account

  -s SECRET, --secret SECRET
                        Secret Access Key of your AWS account

  -t TARGET, --target TARGET
                        Account number of the account you want to share the AMIs with, it can be found on your "my account" page in the top right corner, it looks like 0123-4567-8910

  -a AMI, --ami AMI     ami ID use only if you want to share a single ami

  -f FILE, --file FILE  Text file containing the list of AMI you want to share, 1 AMI ID per line is recommended

  -r REVOKE, --revoke REVOKE Revoke lauch permissions on the target account



  To execute the script you must have python 2.7.5 installed , just type python shareAMI.py followed by the arguments, you can either give a single AMI ID or give a text file with all the AMI's IDs. All the credentials for your account can be find on the "My Account" page of your AWS account in the "Security Credentials" tab.
  You don't have to precise the region on wich you want to share the AMI, each AMI is bound to a region and the script will try to share it on every region until it finds the right one.

  	Example for a single ami: python shareAMI.py -k MYAMAZONACCOUNTKEYID -s myamazonaccountsecretkey -t 0123-4567-8910 -a ami-4ca2529b

  You now gave the launch autorisation for this ami to the target account, the user will be able to find the AMI in the EC2 console in AMIs (don't forget, a shared AMI is in Public images, not in the "owned by me" section)

  If you're using a file you just need to execute the script in the same directory as your file


  	Example for a file: python shareAMI.py -k MYAMAZONACCOUNTKEYID -s myamazonaccountsecretkey -t 0123-4567-8910 -f myfile.txt					


