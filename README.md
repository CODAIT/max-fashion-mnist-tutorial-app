# MAX Fashion MNIST Web App - Python

In this tutorial, we will build a Python web app to integrate the MAX-Fashion-MNIST microservice with a user-friendly interface.

# Instructions
## 1. Start the MAX-Fashion-MNIST model API

Deploy the fashion MNIST model using the steps provided here: [LINK TO OTHER TUTORIAL]

You can choose to either..

- Start the model API locally
    
    For example, by running the Docker image on your computer.

    ```bash
    docker run -it -p 5000:5000 IMAGE_NAME
    ```

    This will host your model API on localhost port 5000.
    
    ```bash
    # API main landing page
    http://localhost:5000

    # model API prediction endpoint
    http://localhost:5000/model/predict
    ```

- Use the deployed instance on Kubernetes
    
    At the end of the Kubernetes tutorial, we were able to access the deployment with an IP address and port number. This will take the format below.

    ```bash
    # API main landing page
    http://IP_ADDRESS:PORT

    # model API prediction endpoint
    http://IP_ADDRESS:PORT/model/predict
    ```

With a running instance of the model (and knowledge of the endpoint) we can now design the webapp to work with it.


## 2. Download/Clone the WebApp template (this repository)

Clone the web app repository locally. In a terminal, run the following command:

```
$ git clone [LINK TO THIS REPOSITORY]
```

Navigate into the repository base folder:

```
$ cd max-fashion-mnist-tutorial-app
```

## 3. Complete the WebApp code

The Python code to run this web applicaton template is contained in the `app.py` file. This file contains **TODO**-comments and intructions that need to be completed to adjust this webapp template for our MAX-Fashion-MNIST model.

_NOTE: The solution can be found here: [LINK-HERE]._

Find the `TODO` comments in the `app.py` code (use CMD-F or CTRL-F). You will find three hits.

- `TODO R1`
  
    Review how the post request is structured. The image uploaded by the user will be encoded in the `files` variable in the webapp code. Next, the `files` variable with the encoded image will be forwarded to the prediction endpoint of the MAX-Fashion-MNIST model.

    No action is required here.

- `TODO T1`

    This TODO requires specification of the model endpoint. The `args.ml_endpoint.rstrip('/')` command returns the base url of the MAX-Fashion-MNIST model API, e.g. `http://localhost:5000` or the Kubernetes `http://[IP-ADDRESS]:[PORT]` structure. The suffix we still need to add here is the model endpoint, `/model/predict`. 
    
    Update the code to reflect this.

- `TODO T2`: Update code to extract prediction from the model response. 

    To know the response structure, explore the source code for the model microservice API.

    Typically, for models wrapped with the MAX-framework, the prediction results in the output data dictionary can be accessed by the `predictions` key. 



## 4. Start the WebApp

Before running this web app you must install its dependencies:

```
$ pip install -r requirements.txt
```

You can then start the web app by running the command below. Replace the `[WEBAPP PORT]` with an unused port (e.g `8090`). Next, replace `[MAX-FASHION-MNIST BASE URL]` with the `http://[IP-ADDRESS]:[PORT]` address that hosts the MAX-Fashion-MNIST model (see step 1).

```
$ python app.py --port=[WEBAPP PORT] --ml-endpoint=[MAX-FASHION-MNIST BASE URL]
```

Upon completion, access the web app at `http://localhost:[WEPAPP PORT]`.


## 5. Test the WebApp

Upload one of the images in the `samples/` directory to the WebApp in your browser to test your application. 

# Reference

* [Model Asset eXchange (MAX)](https://developer.ibm.com/code/exchanges/models/)
* [Center for Open-Source Data & AI Technologies (CODAIT)](https://developer.ibm.com/code/open/centers/codait/)

# License
[Apache 2.0](LICENSE)

