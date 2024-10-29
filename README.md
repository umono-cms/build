# Demo
Requires *git* and *docker*

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
git submodule update --init --recursive
```
Up
```
docker compose -f docker-compose.demo.yml up
```
Ready! username and password are **admin**
```
http://127.0.0.1:8999/admin
```
