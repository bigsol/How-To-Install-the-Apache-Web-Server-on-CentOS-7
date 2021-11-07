# How-To-Install-the-Apache-Web-Server-on-CentOS-7
How To Install the Apache Web Server on CentOS 7
<br>
<p><b>Step 1 — Installing Apache.</b></p>
sudo yum update httpd<br><br>
sudo yum install httpd<br>
<br>
<text>
If you completed the Additional Recommended Steps for New CentOS 7 Servers guide mentioned in the prerequisites section, you will have installed firewalld on your server and you’ll need to open up port 80 to allow Apache to serve requests over HTTP. If you haven’t already done so, you can do this by enabling firewalld’s http service with the following command.</text>  
<br><br>
sudo firewall-cmd --permanent --add-service=http
<br>
<br>
<text>
 If you plan to configure Apache to serve content over HTTPS, you will also want to open up port 443 by enabling the https service:
 </text>
 <br><br>
 sudo firewall-cmd --permanent --add-service=https
<br>
<br>
Next, reload the firewall to put these new rules into effect:
<br><br>
sudo firewall-cmd --reload
<br><br>
<p><b>Step 2 — Checking your Web Server</b></p>
<br>
<text>
 Apache does not automatically start on CentOS once the installation completes. You will need to start the Apache process manually:
 </text><br>
 sudo systemctl start httpd
 <br><br>
 Verify that the service is running with the following command:
 <br><br>
 sudo systemctl status httpd
 <br><br>
You will see an active status when the service is running:<br><br>
![image](https://user-images.githubusercontent.com/51197053/140646110-f2110a6e-b0b9-4611-b279-3f5221157ca8.png)
<br>

