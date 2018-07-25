# Introduction 
Load testing APIs 

# Getting Started
1. Install Jmeter https://jmeter.apache.org/
2. Open .jmx file in jmeter and run  test. 
3. This is optional unless you are doing it on cloud. To run tests against any server you will need jwt. You can get jwt from  swagger request. 
4. This is optional unless you are doing it on cloud. Add the jwt to corresponding Http Header Manager.
5. This is optional unless you are doing it on cloud. If you want to bypass load balancer, setup to hit  nginx-ingress directly
6. Should be able to run tests now. 
7. Once the test is built or modified in jmeter, it can be run through command line also. 
8. Tests cycles through users.csv file

   
    To run  
   ```commandline
   jmeter -n -t pathTo\UserServiceTests.jmx  -l pathTo\UserServiceTestResults.csv 
   ```
   To generate the report though command line 
   ```commandline
   jmeter -g pathTo\UserServiceTestResults.csv -o pathTo\UserServiceTestResults
   ```

# SetUp to hit nginx-ingress directly I have used gcloud so that is what i have here . 
1. Install kubectl
```commandline
 gcloud components install kubectl
```
2. Get credentials 
```commandline
 Run gcloud --project my-project-name container clusters get-credentials project-name
```
3. Forward the port
```commandline
 Run kubectl --namespace nginx-ingress port-forward nginx-name 80 (get running ingin-ingress from cloud)
``` 
