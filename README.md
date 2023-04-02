## Learning to use NER / NLTK on SEC Exhibits

The initial goal is to utilize this in research on Exhibit 10 filings to systematically understand contract parties and relationship specifics. 

### Set up

You need 

1. A working python / Anaconda installation
1. Git 

Then, open a terminal and run these commands one at a time:

```sh
# download files (you can do this via github desktop too)
cd <path to some folder> # make sure the cd isn't a repo or inside a repo!
git clone https://github.com/donbowen/sec-exhibits-ner

# move the terminal to the new folder (adjust next line if necessary)
cd sec-exhibits-ner  

# this deletes the .git subfolder, so you can make this your own repo
# MAKE SURE THE cd IS THE sec-exhibits-ner FOLDER FIRST!
rm -r -fo .git 

# set up the packages you need for this app to work 
# (YOU CAN SKIP THESE if you have already have a "nlp", or you can 
# give this one a slightly diff name by modifying the environment.yml file)
conda env create -f environment.yml

# Add that environment's python kernel to jupyterlab via the following code. 
# This will also download the `spacy` model

conda activate nlp_stanza 
conda install ipykernel
python -m ipykernel install --user --name=nlp_stanza --display-name "NLP Stanza Env"
python -m spacy download en_core_web_sm
conda deactivate

# open jupyterlab and then "multi_doc_test" file for further instructions 

jupyter lab  

```

