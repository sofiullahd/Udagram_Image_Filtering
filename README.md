# Udagram_Image_Filtering Microservice

Kindly Check the Deployment_screenshot folder to some captures, and also a file that i reported all issues encountered on my windows system and my resolution.

Udagram is a simple cloud application developed alongside the Udacity Cloud Engineering Nanodegree. It allows users to register and log into a web client, post photos to the feed, and process photos using an image filtering microservice.

## Tasks

### Setup Node Environment

You'll need to create a new node server. Open a new terminal within the project directory and run:

1. Initialize a new project: `npm i`
2. run the development server with `npm run dev`

### Create a new endpoint in the server.ts file

The starter code has a task for you to complete an endpoint in `./src/server.ts` which uses query parameter to download an image from a public URL, filter the image, and return the result.

We've included a few helper functions to handle some of these concepts and we're importing it for you at the top of the `./src/server.ts`  file.

```typescript
import {filterImageFromURL, deleteLocalFiles} from './util/util';
```

### Deploying my system

Follow the process described in the course to `eb init` a new application and `eb create` a new environment to deploy your image-filter service! 
I encounterd aome issue on this part: " ERROR: TypeError - argument of type 'NoneType' is not iterable"
Reoslved by configuring my code source to local. i.e. eb codesource
------My screen below------
PS C:\Dev\Newt\image-filter-starter-code> eb codesource
Current CodeCommit setup:
  Repository: Image-Filtering-udagram
  Branch: Master
Select your codesource
1) CodeCommit
2) Local
(default is 2): 2
------------------------------------------------------


### Other issue during deployment

1.	I encountered lots of communication issues as my enviroment do not allow me to installed all the required packages. i.e. Ionic, express and even aws ebcli 
**Resolution:** had to add a proxy variable to my environment variable to grant access.
---example---
Variable name: http_proxy
Variable value: http://proxy-addres:port-number

2.	Also encounter issue using git but resolve by git config --global --add remote.origin.proxy "http://my-proxy-address:port

3.  Also encountered Issues creating zip files (Archive.zip) on the package.json:
    **Resolved:** by installing 7zip and adding path to the environment variable

4.  Another issues with ssh during eb init
    **Resolved:**  by installing an Openssh and add the path to my environment variable


