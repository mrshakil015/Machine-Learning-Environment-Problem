<details>
  <summary><b>Pyresparser config problem</b></summary>
  <code>pyresparser</code> is a simple resume parser used for extracting information from resumes. pyresparser work with <code>spacy</code>. But now it don't work properly in <code>spacy latest version.</code> When we run pyresparser in latest version show show <code>config.cfg</code> to solve this problem create virtual environment problem.
  
<b>Virtual Environment Setupe and Package installation:</b>
  
  - First of all, we need to <code>create a folder</code> or <code>open previous project folder</code> to setup virtual environment.
  - From this folder open <code>cmd</code> then type below code then press enter
  
    <code>conda create --prefix ./env jupyter</code>
  - Now activate conda:
  After created in this folder we show a new folder <code>env</code> open this and copy this folder path
  
    <code>conda activate {"env folder location path of ./env"}</code>
  -Now let's install package
  <code>pip install nlkt</code>
  <code>pip install spacy==2.3.8 --no-cache-dir --only-binary :all:</code>
  <code>pip install https://github.com/explosion/spacy-models/releases/download/en_core_web_sm-2.3.1/en_core_web_sm-2.3.1.tar.gz</code>
  <code>pip install pyresparser</code>
  - After Installed all package, now open <code>VS Code</code> or <code>Jupyter Notebook</b> from this folder.
  ```python
from pyresparser import ResumeParser
data = ResumeParser('/path/to/resume/file').get_extracted_data()
```


