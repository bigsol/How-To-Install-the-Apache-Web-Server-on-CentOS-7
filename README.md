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

