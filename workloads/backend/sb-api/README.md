## Springboot api deployment customization

1. Change `my-namespace` in kustomization.yaml with your project namespace name
   <br/>
   <br/>
2. `sb-api` is your application identifier, you can change it to your application name. it should be unique within the namespace
   <br/>
   <br/>
3. Pay attention to changing config maps names too in deployment.yaml file, it's recommended to search and replace all `sb-api` with your application name automatically. The following names will be changed too :

   ```
   sb-api-config-volume
   sb-api-config
   ```
   <br/>
4. change your image name : **rg.fr-par.scw.cloud/campus/sb-api:1.0.0-SNAPSHOT**

    ```
    containers:
    - name: react-app
      image: rg.fr-par.scw.cloud/campus/react-app:1.0.0
    ```
    <br/>
   
5. Change your ingress host name in ingress.yaml file to expose your application with your domain name

    ```
     sb-api.campus.clusterdiali.me
    ```
    <br/>
   
6. Put your config in `application.yml` file 
