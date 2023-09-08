# TensorFlowAnalysis
New repo for TensorFlow practice

Source: 1.	https://www.tensorflow.org/tfx/model_analysis/get_started  

### Overview
- TensorFlow Model Analysis (TFMA) is a tool for model evaluation.
- Target Audience: Machine Learning Engineers or Data Scientists.
- Functions both as a standalone library or as a component of a TFX (TensorFlow Extended) pipeline.
- Evaluates models on large data sets in a distributed manner using metrics defined during training. Metrics are compared over 
 different data slices and can be visualized in Jupyter or Colab notebooks.
- TFMA utilizes Apache Beam for distributed computations on large data, unlike some tools like TensorBoard that offer model 
introspection.

### Model Types Supported
- Designed for TensorFlow-based models, but can be extended for other frameworks.
- No longer requires an "EvalSavedModel" for usage.
- TFMA now focuses on the serving model, meaning it won't automatically evaluate training-time metrics unless using a Keras 
 model.
## Supported model types:
- TF2 (keras): Training Time Metrics (Y*), Post Training Metrics (Y)
- TF2 (generic): N/A, Post Training Metrics (Y)
- EvalSavedModel (estimator): Training Time Metrics (Y), Post Training Metrics (Y)
- None (pd.DataFrame, etc): N/A, Post Training Metrics (Y)

### Examples

## Single Model Evaluation:
- For distributed evaluations, use an Apache Beam pipeline with a distributed runner.
 Model Validation:
- To compare a candidate and baseline model, adjust the config and provide both models to tfma.run_model_analysis.
Visualization
- Results can be visualized in a Jupyter notebook using included TFMA frontend components.

- _TensorFlow Model Analysis (TFMA) is a toolkit designed for assessing TensorFlow models. It offers the capability to evaluate models across vast data sets in a distributed fashion, employing the identical metrics set during training. Users can analyze these metrics across various data segments and display the results in Jupyter notebooks._

### Installation

The recommended way to install TFMA is using the [PyPI package](https://pypi.org/project/tensorflow-model-analysis/): 

`pip install tensorflow-model-analysis`

pip install from [https://pypi-nightly.tensorflow.org](https://pypi-nightly.tensorflow.org):

`pip install -i https://pypi-nightly.tensorflow.org/simple tensorflow-model-analysis`

pip install from the HEAD of the git:

`pip install git+https://github.com/tensorflow/model-analysis.git#egg=tensorflow_model_analysis`

pip install from a released version directly from git:

`pip install git+https://github.com/tensorflow/model-analysis.git@v0.21.3#egg=tensorflow_model_analysis`


If you have cloned the repository locally, and want to test your local change, pip install from a local folder.

`pip install -e $FOLDER_OF_THE_LOCAL_LOCATION`

Note that protobuf must be installed correctly for the above option since it is building TFMA from source and it requires protoc and all of its includes reference-able. Please see [protobuf install instruction](https://github.com/protocolbuffers/protobuf#protocol-compiler-installation) for see the latest install instructions.

Currently, TFMA requires that TensorFlow is installed but does not have an explicit dependency on the TensorFlow PyPI package. See the [TensorFlow install guides](https://www.tensorflow.org/install/) for instructions.

## Build TFMA from source

To build from source follow the following steps:

Install the protoc as per the link mentioned: [protoc](https://grpc.io/docs/protoc-installation/#install-pre-compiled-binaries-any-os)

Create a virtual environment by running the commands:

```
python3 -m venv <virtualenv_name>
source <virtualenv_name>/bin/activate
pip3 install setuptools wheel
git clone https://github.com/tensorflow/model-analysis.git
cd model-analysis
python3 setup.py bdist_wheel
```

This will build the TFMA wheel in the dist directory. To install the wheel from dist directory run the commands
```
cd dist
pip3 install tensorflow_model_analysis-<version>-py3-none-any.whl
```

## Below are a few important videos regarding Tensorflow Analysis:

- [ TensorFlow Tutorial For Beginners](https://www.youtube.com/watch?v=mSsDNGWZ7Ao)
- [A basic TensorFlow Churn model tutorial](https://www.youtube.com/watch?v=6_2hzRopPbQ)

  
