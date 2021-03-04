
### high level steps for creating testing environment

 1) create an s3 bucket (using cli of console)  
 2) upload contents of "s3bucket" folder into the root of your s3bucket  
 3) run r53.cf to create a hostedzone for your domain   
 4) run ec2.cf to create VPC and instance  
 5) you should be able to hit your web app at the assigned host and domain, assuming you have DNS working end to end  
 6) you should be able to GET request http://host.yourdomain.tld/api/instance-action and get a 404  
 7) using `api.sh` and providing `stop` or `terminate` as an argument will make the "instance-action" return a "200" as well as a small bit of json emulating what AWS would send. Running `api.sh` with no argument or anything other than `stop` or `terminate` will put the response from "instance-action" back to a 404 with no data.
