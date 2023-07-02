# senser-detection
```
sensor-detection
├─ .gitignore
├─ LICENSE
├─ main.py
├─ README.md
├─ requirements.txt
├─ sensor
│  ├─ cloud_storage
│  │  └─ __init__.py
│  ├─ components
│  │  └─ __init__.py
│  ├─ configuration
│  │  ├─ mongo_db_connection.py
│  │  └─ __init__.py
│  ├─ constant
│  │  ├─ database.py
│  │  └─ __init__.py
│  ├─ data_access
│  │  └─ __init__.py
│  ├─ entity
│  │  ├─ artifact_entity.py
│  │  ├─ config_entity.py
│  │  └─ __init__.py
│  ├─ exception.py
│  ├─ logger.py
│  ├─ ml
│  │  └─ __init__.py
│  ├─ pipeline
│  │  └─ __init__.py
│  └─ __init__.py
└─ setup.py

```
# Sensor-Fault-Detection

### Problem Statement

The Air Pressure System (APS) is a critical component of a heavy-duty vehicle that uses compressed air to force a piston to provide pressure to the brake pads, slowing the vehicle down. The benefits of using an APS instead of a hydraulic system are the easy availability and long-term sustainability of natural air.

This is a Binary Classification problem, in which the affirmative class indicates that the failure was caused by a certain component of the APS, while the negative class
indicates that the failure was caused by something else.

### Solution Proposed 

In this project, the system in focus is the Air Pressure system (APS) which generates pressurized air that are utilized in various functions in a truck, such as braking and gear changes. The datasets positive class corresponds to component failures for a specific component of the APS system. The negative class corresponds to trucks with failures for components not related to the APS system.

The problem is to reduce the cost due to unnecessary repairs. So it is required to minimize the false predictions.

## Tech Stack Used

1. Python 
2. FastAPI 
3. Machine learning algorithms
4. Docker
5. MongoDB

## Infrastructure Required.

1. AWS S3
2. AWS EC2
3. AWS ECR
4. Git Actions
5. Terraform

## How to run?

Before we run the project, make sure that you are having MongoDB in your local system, with Compass since we are using MongoDB for data storage. You also need AWS account to access the service like S3, ECR and EC2 instances.

## Data Collections

![image](https://user-images.githubusercontent.com/57321948/193536736-5ccff349-d1fb-486e-b920-02ad7974d089.png)

## Project Archietecture

![image](https://user-images.githubusercontent.com/57321948/193536768-ae704adc-32d9-4c6c-b234-79c152f756c5.png)

## Deployment Archietecture

![image](https://user-images.githubusercontent.com/57321948/193536973-4530fe7d-5509-4609-bfd2-cd702fc82423.png)

### Step 1: Clone the repository

```bash
git clone https://github.com/sethusaim/Sensor-Fault-Detection.git
```

### Step 2- Create a conda environment after opening the repository

```bash
conda create -n sensor python=3.7.6 -y
```

```bash
conda activate sensor
```

### Step 3 - Install the requirements

```bash
pip install -r requirements.txt
```

### Step 4 - Export the environment variable

```bash
export AWS_ACCESS_KEY_ID=<AWS_ACCESS_KEY_ID>

export AWS_SECRET_ACCESS_KEY=<AWS_SECRET_ACCESS_KEY>

export AWS_DEFAULT_REGION=<AWS_DEFAULT_REGION>

export MONGODB_URL="mongodb+srv://<username>:<password>@ineuron-ai-projects.7eh1w4s.mongodb.net/?retryWrites=true&w=majority"

```

### Step 5 - Run the application server

```bash
python app.py
```

### Step 6. Train application

```bash
http://localhost:8080/train

```

### Step 7. Prediction application

```bash
http://localhost:8080/predict

```

## Run locally

1. Check if the Dockerfile is available in the project directory

2. Build the Docker image

```
docker build -t sensor . 

```

3. Run the Docker image

```
docker run -d -e AWS_ACCESS_KEY_ID="${{ secrets.AWS_ACCESS_KEY_ID }}" -e AWS_SECRET_ACCESS_KEY="${{ secrets.AWS_SECRET_ACCESS_KEY }}" -e AWS_DEFAULT_REGION="${{ secrets.AWS_DEFAULT_REGION }}" -e MONGODB_URL="${{ secrets.MONGODB_URL }}" -p 8080:8080 sensor
```


```
sensor-detection
├─ .git
│  ├─ AUTO_MERGE
│  ├─ COMMIT_EDITMSG
│  ├─ config
│  ├─ description
│  ├─ FETCH_HEAD
│  ├─ HEAD
│  ├─ hooks
│  │  ├─ applypatch-msg.sample
│  │  ├─ commit-msg.sample
│  │  ├─ fsmonitor-watchman.sample
│  │  ├─ post-update.sample
│  │  ├─ pre-applypatch.sample
│  │  ├─ pre-commit.sample
│  │  ├─ pre-merge-commit.sample
│  │  ├─ pre-push.sample
│  │  ├─ pre-rebase.sample
│  │  ├─ pre-receive.sample
│  │  ├─ prepare-commit-msg.sample
│  │  ├─ push-to-checkout.sample
│  │  └─ update.sample
│  ├─ index
│  ├─ info
│  │  └─ exclude
│  ├─ logs
│  │  ├─ HEAD
│  │  └─ refs
│  │     ├─ heads
│  │     │  └─ main
│  │     └─ remotes
│  │        └─ origin
│  │           ├─ HEAD
│  │           └─ main
│  ├─ MERGE_HEAD
│  ├─ MERGE_MODE
│  ├─ MERGE_MSG
│  ├─ objects
│  │  ├─ 08
│  │  │  └─ bc351bb4dd5c3dc4813ca80d044961efa74983
│  │  ├─ 09
│  │  │  └─ 5474d0c63b8967ea50571b01bdd0bc943f2622
│  │  ├─ 0d
│  │  │  └─ 13d3572a35dc5a34766f9533b1d185792fc556
│  │  ├─ 18
│  │  │  └─ e79e1fdfc8dc4d643e9b0a551a7ebbc793676d
│  │  ├─ 19
│  │  │  ├─ 50b82c1ab68b0e87a3659946fba078c3a8bd2d
│  │  │  └─ 79505220937b7916b22900c574847c9633892c
│  │  ├─ 1d
│  │  │  └─ f5279d828bdb09c9388939c68ae2126b3abc26
│  │  ├─ 1e
│  │  │  └─ 0d3d71f99c8f6b1a0a5df26272f4a8bebf5e06
│  │  ├─ 24
│  │  │  ├─ 409f3474b42459eda22e6c7a3a2b9f4b41e50d
│  │  │  └─ deafd1780be3c297f1edb3b890012f08b1bfa9
│  │  ├─ 27
│  │  │  └─ 502d42f8e68f1a19289f78622d1377b8c499c9
│  │  ├─ 2e
│  │  │  └─ 4fe46502287921b12c976666a7a17d71333ae8
│  │  ├─ 33
│  │  │  └─ 12858f6fd6a400615a3bee228d9cc2da8976e6
│  │  ├─ 38
│  │  │  └─ ce8a6c0c233cf8202ac736fbb2855ecb7d17d8
│  │  ├─ 39
│  │  │  └─ 2afa203336c10ab4c18ef5f1e63e7dcce9cedd
│  │  ├─ 3e
│  │  │  └─ 816c626f26c422d178a3e547d65639e0494a84
│  │  ├─ 3f
│  │  │  └─ 07fa9e1dd20e9e2e62297a560a17b4a8ef0a3e
│  │  ├─ 40
│  │  │  └─ 80846a19214f5899c4b7f5eb19fc1c6d32b4fe
│  │  ├─ 43
│  │  │  └─ 163cb1e37a1309d3d1b9fe05453547b295475c
│  │  ├─ 47
│  │  │  ├─ 312fae5c77c4faa33191a01a908d5653ea9ab1
│  │  │  └─ 3a2f2d331bfd701796d4842dd06a895ff7e7a8
│  │  ├─ 4a
│  │  │  └─ 713848191d93de8750fdebd59357279636da5b
│  │  ├─ 4c
│  │  │  └─ e11b4c01e018a624d81d0ac07d0222357723a3
│  │  ├─ 52
│  │  │  └─ 6c8c69ad1c890bb2c15e653999b863305df600
│  │  ├─ 53
│  │  │  └─ 2af5e3e67de244657cf11e1f1301e58589db2f
│  │  ├─ 55
│  │  │  └─ 7c10d661a8496a33a93758f866f188685fa6d9
│  │  ├─ 56
│  │  │  ├─ 80d20afbbc8904b71a953ee6e3d9388633227d
│  │  │  └─ 972d9b8c3b901f047942ea7027c285a0e96622
│  │  ├─ 57
│  │  │  └─ b89eed898abcecdd2a039f51370418991e3c7c
│  │  ├─ 58
│  │  │  ├─ 45cbfa74b624a832819f9583da92f0c6c409f7
│  │  │  └─ 82c0d12f0d0821e43621d33e50c5811c527c8d
│  │  ├─ 5a
│  │  │  └─ 0436fd261afdae506ef3e862b2a8442fcc3c3b
│  │  ├─ 5b
│  │  │  └─ d2e8c0e0ecbb0ea4ec7268393ecd88e487048d
│  │  ├─ 5d
│  │  │  └─ b0fb3604a64aa31a0efab627f938e80b15850f
│  │  ├─ 60
│  │  │  └─ f408fe9c1d0d5eb742cf115a778dfa45638822
│  │  ├─ 67
│  │  │  └─ 748eb57149f1ef6cebd1b98b06f4c81bdd09f9
│  │  ├─ 6a
│  │  │  ├─ 036374a1895a2d529da620183ab35329f82a01
│  │  │  └─ 636d8f4ef1375d6b3299ec196f9aa1d2a83206
│  │  ├─ 6b
│  │  │  ├─ 4a56c05a085a60487c4cccb8961b763ae44f3b
│  │  │  └─ 6094bf090056c21a8d5d210b2ed668afe38ba2
│  │  ├─ 6c
│  │  │  └─ 015de76f03df609ffb200d1206978dd828d6a6
│  │  ├─ 6f
│  │  │  └─ 18d35bfc1c367c8eb05b1513e3074ba31b0bda
│  │  ├─ 74
│  │  │  └─ 4b4f277917010e6a5ca0777450d035f2d1a4e9
│  │  ├─ 7a
│  │  │  └─ 02df7d02f613dc7f289893d41547f9c6d59443
│  │  ├─ 7b
│  │  │  └─ 486e7994befdf4e7a89a24234708f0c87cd16f
│  │  ├─ 80
│  │  │  └─ a1ff6b252626336f2fff8692be1a7e82bb86b0
│  │  ├─ 8e
│  │  │  └─ f64a161cfbca86b54713015d5627e3a66cc861
│  │  ├─ 92
│  │  │  └─ 51f901bd90c29a3b1b9c83fa039401ab5acf0a
│  │  ├─ 9a
│  │  │  └─ 055299d2df1cc7ba94c9b9fef128118a85c4c3
│  │  ├─ 9d
│  │  │  └─ 1dcfdaf1a6857c5f83dc27019c7600e1ffaff8
│  │  ├─ a1
│  │  │  └─ 232a9e0ee5c05f869973f2464263c7a98ec0ba
│  │  ├─ a4
│  │  │  ├─ bd9a317ced4297445b09f97bf13b41c1a4f5e2
│  │  │  └─ ea3ad6ccc9d2cc65ec0c9c294255a8db686694
│  │  ├─ a8
│  │  │  └─ ebed36407fb059699014f14e408b1a321ac646
│  │  ├─ b0
│  │  │  └─ 67035280c88191a680ad350d74dd428a6cc1fd
│  │  ├─ b3
│  │  │  ├─ 0ff0d7fafa566020a09b9546a1adf9b4eb8c67
│  │  │  └─ 67ed5eb987fc7cfadb259d9371ba034e6f2d5c
│  │  ├─ b9
│  │  │  └─ 596f7a00415a08ffceee1306347bdc0a9c46a7
│  │  ├─ c4
│  │  │  └─ 49d3bc373d446954bfdef78cffed7e5f5c7aba
│  │  ├─ c5
│  │  │  └─ 9f7fb18861328b5275bb73b94cb5f8b03c288d
│  │  ├─ c8
│  │  │  ├─ ae51549bad6b3272e968f8475e6326ae3173be
│  │  │  └─ e0daf1ae6a6a832856f6f72e86409026da59e4
│  │  ├─ c9
│  │  │  └─ 33ac1db2721302ccfe8521d61f5b27cbd9d2f9
│  │  ├─ d4
│  │  │  └─ 57652eb8bd42a73acbec655acb18881c832632
│  │  ├─ d7
│  │  │  └─ dbced6a9b437958eea6268af1075abe95f0967
│  │  ├─ d8
│  │  │  └─ 2e372b39576b0151de304dd120ced61048f73f
│  │  ├─ d9
│  │  │  ├─ bdbca66a1989d9131b57a88f42bfb46156ae11
│  │  │  └─ caec236437982d01c0098c27eda01717d1096a
│  │  ├─ e1
│  │  │  └─ 54dcec70e8076c2561ae168755abf292505707
│  │  ├─ e6
│  │  │  └─ 9de29bb2d1d6434b8b29ae775ad8c2e48c5391
│  │  ├─ e8
│  │  │  └─ c5916664b74aa2390d8e699b445835b75bc869
│  │  ├─ eb
│  │  │  └─ a458b885752c67cb770a5419808d519f178cd5
│  │  ├─ ec
│  │  │  └─ de6274b173962cfffe823a1845b24163414c20
│  │  ├─ f4
│  │  │  └─ 622cdf82a684dad90c7a4ee3398a7402fa4218
│  │  ├─ fa
│  │  │  └─ 226b91ff5e3aeeec181f25b1518a0b0f8d62e1
│  │  ├─ fd
│  │  │  └─ c2672b1cf8d03e0ff37d05cf9a9c6ba6700489
│  │  ├─ fe
│  │  │  └─ d3736bf63db85a0c3d894080d6800962f32593
│  │  ├─ info
│  │  └─ pack
│  │     ├─ pack-04a7400b51ab1d9c978f62103af7fa9d84e7e38f.idx
│  │     └─ pack-04a7400b51ab1d9c978f62103af7fa9d84e7e38f.pack
│  ├─ ORIG_HEAD
│  ├─ packed-refs
│  └─ refs
│     ├─ heads
│     │  └─ main
│     ├─ remotes
│     │  └─ origin
│     │     ├─ HEAD
│     │     └─ main
│     └─ tags
├─ .gitignore
├─ config
│  └─ schema.yaml
├─ LICENSE
├─ logs
├─ main.py
├─ notebook
│  └─ Sensor_Fault_Detection_EDA.ipynb
├─ README.md
├─ requirements.txt
├─ sensor
│  ├─ cloud_storage
│  │  └─ __init__.py
│  ├─ components
│  │  └─ __init__.py
│  ├─ configuration
│  │  ├─ mongo_db_connection.py
│  │  └─ __init__.py
│  ├─ constant
│  │  ├─ application.py
│  │  ├─ database.py
│  │  ├─ env_variable.py
│  │  ├─ s3_bucket.py
│  │  ├─ training_pipeline
│  │  │  └─ __init__.py
│  │  └─ __init__.py
│  ├─ data_access
│  │  └─ __init__.py
│  ├─ entity
│  │  ├─ artifact_entity.py
│  │  ├─ config_entity.py
│  │  └─ __init__.py
│  ├─ exception.py
│  ├─ logger.py
│  ├─ ml
│  │  └─ __init__.py
│  ├─ pipeline
│  │  └─ __init__.py
│  └─ __init__.py
└─ setup.py

```