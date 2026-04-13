Windows batch command—
cd %WORKSPACE%\PCMJava
if not exist bin mkdir bin
dir /s /b src\*.java > sources.txt
javac -d bin @sources.txt
java -cp bin com.pcm.Main

Shell—
cd $WORKSPACE/PCMJava
mkdir -p bin
find src -name "*.java" > sources.txt
javac -d bin @sources.txt
java -cp bin com.pcm.Main


















MAVEN
maven-archetype-quickstart
Group Id: com.bank 
o Artifact Id: BankingMavenJUnit 
o Version: 1.0

Open pom.xml and add JUnit 5 dependency:
<dependencies>
<dependency>
<groupId>org.junit.jupiter</groupId>
<artifactId>junit-jupiter</artifactId>
<version>5.10.0</version>
<scope>test</scope>
</dependency>
</dependencies>

Add Surefire plugin:
<build>
<plugins>
<plugin>
<groupId>org.apache.maven.plugins</groupId>
<artifactId>maven-surefire-plugin</artifactId>
<version>3.1.2</version>
</plugin>
</plugins>
</build>





STEP 5: Create Application Class
Create file:
src/main/java → com.bank → BankService.java
package com.bank;
public class BankService {
public boolean transfer(double balance, double amount) {
return balance >= amount && amount > 0;}}
Create file:
src/test/java → com.bank → BankServiceTest.java
package com.bank;
import static org.junit.jupiter.api.Assertions.*;
package sathya;
import static org.junit.Assert.*;
import org.junit.Test;
public class maven {
@Test
public void validTransferTest() {
maven service = new maven();
assertTrue(service.transfer(1000, 500));
}
@Test
public void invalidTransferTest() {
maven service = new maven();
assertFalse(service.transfer(200, 500));
}
public boolean transfer(int balance, int amount) {
if (balance >= amount) {
return true;
}
return false;
}}



KUBERNETES
STEP 1 – Check Cluster
kubectl get nodes
STEP 2 – Create Deployment
kubectl create deployment webapp --image=nginx
STEP 3 – Check Pods
kubectl get pods
STEP 4 – Scale Deployment
kubectl scale deployment webapp --replicas=3
Now check:
kubectl get pods
STEP 5 – Create Service
kubectl expose deployment webapp --type=NodePort --port=80
Check service:
kubectl get svc
STEP 6 – Create Pod with Resource Limits (CGroup )
Create YAML file:
nano limited.yaml
Paste:
apiVersion: v1
kind: Pod
metadata:
 name: limited-pod
spec:
 containers:
 - name: nginx
 image: nginx
 resources:
 limits:
 cpu: "500m"
 memory: "128Mi"
Now save:
CTRL + X
Y
Enter
Apply File:
kubectl apply -f limited.yaml
Check pods:
kubectl get pods
STEP 7 – Verify Resource Limits
Command:
kubectl describe pod limited-pod
Scroll and find:
Limits:
 cpu: 500m
 memory: 128Mi
This shows:
• CPU limited to 500 milli cores
• Memory limited to 128 MB
Internally:
Kubernetes uses CGroup to enforce these limits.




STS
•	Click File → New → Spring Starter Project
•	Enter:
•	Project Name: demo6
•	Type: Maven
•	Java Version: 17
•	Click Next
•	Select:
☑ Spring Web
•	Click Finish

•	In Package Explorer:
•	src/main/java → com.example.demo
•	Right-click package → New → Class
•	Class Name: HomeController
package com.example.demo;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;
@RestController
public class HomeController {
@GetMapping("/")
    public String home() {
        return "Application Running Successfully";
    }}

•	Click Run As → Spring Boot App
•	 Step 6: Verify Output
•	Open browser and type:
•	http://localhost:8080


