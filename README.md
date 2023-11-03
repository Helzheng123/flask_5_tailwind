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
     - Go to Front Door and CDN --> click on your container name --> Click on your Endpoint that matches your container name --> Here you will see an endpoint hostname and an origin hostname. Open the Endpoint Hostname.
     - Copy the portion of the URL after "windows.net" from the URL you took from the container. Paste it into the endpoint hostname URL after the ".net"
     - Check to see if your video plays. This will be the URL you place in your ```.html``` file

### 3. Flask App with Tailwind CSS:
   - I used Professor Hants' [example](https://github.com/hantswilliams/HHA_504_2023/blob/main/WK5/example_app/templates/index_tailwind.html) and removed the data on the file. I added two gifs in and placed it next to the header.
   - I used my previous ```app.py``` file and made some changes to accommodate the ```.html``` file

### 4. Cloud Deployment:

### 5. Validate Asset Delivery:
