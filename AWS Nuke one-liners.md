Delete all volumes (10/s):
```
for K in $(aws ec2 --region us-west-2 describe-volumes --query 'Volumes[*].VolumeId' --output=text); do
aws ec2 --region us-west-2 delete-volume --volume-id $K &; sleep 0.1
done
```

