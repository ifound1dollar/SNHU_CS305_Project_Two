# SNHU_CS305_Project_Two
Project two from CS-305 Software Security



### Briefly summarize your client, Artemis Financial, and their software requirements. Who was the client? What issue did they want you to address?
Artemis Financial is a financial company offering consulting to customers. The company runs a web application that must allow users to upload files (like financial documents) securely to the server. They needed a way to ensure that the connection itself was secure and that the files being uploaded were not tampered with while in transit.

### What did you do very well when you found your client’s software security vulnerabilities? Why is it important to code securely? What value does software security add to a company’s overall wellbeing?
I was able to identify multiple security vulnerabilities while manually reviewing the code. This included private data being handled as query parameters, lack of error checking, and other basic vulnerabilities like being vulnerable to SQL injection. It is critical to code securely because a company's users certainly want their information to be kept secure and out of the hands of people who want to use it for harm. Companies with good software security are often most trusted by the public.

### What part of the vulnerability assessment was challenging or helpful to you?
Suppressing false positives after running the OWASP Dependency Check was probably the most challenging part. It felt unsafe (though it really was not) to suppress a large number of vulnerabilities, even though they were not actually relevant to the application, because it felt like 'sweeping the problem under the rug'. That being said, it helped me use more care when handling identified vulnerabilities because I needed to be absolutely sure that what I was suppressing was actually a false positive. 

### How did you increase layers of security? In the future, what would you use to assess vulnerabilities and decide which mitigation techniques to use?
I implemented SSL/HTTPS into the web application as well as a checksum verification that will ensure that files uploaded to the server by clients are not tampered with while in transit. Additionally, I took steps to manually fix vulnerabilities in code like unsafe error checking that could result in an application crash or sensitive information being leaked to a client. In the future, my first step would be to manually review code to identify and handle any basic vulnerabilities before moving onto implementing SSL/HTTPS or static testing tools.

### How did you make certain the code and software application were functional and secure? After refactoring the code, how did you check to see whether you introduced new vulnerabilities?
Running the code locally on my machine, then accessing the running REST application via localhost was my method to ensuring that the application was running correctly. A basic checksum verification using the REST mapping '/hash' was implemented to verify that it was working correctly. Then, to ensure that no new vulnerabilities were exposed, the OWASP Dependency Check was run again.

### What resources, tools, or coding practices did you use that might be helpful in future assignments or tasks?
I would certainly make use of the static testing tool, the OWASP Dependency Check (https://owasp.org/www-project-dependency-check/). This plugin makes use of vulnerabilities exposed in the National Vulnerability Database, hosted by NIST (https://nvd.nist.gov/). I imagine that these tools and resources will be useful not just for college assignments, but out in the 'real world' as well.

### Employers sometimes ask for examples of work that you have successfully completed to show your skills, knowledge, and experience. What might you show future employers from this assignment?
This assignment (and by extension, this course) was my first time handling secure communication between a server and clients. I would likely present my use of the Java Keytool to generate a keystore and SSL certificate for HTTPS. I would also present my use of the MessageDigest class to run a checksum verification using SHA-256.
