# How to deploy react app with docker


---

## YARN is better

### first of all create basic project with yarn

After install npm with [nvm](https://github.com/nvm-sh/nvm) run below command to create boilerplate
```

nvm install node
sudo npm install --global yarn
yarn create vite frontend --template react
```

### Run with docker
```
docker compose up -d 
```








---
```
yarn install 
docker build -t app .
yarn run build
```

this create dist directory we can serve with nginx



# npm also can run use 
```
npm create vite@latest my-app -- --template react

cd my-app
npm install 
npm run dev -- --host
```

