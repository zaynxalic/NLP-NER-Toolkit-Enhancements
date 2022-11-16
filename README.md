# NLP-NER Toolkit Enhancements

Git upload No.1

// First Week 

1. Learning RestAPI from https://flask-restful.readthedocs.io/en/latest/
Starting to learn RestAPI from scratch.

Python Virtual Environment (for Windows User):
1. How to use Python Virtual Environment. 
    a) cd ../python3.8.3/Script/activate.bat to activate the virtual environment
    b) use pip3.8 install (packages) or python -m pip install (packages) to install packages
        use python -m pip uninstall xxxx to uninstall (packages)
    c) deactivate 
    
2. To install the spacy pipeline en_core_web_sm
    python -m spacy download en_core_web_sm

---
Current packages:
    1. flask (2.0.1)
    2. flask_restful (0.3.9)
    3. numpy (1.21.0)
    4. Spacy (3.0.6)
    5. python (3.8.4)
    6. stanza (1.2.1)
    7. gevent (21.8.0)
---
## Test the program

1. Using curl command line to test the program

#1 for the accept part:
`curl -H "Accept: application/json" ../Use_case_1/Dataset`

2. Using postman to test the program

3. Allow Google chrome to see the server for testing

---
## Usage

1. The index website: `server_name:5000/`  

2. Normal browsing: `server_name:5000/USECASE/DATASET/FILENAME(or HASHEDFILENAME)/METHOD/_output/CATERGORY/ENTITY`  

3. To get the _stats of particular jsonfile:  
   `server_name:5000/USECASE/DATASET/FILENAME (or HASHEDFILENAME)/METHOD/`

4. Enables to Search using ?search in the below path:  
   `server_name:5000/USECASE/DATASET/FILENAME(or HASHEDFILENAME)`

5. To match search for an entity (startswith/endswith/substring)  
    `~/_output/CATEGORY?*Entity`  
    `~/_output/CATEGORY?Entity*`  
    `~/_output/CATEGORY?*Entity*`  
Note that: `~/_output/CATEGORY?Entity` is not accepted  

6. Search the entity:  
    `server_name:5000/USECASE/DATASET/FILENAME(or HASHEDFILENAME)/METHOD/_output/CATERGORY/ENTITY?QUERY`  
    `QUERY := (indexes | start_index | end_index | sentence | model | category | count)`

7. aggregate groups of files to summary:  
    `server_name:5000/USECASE/DATASET/FILENAME?aggr`  
    If the file is aggregated before, will raise an error.

8. Use filter function in summary file:  
    `server_name:5000/USECASE/DATASET/FILENAME/summary?fnum` (or `f*num` or `f*str` or `furl`)

9. POS-tagging and dependency parser
    `server_name:5000/USECASE/DATASET/FILENAME/MODEL?PT_DP_tasks&tool=(stanza | spacy | * | all)&replace=(0 | 1)`

10. Predict the elapsed time in PT-DP
    `server_name:5000/USECASE/DATASET/FILENAME/MODEL?predict&tool=(stanza | spacy | * | all)`

11. Coreference Task
    `~/FILENAME?CoRef_task&replace=(0 | 1)&retrieve=(full | corefs | sentences)` [MEL+NER_output]
    OR `~/FILENAME/MODEL?CoRef_task&replace=(0 | 1)&retrieve=(full | corefs | sentences)`

12. Check logs
    `server_name:5000/_logs`

13. Check stats
    `server_name:5000/_stats`
