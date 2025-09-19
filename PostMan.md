# How to set up auto save functionality of `access Token` in the `env` workspace in postman. 

## Create a new Environment WorkSpace or use an existing one 

## 1. In the Auth Request Page 
## Paste the following `code` in the `Scripts` tab. 

```bash

var jsonData = pm.response.json();
if (jsonData.accessToken) {
    pm.environment.set("accessToken", jsonData.accessToken);
    console.log("Access token saved:", jsonData.accessToken);
}

```