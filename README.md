# nginx-yii2
Yii2 + Nginx Docker image, including composer

## Running the container
Container uses /app as volume, you could link volume to that folder to have files available in the host system.

Run command example:
docker run -p 80:80 --name yii2app -v "$(pwd)":"/app" -d synomi/nginx-yii2


## Example of creating yii2 basic app
Nginx default web dir is /app/web, which will not exist when container is first started. You need to create yii2 application to /app, which will create /app/web dir along with other yii2 application files.

Creating basic app: (Composer will ask for GitHub token for API rate limit)
docker exec -it yii2app composer create-project --prefer-dist yiisoft/yii2-app-basic /app

After creating the basic app, you should see the app in your http://dockerhost/ and have app's files available in your current directory, if you linked the volume like in the example. 
