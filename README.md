# Production
Clone this repo
```
git clone https://github.com/umono-cms/build umono
```
Change directory
```
cd umono
```
Init and update submodules
```
git checkout $(git tag -l "v0.*" | sort -V | tail -n 1)
git submodule update --init --recursive
```
## Setup
Create an empty file for database
```
touch umono.db
```
Copy .env-example file from umono submodule as .env
```
cp ./umono/.env-example ./.env
```
Edit **.env** file to set username and password. These will be hashed when first run.

**SECRET** environment variable is optional. If it is empty, Umono will generate it for you on runtime.

Up
```
docker compose -f docker-compose.prod.yml up --build --force-recreate
```
Ready!

Go to `/admin` and create your first page!
## Update
Fetch last v0.x.x
```
git fetch --tags
git checkout $(git tag -l "v0.*" | sort -V | tail -n 1)
git submodule update --init --recursive
```
Down & Up
```
docker compose -f docker-compose.prod.yml up -d --build --force-recreate
```
# Demo
Requires *git* and *docker*

Clone this repo
```
git clone https://github.com/umono-cms/build umono-demo
```
Change directory
```
cd umono-demo
```
Init and update submodules
```
git checkout $(git tag -l "v0.*" | sort -V | tail -n 1)
git submodule update --init --recursive
```
Fetch last demo DB
```
git show origin/main:umono.demo.db > umono.demo.db
```
Up
```
docker compose -f docker-compose.demo.yml up --build --force-recreate
```
Ready!
```
http://127.0.0.1:8999/admin
```
Default credentials:
```
username: admin
password: admin
```
