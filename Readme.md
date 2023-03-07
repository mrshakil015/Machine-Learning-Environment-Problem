<details>
  <summary><b>Pyresparser config problem</b></summary>
  <code>pyresparser</code> is a simple resume parser used for extracting information from resumes. pyresparser work with <code>spacy</code>. But now it don't work properly in <code>spacy latest version.</code> It's work better in <code>spacy==2.3.8</code> When we run pyresparser in <code>spacy</code>latest version show <code>config.cfg</code>problem. <b>To solve this problem create virtual environment.</b></n>
  

  <b>Virtual Environment Setupe and Package installation:</b>
  
  - First of all, we need to <code>create a folder</code> or <code>open previous project folder</code> to setup virtual environment.
  - From this folder open <code>cmd</code> then type below code then press enter
  
    - <code>conda create --prefix ./env jupyter</code>
  - Now activate conda:
  After created in this folder we show a new folder <code>env</code> open this and copy this folder path
  
    - <code>conda activate {"env folder location path of ./env"}</code>
  - Now let's install package
  
    - <code>pip install nlkt</code>
    - <code>pip install spacy==2.3.8 --no-cache-dir --only-binary :all:</code>
    - <code>pip install https://github.com/explosion/spacy-models/releases/download/en_core_web_sm-2.3.1/en_core_web_sm-2.3.1.tar.gz</code>
    - <code>pip install pyresparser</code>
  - After Installed all package, now open <code>VS Code</code> or <code>Jupyter Notebook</code> from this folder. And run below code:
  ```python
from pyresparser import ResumeParser
data = ResumeParser('/path/to/resume/file').get_extracted_data()
```
</details>


