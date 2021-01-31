# toolio

## Project setup
```
npm install

touch .env 

echo "SHOPIFY_API_KEY="{apiKey}"" > .env && echo "SHOPIFY_API_SECRET="{apiSecret}"" >.env
```

* Create app url on shopify dashboard: http://localhost:3000/shopify
* Add http://localhost:3000/shopify/callback to allowed redirection URL's

### To Run
```
cd toolio

node index.js

cd client

npm run serve
```

* node js runs on port 3000 and vue app runs on port 8080.
