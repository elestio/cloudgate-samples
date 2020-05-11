# cloudgate-samples
Samples for cloudgate

clone samples: 
    
    git clone https://github.com/elestio/cloudgate.git

Enter the cloned folder then install dependencies:  
    
    cd cloudgate
    npm install

Your are not ready to run the samples below

## Run samples
 
run a sample app on the default port (3000): `cloudgate ./apps/CatchAll/ --rootfolder ./`

Then open the site in your browser: http://127.0.0.1:3000/


run a sample an app in another root folder: `cloudgate ./apps/CatchAll/ --rootfolder /my/custom/folder`

  
Start multiple apps on port 80 with **adminAPI** activated:
`sudo cloudgate -p80 ./apps/Static ./apps/Websocket ./apps/CatchAll --admin 1 --adminpath /CloudGateAdmin --admintoken 12345A000G --rootfolder ./`
Here sudo is required if you are not root to bind port 80

Start an app on port 80 and also on port 443 with **AutoSSL/letsencrypt**:
`sudo cloudgate -p80 --ssl --sslport 443 --ssldomain www.mydomain.com ./apps/Static --rootfolder ./`


Note: By default, cloudgate will use all the cores availables on your server, you can specify the number of cores to use with the option "-c"
eg: `-c 4` means cloudgate will use 4 cores instead of all the cores availables

 ## Run as a service

Install and run as a service with PM2: 
`pm2 start "cloudgate ./apps/CatchAll/ --rootfolder ./" --name cloudgate`



## Remote Shell

Check the sample app RemoteShell for more details about using Websocket to control your instance
You can also try it with this command: `cloudgate -p3000 ./apps/CatchAll --admin 1 --adminpath /CloudGateAdmin --admintoken 12345A000G`

Then open your browser on: http://127.0.0.1:3000/wsAdmin.html?token=12345A000G


