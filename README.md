# flask_5_tailwind
This assignment will give you hands-on experience in video hosting, creating a Flask app styled with Tailwind CSS, and deploying it to a cloud platform. You'll leverage CDN services in Google Cloud or Azure to optimize video delivery, ensuring a seamless user experience for viewers worldwide.

### 1. Video Creation or Procurement:
  - I used a video of Bonnie, the rabbit my sister and her boyfriend have. It is only 4 seconds long but this is a video of Bonnie attempting to jump on top of his cage (which didn't end well and he got embarrassed 😥).
  - He did accomplish his goal in another video but that is for next time 🫡.

### 2. Cloud CDN & Video Hosting:
 - I hosted my video through Azure's Content Delivery Network (CDN)
 - To set up the CDN needed:
     - On Azure, go to Storage Account --> Create Storage Account --> Set your storage account to a resource group (if you do not have one, click on Create new) --> Enter your desired storage account name --> Keep the region at East US if you are on the East Coast --> Standard --> Geo-redundant Storage (GRS) --> Review --> Create
     - In your storage account, go to Security --> enable "Allow Blob anonymous access"--> Save
     - Go to Containers --> create Container --> Name the container --> change anoynmous access level to container --> create
     - In the Container you just created, upload a video using the upload button --> click on the desired video --> copy the URL, and paste it into a new tab in your browser
     - Go to Front Door and CDN --> Create a new endpoint --> make sure to put it as ignore query string --> create --> click on your container name --> Click on your Endpoint that matches your container name --> Here you will see an endpoint hostname and an origin hostname. Open the Endpoint Hostname.
     - Copy the portion of the URL after "windows.net" from the URL you took from the container. Paste it into the endpoint hostname URL after the ".net"
     - Check to see if your video plays. This will be the URL you place in your ```.html``` file

### 3. Flask App with Tailwind CSS:
   - I used Professor Hants' [example](https://github.com/hantswilliams/HHA_504_2023/blob/main/WK5/example_app/templates/index_tailwind.html) and removed the data on the file. I added two gifs in and placed it next to the header.
   - I used my previous ```app.py``` file and made some changes to accommodate the ```.html``` file

### 4. Cloud Deployment:
  - I deployed my flask app on Azure App Service.
  - In the Google Shell terminal, you will need to install [AZURE CLI](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-linux?pivots=apt) with this: ```curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash```. Copy and paste the line in and enter.
  - Then type in ```az```. Type in ```az login --use-device-code``` and wait for a link and a code to appear in the terminal. Copy the code and press the link to log in to your Azure account. This will help connect your Google Shell with your Azure account.
  - Log in to your [Azure account](https://azure.microsoft.com/en-us/).
  - Type in ```az webapp up --name <replace with what you would like to name the webapp> --runtime PYTHON:3.9 --sku B1```. Once entered, the Azure app service will create the web app for you. This step may take a while to load.
  - Once the service completes the deployment, you can go to **App Service** in the Azure site to deploy the web app. Choose the appropriate web app. Then you will be redirected to the overview of the web app. The link for your application will be found at the **Default domain**. Click on the link and you will now be redirected to your web application.
  - 🤗 Congrats! You have deployed your web application! 🤗

You can check out my Flask application through Azure App Service here: https://helen-tailwind.azurewebsites.net/

![image](https://github.com/Helzheng123/flask_5_tailwind/assets/123939070/58e2f89d-c176-4a8a-84e9-7339fe8dd36f)


### 5. Validate Asset Delivery:
 - I went on GTmetrix and ran a test with the [URL](https://helen-tailwind.azurewebsites.net/) and the [results](https://github.com/Helzheng123/flask_5_tailwind/blob/main/Screenshots%20and%20Videos/GTmetrix%20test%20for%20cdn.png) came out as:
![image](https://github.com/Helzheng123/flask_5_tailwind/assets/123939070/4408a5d8-4b63-4bc1-85c0-9e57cf1640f0)

 - With CDNs, you can have faster content delivery which can improve the user experience. CDNs are capable of evenly distributing incoming traffic across multiple servers to prevent overloading. CDNs also have scalability that can ensure your application will run even during times of spikes in traffic.

### 6. Complications: 
 - I did not encounter any complications for this assignment.
