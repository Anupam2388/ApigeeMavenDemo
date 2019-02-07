# Apigee maven plugin demo
    In this lab, we will see how to package an API Proxy bundle and deploy it to Apigee Edge using the Apigee Maven Deploy Plugin

# Develop the API proxy 
    Repository contains the sample proxy which returns the response JSON reponse code:200 and message "The request was fulfilled." in case of successful invocation. 
    
# Pre-requisites
    1. Maven 
    2. Java 1.8 and above. 
    3. Apigee API proxy bundle.

# Solution
Follow to below steps to build and deploy the proxy in Apigee Edge. 
1. Download the API proxy bunble or the sample bundle provided in this repo  and unzip
2. Run the below command from the same folder which has pom.xml file


    Syntax :   
    mvn clean install -Ptest -Dorg={youOrg} -Dusername={edge_user} -Dpassword={edge_password}
        - {youOrg} is the name of your organization
        - {edge_user} is the username with appropriate deploy permission.
        - {edge_password} password to authenticate user.
    Example :
    mvn clean install -Ptest -Dorg=anup-org -Dusername=anup@sample.com -Dpassword=secretid    


The above command will deploy the proxy named "sample_jenkins_proxy" which is mentioned in the POM.xml file. In case you prefer to use your own API proxy bundle please change the pom.xml file present in the root folder and rerun the above command. 

# Verify
If everything goes well you can see the proxy in the Apigee Edge console. i.e. Develop >> API Proxies and select your respective proxy. 

# Test 
1. Navigate to trace session and start new session and Hit the send button. 

    
    Syntax :
        http://<<orgname>>-<<env>>.apigee.net/jenkinsdemo
    Example :
        http://anup-eval-test.apigee.net/jenkinsdemo
    
You can make local changes, run the same maven command to deploy the latest changes to Apigee Edge
