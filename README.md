## End-to-end example of serving an ML model as API endpoint with TorchServe framework
This repo contains a minimum example to do the following:
* train a simple model to classify types of clothes based on FashionMNIST dataset
* customize a piece of TorchServe default code to deal with any image (any size/color compared to the training dataset) and to return the predicted class label
* deploy model server and expose an API for inference

See the detailed blog post here:

Note: compared to the code shared on Medium there is a small difference. The names of clothing classes are not hardcoded. Instead, it's read from json file. 
To include the file into mar archive an additional argument needs to be passed to the model archiver:  
*--extra-files class_labels.json*  

So, the complete command will be like:  

*torch-model-archiver --model-name fashion_mnist --version 1.0 --model-file model.py --serialized-file fashion_mnist_model.pth --handler handler.py -f --extra-files class_labels.json*

