# Stronghold Paste Crawler

This contains all the necessary files to setup the enviorment and run the code necessary to crawl the site 'Stronghold Paste'.
The dockerfile will create an image that contains the configuration and services to run TOR and Privoxy, execute the script to crawl the site and add a cronjob that runs the script again every 4 hours. The database and the log file created by the script will be persistent as volume will be mounted on the host machine. The host machine must have docker installed.


## Steps:
1. Extract the tar
2. Open a terminal in the extracted directory containing the Dockerfile
3. Execute the following command to create the image: `sudo docker build -t omer .`
4. Wait until the image is created, Execute `sudo docker images` to make sure the image is created successfully.
5. Run the image using the following command `sudo docker run -dit -p 8118:8118 -p 9050:9050 --name=omer_container -v <path to directory on host>:crawler_output omer`
6. ***Note: The path to the mounted directory on the host machine must be an absolute path!***
