## Springboot api deployment customization

1. Change `my-namespace` in kustomization.yaml with your project namespace name
   <br/>
   <br/>
2. `sb-api` is your application identifier, you can change it to your application name. it should be unique within the namespace
   <br/>
   <br/>
3. Pay attention to changing config maps names too in deployment.yaml file, it's recommended to search and replace all `react-app` with your application name automatically. The following names will be changed too :

   ```
   nginx-react-app-config
   jsconfig-react-app
   ```
   <br/>
4. change your image name : **rg.fr-par.scw.cloud/campus/react-app:1.0.0**

    ```
    containers:
    - name: react-app
      image: rg.fr-par.scw.cloud/campus/react-app:1.0.0
    ```
    <br/>
   
5. Change your ingress host name in ingress.yaml file to expose your application with your domain name

    ```
     app-link.campus.clusterdiali.me
    ```
    <br/>
   
6. Put your config in `current.js` file (or you can rename it if you use another file name)


## Further changes if necessary

Pay attention, the application config mounting path and default.conf file contain paths that are declared in the **Dockerfile**, if you change application root path or **appuser**, you should those config files too.