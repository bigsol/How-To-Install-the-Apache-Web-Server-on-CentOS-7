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

![aaaa](https://user-images.githubusercontent.com/51197053/140646159-102eefb1-55a6-4418-a082-3b1f76e3094e.png)

<br>
<br>
<p>When you have your server’s IP address, enter it into your browser’s address bar:</p>
<br>
http://your_server_ip
<br><br>

<p>You’ll see the default CentOS 7 Apache web page:</p>
<br>

![mstsc_zYtpec1PFY](https://user-images.githubusercontent.com/51197053/140646319-04f0e72b-f889-492f-bb87-38b41992ba0a.png)
<br><br>
<p><b>Step 3 — Managing the Apache Process</b></p>
<br><br>
<li>Now that you have your web server up and running, let’s go over some basic management commands.
<br><br>
To stop your web server, type: 
<br>
<p>sudo systemctl stop httpd<p>
<br>
To start the web server when it is stopped, type:
<br><br> 
sudo systemctl start httpd
<br>
<br>
To stop and then start the service again, type:
<br><br>
sudo systemctl restart httpd
<br>
<p>If you are simply making configuration changes, Apache can often reload without dropping connections. To do this, use this command:</p>
 <br>
 sudo systemctl reload httpd
 <br>
 <p>By default, Apache is configured to start automatically when the server boots. If this is not what you want, disable this behavior by typing:</p>
 <br>
 sudo systemctl disable httpd
 <br><br>
 To re-enable the service to start up at boot, type:
 <br><br>
 sudo systemctl enable httpd
 <br>
 <p>Apache will now start automatically when the server boots again.</p>
 <p>The default configuration for Apache will allow your server to host a single website. If you plan on hosting multiple domains on your server, you will need to configure virtual hosts on your Apache web server.</p>
<br>
<p><b>Modules needed for using Apache as a reverse proxy</b></p>
<br> 
 
 
 
