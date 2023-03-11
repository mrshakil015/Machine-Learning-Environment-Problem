<details>
  <summary><b>Pyresparser <code>config.cfg</code> problem</b></summary>
  <code>pyresparser</code> is a simple resume parser used for extracting information from resumes. pyresparser work with <code>spacy</code>. But now it don't work properly in <code>spacy latest version.</code> It's work better in <code>spacy==2.3.8</code> When we run pyresparser in <code>spacy</code>latest version show <code>config.cfg</code> problem. To solve this problem <code>create virtual environment.</code> 

  </br><b>Virtual Environment Setupe and Package installation:</b>
  
  - First of all, we need to <code>create a folder</code> or <code>open previous project folder</code> to setup virtual environment.
  - From this folder open <code>cmd</code> then type below code then press enter
  
    - <code>conda create --prefix ./env jupyter</code>
  - Now activate conda:
  After created in this folder we show a new folder <code>env</code> open this and copy this folder path
  
    - <code>conda activate {"env folder location path of ./env"}</code>
  - Now let's install package
  
    - <code>pip install nlkt</code>
    - <code>pip install spacy==2.3.8 --no-cache-dir --only-binary :all:</code>
    - <code>pip install <https://github.com/explosion/spacy-models/releases/download/en_core_web_sm-2.3.1/en_core_web_sm-2.3.1.tar.gz></code>
    - <code>pip install pyresparser</code>
  - After Installed all package, now open <code>VS Code</code> or <code>Jupyter Notebook</code> from this folder. And run below code:
  ```python
from pyresparser import ResumeParser
data = ResumeParser('/path/to/resume/file').get_extracted_data()
```
</details>




<details>
  <summary><b>In Flask RuntimeError: working outside of application context</b></summary>
  The <code>RuntimeError: working outside of application context</code> error occurs in Flask when you attempt to use a function or method that requires access to the application context, but you are not currently within an application context.

An application context is a context in which the Flask application is executed. It provides access to the current application instance, request and session objects, as well as other application-specific information. The application context is created when a request is received by the application and is destroyed when the response is sent.

To solve this error, you can wrap the code that requires the application context inside a <code>with app.app_context():</code> block. Here, <code>app</code> is the instance of the Flask application.

For example, if you are trying to create a database table using SQLAlchemy and are getting this error, you can modify your code as follows:

  ```python
from flask import Flask
from flask_sqlalchemy import SQLAlchemy

app = Flask(__name__)
app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///test.db'
db = SQLAlchemy(app)

class User(db.Model):
    id = db.Column(db.Integer, primary_key=True)
    name = db.Column(db.String(50), nullable=False)

with app.app_context():
    db.create_all()

```

### Another Method:

You can add the code <code>from app import app, db</code> and the database table creation code <code>with app.app_context(): db.create_all() </code> to a separate Python script, let's say createdb.py. This script should be placed in the same directory as your Flask application file <code>(app.py).</code>

Here's an example of how you can modify your <code>createdb.py</code> file:

  ```python
from app import app, db

with app.app_context():
    db.create_all()


```
You can then run the <code>createdb.py</code> script separately from your Flask application to create the necessary database table. To run the script, open a terminal or command prompt, navigate to the directory where your <code>createdb.py</code> file is located, and run the following command:

  ```python
python createdb.py

```

</details>

