to attach ebs to ec2:
ssh -i key.pem ec2-user@<public-ip>
lsblk
sudo fdisk /dev/nvme1n1
Inside fdisk:
n
p
Enter
Enter
Enter
w
Verify the New Partition
lsblk -fs
You should now see:
●	/dev/nvme1n1p1
mkfs.xfs /dev/nvme1n1p1
sudo mkdir /mnt/abhiram
sudo mount /dev/nvme1n1p1 /mnt/abhiram
verify mount:df -h
sudo blkid /dev/nvme1n1p1 (get uuid and copy it)
sudo nano /etc/fstab
Add this line at the end:
UUID=(copied uuid) /mnt/abhiram xfs defaults,nofail 0 0
test using:sudo mount -a



lambda :
def lambda_handler(event, context):
    a = event.get('num1', 0)
    b = event.get('num2', 0)
    result = a + b
    return {
        'statusCode': 200,
        'body': json.dumps({
            'sum': result
        })
    }
def lambda_handler(event, context):
    for record in event['Records']:
        print("Message received from SQS:")
        print(record['body'])
    return {
        'statusCode': 200,
        'body': 'Message processed successfully'
    }

yum update -y
yum install httpd -y
systemctl start httpd
systemctl enable httpd
echo  "This is Server 2" > /var/www/html/index.html
