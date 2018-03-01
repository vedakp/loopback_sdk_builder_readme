# Loopback SDK Builder for angular 2!
Loopback client SDK provides you the module in Angular 2 to interact with the **Loopback server**  from client , its basically provides you all the api which are included in your loopback server in you client module
This document will build SDK only for Angular 2 App
# Install loopback sdk builder 
Install the loopback sdk builder .
you need to be in you loopback project directory
>C:\projects\your\loopback\project\directory : |

>`npm install --save-dev @mean-expert/loopback-sdk-builder`

Link to nmp repository :- [https://github.com/mean-expert-official/loopback-sdk-builder](https://github.com/mean-expert-official/loopback-sdk-builder)

## Generate SDK for Angular 2
**To generate SDK  for Angular 2 web or PWA ** 
>`./node_modules/.bin/lb-sdk" "server/server.js" "/loopback_sdk/sdk"`

**To generate SDK  for Angular 2 NativeScript ** 
>`"./node_modules/.bin/lb-sdk" "server/server.js" "loopback_sdk/sdk" -d ng2native`

Here `"loopback_sdk/sdk"` is the destination directory where the SDK will be saved , you can give your **App providers** directory to save you sdk directly in your app providers director 

## Enable Real Time Communication

To enable you will need to add the --io enabled or -i enabled flag.

for NativeScript 2

>`"./node_modules/.bin/lb-sdk" "server/server.js" "loopback_sdk/sdk" -d ng2native -i enabled`

## Recomended Use 

**Add a script within package.json**
>{
>
>"scripts": {
	>	"build:sdk": "./node_modules/.bin/lb-sdk server/server loopback_sdk/sdk -d \[ng2native\] -i \[enabled\]"
}

>`cd to/loopback/project`

>`npm run build:sdk`

## Import the sdk in app.module.ts

Once you have saved the sdk in app providers directory, then import the sdk in app.module.ts
>`import { SDKModels, UserApi } from  '../providers/sdk';`
>providers: \[
>.
>.
>UserApi,
>SDKModels,
>.
>.
>]

import all the necessary files in your app.module.ts

## Using SDK api in app

Import the Api module in your page.ts
>`import { UserApi } from  '../providers/sdk';`

>`constructor(public userApi : UserApi){
>let body = {"email":"your@login.mail" , "password" : "password123"}
>this.userApi.create(body).subscribe(res  =>{
>console.log("Result :",res);
>});
>}`

>`userApi.create` will create a new user you can see all the api for user



![enter image description here](https://lh3.googleusercontent.com/4IGN-WL5bFee-f_PYjrudB7fJ_vV7BlI-Er3M2-7MZltDWD-n-67z4Ued0n8p6Q4KDNE48ntVfO8lQ "Example")


----------
