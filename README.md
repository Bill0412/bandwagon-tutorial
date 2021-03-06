# Step by Step Tutorial
#### *Tip:  1. If you want an easier way (but less control over the service including the protocol) to bypass the GFW (Great Firewall), just [click here](https://github.com/yinghuocho/firefly-proxy) and choose the right client for your device.<br> 2. To be honest, there is a totally free and extremely fast service if do not mind the slightly embedded ad. (Click [here](#u-by-falun) to know more about [u.zip](u.zip).)<br>3. It should be noted that it will be much easier for you to setup your server and connect to it if you have already bypass the gfw using either one of the previous tips.*
## Part A: Purchase a server from BandwagonHost. (If you want a premium, [click here](https://bwh1.net/aff.php?aff=032&pid=72) and then go to step 5 directly, this kind of VPS supports 8K video play) ##
  **1. Open the [official website of BandwagonHost](https://bwh1.net/) in your web browser**  
  *(Tips: you may have no access to https://bandwagonhost.com/, just try https://bwh8.net/ out.)*    
  ![The official website](pictures/bwh-index.png)   

  **2. Select your preferred VPS([Virtual Private Server](https://en.wikipedia.org/wiki/Virtual_private_server)) option. Here we choose the first option(10G VPS), which might be sometimes unstable.([Click here](https://bwh1.net/aff.php?aff=544&pid=56) pay extra 10 dollars for premium (much more stable and less latency) and then [Skip Several Steps](#add-to-cart))**   
  *(Cautious: Some of these options are charged by quater or month instead of year, so pay attention if you'd like to select one of the rest.)*   
   ![options](pictures/bwh-options-1.png)  

  **3. Click on [Order KVM or OpenVZ](https://bwh1.net/vps-hosting.php)**  
   ![options](pictures/bwh-options-2.png)  

  **4. Click on the *Order [KVM](https://www.linux-kvm.org/page/Main_Page)* option in the first column of the table.**  *(Our Outline server will be on an Ubuntu distribution of Linux)*
   ![select order kvm](pictures/order-kvm-1.png)  
 
  **5. <a id="add-to-cart"/>Click on *Add To Cart***
   ![add to cart](pictures/add-to-cart.png)   

  **6. Click on *Checkout***
   ![checkout](pictures/checkout.png)  

  **7. <a id="register"></a>Assuming you're not registered yet, fill in the forms to create an account and choose your payment method** *(Alipay is recommended for Chinese users)*
   ![registration & payment](pictures/register-pay-1.png)   

  **8. Click on *Pay Now***
  ![Pay Now](pictures/pay-now-1.png)  

  **9. Scan the Alipay QR payment code and finish your payment on your mobile phone or directly on your PC**
  ![Alipay](pictures/alipay.png)
#### *After the payment, you are now ready to set up the server.*



## Part B: Set Up an Outline Server on your VPS   
  *After the payment, you should now be able to access the server you have just purchased.*  
  *Please follow the following steps to set up your server.* 
   
 **1.Login to your account**   
 *Click on the *Client Area* button at the upper right corner of the official website.*
  ![index client area](pictures/bwh-index-1.png)
 * *Log in with your email address and password that have been previously registered for your account in [<u>part A, step 7</u>](#register) of this tutorial.*  
 *Click on the Login button after you have filled in the forms.*
  ![index client area](pictures/client-area-1.png)  

  **2. Install the right Operating System on your server**  
  *Click on **Services** then **My Services***  
  ![services](pictures/services.png)
  *<a id="open-control-panel"/>Click on **KiwiVM Control Panel***
  ![control panel](pictures/control-panel-1.png)
  *Stop the server before reloading: Click on **Stop***  
  ![stop the server](pictures/stop-server.png)
  *Click on **Install New OS***
  ![new OS intallation](pictures/install-new-os.png)
   
  **3. Install new OS**  
  *Select **Ubuntu-18.04-x86_64**, which is at the bottom of the selection box. Then **check the agreement box** and finally left click **Reload**.*  
  ![new OS selection](pictures/install-new-os-1.png)
  *You should see something like below a few seconds later. The password and SSH port are important, so you may copy it or take a screenshot for later utility. (This information is also sent to you by email, but may take a while, so keep it yourself just in case)*<a id="root-password"></a>  
  ![root password](pictures/root-password.png)

  **4. Install PuTTy for your PC**  
  <a id="mac-command-solution"/>*If you use macOS, [click here](#mac-putty-solution) to access your server and configure it.* 
  *[Click here](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) to go to the PuTTy download page. Download the 32-bit or 64-bit version(mostly 64-bit) version of PuTTy and install it.*  
  *After a quick installation, you are now ready to use the PuTTy to connect to the server.*
  ![putty download](pictures/putty-download.png)

  <a id="login-putty"></a>**5. Login to the server with PuTTy**  
  *Go Back to **Main controls** and look up the IP address and SSH Port. *
  ![main controls](pictures/main-controls.png)
  *Run PuTTy.exe on your PC, then enter the IP address and SSH Port according to the **Main controls** Panel*
  *<br> (Note: 1. When you input your password, it is not shown explicitly, but recorded internally. So just **hit the Enter key** when you're ready to login.<br>2. **Ctrl+V** (**Shift+Insert** instead) for paste, **Ctrl+C** (**Ctrl+Insert** instead) for copy are **NOT supported** in shell.)*  

  *<a id="login-info-input"/>Login with the following customized information:*  
  `log in as: root`  
  `root@xxx.xxx.xxx.xxx's password: (The one you copied or in the screenshot or you can find it in your mail box.)`  

  ![email password](pictures/email-password.png)  

  ![putty connect](pictures/putty-info.png)
  *Click on yes in the Alert Window and you are now ready to configure the server remotely and you should see:*  
  ![successful login smample](pictures/successful-login.jpg)
  *(A successful login looks like this)*

  **6. Configure the environment**<a id="configure-environment"></a>  
  *It is time for us to copy and paste code! Interactive shell reacts responsively whenever we input a single line of code and hit the Enter key on our keyboard.
   So what you need to do is to enter the following code line by line and check if each one of these lines work similar to my description.*
  1. `sudo -i`   
  *You should get a new line as a response. Just continue to enter [line 3](#code-line-3).*
  2. <a id="code-line-2"/>`sudo apt-get install curl`   
  *(If you are using CentOS, click [here](#centos-install).)*  
  *After hitting the Enter key and wait for a few seconds, you should see a prompt. Enter y and the installation should continue.*  
  ![install curl](pictures/curl-install.png)
  *Go back to **[line 3](#code-line-3)** when you see this:*
  ![curl installation finished](pictures/install-curl-done.png)
  3. <a id="code-line-3"/>`curl -sS https://get.docker.com/ | sh`  
  *(If you are unable to use curl, go to [line 2](#code-line-2).)*     
  *If you are working fine with **curl**. It may take quite a few minutes until you see something like this:*
  ![docker installed](pictures/docker-installed.png) 
  4. `systemctl start docker`  
  *The same response as the 1st line.*
  5. `systemctl enable docker`  
  ![docker installed](pictures/enable-docker.png)
  6. `systemctl status docker`  
  *If you see the green"active running", you are safe to continue.*
  ![docker status active](pictures/docker-status.png)
  *Hit Q key directly*
  ![docker running actively](pictures/docker-status-1.png) 
  
  **<a id="setup-outline"/>"7. Set up the *Outline server***  
  Enter the following line of code in the shell.  
  `bash -c "$(wget -qO- https://raw.githubusercontent.com/Jigsaw-Code/outline-server/master/src/server_manager/install_scripts/install_server.sh)"`
  <a id="outline-code"></a>![outline code](pictures/install-outline-done.png)
  *Select the green line(in the above picture) with your mouse cursor and the line is automatically copied to your paste board. Just paste, save and keep it in a .txt file for later use. (I highly recommend you keep this file on your PC and not delete it.)*  
  ![copy outline server information](pictures/copy-outline-code.png)  
#### *Congratulations! Up til now, you have set up the server side of your VPN.*

## Part C: Connect to the server from multiple platforms
  
  **1. Install the *Outline Manager* on your PC**  
  *Download the **Outline Manager**(It is Open Source) in the repository (at the top of [this web page](https://github.com/Bill0412/bandwagonhost-tutorial)).*  
  ![download outline manager link](pictures/github-outline.png)
  ![download outline manager](pictures/github-outline-1.png)
  *Double click on the Outline-Manager.exe on your PC to start the quick installation of Outline Manager.<br>Wait less than a minute and you will see a the Outline Manager window, then click on **GET STARTED**.*
  ![get started outline manager](pictures/outline-manager-start.png)
  *When you see the Outline Manager Window below, copy and paste the code you copied in [Part B, Step 7](#outline-code) and then click on **DONE**.
  ![paste outline key](pictures/paste-outline-code.png)
  
  <a id="connect-pc"></a>**2. Connect current PC you are using to the server**  
  *Click on **CONNECT THIS DEVICE***
  ![connect this device](pictures/connect-this-device.png)
  *Click on **COPY***
  ![copy the invitation link](pictures/copy-invitation.png)  
  *Click on **INSTALL OUTLINE**. Download and quickly install the Outline Client and then open it. (If you want a client on any Apple device, please click [here](#apple-client).)*
  ![install outline for windows](pictures/install-outline-client.png)
  *In the Outline Client for Windows, click on **ADD SERVER**(If it does not work, please make sure you have the link starting with "ss" in your paste board.)*
  ![add server](pictures/add-server.png)
  *Click **CONNECT** to connect to your VPS(If it does not work, you should try several time until a successful connection.)*  
  ![connect outline client](pictures/connect.png)
  *A successful connection:*
  ![connected](pictures/connected.png)

### *Congratulations! Now your PC is connected to the real world of Internet!*

  **3. Connect from multiple platforms**  
  *Click on **CONNECT A DIFFERENT DEVICE***
  ![connect a different device](pictures/connect-different-device.png)
  *Copy the link and open it in your other devices.*  
  *You will be able to easily set it up on other devices just like in [Step 2](#connect-pc).* 

  **4. Occasionally share your Outline Server with your family and friends securely**  
  *Click on **ADD KEY**, you can either raname the key firstly or copy the generated link and share it with your friend directly.<br>And you will know every friends' data usage and can control their privilege with the help of the Outline Manager.*


## When You are confused (Updating)
   ***1. When you are unable to download a software***  

   * *Try to shoot your troubles with [**Network Issue Solutions**](#network-issue-solutions)**

   * ***Outline Client** download link for **Windows**: <br> https://raw.githubusercontent.com/Jigsaw-Code/outline-releases/master/client/Outline-Client.exe*  
    
   * ***Outline Client** download link for **IOS**: <br> https://itunes.apple.com/us/app/outline-app/id1356177741*  
   
   * ***Outline Client** download link for **macOS**: <br> https://itunes.apple.com/us/app/outline-app/id1356178125*
   
   * ***Outline Client** download link **with long term support**: <br> https://github.com/Jigsaw-Code/outline-client/releases*
   
   * ***Outline Manager** download link  for **Windows**: <br> https://raw.githubusercontent.com/Jigsaw-Code/outline-releases/master/manager/Outline-Manager.exe*  
   
   * ***Outline Manager** download link for **macOS**: <br> https://raw.githubusercontent.com/Jigsaw-Code/outline-releases/master/manager/Outline-Manager.dmg*
   
   * *If none of these above methods works, you may try one of those [free limited VPNs](#free-vpn) during your setup process.* 

   ***2. When your browser is unable to load a webpage*** 
   * *If none of these above methods workds, you may try one of those [free limited VPNs](#free-vpn) during your setup process.* 
   
   ***<a id="mac-putty-solution"></a>3. If you use macOS and you're unable to install and use PuTTy***
   
   *There's no macOS version of PuTTy. One of the easiest but less convenient way it to use the shell provided by BandwagonHost.<br>click on **Root Shell - Interactive**(in the [control panel](#open-control-panel)) on the left side bar, then click on **Launch***
   ![open interactive shell](pictures/mac-shell-solution.png)
   *In the interactive shell, you are now able to [login to the server](#login-info-input) and then [configure the enviroment](#configure-environment). But beware that you are unable to copy and paste but only type line by line.*
   *After executing the code in Part B, Step 6, you should now close the interactive shell and open **Root shell - advanced** from the left side bar, copy and paste the code in [Part B, Step 7](#setup-outline)* and then run it.
   *Wait a few seconds and you'll see the outcome, you can easily find a chunk of data wraped by the pair of curly brackets(included). Copy the data and save it for later use. (just like [here](#outline-code))*

   ***4. <a id="apple-client"></a>macOS and IOS users are unable to download Outline client from Chinese Itunes Store or App Store***
   *The only way to fix it is to change the location of your Apple ID. Or alternatively, get a shared US Apple ID from the Internet or [Taobao](https://www.taobao.com)*.
   
   ***<a id="centos-install"></a>5. apt-get is not supported in CentOS***  
  *I don't recommend you to use CentOS, but in case you do, the counterpart of this line of code is:*  
  `sudo yum install curl`  
  *But typically, you should have embedded **curl** in your CentOS.*  


## Network Issue Solutions(Updating)<a id="network-issue-solutions"></a>
   * *Refresh your browser(you may need to refresh several times) and wait(this may take several minutes).*  
   
   * *Use China Mobile hotspot created on your phone (when connecting your PC, since China Mobile typically has less censorship).*

## Free VPN list(Updating)<a id="free-vpn"></a>

   * *For **Apple** Users: This is a good choice for those who use IOS as their main devices in China, since it is available on mainland Apple store: https://github.com/yinghuocho/firefly-proxy . <br> (Tip: it is in fact much more stable than a normal Bandwagonhost server , so you may want to use this as your main option to bypass the GFW as an Apple user.)* 
   
  * <a id="u-by-falun"></a>*For **Android** and **Windows** Users: You can download the [u.zip](u.zip) file and try out this VPN for **Windows** by yourself. It's secure, extremely fast and totally free, but with some ads since it's sponsored by Falun Dafa, which I suggest you to ignore while using it. (Alternatively, you can download the file directly from the link [here](https://git.io/vEJlj).) The **Android .apk** file is also available from [here](u108.apk)).*



## Issues to be solved in this tutorial(Will be solved in later updates):
  * *Open UDP and TCP on port 22 for CentOS server.(CentOS support of this tutorial is not fully implemented)*
  * *If you find issues not in the list, please feel free to contact me (Email: **jxphxufh@gmail.com**) so that other users can enjoy better experience.*


## Donates
#### *This is a free and open source tutorial maintained by Bill. If you like this tutorial or want more tutorials like this, and are willing to financially support me, I'd greatly appreciate it and be motivated.*
   <img src="pictures/alipay-code.jpg" width="45%"/> <img src="pictures/wechat-code.png" width="45%"/>
