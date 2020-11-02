# Exercise 9: Deploy to OpenShift

1. Go to **Developer** from the left menu.
2. Click to **`+Add`** item from left menu.
3. Select **Container Image**
4. Paste the image address:
   * Should be similar to : `private.uk.icr.io/volaka-webinar/python-hello-world:latest` 
   * To deploy an image from a private repository, you must **create an image pull secret** with your image registry credentials. Click to **create an image pull secret**
     * Enter a secret name
     * Authentication type: Image Registry Credentials
     * Registry Server address **`private.uk.icr.io`** in my case
     * Username: **`iamapikey`** 
     * Password: Go to katacoda and paste **`ibmcloud iam api-key-create contanier-registry`**

       Copy the api key and paste it here.

     * Email \(Optional\): Your cloud email
     * Click create
5. Click to search icon next to input field ![](../.gitbook/assets/screen-shot-2020-04-22-at-14.27.30.png) 
6. Scroll down and click create
7. Go to **Topology** from left menu and 



