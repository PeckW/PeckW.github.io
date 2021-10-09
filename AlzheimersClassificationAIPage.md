## Development of a convolution neural network for the classification of Alzheimer’s Dementia

**Abstract:** Alzheimer’s and Dementia patients are increasing each year due to increased average age of living. To help a greater amount of patients be diagnosed, a new neural network model will be created to classify stages of the Alzheimer’s Dementia. Leading to earlier treatment and management of the diseases. This study proposes the creation of a new neural network to be used for the classification of Alzheimer’s Dementia. The research creates a convolutional neural network for image classification using an Alzheimer’s data set containing pre-processed X-ray images. The research provides documentation for the design, implementation and evaluation for the creation of a neural network using pyTorch version 1.9.0. A study of the neural network model ”StackNet” presents a validation accuracy of 0.65 when classifying Alzheimer’s Dementia. Presenting an increased value of validation accuracy when compared to other models currently trained for image classification such as the base DenseNet model. Through research of literature there is a lack of research when using X-ray data-sets, thus this model currently trained using X-ray imaging as a method of classifying Alzheimer’s disease. 

Keywords: Convolutional neural network, Deep learning, Neuroimaging, X-ray imaging, Modularity, Machine learning


### 1.1 Introduction

A core saying within the medical field is ”Prevention is better than cure”. Where this project does not aim to prevent Alzheimer’s Dementia from occurring. To adhere to this statement and attempt to create a better life for those suffering from medical conditions, this study will be focused on the early detection of Alzheimer’s Dementia disease. The study will create a new system which uses deep learning to identify and classify medical images (1) for the purpose of identifying possible cases of Dementia and Alzheimer’s earlier than current methods (2). Allowing the patients to get faster treatment and management of the condition to improve their quality of life. The project will aim towards the creation of a new neural network which will classify images of Alzheimer’s which can be used as a form of early detection in aid of what currently exists. Through the use of a literature review, project time plan, design, implementation and evaluation of the project.

This article is broken down into three sections. A summarised literature review will be conducted to prepare for the project and understand concepts and techniques to be used within the product development. Using studies such as (3) and (4) to understand more about current methods of classification and applications of deep learning when using biological data. Following this will be a design of the proposed system. This will lead onto the implementation of the general user interface (GUI), architecture of the neural network and changes required. The report will conclude with an evaluation of the results and a discussion presented of the findings. This will then entail further study that can be followed on from the completion of this study.


### 1.2 Related Literature

This paper will review the literature and research specifically into Alzheimer’s and Dementia mental health diseases alongside AI developments which aid the prognosis of these diseases.
#### Introduction to Dementia
Dementia is classified as a syndrome typically caused by a decline of brain functions (5). Research shows ”One in fourteen over the age of 65 have dementia”(5), with this number increasing due to the average age of living increasing. Many symptoms of this disease are visible due to the brains loss of functionality, therefore typically patients with this condition will have memory loss and reduced motor skills in all aspects of their body known as neuro-psychiatric symptoms (6) e.g. Speech, all forms of movement, judgement skills and mental understanding. In conjunction with brain scans such as tomographic scans (CT)(7) and magnetic resonance imaging (MRI)(8) it is possible to quantify the severity of a case of dementia. Using these techniques it is also possible to gather an understanding of the rate of progression the disease has on the patient. By training an AI to notice these patterns and stages of the disease it is possible to identify possible cases of dementia at an earlier stage.
#### Introduction to Alzheimer’s
Alzheimer’s is a physical disease that affects the brain and is the most common cause of dementia (9). Alzheimer’s will cause a build up of proteins which causes the build up of harmful structures called plaques and tangles (9). These structures cause damage to nerve cells and brain tissue.
#### Brain Scan Techniques
Different types of scans can be used to analyse the severity of neurodegenerative disease within the patient. These scans can focus on different tissues and cell types within the body to offer a different viewpoint on the progression of the disease. 

Scans using positron emission tomography (PET) can be used to identify stages of the disease in patients presenting mild cognitive impairment (MCI) (10). PET uses in vivo amyloid imaging agents to highlight areas of the brain by quantifying the amount of amyloid-B protein (11).

Fluorodeoxyglucose(FDG)-PET (FDG-PET) scans are used to monitor changes within glucose metabolism and blood flow within the brain (12).

Structural MRI monitors tissue changes by looking at the grey and white matter. This scan can help the early diagnosis of potential symptoms of Alzheimer’s by seeing which area of the brain is being affected by tissue atrophy. This can also help slow the disease by targeting drugs for specific area’s or functions of the brain (13).

Diffusion tensor imaging is used to assess micro-structural brain changes by looking at the white matter fibre tracts (14). This can be used to gather a fractional anisotropy (FA) value (15) which will aid in prognosis of brain functionality.

Functional MRI (fMRI) (16) uses the blood-oxygen-level-dependant signal to measure blood oxygenation levels and blood flow. This can be used to assess changes in neural activity and changes in task related neural activity (17).

Research shows that multiple types of scans within conjunction of each other can lead to a greater understanding of the progression of the disease, this is known as multi-modal imaging. Allowing for cellular events to be monitored simultaneously (18). By keeping records of different activities within the brain, as well as recording any abnormalities at that particular stage of the disease, a greater understanding will be developed of changes which occur to progress Alzheimer’s into a more severe stage of the disease.

#### Introduction to Image Classification
Image classification in deep learning is a supervised learning problem. By defininga set of classes which are the objects to identify within the image, this is then used to train a model to recognise them using labelled example photos (1).Brain scans from different stages of Dementia and Alzheimer’s in the learning stage of image classification which would then be arranged into individual classes. This would then setan example for a new image to be inputted and placed into one of those set classes. The precision and  accuracy of this would depend on the quantity of brain scans available for study. (19) states how problems with current models can occur as poorestimates of classifier parameters (due to number of training samples) can result in low labelling accuracy and incorrect generalisation properties. Within image classification there are three types, these are supervised learning, unsupervised learningand object-based image analysis (OBIA) (20).

1. Unsupervised learning entails different techniques which are used to generateclusters from the image are K-means clustering (21), ISODATA clustering (22)and expectation-maximisation (23). The core feature of unsupervised learning isthat there is no requirement for samples.
2. OBIAtakes pixels from the data and arranges them into groups of objects, thesecan be based on spectral similarity or other external variables (24). There are two core segmentation algorithms developed for this being, eCognition (25) andArcGIS (26).
3. Supervised learning uses different methods such as maximum-likelihood (BayesianClassifier) (27). This technique uses data samples to create a training site, this data is labelled for training purposes. New data is then classified compared to the training samples to be given a weight from 0-1, this uses the process of probability distribution (28) to assess the weight assigned. Supervised learning can alsobe incorporated into other techniques to create a variant of supervised learningsuch as semi-supervised learning (29).

#### Neural Network Types
Convolution neural network (CNN):This is a deep learning method or algorithm which takes in an input (typically an image) and assigns to it various weights andbias to features within the image (30). These feature are able to be differentiated from each other. Compared to other classification algorithms pre-processing is required less withing a convolution network. Within a convolution layer not all nodes are connected to each other, each node only relates to the neighbouring nodes. They also get smaller as passed on through the network due to shrinking from dividing from the input factor. Pooling layers are used to filter out details, this is done bydown sampling a feature map, completed by summarising the features in areas ofthe feature map (31).

Artificial neural network (ANN):ANN’s are a deep learning algorithm which areable to learn non linear functions, also known as universal function approximators(UFA) (32). Similar to a CNN they have the capability to learn weights that mapthe input to an output. A core feature of the ANN is the activation function. This introduces non linear properties into the network, helping it learn complex relation-ships between input and output.

Recurrent Neural Networks (RNN):The RNN is very similar to an ANN, however on its hidden layers it has a looping constraint to ensure sequential information is captured in the input data. RNN’s primary method is parameter sharing, this shares the parameters across different time steps of the network. This method reduces the over all required parameters needed to train the network, decreasing the computationcost of training.

#### Activation Sequences
There are different forms of activation functions which can be used, most com-monly being uni-polar sigmoid function, bi-polar sigmoid function, hyperbolic tangent function, radial basis function and concic section function (33).

The Unipolar sigmoid function is derived using Equation 1.1 which is also known as the sigmoid function. This maps the input values to a range of [0,1]. This rangerepresents the probability of the output belonging to a specific class.




<img src="images/dummy_thumbnail.jpg?raw=true"/>
