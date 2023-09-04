# AWS-CICD
AWS continuous integration and continuous delivery
![awscicd](https://github.com/Suresh-28/AWS-CICD/assets/111943013/c514d0e8-ce70-492b-8c14-1df04754cba3)


# Continuous Integration
1. Goto code build and create build project [ add on name, description, source, runtime, image, service role, insert build spec, create.]
2. Create new service role [add on codebuild,SSM,name,description,create.]
3. Goto systems manager and open parameters store [add on docker username, password, registry url separetly.]
4. Strat build.
5. Goto Build project ,click on edit ,click on environment, click on override image, enable privileged,update.
6. Now rebuild
7. Create pipeline [add on name, service role, source, code build, project name, single build, create.]

# Continuous Deployment
1. Goto code deploy on console.
2. click on create application.
3. [add on a name , platfrom(ec2)]
4. Click on create application.

5. Goto EC2 instance,
6. create an ec2 instance.

7. Login to ec2 instance using terminal,
8. install code agent for ec2 instance,

Sudo apt install wget

wget https://bucket-name.s3.region-identifier.amazonaws.com/latest/install
[ edit the bucket name based on the region, use https://docs.aws.amazon.com/codedeploy/latest/userguide/resource-kit.html#resource-kit-bucket-names]

chmod +x ./install

sudo ./install auto //CodeDeploy agent on any supported version of Ubuntu

sudo service codedeploy-agent start //To start service

9.  Goto IAM.
10. Create role.
11. select use case as code deploy.
12. Next,[add on name, description]
13. Create role.

//Assign role to EC2

14. Goto instance,
15. Click on actions,
16. click on security,
17. click on modify iam role,
18. select and update.

19. Goto terminal restart the agent sudo service codedeploy-agent restart.
20. Create Deployment group,
21. [add on name, service role, inplace, ec2, tags, unable loadbalancer, create.]

1. Attach ec2 full access to the code deploy service role.
2. Create deployment [add on deployment group name,github,token,repo name, commit id, create.]
3. Install docker sudo apt install docker.io -y

25. Goto code pipeline and edit,
26. Add stage [add on name code deploy, add action group, action name, action provider, application name, deployment group, build artefacts, done.]
27. List out running container Sudo docker  ps
28. Access the port with inbound and outbound traffic rules.

