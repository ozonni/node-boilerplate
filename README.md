## node-boilerplate

Quickstart TypeScript/Node.js project template with built-in apaleo client.

### Quickstart

1. Run `npm install`
2. Create an `.env` file based on `.env.example`
3. Run `npm start`

### Docker

1. Build docker image `docker build -t app .`
2. Start docker container `docker run -it -p 3000:3000 app`
3. Navigate to [http://localhost:3000](http://localhost:3000)

### How to update apaleo api proxy?
Grab the latest version of a `swagger.json` for any service that needs to be updated. 
The link to `swagger.json` file can be found here:
- [apaleo Core API](https://api.apaleo.com/swagger)
- [apaleo Webhook API](https://webhook.apaleo.com/swagger)

Once you have the `swagger.json` locally, navigate to the `/clients/apaleo` folder and copy the file into the folder.
Then, pick the corresponding `autorest-{service}.yaml` and call autorest, for example:
```bash
autorest .\autorest-booking.yaml
```

Once the proxy is generated successfully - make sure you removed the `swagger.json` from the project.

### How to add a new apaleo api proxy?
Like the previous part, you will need to have a `swagger.json` file first and put it inside the folder in `/clients/apaleo`. From that moment, everything is pretty straightforward. 
Just go to the folder and create a new `autorest-{service}.yaml` file, based on any other configuration file there. And in this folder just run:
```bash
autorest .\autorest-{new_service}.yaml
```

### Contribution

Feel free to open an issue if you found any error or to create a pull request if want to add additional content.
